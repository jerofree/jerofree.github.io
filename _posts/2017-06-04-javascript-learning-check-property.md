---
layout: post
title:  "javascript之检测属性!"
category: javasctipt learning
tags: [对象,检测属性]
---


```
	var o={x:1};
	console.log("x" in o); //true
	console.log("y" in o);//false
	"tostring" in o; //true
	var o={x:1};
	console.log(o.hasOwnProperty("x"));true：o有一个自有属性x
	console.log(o.hasOwnProperty("y"));false：o中不存在属性y
	console.log(o.hasOwnProperty("tostring"));false：tostring是继承属性
	var o=inherit({y:2});
	o.x=1;
	o.propertyIsEnumerable("x");//true
	o.propertyIsEnumerable("y");//false
	console.log(Object.prototype.propertyIsEnumerable("tostring"));//false:不可枚举
	
	
	
	
```	
	
	
	
	
	
	
	
	
	
	
	
	
