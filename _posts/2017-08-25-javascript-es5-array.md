---
layout: post
title:  "ES5中的数组方法总结"
category: javascript
tags: [javascript]
---
###	ES5中定义了9个新的数组方法来遍历，映射，过滤，检测，简化和搜索数组。
###	大多数方法的第一个参数是一个函数，也就是所谓的回调函数。在大多数情况下，该回调函数提供三个参数：数组元素，元素的索引，数组本身。
这里说一下箭头函数实质上是参数到函数体的映射，this自动为词法作用域。

- - -
```javascript
### forEach()方法从头至尾遍历数组，为每个元素调用指定的函数，无法在所有的元素都传递给调用的函数前终止遍历。
 var data=[1,2,3,4,5];
    var sum=0;
    data.forEach(value=>sum+=value);
    data.forEach((v,i,a)=> {
        a[i]=v+1;
    }
    );
    console.log(sum);
    console.log(data);
```	
```	javascript
### map() 方法将调用的数组的每个元素传递给制定的函数，并返回一个数组，它包含该函数的返回值。
### a=[1,2,3];
    b=a.map(x=>x*x);//b是[1,4,9], a依然是[1,2,3]
### 需要注意的是，map()返回的是新数组，它不修改调用的数组，如果是稀疏数组，返回的也是相同方式的稀疏数组：它具有相同的长度，相同的缺失元素。
 a=[1,2, , ,3];
    b=a.map(x=>x*x);//b[1,4,undefined,undefined,9]	
```	
```javascript
### filter() 故名思义 该方法返回的数组元素是调用元素的一个子集，也就是筛选出特定的元素。传递的函数是用来逻辑判定的，该函数返回true或者false，调用判定函数
就像调用forEach和map一样。如果返回值位true或者能转化为true的值，那么传递给判定函数的元素就是这个子集的成员，它将被添加到一个作为返回值的数组中。
	a=[5,4,3,2,1];
    b=a.filter(x=>x<3);b[2,1]
###	需要注意的是filter()会跳过稀疏数组中缺少的元素，它返货的总是稠密的。 	
	a=[5, , , ,1];
    b=a.filter( x=>true);b[5,1] b.length==2
### 如果需要压缩空缺并且删除undefined和null元素,可以这样使用filter():
	a=[5, ,undefined,null ,1];
    b=a.filter( x=>x!=undefined&&x!=null);b[5,1],b.length==2
```	
```javascript
###	every()和some()方法是数组的逻辑判定，他们对数组所有元素应用指定的函数进行判定，返回true或者false。
	a=[1,2,3,4,5];
    a.every(x=>x<10)//true
	a=[1,2,3,4,5];
    a.every(x=>x<5)//false  //针对的是数组的所有元素
	a.some(x=>x<5)  //true
	a.some(x=>x<0)  //false
	a.some(x=>x<1)  //false
	a.some(x=>x<2)  //true  some是要判断是否存在就返回
### 一旦every()和some()确定返回什么值他们就会停止遍历数组元素。some()在判定函数第一次返回true后就返回true，但如果判定函数一直返回false，它将会遍历整个数组。
every正好相反，事实上根据定义这是显然的，
```
```javascript
###	数组的reduce和reduceRight方法
    语法array.reduce(function(accumulator, currentValue, currentIndex, array), initialValue)
###	参数:
	callback
	执行数组中每个值的函数，包含四个参数
	accumulator
	上一次调用回调返回的值，或者是提供的初始值（initialValue）
	currentValue
	数组中正在处理的元素
	currentIndex
	数据中正在处理的元素索引，如果提供了 initialValue ，从0开始；否则从1开始
	array
	调用 reduce 的数组
	initialValue
	可选项，其值用于第一次调用 callback 的第一个参数。如果没有设置初始值，则将数组中的第一个元素作为初始值。空数组调用reduce时没有设置初始值将会报错。
	var total = [0, 1, 2, 3].reduce(function(sum, value) {
  return sum + value;
	}, 0); //total的值为6
	var total = [0, 1, 2, 3].reduce(function(sum, value) {
  return sum + value;
	}, 1); //total的值为7（1和数组中所有元素的和）
	
	var flattened = [[0, 1], [2, 3], [4, 5]].reduce(function(a, b) {
	return a.concat(b);
	});  flattened [0,1,2,3,4,5]展开为一个数组
	
	reduce如何运行
	例如执行下面的代码

	[0, 1, 2, 3, 4].reduce(function(accumulator, currentValue, currentIndex, array){
	  return accumulator + currentValue;
	});
	callback 被调用四次，每次调用的参数和返回值如下表：

	callback	accumulator	currentValue	currentIndex	array	return value
	first call	0			1					1		[0,1,2,3,4]		1
	second call	1			2					2		[0,1,2,3,4]		3
	third call	3			3					3		[0, 1, 2, 3, 4]	6
	fourth call	6			4					4		[0, 1, 2, 3, 4]	10
	通过reduce方法返回的值是最后一次调用callback(10)的结果

	你同样可以使用箭头函数的形式，下面的代码会输出跟前面一样的结果

	[0, 1, 2, 3, 4].reduce( (prev, curr) => prev + curr );
	如果你打算提供一个初始值作为reduce方法的第二个参数，以下是运行过程及结果：

	[0, 1, 2, 3, 4].reduce(   (accumulator, currentValue, currentIndex, array) => { return accumulator + currentValue; }, 10 );
	callback	accumulator	currentValue	currentIndex	array		return value
	first call	10				0			0			[0, 1, 2, 3, 4]		10
	second call	10				1			1			[0, 1, 2, 3, 4]		11
	third call	11				2			2			[0, 1, 2, 3, 4]		13
	fourth call	13				3			3			[0, 1, 2, 3, 4]		16
	fifth call	16				4			4			[0, 1, 2, 3, 4]		20
	这种情况下最终的返回值是20
	
###	例子
	将数组里的值求和

	var sum = [0, 1, 2, 3].reduce(function (a, b) {
	  return a + b;
	}, 0);
	// sum is 6
###	将二维数组转化为一维
	var flattened = [[0, 1], [2, 3], [4, 5]].reduce(
	  function(a, b) {
		return a.concat(b);
	  },
	  []
	);
	// flattened is [0, 1, 2, 3, 4, 5]
###	你也可以写成箭头函数的形式：

	var flattened = [[0, 1], [2, 3], [4, 5]].reduce(
	  ( acc, cur ) => acc.concat(cur),
	  []
	);//这里可以不写初始值	
###	计算数组中每个元素出现的次数
	var names = ['Alice', 'Bob', 'Tiff', 'Bruce', 'Alice'];

	var countedNames = names.reduce(function (allNames, name) { 
	  if (name in allNames) {
		allNames[name]++; //这里类似传统语言的key-value,通过key直接定位到value,因此事件复杂度O(1)
	  }
	  else {
		allNames[name] = 1;
	  }
	  return allNames;
	}, {});这里必须写初始值
	// countedNames is:
	// { 'Alice': 2, 'Bob': 1, 'Tiff': 1, 'Bruce': 1 }
	
	var friends = [{
	  name: 'Anna',
	  books: ['Bible', 'Harry Potter'],
	  age: 21
	}, {
	  name: 'Bob',
	  books: ['War and peace', 'Romeo and Juliet'],
	  age: 26
	}, {
	  name: 'Alice',
	  books: ['The Lord of the Rings', 'The Shining'],
	  age: 18
	}];
	var allbooks = friends.reduce(function(prev, curr) {
	  return [...prev, ...curr.books];
	}, ['Alphabet']);这里若给一个空的数组，返回的是6本书
	 allbooks = [
	  'Alphabet', 'Bible', 'Harry Potter', 'War and peace', 
	  'Romeo and Juliet', 'The Lord of the Rings',
	   'The Shining'
	 ]  //这里初始值一本共七本书
	 
###		reduceRight() 方法接受一个函数作为累加器（accumulator）和数组的每个值（从右到左）将其减少为单个值。
```	










```	


