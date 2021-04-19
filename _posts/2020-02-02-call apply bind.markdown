---
layout:     post
title:      "call apply bind"
date:       "2020-02-02"
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - js 
---

## 差异
bind 和 call 传参方式一样，但是bind返回的是一个函数，绑定this，且可传递预置参数
call 和 apply 传参方式不一样，apply接收两个参数，第二个参数是一个参数数组
这三个都是用来重定义 this 这个对象的，下面的例子可以简单看出几个方法的不同

```js
var student = {
  name: "高三学生",
  age:18,
  sayHi: function (province,city) {
    console.log("HI~我是" + this.name +"，今年"+this.age+ "，来自" + province+city);
  },
};
var san = {
  name: "张三",
  age :20
};
student.sayHi.call(san,'湖南','长沙')
student.sayHi.apply(san,['湖南','长沙'])
student.sayHi.bind(san,'湖南','长沙')()
// 三个打印出来
// HI~我是张三，今年20,来自湖南长沙
```
## 实现这三个方法
```js
Function.prototype.apply = function(context = window, args) {
  if (typeof this !== 'function') {
    throw new TypeError('Type Error');
  }
  const fn = Symbol('fn');
  context[fn] = this;

  const res = context[fn](...args);
  delete context[fn];
  return res;
}

Function.prototype.call = function(context = window, ...args) {
  if (typeof this !== 'function') {
    throw new TypeError('Type Error');
  }
  const fn = Symbol('fn');
  context[fn] = this;

  const res = context[fn](...args);
  delete context[fn];
  return res;
}

Function.prototype.bind = function(context, ...args) {
  if (typeof this !== 'function') {
    throw new Error("Type Error");
  }
  // 保存this的值
  var self = this;

  return function F() {
    // 考虑new的情况
    if(this instanceof F) {
      return new self(...args, ...arguments)
    }
    return self.apply(context, [...args, ...arguments])
  }
}

```

