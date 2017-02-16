1. ``npm init``

``name: (flikker) myapp_fed
version: (1.0.0)
description:
entry point: (index.js)
test command:
git repository:
keywords:
author:
license: (ISC)
About to write to /Users/Astha/Desktop/flikker/package.json:

{
  "name": "myapp_fed",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}
``

2. ``npm install --save-dev react react-dom react-router webpack webpack-dev-server``
Babel installation for JSX support
``npm install babel-loader babel-core babel-preset-react babel-preset-es2015 --save-dev``

Add css loader

3. ``mkdir js css``


4. ``touch index.html webpack.config.js``
add to webpack

```var path = require('path');
var webpack = require('webpack');

module.exports = {
  entry: path.join(__dirname, 'js', 'app.js'),
  output: { path: __dirname, filename: 'bundle.js' },
  module: {
    loaders: [
      {
        test: /.jsx?$/,
        loader: 'babel-loader',
        exclude: /node_modules/,
        query: {
          presets: ['es2015', 'react']
        }
      }
    ]
  },
};
