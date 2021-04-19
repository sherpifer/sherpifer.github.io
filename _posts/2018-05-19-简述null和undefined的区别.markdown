---
layout:     post
title:      "简述null和undefined区别"
date:       “2018-04-05”
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags: js基础 null undefined
---

- undefined，变量声明但未赋值
- 函数没有返回值时，默认返回undefined。
- 销毁一个对象的堆内存，可赋值null
- typeof null 是object ； typeof undefined  还是undefined
- Object.prototype.__proro__=null
- null==undefined true