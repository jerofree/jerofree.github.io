---
layout: post
title:  "python学习"
category: python循环
tags: [python]
---
###	其他语言中的循环
####	javascript中的循环和C/C++，java中的循环很相似。
```javascript
var colors = ["red", "green", "blue", "purple"];
for (var i = 0; i < colors.length; i++) {
    console.log(colors[i]);
}
```
###	python中的while循环  和C风格的循环类似
```python
colors = ["red", "green", "blue", "purple"]
i = 0
while i < len(colors):
    print(colors[i])
    i += 1
```
###	很多python程序员尝试以一种创新的方式使用for循环 实际上在python中使用for-in 循环（类似foreach）
```python
colors = ["red", "green", "blue", "purple"] 
	for i in range(len(colors)): 
	print(colors[i])

```
### for-in 直接迭代	事实上，我们不关心下标索引，我们仅仅为了在我们的列表中获取元素时使用索引。
```python
colors = ["red", "green", "blue", "purple"]
for i in colors:
    print(i)
```
###	倘若我们需要索引时候,下面看看如何打印出总统名字和基于列表索引的数字
```python
presidents = ["Washington", "Adams", "Jefferson", "Madison", "Monroe", "Adams", "Jackson"]
for i in range(len(presidents)):
     print("President {}: {}".format(i + 1, presidents[i]))
```
###	但是我们有一种更加符合习惯的方式来完成这个任务，使用enumerate函数
#### python内置的enumerate函数允许我们循环列表，同时获取列表中的索引和值. enumerate给了我们一个iterable，每一个元素是一个元组，包含item的索引和原始的item值
#### This function is meant for solving the task of:

Accessing each item in a list (or another iterable)
Also getting the index of each item accessed
So whenever we need item indexes while looping, we should think of enumerate.
Note: the start=1 option to enumerate here is optional. If we didn’t specify this, we’d start counting at 0 by default.
```python
presidents = ["Washington", "Adams", "Jefferson", "Madison", "Monroe", "Adams", "Jackson"]
for num, name in enumerate(presidents, start=1):
    print("President {}: {}".format(num, name))

```
### 在多个可迭代对象上循环
#### Note that we only need the index in this scenario because we’re using it to lookup elements at the same index in our second list. What we really want is to loop over two lists simultaneously: the indexes just provide a means to do that.
```python
colors = ["red", "green", "blue", "purple"]
ratios = [0.2, 0.3, 0.1, 0.4]
for i, color in enumerate(colors):
    ratio = ratios[i]
    print("{}% {}".format(ratio * 100, color))
```
### python的zip函数允许我们在多个列表上同时循环
#### The zip function takes multiple lists and returns an iterable that provides a tuple of the corresponding elements of each list as we loop over it.

Note that zip with different size lists will stop after the shortest list runs out of items. You may want to look into itertools.zip_longest if you need different behavior. Also note that zip in Python 2 returns a list but zip in Python 3 returns a lazy iterable. In Python 2, itertools.izip is equivalent to the newer Python 3 zip function.
```python
colors = ["red", "green", "blue", "purple"]
ratios = [0.2, 0.3, 0.1, 0.4]
for color, ratio in zip(colors, ratios):
    print("{}% {}".format(ratio * 100, color))

```






