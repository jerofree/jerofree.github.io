---
layout: post
title:  "javascript之new的诡异现象"
category: [javascript]
tags: [javascript,new]
---
##	看下面函数new的过程，第一次new的时候不能访问prototype上的任何东西，原因在于js对象构造的时候原型的拷贝是先于构造函数执行的，这里和new的过程有关。由new的过程
##	可知，第一次person.prototype还未执行就已经赋值了默认的prototype，因此第一次访问不到任何内容。
##	new的过程
###	1、创建一个空对象
###	2、设置这个导弹的原型，就是指定__proto__的指向
###	3、将构造函数的作用域赋给新的对象(因此this就指向了新对象)
###	4、执行构造函数中的代码（给这个对象添加方法和属性）
###	5、返回这个对象(this)

```c++
function Person(){
    "use strict";
    Person.prototype={
        construct:Person,
        name:"Nooo",
        age:29,
        job:"software enginner",
        sayName:function () {
            alert("哈哈哈");
        }
    }
}
var obj=new Person();
var obj1=new Person();
console.log(obj.sayName);
console.log(obj1.sayName);
```


































