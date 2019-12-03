```
cnpm i express --save
cnpm i eslint --save
```

​	

# 安装express应用生成器

```
全局安装
cnpm install express-generator -g

创建hello应用
	express hello
进入hello文件中
	cd hello
安装依赖
	cnpm i
运行应用(将hello改为应用文件名)
	window环境下: 
		SET DEBUG=hello:* & npm start
	Linux/macOS环境下:
		DEBUG=hello:* npm start
安装自动重启服务器的工具
	cnpm install --save-dev nodemon
在package.json中的scripts加入
	"scripts": {
    	"start": "node ./bin/www",
    	"devstart": "nodemon ./bin/www"
  	}
保存后先
	DEBUG=hello:* npm start
后退出再运行
	DEBUG=hello:* npm run devstart
```



# 项目中各部分的功能

- [cookie-parser](https://www.npmjs.com/package/cookie-parser)：用于解析 cookie 头来填充 `req.cookies`（提供了访问 cookie 信息的便捷方法）。
- [debug](https://www.npmjs.com/package/debug)：一个小型 node 调试程序，仿照 node 核心的调试技术建立。
- [http-errors](https://www.npmjs.com/package/http-errors)：处理错误中间件。
- [morgan](https://www.npmjs.com/package/morgan)：node 专用 HTTP 请求记录器中间件。

