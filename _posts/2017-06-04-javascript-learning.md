---
layout: post
title:  "javascript学习!"
category: javasctipt learning
tags: [类型, 值, 变量]
---


### javascript中除了数字，字符串，布尔值，null，和undefined之外就是对象了。
```
	var s="test"
	s.len=4;创建一个临时字符串对象，随即销毁这个对象,存取字符串，数字，布尔值的属性时创建的临时对象称做包装对象。
	var t=s.len;
	console.log(s.len=9)
	console.log(t)
	
```

### 不可变的原始值和可变的对象引用
```
var s="hello world";
console.log( s.toUpperCase());返回HELLO WORLD,但并没有改变s的值。
console.log(s);返回 hello world


var a=[];  javascript中数组也是对象，对象为引用类型，对象值都是引用，对象的比较均是引用的比较，当且仅当他们引用同一个基对象时，他们才相等。
	var b=a;
	b[0]=1;
	console.log(a)
	console.log(a===b)

```	
	
	
	
	
	
	
	
	
	
	
	
	
