## 结构

![image-20200819133435075](E:\Workspace\Demo\LearningReact\admin-client\README.assets\image-20200819133435075.png)

## 笔记
  1） git init
  2） git add .
  3)  git commit -m "init"
  4)  git remote ...
  5)  git push origin master
  6)  git checkout -b dev   创建并切换分支
  7） git push origin dev   推送到分支
  8)  gti pull origin dev   拉取分支代码
  9） git clone
  10) git branch 查看分支
  11）git checkout -b dev origin/dev  根据远程dev分支建立本地仓库dev分支(clone
  之后有记录直接使用，否则新分支需执行先执行git pull后才能使用)
  12） git diff dev master

## antd

```
yarn add antd
```

## 实现组件的按需打包

1. 下载依赖模块

   ```
   yarn add react-app-rewired customize-cra babel-plugin-import
   ```

2. 定义加载配置的js模块：config-overrides.js

   ```javascript
   const {override,fixBabelImports} = require('customize-cra')
   module.exports = override(
   	fixBabelImports('import',{  // 配置上babel-plugin-import
           libraryName: 'antd',	// 针对的是antd
           libraryDirectory: 'es', // 源码文件夹中的es文件夹
           style: 'css'			// 自动打包相关的css
       })
   );
   ```

   

3. 修改配置：package.json

   ```javascript
   "scripts": {
       "start": "react-app-rewired start",
       "build": "react-app-rewired build",
       "test": "react-app-rewired test",
       "eject": "react-scripts eject"
     },
   ```

   

