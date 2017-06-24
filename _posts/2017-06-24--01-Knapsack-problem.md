---
layout: post
title:  "01背包问题"
category: 背包问题
tags: [01背包问题及其空间优化版本]
---

### 01背包问题：一个背包总容量为V，现在有N个物品，第i个 物品体积为weight[i]，价值为value[i]，现在往背包里面装东西，怎么装能使背包的内物品价值最大？
```

#include "stdafx.h"
#include<iostream>
using namespace std;
#define  V 1500  
//unsigned int f[10][V];//全局变量，自动初始化为0  
unsigned int weight[10];
unsigned int value[10];
#define  max(x,y)   (x)>(y)?(x):(y)
	//int N, M;
//	//cin >> N;//物品个数  
//	//cin >> M;//背包容量  
//	//for (int i = 1; i <= N; i++)
//	//{
//	//	cin >> weight[i] >> value[i];
//	//}
//	//for (int i = 1; i <= N; i++)
//	//for (int j = 1; j <= M; j++)
//	//{
//	//	if (weight[i] <= j)
//	//	{
//	//		f[i][j] = max(f[i - 1][j], f[i - 1][j - weight[i]] + value[i]);
//	//	}
//	//	else
//	//		f[i][j] = f[i - 1][j];
//	//}
//
//	//cout << f[N][M] << endl;//输出最优解  
//	//cout << "输出表格" << endl;
//	//for (int i = 1; i <= N; i++)
//	//{
//	//	for (int j = 1; j <= M; j++)
//	//	{
//	//		cout << f[i][j] << " ";
//	//	}
//	//	cout << endl;
//	//}
//	system("pause");
//	return 0;
//}
```
###	01背包问题空间优化版本  
#### //这里max中的f[j]是i-1时候的值，而外面的f[j]是i对应的值，如果循环j从1到M，则i-1时候的f[j]会被替换为i时的f[j],以为数组是一维度的，不能保存i-1时候的状态
```
#include "stdafx.h"
#include<iostream>
#define  V 1500  
unsigned int f[V];//全局变量，自动初始化为0  
using namespace std;

//unsigned int f[10][V];//全局变量，自动初始化为0  

unsigned int weight[10];
unsigned int value[10];
#define  max(x,y)   (x)>(y)?(x):(y)  

int _tmain(int argc, _TCHAR* argv[])
{


	int N, M;
	cin >> N;//物品个数  
	cin >> M;//背包容量  
	for (int i = 1; i <= N; i++)
	{
		cin >> weight[i] >> value[i];
	}
	for (int i = 1; i <= N; i++)
	for (int j = M; j >=1; j--)
	{
		if (weight[i] <= j)
		{
			f[j] = max(f[j], f[j - weight[i]] + value[i]);
		}
	}
	for (int j = M; j >= 1; j--){
		cout << f[j] << endl;//输出最优解 
	}
```

