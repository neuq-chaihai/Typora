```
react-native启动时红屏报错：Unable to load script.Make sure you're either running a metro server or that ....


1. 项目中在android/app/src/main/创建文件夹  assets
2. 查看自己项目是否有 index.android.js这个文件，如果有回车执行命令即可，否则会会报错，找不到这个index.android.js文件；把index.android.js改为index.js
3. 项目中执行命令
react-native bundle --platform android --dev false --entry-file index.android.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res 
执行这句命令后会在新建的assets文件夹下生成一个index.android.bundle文件
4. 运行启动
```

```
SDK location not found.

在react-native创建的项目目录下的Android目录下新建一个local.properties文件
sdk.dir = /home/linux/Android
```

