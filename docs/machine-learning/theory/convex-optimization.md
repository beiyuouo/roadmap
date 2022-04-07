# 凸优化

## 凸集

对集合 $C$ 内的任意两点 $x_1, x_2 \in C$，若它们之间连线上的所有点仍属于集合 $C$，即

$$
\theta x_1 + (1-\theta) x_2  \in C, (\forall 0 \leqslant \theta \leqslant 1)
$$

## 凸函数

对定义在凸集上的函数 $f:\mathbb{R}^d\to \mathbb{R}$，令 $\Psi$ 表示其定义域，若 $\forall x, z \in \Psi$ 均满足

$$
f(\theta x + (1-\theta) z) \leqslant \theta f(x) + (1-\theta) f(z), (\forall 0 \leqslant \theta \leqslant 1)
$$

不等号反向，则为凹函数。

## $\lambda$-强凸

对定义在凸集上的函数 $f:\mathbb{R}^d\to \mathbb{R}$，若 $\exists \lambda \in \mathbb{R}_{+}$ 使得 $\forall x,z \in \Psi$ 都有

$$
f(\theta x+(1-\theta) z) \leqslant \theta f(x) + (1-\theta) f(z) - \frac{\lambda}{2} \theta(1-\theta)\|x-z\|^2_2
$$

等价于

$$
(\nabla f(x) - \nabla f(z)) ^{T} (x-z) \geqslant \lambda \|x-z\|^2_2
$$

更一般的，如果一个函数是 $\lambda$-强凸的，$\lambda \in \mathbb{R}_{+}, 0<t<1$ 使得 $\forall x,z \in \Psi$ 都有

$$
f(tx+(1-t)z) \leqslant t f(x) + (1-t) f(z) - \frac{\lambda}{2} t(1-t)\|x-z\|^2_2
$$

如果函数 $f$ 二阶可导，那么可以用 Hessian 矩阵表示，即

$$
\nabla ^2 f(x) \geqslant \lambda I, x\in \text{dom } f
$$

## $l$-Lipschitz 连续

$\exists l \in \mathbb{R}_+$，使得 $\forall x, z \in \Psi$ 都有

$$
\| f(z) - f(x)\|_2 \leqslant l \|z - x\|_2
$$

## $L$-光滑 ($L$-smooth)

$\exists L \in \mathbb{R}_+$，使得 $\forall x, z \in \Psi$ 都有

$$
\| \nabla f(z) - \nabla f(x)\|_2 \leqslant L \|z - x\|_2
$$

$L$-光滑是比连续更强的一个条件，如果任何一个可微分函数的梯度是$L$-连续的，那么他是一个连续可微分函数。

如果一个函数是 $L$-光滑的，那么他满足下式：

$$
f(x) \leqslant f(y) + \nabla f(y)^T (x-y) + \frac{L}{2} \|x-y\|^2_2
$$

## References

- 《机器学习理论导引》- 周志华
- [斯坦福大学凸优化课程课件](https://www.stat.cmu.edu/~ryantibs/convexopt-F13/) - [4. Convexity (Barnabas)](https://www.stat.cmu.edu/~ryantibs/convexopt-F13/scribes/lec4.pdf)
- [EECS 598-006 Lecture Notes](https://web.eecs.umich.edu/~fessler/course/598/l/) - [03. Gradient-based methods](https://web.eecs.umich.edu/~fessler/course/598/l/n-03-gd.pdf)