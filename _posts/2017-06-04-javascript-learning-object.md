---
layout: post
title:  "javascript学习!"
category: javasctipt learning
tags: [对象,原型链 ]
---

```
	
var o={};
o.x=1;

var unitcircle={r:1}
var c=inherit(unitcircle)
c.x=1;c.y=1;
c.r=2;//如果允许赋值操作，它也总是在原始对象上创建属性或对已有的属性赋值，而不会去修改原型链。
console.log(unitcircle.r);

function inherit(p) {
    if (p == null) throw TypeError();
    if (Object.create)
        return Object.create(p);
    var t = typeof p;
    if (t !== "object" && t != "function") throw TypeError();
    function f() {
    };
    f.prototype = p;
    return new f();
}
```	
	
	
	
	
	
	
	
	
	
	
	
	
