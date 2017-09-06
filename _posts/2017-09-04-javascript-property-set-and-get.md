---
layout: post
title:  "javascript 温故而知新"
category: javascript属性操作
tags: [javascript属性操作]
---
## 下面的例子可以说明不管使用哪种形式的属性访问表达式,在“.”和“[”之前的表达式总是会被首先计算。
	如果计算出的结果是null或者undefined，表达式会抛出一个类型错误异常，因为这两个值都不能包含任意属性。
```javascript
	var obj={x:1}
	obj["x"]        //1
	obj["y"]       //undefined 
	obj.y.z       //TypeError: Cannot read property 'x' of undefined不能设置undefined的x属性，这说明了obj.y是undefined.
    obj.y.x=1 //属性设置也是同样的道理,“.”号之前的表达式会先计算，obj存在,obj.y是undefined，obj.y.x=1就会抛出错误。
			  //Cannot set property 'x' of undefined        不能设置undefined的x属性,说明先查询obj.y，返回结果是undefined.
	var xs=obj&&obj.y&&obj.y.x;	利用逻辑与表达式	//这样做返回值要么是undefined要么是obj.y.x的值;	  		

```
## 有一个问题需要注意, .identifer只适用于要访问的名称是合法的标识符,并且需要知道要访问的属性的名字. 如果属性名称是一个保留字，
或者包含空格和标点符号,或者是一个数字(对于数组而言)，则必须使用方括号的写法。当属性名是通过运算得出来的值而不是固定的值的时候，
这时候必须用方括号的写法。

## 属性删除部分在下一章写       		
	

	



		


	






