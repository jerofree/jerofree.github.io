---
layout: post
title:  "javascript之枚举属性"
category: 枚举属性
tags: [枚举属性]
---


###	存储器属性定义为一个和两个和属性同名的函数，这个函数定义没有使用function关键字，而是使用get和set.存储器属性可以继承。

```
	var serialnum={
    $n:0,
    get next(){
        return this.$n++;
    },
    set next(n){
        if(n>=this.$n) this.$n=n;
        else throw "序列号的值不能比当前值小";
    }

	}
	serialnum.next=8
	console.log(serialnum.next)
	console.log(serialnum.$n)
```


