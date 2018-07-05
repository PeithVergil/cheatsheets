Babel
=====

A tool for compiling ES6 to ES5.


Babel CLI
---------

Install the `babel` command line tool.

```bash
npm install --save-dev babel-cli
```

Compile a single file.

```bash
npx babel src/app.js -o dst/app.js
```

Compile a single file with source maps.

```bash
npx babel -s src/app.js -o dst/app.js
```

Compile a single file automatically everytime it is updated.

```bash
npx babel -w src/app.js -o dst/app.js
```

Compile an entire directory.

```bash
npx babel -w src -d dst
```


Babel + Webpack
---------------

```bash
npm install --save-dev babel-core babel-loader babel-preset-env webpack webpack-cli
```

In `webpack.config.js`:

```javascript
var path = require('path');
var webpack = require('webpack');
module.exports = {
    entry: './src/app.js',
    output: {
        path: path.resolve(__dirname, './dist'),
        filename: 'app.js',
    },
    module: {
        rules: [
            { 
                test: /\.js$/,
                loader: 'babel-loader',
                include: [
                  path.resolve(__dirname, 'src'),
                ],
                exclude: [
                  path.resolve(__dirname, 'node_modules'),
                ],
            }
        ]
    }
};
```

In `package.json`:

```javascript
{
  "name": "Sample App",
  "version": "0.1",
  "scripts": {
    "webpack": "webpack --watch"
  }
}
```

In `.babelrc`:

```javascript
{
  "presets": ["env"]
}
```

```bash
npm run webpack
```