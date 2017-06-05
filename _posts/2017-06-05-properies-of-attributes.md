---
layout: post
title:  "javascript之属性的特性"
category: 属性的特性
tags: [属性的特性]
---


###	

```javascript
	
	//从函数名字就可以一看出该函数只能得到自有属性的描述符
	console.log(Object.getOwnPropertyDescriptor({x:1},"x"));

	//对于继承属性和不存在的属性，返回undefined 要想获得继承属性的特性需要遍历原型链
	console.log(Object.getOwnPropertyDescriptor({},"x"))
	console.log(Object.getOwnPropertyDescriptor({},"tostring"))
	
	//要想设置属性的特性，或者让新建的属性具有某种特性，需要Object.defineProperty()
	var o={};
	Object.defineProperty(o,"x",{configurable:true,enumberable:true, writable:true, value:1})
	console.log(o.x)
	console.log(Object.keys(o))
	Object.defineProperty(o,"x",{writable:false})
	o.x=2;
	console.log(o.x)

```


