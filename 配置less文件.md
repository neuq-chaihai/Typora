1. 安装less和less-loader

   ```
   cnpm i less less-loader --save
   ```

2. 在终端运行

   ```
   npm run eject
   ```

3. 在config里面的webpack.config文件中输入

   ```
   ctrl+f
   ```

   

4. 找到scss进行修改，共修改三处

5. ```
   第一处，在52行后面加入
   
   const lessRegex = /\.less$/;
   const lessModuleRegex = /\.module\.less$/;
   
   第二处，搜索scss，在第二个后面加入
   
   			{
                 test: lessRegex,
                 exclude: lessModuleRegex,
                 use: getStyleLoaders(
                   {
                     importLoaders: 2,
                     sourceMap: isEnvProduction && shouldUseSourceMap,
                   },
                   'less-loader'
                 ),
                 // Don't consider CSS imports dead code even if the
                 // containing package claims to have no side effects.
                 // Remove this when webpack adds a warning or an error for this.
                 // See https://github.com/webpack/webpack/issues/6571
                 sideEffects: true,
               },
               
   第三处，在第二处后面的scss加入
   			{
                 test: lessModuleRegex,
                 use: getStyleLoaders(
                   {
                     importLoaders: 2,
                     sourceMap: isEnvProduction && shouldUseSourceMap,
                     modules: true,
                     getLocalIdent: getCSSModuleLocalIdent,
                   },
                   'less-loader'
                 ),
               },
   
   ```

   