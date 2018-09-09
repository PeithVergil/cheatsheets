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
        "noImplicitAny": true,
        "sourceMap": true,
        "allowJs": true,
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
                exclude: /node_modules/,
            },
            {
                test: /\.ts$/,
                loader: 'ts-loader',
                exclude: /node_modules/,
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