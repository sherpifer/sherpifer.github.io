---
layout:     post
title:      "uniapp APP端微信分享小程序卡片"
date:       "2021-01-10"
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - uniapp 小程序
---

## App分享 微信小程序
- App中分享一个内容到微信好友，对方微信中呈现的是一个小程序卡片[uniapp share文档](https://uniapp.dcloud.io/api/plugins/share?id=share)

```js
uni.share({
    provider: 'weixin',
    scene: "WXSceneSession",
    type: 5,
    imageUrl: 'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/962fc340-4f2c-11eb-bdc1-8bd33eb6adaa.png',
    title: '欢迎体验uniapp',
    miniProgram: {
        id: 'gh_abcdefg',// 小程序的原始ID 上开放者平台查看
        path: 'pages/index/index',
        type: 0,// 微信小程序版本类型，可取值： 0-正式版； 1-测试版； 2-体验版。 默认值为0。
        webUrl: 'http://uniapp.dcloud.io'
    },
    success: ret => {
        console.log(JSON.stringify(ret));
    }
});
```
## android 获取应用签名

- 手机装上我们自己开发的APP
- [开放者平台-资源下载](https://developers.weixin.qq.com/doc/oplatform/Downloads/Android_Resource.html)
![image.png](https://upload-images.jianshu.io/upload_images/25292152-2ac990189970fb32.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 下载开放平台文档提供的获取应用签名的apk，获取签名
![image.png](https://upload-images.jianshu.io/upload_images/25292152-7962ff448aa77a7a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## iOS申请通用链接（Universal Link）
- [设置通用链接](https://ask.dcloud.net.cn/article/36393#unilink)


## 完善开放者平台的应用信息
- 登录[开放平台](https://open.weixin.qq.com/)
- 管理中心 / 修改应用 / 修改开发信息 填写应用签名
![image.png](https://upload-images.jianshu.io/upload_images/25292152-a3d20e9277e910af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 修改项目mainfest.json文件 填写好微信分享的appid(应用的非小程序的)和IOS的通用链接
![image.png](https://upload-images.jianshu.io/upload_images/25292152-03561cf7a854af45.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 运行测试
需打包自定义基座 重新运行即可从APP分享小程序卡片到聊天中





