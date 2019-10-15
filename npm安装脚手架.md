`npm init -y` //快速初始化项目

在src下创建文件index.js和index.html

```
//全局安装cnpm
npm i cnpm -g 
```

```
cnpm i webpack -D
```

在目录下创建文件webpack.config.js

```
在webpack.config.js中向外暴露一个打包的配置对象： 
		module.exports = { 
//mode的参数为development和production(必选项)

mode: 'development'

}
```

```
cnpm i webpack-dev-server -D
```

在package.json中的scripts中加入

```
"dev": "webpack-dev-server --open"
```

 

//将index.html放入到内存中，使用工具

```
cnpm i html-webpack-plugin -D
```

在module.exports中加入

```
const path = require('path');
const HTMLwebpackplugin = require('html-webpack-plugin');

const htmlPlugin = new HTMLwebpackplugin({
    template: path.join(__dirname, './src/index.html'),
    filename: 'index.html'
})

module.exports = {

​    plugins: [

​        htmlPlugin

​    ],

}
```



```
cnpm i react react-dom -S
```

//在index.js中引入react和react-dom

```
import React from 'react'
```

```
import ReactDOM from 'react-dom'
```

在webpack.config.js中open代表默认直接打开(可以加浏览器，也可以不加 )，port+ 端口号, hot ,progress ,compress, host

//安装babel

```
cnpm i @babel/core -D

cnpm i babel-core babel-loader babel-plugin-transform-runtime -D

cnpm i babel-preset-env babel-preset-stage-0 babel-preset-react -D


或者

cnpm i @babel/core babel-core babel-loader@7.1.5 babel-plugin-transform-runtime babel-preset-env babel-preset-stage-0 babel-preset-react -D
```

//babel安装完毕，进行配置

在项目根目录中添加 .babelrc 配置文件并在文件中设置

```
{ 

​	"presets": ["env", "stage-0", "react"], 

​	"plugins": ["transform-runtime"] 

}
```

在webpack.config.js中添加babel-loader配置项：

```
module: { 

​	//要打包的第三方模块 

​	rules: [ { test: /\.js|jsx$/, use: 'babel-loader', exclude: /node_modules/ } ] 

}
```

### 运行时可能需要`cnpm install babel-loader@7.1.5 -D`

在src目录下创建components的目录用于存放组件，组件后缀名为.jsx

在组件.jsx中需要import

`import React from 'react'`

`并且使用export default`向外暴露出去



在index.js中引入组件时，需要import

`import 组件名 from './components/组件名.jsx'`

如果想要省略.jsx，需要在webpack.config.js中的module.exports中配置

```
resolve: {

​        extensions: ['.js', '.jsx', '.json'],				//是.js, .jsx, .json文件后缀名可以省略

​        alias: {

​			//表示别名

​            '@': path.join(__dirname, './src')          //使@符号在项目中表示的是根目录下的src目录

​        }

​    }
```



```
cnpm i style-loader css-loader  -D
```

并且在webpack.config.js 的module的rules中添加style-loader和css-loader配置项：

```
module: { //要打包的第三方模块 

​        rules: [ 

​            { test: /\.js|jsx$/, use: 'babel-loader', exclude: /node_modules/ },

​			//如果css-loader没有加?modules那么css样式是在项目中全局使用的

​			//css模块化只对类选择器和ID选择器有用。

​			//使用模块化之后要点出来类选择器名

​			例如：cssobj.item

​			//cssobj是import出的，item是选择器名

​            { test: /\.css$/, use: ['style-loader', 'css-loader']}

​        ] 

}
```

//如果想使某个类名不被模块化，可以使用:global(.类名)，使用时直接使用。

//想同时使用多个类名时：模块化类名m1,m2(import cssobj)，全局类名g1,g2

//第一种：className([m1,g1].join(' '))

//第二种：className(m1+' '+"g1")

//:local(.类名)可以被模块化，平时不使用:local()和:global()时，默认使用:local()



```
cnpm i bootstrap@3.3.7 -S
```

​    最新版本为4.多

在webpack.config.js中的modul的rules中配置处理字体文件

```
module: { //要打包的第三方模块 

​        rules: [ 

​            { test: /\.js|jsx$/, use: 'babel-loader', exclude: /node_modules/ },

​            { test: /\.css$/, use: ['style-loader', 'css-loader']},

​            { test: /\.ttf|woff|woff2|eot|svg$/, use: 'url-loader' }        //打包处理字体文件

​        ] 

​    }
```

//安装url-loader

```
cnpm i url-loader -D
```

//url-loader运行需要file-loader

```
cnpm i file-loader -D
```

import bootcss from 'bootstrap/dist/css/bootstrap.css'





**自己规定，自己写的css文件使用.scss和.less后缀名.**

安装能解析.scss文件的loader

```
cnpm i sass-loader node-sass -D
```

在model.export中配置

```
module: { //要打包的第三方模块 

​        rules: [ 

​            { test: /\.js|jsx$/, use: 'babel-loader', exclude: /node_modules/ },

​            { test: /\.css$/, use: ['style-loader', 'css-loader']},

​            { test: /\.ttf|woff|woff2|eot|svg$/, use: 'url-loader' },        //打包处理字体

​            { test: /\.scss$/, use: ['style-loader', 'css-loader?modules', 'sass-loader']}      //打包安装scss的loader

​        ] 

​    }
```





安装React路由包

**react-router-dom**

```
使用 
	yarn add react-router-dom

或者 
	npm i react-router-dom -S
```

使用 `import{HashRouter, Route, Link} from 'react-router-dom'`

**HashRouter**: 表示一个路由的跟容器，将来所有与路由有关的东西都要放在HashRouter里面，一个网站只需要						 使用一次HashRouter。

**Router**: 表示一个路由规则。有两个比较重要的属性，**path**和**component**。默认情况下，Router匹配是模糊匹配的，如果想要精确匹配，需要新加第三个属性**exact**，表示精确匹配。

​				eg: <Route path='/home' component={Home} exact/>

​				如果要匹配参数，需要使用 `:修饰符`

​				eg: <Route path='/home/:type/:id' component={Home} exact/>

**Link**: 表示一个路由的连接