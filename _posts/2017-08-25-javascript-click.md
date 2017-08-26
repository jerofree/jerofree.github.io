---
layout: post
title:  "click与onclick的区别"
category: javascript
tags: [javascript]
---
###	原生javascript的click在w3c里边的阐述是DOM button对象，也是html DOM click() 方法，可模拟在按钮上的一次鼠标单击。
###	onclick是一个事件，Event对象 。支持该事件的 JavaScript 对象：button, document, checkbox, link, radio, reset, submit
###	1.事件名前一般都以on开头；
 　2.方法是程序员写语句直接调用，即显示调用；【可以触发onclick事件】　
 　3.事件不需程序员调用，但是，必须由程序员写一个函数且将该函数赋值给相应的事件，其调用是在相应的事件触发时。
 【告诉浏览器在鼠标点击时候要做什么】所以调用顺序是：首先方法其次事件。

- - -
```

```	





