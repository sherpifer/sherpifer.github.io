---
layout:     post
title:      "十六进制色值转rgba"
date:       ""
author:     "Sherpifer"
header-img: "img/post-bg-2015.jpg"
tags:
    - rbga hex
---
``` js
function hexToRgb(hex) {
  return 'rgb(' + parseInt('0x' + hex.slice(1, 3)) + ',' + parseInt('0x' + hex.slice(3, 5))+ ',' + parseInt('0x' + hex.slice(5, 7)) + ')';
}

function hexToRgba(hex, opacity) {
  return 'rgba(' + parseInt('0x' + hex.slice(1, 3)) + ',' + parseInt('0x' + hex.slice(3, 5)) + ','+ parseInt('0x' + hex.slice(5, 7)) + ',' + opacity + ')';
}
```
ps:安卓端无法显示css 8位的颜色十六进制色值