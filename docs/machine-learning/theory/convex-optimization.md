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

## $l$-Lipschitz 连续

$\exists l \in \mathbb{R}_+$，使得 $\forall x, z \in \Psi$ 都有

$$
\| f(z) - f(x)\|_2 \leqslant l \|z - x\|_2
$$

## $L$-光滑 ($L$-smooth)




## References

- 《机器学习理论导引》- 周志华
- [斯坦福大学凸优化课程课件](https://www.stat.cmu.edu/~ryantibs/convexopt-F13/)