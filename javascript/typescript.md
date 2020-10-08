Installing the TypeScript compiler
----------------------------------

```bash
npm install -g typescript --prefix=/path/to/directory
```

Make sure you add `/path/to/directory/bin` to the system `$PATH`.


Updating the TypeScript compiler
--------------------------------

```bash
npm update -g typescript --prefix=/path/to/directory
```


Compiling `.ts` to `.js`
------------------------

Compiling a single TypeScript file. Note that `--outDir` is optional.

```bash
tsc sample.ts --outDir /path/to/output/directory
```

Auto compilation.

```bash
tsc *.ts --watch --outDir /path/to/output/directory
```


Using TypeScript with Webpack
-----------------------------

Install Webpack, the TypeScript compiler, and the TypeScript loader.

```bash
npm install --save-dev webpack webpack-cli typescript ts-loader
```

Example `tsconfig.json`:

```json
{
    "compilerOptions": {
        "strictNullChecks": true,
        "noImplicitAny": true,
        "sourceMap": true,
        "outDir": "./dist/",
        "module": "es6",
        "target": "es5",
        "jsx": "react"
    }
}
```

Example `webpack.config.js`:

```javascript
var path = require('path');

module.exports = {
    entry: './src/index.ts',
    output: {
        path: path.resolve(__dirname, './dist'),
        filename: 'bundle.js',
    },
    module: {
        rules: [
            {
                test: /\.tsx$/,
                loader: 'ts-loader',
                include: [
                    path.resolve(__dirname, 'src'),
                ],
            },
            {
                test: /\.ts$/,
                loader: 'ts-loader',
                include: [
                    path.resolve(__dirname, 'src'),
                ],
            },
        ],
    },
    resolve: {
        extensions: [
            '.ts', '.tsx', '.js', '.jsx',
        ],
    },
    devtool: 'inline-source-map',
};
```


Using TypeScript, Webpack, and Babel
------------------------------------

Install Babel, Webpack, and the TypeScript compiler.

```bash
npm install --save-dev webpack webpack-cli typescript babel-loader @babel/core @babel/preset-env @babel/preset-typescript
```

Example `.babelrc`:

```json
{
    "presets": [
        "@babel/env",
        "@babel/typescript"
    ]
}
```

Example `tsconfig.json`:

```json
{
    "compilerOptions": {
        "strictNullChecks": true,
        "noImplicitAny": true,
        "sourceMap": true,
        "outDir": "./dist/",
        "module": "es6",
        "target": "es5",
        "jsx": "react"
    }
}
```

Example `webpack.config.js`:

```javascript
var path = require('path');

module.exports = {
    entry: './src/index.ts',
    output: {
        path: path.resolve(__dirname, './dist'),
        filename: 'bundle.js',
    },
    module: {
        rules: [
            {
                test: /\.tsx$/,
                loader: 'babel-loader',
                include: [
                    path.resolve(__dirname, 'src'),
                ],
            },
            {
                test: /\.ts$/,
                loader: 'babel-loader',
                include: [
                    path.resolve(__dirname, 'src'),
                ],
            },
        ],
    },
    resolve: {
        extensions: [
            '.ts', '.tsx', '.js', '.jsx',
        ],
    },
    devtool: 'inline-source-map',
};
```
