---
layout:     post
title:      "vue风格化的eslint规则配置"
date:       "2020-11-12"
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - vscode vue eslint
---

Vue项目根目录 .eslint.js 文件配置规则
```js
module.exports = {
 // ...
  rules: {
    'no-console': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
    'no-debugger': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
    //Vue 风格
    // 指令缩写
    'vue/v-bind-style': ['error', 'shorthand'],
    'vue/v-on-style': ['error', 'shorthand'],
    // 组件/实例的选项的顺序
    'vue/order-in-components': [
      'error',
      {
        order: [
          'el',
          'name',
          'parent',
          'functional',
          ['delimiters', 'comments'],
          ['components', 'directives', 'filters'],
          'extends',
          'mixins',
          'inheritAttrs',
          'model',
          ['props', 'propsData'],
          'data',
          'computed',
          'watch',
          'LIFECYCLE_HOOKS',
          'methods',
          ['template', 'render'],
          'renderError'
        ]
      }
    ],
    // 元素/组件特性，属性的顺序
    'vue/attributes-order': [
      'error',
      {
        order: [
          'DEFINITION',
          'LIST_RENDERING',
          'CONDITIONALS',
          'RENDER_MODIFIERS',
          'GLOBAL',
          'UNIQUE',
          'TWO_WAY_BINDING',
          'OTHER_DIRECTIVES',
          'OTHER_ATTR',
          'EVENTS',
          'CONTENT'
        ]
      }
    ]
  }
}
```
参考 [Vue风格指南总结及对应ESLint规则配置](https://www.cnblogs.com/dreamsqin/p/10906951.html)]

