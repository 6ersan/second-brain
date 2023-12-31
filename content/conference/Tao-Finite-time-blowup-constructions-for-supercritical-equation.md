---
title: 陶哲轩 - 关于超临界方程的有限时间blowup的构造
linktitle: 陶哲轩 - 关于超临界方程的有限时间blowup的构造
date: '2023-08-01T00:00:00+01:00'
# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 2
---
视频链接：[YouTube](https://youtu.be/_ckfHYuAjRA) [Bilibili](https://www.bilibili.com/video/BV1w64y1i71f/?share_source=copy_web&vd_source=c03d7cc5fdf8b11a02fed28dafbf15b3)



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

* 对于(ODE)$\partial_t u = F(u)$，指定初始位置$u(0) = u_0 \in \mathbb{R}^m$.
* 对于(NLW)$- \partial_{tt} u + \Delta u = F(u)$，指定初始位置 $u(0) = u_0:\mathbb{R}^d \rightarrow \mathbb{R}^d$以及初始速度 $\partial_t u(0) = u_1: \mathbb{R}^d \rightarrow \mathbb{R}^m.$
* 对于(NLS)$i \partial_t u + \Delta u = F(u)$，指定初始位置$u(0) = u_0: \mathbb{R}^d \rightarrow \mathbb{C}^m$.

对于Navier-Stokes方程和Euler方程

$$
\begin{aligned}
\partial_t u + (u \cdot \nabla) u & =  \nu \Delta u - \nabla p \\\\
\nabla \cdot u &= 0
\end{aligned}
$$

仅需指定满足不可压条件$\nabla \cdot u = 0$速度场的初值$u_0: \mathbb{R}^3 \rightarrow \mathbb{R}^3$，无需指定压力的初值，因为压力初值可以通过速度初值导出.

- 一般来说，给定光滑性足够好的初值，容易建立这些初值问题的局部存在性（唯一性），但是整体存在性往往十分困难.

- 例如，ODE的初值问题$\partial_t u = F(u), \  u(0) = u_0$，其中$u_0 \in \mathbb{R}^m$以及$F : \mathbb{R}^m \rightarrow \mathbb{R}^m$给定，$F$足够光滑，借助Picard存在性以及唯一性定理可保证最大时间$T_\* \in (0, \infty]$的存在性和初值问题的光滑解$u : [0, T_\*)\rightarrow \mathbb{R}^m$的存在唯一性.

- 进一步可证明，只有两种情况发生：要么$T_\* =  +\infty$，要么$T_\* < \infty$且当$t \rightarrow T_\*$时有$u(t) \rightarrow \infty$

- 对于简单的ODE方程：Ricatti方程 $\partial_t u = u^2, \  u: [0, T_\*) \rightarrow \mathbb{R}$，存在有限时间的blowup，例如显式解$u(t) = \dfrac{1}{1 - t}, \ 0 \le t < 1$.

- 同样对于方程$\partial_t u = u^2$, 当解$u \sim 2^n$，则$\partial_t u \sim 2^{2n}$，所以时间$t$增加$ 2^{-n}$，$u$加倍增加到$2^{n + 1}$，再由级数$\sum^\infty_{n = 1} 2^{-n}$的收敛性可知可能发生有限时间的blowup，参考图1.

{{< figure src="/Tao-Finite-time-blowup-constructions-for-supercritical-equation/1.png" caption="一个blowup的例子" numbered="true" >}}

- 对于ODE，有限时间blowup是可以避免的：如果存在**守恒律**（conservation law）且其是**强制**的（coercive，解被限制在一个紧集内）.

- 例如，考虑（Hamiltonian ODE）$\partial_{tt} u = - (\nabla_{\mathbb{R}^m}V)(u), \ u :[0, T_\*) \rightarrow \mathbb{R}^m$，某个光滑势函数 $V : \mathbb{R}^m \rightarrow \mathbb{R}$.此ODE能量守恒：$$
E(t) := \frac{1}{2}\|\partial_t u(t)\|^2_{\mathbb{R}^m} + V(u(t))
$$以及$E(t) = E(0), \forall t \in [0, T_\*)$.若$V$是defocusing，即当$u \rightarrow \infty$时有$V(u) \rightarrow + \infty$，相反，若$V$是focusing，即当$u \rightarrow \infty$时有$V(u) \rightarrow - \infty$，则有可能blowup.参考图2.

{{< figure src="/Tao-Finite-time-blowup-constructions-for-supercritical-equation/2.png" caption="defocusing与focusing" numbered="true" >}}

不同于ODE，PDE的情况则更加复杂，强制的守恒律也不一定能避免有限时间blowup.

一个显式反例由一维focusing五次NLS给出
$$
i\partial_t u + \dfrac{1}{2} \partial_{xx}u = - |u|^4 u.
$$
此方程质量守恒
$$
M(t) := \int_\mathbb{R} |u(t, x)|^2 dx.
$$
然而，存在一个光滑解（甚至是Schwartz）在有限时间内blow up

$$
u(t, x) := \dfrac{e^{-i \dfrac{3}{8(t - 1)} + \dfrac{i x^2}{2(t - 1)}}}{(i ( t - 1))^{1/2}}Q\left(\dfrac{x}{t - 1}\right)
$$
其中$Q(x): = (3/ 8)^{1/4}cosh^{- 1/ 2} (x)$是基态.