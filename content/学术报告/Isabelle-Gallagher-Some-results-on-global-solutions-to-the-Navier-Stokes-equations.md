---
title: Isabelle Gallagher - 关于Navier-Stokes方程整体解的一些结果
linktitle: Isabelle Gallagher - 关于Navier-Stokes方程整体解的一些结果
date: '2023-08-01T00:00:00+01:00'
# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 1
---

视频链接：[YouTube](https://youtu.be/27nyEX8I5dw)

### 介绍

Navier-Stokes方程：

{{< math >}}$$
\left\{\begin{aligned}
\partial_t u + u \cdot \nabla u - \Delta u & = - \nabla p \quad \text{in}\; \mathbb{R}^3\\
\text{div} \  u &= 0 \\
u|_{t = 0} & = u_0
\end{aligned}\right.
$${{< /math >}}

通过将算子{{< math >}}$\mathbb{P} = \text{Id} - \nabla \text{div} \Delta^{-1}${{< /math >}}作用到方程两边可以消去压力项，得到只与{{< math >}}$u${{< /math >}}有关的方程：
{{< math >}}$$
\partial_t u + \mathbb{P} \text{div}(u \otimes u) - \Delta u = 0
$${{< /math >}}

算子{{< math >}}$\mathbb{P}${{< /math >}}的作用是将向量场投影成divergence-free的向量场.


