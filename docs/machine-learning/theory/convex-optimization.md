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

### 一阶条件

假设 $f$ 可微，函数 $f$ 是凸函数的充要条件是 $\text{dom} f$ 是凸集且 $\forall x,y \in \text{dom} f$，下式成立

$$
f(y) \leqslant f(x) + \nabla f(x)^{T} (y-x)
$$

如果添加条件 $x\neq y$，则取不到等号。

*Proof:*

对任意 $0 < t \leqslant 1$，$x + t(y-x) \in \text{dom} f$，由函数 $f$ 的凸性可得

$$
f(x+t(y-x)) \leqslant (1-t)f(x) + tf(y)
$$

两边同时除 $t$ 可得

$$
f(y) \geqslant f(x) + \frac{f(x+t(y-x))-f(x)}{t}
$$

令 $t \to 0$，对右边分式应用洛必达法则，即可得到

$$
f(y) \geqslant f(x) + \frac{\nabla f(x+t(y-x))(y-x)}{1}
$$

变形化简即可得证必要性。

充分性：

应用不等式两次可得，

$$
\begin{align*}
f(x) \geqslant f(z) + f'(z)(x-z) & (1)\\ f(y) \geqslant f(z) + f'(z)(y-z) & (2)\\
\end{align*}
$$

其中，$x\neq y, 0\leqslant \theta \leqslant 1,z=\theta x + (1-\theta) y$， 令$\theta (1) + (1-\theta) (2)$，稍微化简下得到

$$
\theta f(x) + (1-\theta) f(y) \geqslant f(z)
$$

即可证明凸性。

更一般的，可以通过设 $g(t) = f(tx + (1-t)y)$，对其求导，假设是凸的，$g'(t)=\nabla f(tx+(1-t)y)^{T}(x-y)$，则可得 $g(1)\leqslant g(0) + g'(0)$，记得得到不等式。

最后再来证明 $g$ 的凸性，有了上述结论，设置两个 $t$，即可证明凸性。

### 二阶条件

假设 $f$ 二阶可微，函数 $f$ 是凸函数的充要条件是，其 Hessian 矩阵 $H$ 是半正定矩阵，即对$\forall x \in \text{dom} f$

$$
\nabla ^2 f(x) \succeq 0
$$

*Proof:*

~~[留坑]~~


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
\nabla ^2 f(x) \succeq \lambda I, x\in \text{dom } f
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
- 《凸优化》 - Stephen Boyd