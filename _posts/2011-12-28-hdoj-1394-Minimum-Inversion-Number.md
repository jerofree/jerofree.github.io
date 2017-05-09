---
layout: post
title:  "hdoj 1394 Minimum Inversion Number"
category: ACM
tags: [acm, hdoj, Inversion Number, ��״����]
---

#### ��Ŀ����

http://acm.hdu.edu.cn/showproblem.php?pid=1394

#### ��Ŀ����

����һ����n��������ɵ����У������Ķ���m(0<=m<n)��Ԫ���Ƶ���β�����γ�����һ������

����Ϊn������ͨ�����ַ�ʽ���Եõ�n�ֲ�ͬ�����У�����n����������������С�����е�������

<!-- more -->

#### �㷨

##### ������״����

�ο�[����״���顷](/ACM/2011-12/tree_array.html)

##### ����״������ԭʼ����������

��ԭʼ�����е�����Ԫ�أ���Ԫ��ֵ+1����Ϊ��״���鲻�ܴ���0�����б��뱣֤Ҫ�����������û��ֵΪ0��Ԫ�أ�

��ԭʼ�����е�Ԫ�أ��Ӷ�β�����ף����ζ�ÿ��Ԫ�������²�����

1.�Ѹ�Ԫ��q���뵽��״����a�У���a.modify(q, 1)

2.������q֮ǰ���뵽a�ұ�qС��Ԫ�ظ�������ret = getsum(i - 1)

3.�����е�������� += ret

�������е�Ԫ��ȫ�������꣬���ܼ���������е����������

##### ������������е��������

��f(m)Ϊ��ԭʼ����s��ǰm��Ԫ���Ƶ���β�õ������е��������

���������f(0)

��һ��Ԫ��q�Ƶ���β��f(1)=f(0)+��q���Ԫ�ظ���-��qС��Ԫ�ظ���

�������ƣ�f(m) = f(m-1) + ��s[m-1]���Ԫ�ظ��� - ��s[m-1]С��Ԫ�ظ���

�����Ϳ������μ�����������е����������

#### ����

```c++
    #include <stdio.h>  
    #define MAXN 10000  
      
    int c[MAXN],a[MAXN],n;  
      
    int min(int a,int b)  
    {  
        if (a < b) return a;  
        else return b;  
    }  
      
    int lowbit(int i)  
    {  
        return i & -i;  
    }  
      
      
    void update(int i,int x)  
    {  
        while (i <= n)  
        {  
            c[i] += x;  
            i += lowbit(i);  
        }  
    }  
      
    int getsum(int x)  
    {  
        int sum = 0;  
        while (x > 0)  
        {  
            sum += c[x];  
            x -= lowbit(x);  
        }  
        return sum;  
    }  
      
    int main()  
    {  
        while (scanf("%d", &n) == 1)  
        {  
            for (int i = 1; i <= n; i++)  
                c[i] = 0;  
            int sum = 0;  
            for (int i = 1; i <= n; i ++)  
            {  
                scanf ("%d", &a[i]);  
            }  
            for (int i = n; i >= 1; i --)  
            {  
                update (a[i] + 1, 1);  
                sum += getsum (a[i]);  
            }  
            int ans = sum;  
            for (int i = 1; i <= n; i++)  
            {  
                sum = sum - a[i] + (n - a[i] - 1);  
                ans = min(ans, sum);  
            }  
            printf("%d\n", ans);  
        }  
        return 0;  
    }  
```
