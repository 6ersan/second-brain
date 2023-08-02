---
title: 陶哲轩-关于超临界方程的有限时间blowup的构造
linktitle: 陶哲轩-关于超临界方程的有限时间blowup的构造
date: '2023-08-01T00:00:00+01:00'
# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 2
---
视频链接：{{< cta cta_text="YouTube" cta_link="https://youtu.be/_ckfHYuAjRA" >}} {{< cta cta_text="Bilibili" cta_link="https://www.bilibili.com/video/BV1w64y1i71f/?share_source=copy_web&vd_source=c03d7cc5fdf8b11a02fed28dafbf15b3" >}} 


**发展方程**是指关于时间变量$t$的ODE(s)或PDE(s)，一些简单例子:

* 一阶ODE $\partial_t u = F(u)$ , 其中$u :[0, T) \rightarrow \mathbb{R}^m$是未知的场，$F : \mathbb{R}^m \rightarrow \mathbb{R}^m$是非线性的；
* 非线性波方程(NLW) $- \partial_{tt} u + \Delta u = F(u)$，其中$u: [0, T) \times \mathbb{R}^d \rightarrow \mathbb{R}^d$是未知的场，$F : \mathbb{R}^m \rightarrow \mathbb{R}^m$是非线性的；

* 非线性Schrödinger方程(NLS) $i \partial_t u + \Delta u = F(u)$，其中$u: [0, T) \times \mathbb{R}^d \rightarrow \mathbb{C}^m$是未知的场，$F: \mathbb{C}^m \rightarrow \mathbb{C}^m$是非线性的.

此报告关注那些在空间中衰减的**光滑**解.


一个重要的发展方程的例子**不可压Navier-Stokes方程**

$$
\begin{aligned}
\partial_t u + (u \cdot \nabla) u & =  \nu \Delta u - \nabla p \\\\
\nabla \cdot u &= 0
\end{aligned}
$$

其中$u : [0, T) \times \mathbb{R}^3 \rightarrow \mathbb{R}^3$是未知速度场，$p: [0, T) \times \mathbb{R}^3 \rightarrow \mathbb{R}$是未知压力，$\nu > 0$是给定的粘性常数.

**欧拉方程**是Navier-Stokes方程的$\nu = 0$的极限情况.

关于解发展方程的一个自然的问题是**初值问题**，即当给定$t = 0$的初始数据时，构造与这一初值对应的之后时间的解.

* 对于ODE（ $\partial_t u = F(u)$），指定初始位置$u(0) = u_0 \in \mathbb{R}^m$.
* 对于NLW（$- \partial_{tt} u + \Delta u = F(u)$），指定初始位置 $u(0) = u_0:\mathbb{R}^d \rightarrow \mathbb{R}^d$以及初始速度 $\partial_t u(0) = u_1: \mathbb{R}^d \rightarrow \mathbb{R}^m.$
* 对于NLS （ $i \partial_t u + \Delta u = F(u)$），指定初始位置$u(0) = u_0: \mathbb{R}^d \rightarrow \mathbb{C}^m$.


