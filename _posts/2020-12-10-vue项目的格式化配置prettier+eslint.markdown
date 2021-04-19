---
layout:     post
title:      "vue项目的格式化配置 prettier+eslint"
date:       "2020-12-10"
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - vscode vue eslint
---
uniapp项目的格式化和eslint同样适用

## 先安装vscode插件
* prettier
* eslint
## 创建settings.json与.prettierrc文件
.vscode>>settings.json

```json
{
  "eslint.validate": ["javascript", "javascriptreact", "vue-html", "vue"],
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "eslint.run": "onSave",
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```
根目录新建一个.prettierrc文件
```js
{
    "tabWidth": 2,
    "useTabs": true, // 使用tab（制表符）缩进而非空格
    "singleQuote": true,// 单引号
    "printWidth": 175,// 一行超过175个字符就换行
    "semi": false,// 是否在行尾加分号
    "trailingComma": "none",// 数组、对象最后一个元素的尾逗号
    "bracketSpacing": true,// 花括号前后空格
    "jsxBracketSameLine": false, // 使多行JSX元素最后一行末尾的 > 单独一行
    "arrowParens": "avoid",//只有一个参数的箭头函数的参数是否带圆括号（默认avoid不带）
    "htmlWhitespaceSensitivity": "ignore",//  HTML 文件空格敏感度
  }
```
## 给Vue项目添加eslint

`vue add eslint`

![image.png](https://upload-images.jianshu.io/upload_images/25292152-d773b565c7c858de.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

选择Error prevention only，eslint会使用`eslint:recommended`，即eslint的推荐核心规则
![image.png](https://upload-images.jianshu.io/upload_images/25292152-a7b90c2642fe19ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
选择保存时检查

然后会自动下载eslint相关的依赖，根目录会出现一个.eslint.js的文件
![image.png](https://upload-images.jianshu.io/upload_images/25292152-a9dc3f1bde3a65b3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这样界面和控制台都会有报错提示
![image.png](https://upload-images.jianshu.io/upload_images/25292152-ac988834d44dd87f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

PS 界面没有报错提示则检查vscode的状态栏的eslint是否开启的状态
![image.png](https://upload-images.jianshu.io/upload_images/25292152-16a49488d1ebf8da.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

PS：uniapp 的uni会报错 在.eslint.js中加入全局变量，就不会报错了

```js
module.exports = {
  // ...
  globals: {
    uni: true
  }
}
```


