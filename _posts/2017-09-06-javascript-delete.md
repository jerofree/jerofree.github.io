---
layout: post
title:  "javascript 属性删除"
category: javascript属性删除
tags: [javascript 属性删除]
---
## delete运算符可以删除对象的属性，delete仅仅是断开属性和宿主对象的联系，而不会去删除属性中的属性。
   delete运算符只能删除自有属性不能删除对象原型链上的属性（需要从定义这个属性的原型对象上删除） 	
```javascript
	a={p:{x:1}}
	b=a.p
	delete a.p	//这段代码执行完后b.x的值仍然是1，对象属于引用类型，这里能访问b.x也是正常。
	delete Object.prototype //false
	Object.getOwnPropertyDescriptor(Object,'prototype')
	//上句返回 Object {value: Object, writable: false, enumerable: false, configurable: false}不可写，不可枚举，不可配置
	var x=1;//申明一个全局变量
	delete this.x;//不能删除这个属性
	（function(){
	var localVal=1;
	return delete localVal;
	}
	)(),返回false,局部变量不能被删除
	
	function f(){}  delete f;//返回false 函数不能被删除（不论全局还是局部）
	
	隐式创建的全局变量可以delete(不推荐)
	
	eval中通过var 定义的变量可以被删除掉。
	当delete表达式删除成功或者没有任何副作用时候它返回true.
	```
## 当时数组的时候delete 成功了，但是数组对应的位置变为undefined,数组的长度不变。
	f=[1,2,3]
	delete f[1] //返回true
	f 变为[1, undefined × 1, 3]，f.length依然为3	
	

	



		


	






