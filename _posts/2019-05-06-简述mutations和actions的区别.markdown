---
layout:     post
title:      "简述mutations和actions的区别"
date:       ”2019-05-06“
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - vuex mutations actions
---

-
#### mutations 和 actions 区别
- mutations 内都是同步的方法，主要用来改变state的变量
- actions 内是异步的方法，异步回调后去触发 mutations里面的方法去改变state

#### 为何mutations只能是同步方法
- 因为内部运行机制里每次mutations的方法被调用，就会捕捉一个调用前和调用后的快照，进行状态跟踪，如果mutations里的是异步方法，就无法跟踪到状态的改变