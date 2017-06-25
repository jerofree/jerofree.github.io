---
layout: post
title:  "完全背包问题"
category: 背包问题
tags: [完全背包问题]
---
###	 完全背包是在N种物品中选取若干件（同一种物品可多次选取）放在空间为V的背包里，每种物品的体积为C1，C2，…，Cn，与之相对应的价值为W1,W2，…，Wn.求解怎么装物品可使背包里物品总价值最大。
###	 完全背包问题空间优化内层for循环主题部分为f[j]=max(f[j],f[j-weight[i]]+value[i])
```C++
// complete knapsack problem.cpp : Defines the entry point for the console application.
//反向输出解
#include "stdafx.h"
#include <iostream>
using namespace std;

#define  V 1500  
unsigned int f[10][V];//全局变量，自动初始化为0  
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
	for (int j = 1; j <= M; j++)
	{
		if (weight[i] <= j)
		{
			f[i][j] = max(f[i - 1][j], f[i][j - weight[i]] + value[i]);
		}
		else
			f[i][j] = f[i-1][j];
	}

	cout << f[N][M] << endl;//输出最优解  

	int i = N;
	int j = M;
	while (i > 0 && j > 0)
	{
		if (f[i][j] == f[i][j - weight[i]]+value[i]){
			cout << weight[i] << " " << value[i] << endl;
			j = j - weight[i];
		}
		else
			i--;

	}

	system("pause");

	return 0;
}

```