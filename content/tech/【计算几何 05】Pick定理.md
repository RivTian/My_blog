---
title: "【计算几何 05】Pick定理"
date: 2020-10-20T15:30:46+08:00
draft: false
tags:
  - 计算几何
topics:
  - 
---

什么是Pick定理（皮克定理）

> 来自wiki的介绍：
>
> 给定顶点座标均是整点（或正方形格子点）的简单多边形，皮克定理说明了其面积 $A$和内部格点数目 $i$ 、边上格点数目 $b$ 的关系：$A = i + \frac b 2 - 1$。

因为所有简单多边形都可切割为一个三角形和另一个简单多边形。考虑一个简单多边形 $P$，及跟$P$有一条共同边的三角形$T$。若$P$ 符合皮克公式，则只要证明$P$加上$T$ 的$PT$亦符合皮克公式（I），与及三角形符合皮克公式（II），就可根据数学归纳法，对于所有简单多边形皮克公式都是成立的。

~~详细证明：[Click Here](https://zh.wikipedia.org/zh-cn/%E7%9A%AE%E5%85%8B%E5%AE%9A%E7%90%86)~~

Update：证明过程更新

### 小学生都看得懂的证明

学习Pick定理的时候发现有很多证明过程都写复杂了，但我发现蒟蒻dalao记录的一篇证明非常易懂。

在这个证明之前，我们需用到一个很浅显的预备知识：“多边形外角和等于一个周角”。

以下图的格点多边形ABCDE为例，其边界上有a个格点，内部有b个格点。

![](https://gitee.com//riotian/blogimage/raw/master/img/20201027193534.jpeg)

设想在平面的每个格点放一个铁饼，满足：
(1)每个铁饼都一样大的圆（或者说是圆柱），圆心是格点；
(2)每个铁饼都恰好重1克；
(3)每个铁饼的半径都做得尽量小——不仅铁饼之间互相不重叠，而且还使得多边形ABCDE内部的每个格点上所放的铁饼，都完全落在该多边形的内部；多边形ABCDE外部的每个格点上所放的铁饼，都完全落在该多边形的外部。

首先，考虑多边形ABCDE的边界以内的铁的总重。
这可以分如下两类进行计算：

第一类：其内部格点上放的铁饼．此类总重显然是b克。

第二类：其边界格点上放的铁饼落在边界以内的铁．假设每个边界格点上放的铁饼，恰有一半落在边界以内，则总重为 $a/2$ 克．但显然在每个顶点处放的铁饼，落在边界以内的铁实际不足一半，比一半还少该顶点的一个外角内所含的铁，然后我们知道多边形的外角和为 $360°$ ，所以所有这种外角内所含的铁恰好拼成一块完整的铁饼（因为多边形外角和等于一个周角）．所以后一类铁的总重是 $a/2 -1$克。

因而，多边形ABCDE的边界以内的铁的总重是 $a/2＋b－1$ 克．

接下来，设想将平面上所有铁饼全部熔化，打造成一张厚薄均匀的铁板盖在整个平面上．这可以看作是：将每个单位正方形的四个顶点处的每个 $90°$ 的扇形铁饼，熔化在这个正方形内部，故熔化后每个单位正方形内的铁都是 $1$ 克．进而，平面上任意图形，其面积是多少，其内部就含多少克铁。

因而，熔化并重新打造后，多边形ABCDE的边界以内的铁的总重是 $S$ 克。

最后，注意到这个熔化并重新打造的过程，可以看成是：每个格点处的铁饼中的铁，按(以该格点为中心)放射状的方式重新适当改动位置而已．这样的改动，不会使格点多边形ABCDE外面的铁跑到多边形内部，也不会使内部的铁跑到外部。

即熔化并重新打造的前后，多边形ABCDE的边界以内的铁的总重是不变的，所以 $S＝a/2＋b－1$。

特别感谢思路提供者[Orz大佬](http://blog.sina.com.cn/s/profile_2713979363.html)！

---

Pick定理有以下推广：

-   取格点的组成图形的面积为一单位。在平行四边形格点，皮克定理依然成立。套用于任意三角形格点，皮克定理则是 ${\displaystyle A=2 \times i+b-2}$ 。
-   对于非简单的多边形 ${\displaystyle P}$ ，皮克定理 ${\displaystyle A=i+{\frac {b}{2}}-\chi (P)}$ ，其中 ${\displaystyle \chi (P)}$ 表示 ${\displaystyle P}$ 的 **欧拉特征数** 。
-   高维推广：Ehrhart 多项式
-   皮克定理和 **欧拉公式** （ ${\displaystyle V-E+F=2}$ ）等价。

## 一道例题 (POJ 1265)

### 题目大意

给一个平面上的简单多边形，求边上的点，多边形内的点，多边形面积。

### Solution

这道题目其实用了以下三个知识：

-   以格子点为顶点的线段，覆盖的点的个数为 $\gcd(dx,dy)$ ，其中， $dx,dy$ 分别为线段横向占的点数和纵向占的点数。如果 $dx$ 或 $dy$ 为 $0$ ，则覆盖的点数为 $dy$  **或**  $dx$ 。
-   Pick 定理：平面上以格子点为顶点的简单多边形的面积 = 边上的点数/2 + 内部的点数 - 1。
-   任意一个多边形的面积等于按顺序求相邻两个点与原点组成的向量的叉积之和（这个也可以通过顺时针定积分求得）。

于是这题就愉快地做完了

```cpp
// Author : RioTian
// Time : 20/10/21
#include <cmath>
#include <cstdio>
#include <iostream>
using namespace std;
typedef long long ll;
const int N = 100 + 10;
struct node {
    int x, y;
} p[N];
inline int gcd(int a, int b) { return b == 0 ? a : gcd(b, a % b); }
inline int area(int a, int b) { return p[a].x * p[b].y - p[a].y * p[b].x; }
int main() {
    // freopen("in.txt", "r", stdin);
    ios::sync_with_stdio(false), cin.tie(0), cout.tie(0);
    int t, ncase = 1;
    cin >> t;
    while (t--) {
        int n, dx, dy, x, y, num = 0, sum = 0;
        cin >> n;
        p[0].x = p[0].y = 0;
        for (int i = 1; i <= n; ++i) {
            cin >> x >> y;
            p[i].x = x + p[i - 1].x, p[i].y = y + p[i - 1].y;
            dx = x, dy = y;
            if (x < 0) dx = -x;
            if (y < 0) dy = -y;
            num += gcd(dx, dy);
            sum += area(i - 1, i);
        }
        if (sum < 0) sum = -sum;
        if (sum < 0) sum = -sum;
        printf("Scenario #%d:\n", ncase++);
        printf("%d %d %.1f\n\n", (sum - num + 2) >> 1, num, sum * 0.5);
    }
}
```

