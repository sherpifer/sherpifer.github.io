---
layout:     post
title:      "用vscode开发uniapp"
date:       "2020-10-10"
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - vscode uniapp
---

## 创建项目
[uniapp官方文档](https://uniapp.dcloud.io/quickstart?id=_2-%e9%80%9a%e8%bf%87vue-cli%e5%91%bd%e4%bb%a4%e8%a1%8c)
1、`npm install -g @vue/cli`
2、`vue create -p dcloudio/uni-preset-vue my-project`
3、此时，会提示选择项目模板，初次体验建议选择 `hello uni-app` 项目模板，如下所示：
![image](https://upload-images.jianshu.io/upload_images/25292152-a408b3cb06c65e94.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
4、`npm install`
5、`npm run dev:mp-weixin`

## vscode插件
uniapp-snippet (uniapp 代码片段提示)
![image.png](https://upload-images.jianshu.io/upload_images/25292152-9f945855a495c351.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 导入 HBuilderX 自带的代码块
从github上下载 [uni-app 代码块](https://github.com/zhetengbiji/uniapp-snippets-vscode)，放到项目的.vscode目录下
![image.png](https://upload-images.jianshu.io/upload_images/25292152-b5249cb870267986.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

然后基本上就可以舒舒服服地在Vscode上开发uniapp啦，不用抛弃我们可爱的Vscode啦~

项目的格式化与eslint配置请
[vue项目的格式化配置 prettier+eslint](https://www.jianshu.com/p/c85975828249)
[vue风格化的eslint规则配置](https://www.jianshu.com/p/fc8dfb04d219)
