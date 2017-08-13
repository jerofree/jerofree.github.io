---
layout: post
title:  "javascript之Function与Object"
category: javascript
tags: [Function,Object]
---
##理解Function instanceof Object与Object instanceof Function都为true
- - -
```javascript
1、Function.__proto__==Function.prototype  //Function本身继承了Function的原型
2、Function.prototype.__proto__==Object.prototype//Function的原型继承了Object的原型，因此Function可以获得原型上的toString,valueOf等方法
经过上面的1和2可知Funtion的原型链上有Object,因此Function instanceof Object为true 
3、Object.__proto__==Function.prototype//Object继承了Function的原型//因此Object可以获得Function的apply,call,bind等方法
由 3可知Object instanceof Function为true



```



