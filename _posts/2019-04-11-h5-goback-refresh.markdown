---
layout:     post
title:      "H5 返回上一级页面后刷新页面"
date:       2019-04-11 09:00:00
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - h5 
---

## 正文
h5页面返回上一个页面并刷新的实现方法
监听页面的pageshow 事件判断当前页面是否从浏览器缓存中加载，如果是则强行刷新获取最新数据
```
// 页面是否从浏览器缓存中加载
  window.addEventListener('pageshow', function(event) {
    if (event.persisted) {
      location.reload();
    }
  });

```