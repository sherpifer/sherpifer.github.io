---
layout:     post
title:      "canvas解决图片跨域问题 生成分享图片"
date:       2019-04-11 09:00:00
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - h5 canvas 画布污染 跨域图片 
---

## 正文
最近在做一个需求将H5页面的内容生成海报图片保存
因为页面的图片涉及微信头像二维码还有存在oss服务器的图片，所以遇到画布污染问题不能直接调用 html2canvas + Canvas2Image 这样的方案（这两个的坑也挺多的），最后选了个最保守，不出错的做法是让后端同学在后端将图片处理一下，返回图片的base64到前端页面，这样就不涉及跨域了 哈哈哈

```
var opts = {
  useCORS: true, //（图片跨域相关）
  allowTaint: true //（图片跨域相关）
}
<!-- node-要转换图片的dom opts-配置 image-显示图片的标签 -->
html2canvas(node, opts, image).then(function(canvas) {
  var img = new Image()
  img.crossOrigin = 'anonymous'
  img = Canvas2Image.convertToImage(canvas)
  image.src = canvas.toDataURL(img)
})

```