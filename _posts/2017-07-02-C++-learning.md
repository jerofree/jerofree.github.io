---
layout: post
title:  "结构体与联合体"
category: C++
tags: [结构体与联合体]
---
##	结构体

	####	与类的唯一区别：类的缺省访问权限是private，结构体的缺省访问权限是public
	####	结构体存在的主要原因：与C语言保持兼容
	####	什么时候用结构体而不用类
	####	定义主要用来保存数据、而没有什么操作的类型
	####	人们习惯将结构体的数据成员设为公有，因此这时用结构体更方便
 

##	结构体的定义
```c++
struct 结构体名称 {
	 公有成员
protected:
    保护型成员
private:
     私有成员
};
```
##	结构体的初始化

####	如果一个结构体的全部数据成员都是公共成员，并且没有用户定义的构造函数，没有基类和虚函数（基类和虚函数将在后面的章节中介绍），这个结构体的变量可以用下面的语法形式赋初值
类型名 变量名 = { 成员数据1初值, 成员数据2初值, …… };
例4-7用结构体表示学生的基本信息
```c++
#include 
#include 
#include 
using namespace std;

struct Student {	//学生信息结构体
	int num;		//学号
	string name;	//姓名，字符串对象，将在第6章详细介绍
	char sex;		//性别
	int age;		//年龄
};

int main() {
	Student stu = { 97001, "Lin Lin", 'F', 19 };
	cout << "Num:  " << stu.num << endl;
	cout << "Name: " << stu.name << endl;
	cout << "Sex:  " << stu.sex << endl;
	cout << "Age:  " << stu.age << endl;
	return 0;
}

运行结果：
Num:  97001
Name: Lin Lin
Sex:  F
Age:  19
```

##	联合体

###	声明形式
```c++
union 联合体名称 {
    公有成员
protected:
    保护型成员
private:
    私有成员
};
```
###	特点

####	成员共用同一组内存单元
任何两个成员不会同时有效
联合体的内存分配

## 举例说明：
```c++
union Mark {	//表示成绩的联合体
	char grade;	//等级制的成绩
	bool pass;	//只记是否通过课程的成绩
	int percent;	//百分制的成绩
};
```
##	特点
```c++
union {
  int i;
  float f;
}
在程序中可以这样使用：
i = 10;
f = 2.2;
```
##下面我们看一个联合体的例题

###例4-8使用联合体保存成绩信息，并且输出。
```c++
#include 
#include 
using namespace std;
class ExamInfo {
private:
	string name;	//课程名称
	enum { GRADE, PASS, PERCENTAGE } mode;//计分方式
	union {
		char grade;	//等级制的成绩
		bool pass;	//只记是否通过课程的成绩
		int percent;	//百分制的成绩
	};
public:
	//三种构造函数，分别用等级、是否通过和百分初始化
	ExamInfo(string name, char grade)
		: name(name), mode(GRADE), grade(grade) { }
	ExamInfo(string name, bool pass)
		: name(name), mode(PASS), pass(pass) { }
	ExamInfo(string name, int percent)
		: name(name), mode(PERCENTAGE), percent(percent) { }
	void show();
}

void ExamInfo::show() {
	cout << name << ": ";
	switch (mode) {
	  case GRADE: cout << grade;  break;
	  case PASS: cout << (pass ? "PASS" : "FAIL"); break;
	  case PERCENTAGE: cout << percent; break;
	}
	cout << endl;
}

int main() {
	ExamInfo course1("English", 'B');
	ExamInfo course2("Calculus", true);
	ExamInfo course3("C++ Programming", 85);
	course1.show();
	course2.show();
	course3.show();
	return 0;
}
运行结果：
English: B
Calculus: PASS
C++ Programming: 85
```




































