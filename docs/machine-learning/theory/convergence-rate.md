# 收敛率

## 基本概念

### 收敛率

收敛率旨在刻画优化误差 $f(w_{T})-f(w_{\ast})$ 与迭代轮次 $T$ 之间的关系

### 迭代复杂度

迭代复杂度则是刻画为了达到 $\epsilon$-最优解

### 梯度下降收敛分析 (Gradient Descent Convergence Analysis)

假设函数 $f: \mathbb{R}^{d}\to \mathbb{R}$ 是凸且可微分的，梯度满足 $l$-Lipschitz 连续，经过 $k$ 轮迭代，步长为 $t\leqslant \frac{1}{l}$，则解满足
$$
f(x^{(k)})-f(x^{\ast})\leqslant \frac{\|x^{(0)}-x^{\ast}\|}{2tk}
$$

收敛率为 $O(\frac{1}{t})$

*Proof*:

由 $f$ 满足 $l$-Lipschitz 连续，则 $\nabla f^{2} \preceq LI$

## References

- 《机器学习理论导引》- 周志华
- [斯坦福大学凸优化课程课件](https://www.stat.cmu.edu/~ryantibs/convexopt-F13/)