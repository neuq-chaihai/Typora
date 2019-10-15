# 1. 在根目录下创建文件webpack.config.js中

```

const path = require('path');
const HTMLwebpackplugin = require('html-webpack-plugin');

const htmlPlugin = new HTMLwebpackplugin({
    template: path.join(__dirname, './src/index.html'),
    filename: 'index.html'
})
 

module.exports = {
    mode: 'development',

    plugins: [
        htmlPlugin
    ],

    module: { //要打包的第三方模块 
        rules: [ 
            { test: /\.js|jsx$/, use: 'babel-loader', exclude: /node_modules/ },
            { test: /\.css$/, use: ['style-loader', 'css-loader']},
            { test: /\.ttf|woff|woff2|eot|svg$/, use: 'url-loader' },        //打包处理字体
            { test: /\.scss$/, use: ['style-loader', 'css-loader?modules', 'sass-loader']}      //打包安装scss的loader
        ] 
    },

    resolve: {
        extensions: ['.js', '.jsx', '.json'],
        alias: {
            '@': path.join(__dirname, './src')          //使@符号在项目中表示的是根目录下的src目录
        }
    }
}
```

# 2. 在根目录中的package.json

```
{
  "name": "03_webpack_base",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "webpack-dev-server --open"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@babel/core": "^7.5.5",
    "babel-core": "^6.26.3",
    "babel-loader": "^7.1.5",
    "babel-plugin-transform-runtime": "^6.23.0",
    "babel-preset-env": "^1.7.0",
    "babel-preset-react": "^6.24.1",
    "babel-preset-stage-0": "^6.24.1",
    "css-loader": "^3.2.0",
    "html-webpack-plugin": "^3.2.0",
    "node-sass": "^4.12.0",
    "react": "^16.9.0",
    "react-dom": "^16.9.0",
    "sass-loader": "^8.0.0",
    "style-loader": "^1.0.0",
    "url-loader": "^2.1.0",
    "webpack": "^4.39.3",
    "webpack-cli": "^3.3.7",
    "webpack-dev-server": "^3.8.0"
  },
  "dependencies": {
    "bootstrap": "^3.3.7"
  }
}

```

# 3. 在根目录下创建.babelrc文件，在文件中输入

```
{ "presets": ["env", "stage-0", "react"], "plugins": ["transform-runtime"] }
```

