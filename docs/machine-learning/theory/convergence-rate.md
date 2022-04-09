# 收敛率

## 基本概念


## 梯度下降收敛分析 (Gradient Descent Convergence Analysis)

假设函数 $f: \mathbb{R}^{d}\to \mathbb{R}$ 是凸且可微分的，梯度满足 $l$-Lipschitz 连续，经过 $k$ 轮迭代，步长为 $t\leqslant \frac{1}{l}$，则解满足

$$
f(x^{k})-f(x^{\ast})\leqslant \frac{\|x^{(0)}-x^{\ast}\|}{2tk}
$$

收敛率为 $O(\frac{1}{k})$

*Proof*:

由 $f$ 满足 $l$-Lipschitz 连续，则 $\nabla f^{2} \preceq LI$，所以 $\nabla f^2 - LI$ 是一个负半正定矩阵。

对 $f$ 的二次展开式，有

$$
\begin{align*}
f(y) & \leqslant f(x) + \nabla f(x)^T (y-x) + \frac{1}{2} \nabla f^2(x) \|y-x\|^2_2 \\
& \leqslant f(x) + \nabla f(x)^T (y-x) + \frac{1}{2} l \|y-x\|^2_2
\end{align*}
$$

由梯度下降公式 $y=x - t\nabla f(x)$

$$
\begin{align*}
f(y) & \leqslant f(x) - \nabla f(x)^T t\nabla f(x) + \frac{1}{2} l \|t\nabla f(x)\|^2_2 \\
&= f(x) - t \| \nabla f(x) \|_2^2 + \frac{1}{2} lt^2 \|\nabla f(x)\|^2_2 \\
&= f(x) - (1-\frac{1}{2} lt) t \|\nabla f(x)\|_2^2
\end{align*}
$$

又 $t\leqslant \frac{1}{l}$，$-(1-\frac{1}{2}lt) \leqslant -(1-\frac{1}{2})=-\frac{1}{2}$，即

$$
f(y) \leqslant f(x) - \frac{1}{2} t \|\nabla f(x)\|^2_2
\tag{1}
$$

由 $f$ 是凸函数

$$
f(x^{\ast}) \geqslant f(x) + \nabla f(x)^{T} (x^{\ast}-x)  
$$

等价于 

$$
f(x) \leqslant f(x^{\ast}) + \nabla f(x)^{T} (x-x^{\ast})
$$

代入 $(1)$ 得

$$
f(y) \leqslant f(x^{\ast}) + \nabla f(x)^{T} (x-x^{\ast}) - \frac{1}{2} t \|\nabla f(x)\|^2_2
$$

即

$$
\begin{align*}
f(y)-f(x^{\ast}) & \leqslant \nabla f(x)^{T} (x-x^{\ast}) - \frac{1}{2} t \|\nabla f(x)\|^2_2 \\
&= \frac{1}{2t}\left (2t\nabla f(x)^{T}(x-x^{\ast}) -t^2 \|\nabla f(x)\|^2_2\right ) \\
&= \frac{1}{2t}\left (2t\nabla f(x)^{T}(x-x^{\ast}) -t^2 \|\nabla f(x)\|^2_2 + \|x-x^{\ast}\|_2^2 + \|x-x^{\ast}\|_2^2\right ) \\
&= \frac{1}{2t}\left (\|x-x^{\ast}\|_2^2 - \|x-x^{\ast}-t\nabla f(x)\|_2^2 \right ) \\
&= \frac{1}{2t}\left (\|x-x^{\ast}\|_2^2 - \|y-x^{\ast}\|_2^2 \right ) \\
\end{align*}
$$

做一个求和

$$
\begin{align*}
\sum_{i=1}^{k} f(x^{(i)}-f(x^{\ast})) & \leqslant \sum_{i=1}^{k} \frac{1}{2t}\left (\|x^{(i-1)}-x^{\ast}\|_2^2 - \|x^{(i)}-x^{\ast}\|_2^2 \right ) \\
&= \frac{1}{2t}\left (\|x^{(0)}-x^{\ast}\|_2^2 - \|x^{k}-x^{\ast}\|_2^2\right ) \\
&\leqslant  \frac{1}{2t} \|x^{0}-x^{\ast}\|_2^2
\end{align*}
$$

即

$$
\begin{align*}
f(x^{k})-f(x^{\ast}) &\leqslant \frac{1}{k}\sum_{i=1}^{k} (f(x^{i})-f(x^{\ast})) \\
&\leqslant \frac{\|x^{(0)}-x^{\ast}\|}{2tk} 
\end{align*}
$$


因此，为了使得 $f(x^{k})-f(x^{\ast}) \leqslant \epsilon $，需要进行 $O(\frac{1}{\epsilon })$ 次迭代。

## 次梯度方法收敛分析 (Subgradient Method Convergence Analysis)

次梯度方法是为了解决梯度下降中函数 $f$ 不可导的问题，只需要有一个次梯度 bound 住即可，当然对于 $f$ 可导的情况，次梯度方法也是可行的，这里为了方便表示，次梯度 $g$ 都写成了 $\nabla f$，以便于理解。

对于梯度下降，如果 $f$ 是凸的，有

$$
f(x^{\ast}) \geqslant f(x) + \nabla f(x)^{T} (x^{\ast}-x)
$$

变形即可得到

$$
\nabla f(x)^{T} (x-x^{\ast}) \geqslant f(x) - f(x^{\ast}) \geqslant 0
$$

计算 $x^{(k+1)}$ 和 $x^{\ast}$ 的距离

$$
\begin{align*}
\|x^{(k+1)}-x^{\ast}\|_2^2 &= \| x^{k}-x^{\ast} - \gamma \nabla f(x^{k})\|_2^2 \\
&= \|x^{k} - x\|_2^2 - 2\gamma \nabla f(x^{k})^{T}(x^{k}-x^{\ast}) + \gamma^2 \|\nabla f(x^{k})\|_2^2 \\

& \leqslant \|x^{k} - x\|_2^2 - 2\gamma (f(x^{k}) - f(x)) + \gamma^2 \|\nabla f(x^{k})\|_2^2

\end{align*}
$$

通常在次梯度方法中不会选择 fix 的步长，通常会用 
*Polyak step size*，即

$$
\gamma^k = \frac{f(x^{k}) - f(x^{\ast})}{\|\nabla f(x^{k})\|_2^2}
$$

所以上面的可以继续推导出

$$
\|x^{(k+1)}-x^{\ast}\|_2^2 \leqslant \|x^{k} - x^{\ast}\| - \frac{(f(x^{k}) - f(x^{\ast}))^2}{\|\nabla f(x^{k})\|_2^2}
$$

令 $B \geqslant \|\nabla f(x^{k})\|$，也就是被 bounded 住。

如果 $f$ 是凸的并且有 bounded gradient，那么收敛序列利用梯度下降和 Polyak step size 满足

$$
\min_{k\in [T]}f(x^{k})-f(x^{\ast}) \leqslant \frac{B\|x^{0}-x^{\ast}\|}{\sqrt{T+1}}
$$

*Proof:*

$$
\|x^{(k+1)}-x^{\ast}\|_2^2 \leqslant \|x^{k} - x^{\ast}\| -\frac{(f(x^{k}) - f(x^{\ast}))^2}{B^2}
$$

求和得

$$
\sum_{k=0}^{T} (f(x^{k})-f(x^{\ast}))\leqslant B^2(\|x^{0}-x^{\ast}\|_2^2-\|x^{k+1}-x^{\ast}\|_2^2)
$$

有因为左式 $\geqslant (T+1) \min_{k\in[T]} f(x^{k})-f(x^{\ast})$，稍微变形化简即可得到证明。

如果此时要使得 $f(x^{k})-f(x^{\ast}) \leqslant \epsilon$，需要进行 $O(\frac{1}{\epsilon^2})$ 次迭代，小于梯度下降的收敛速率。


## References

- 《机器学习理论导引》- 周志华
- [斯坦福大学凸优化课程课件](https://www.stat.cmu.edu/~ryantibs/convexopt-F13/) - [6. Subgradients (Ryan)](https://www.stat.cmu.edu/~ryantibs/convexopt-F13/scribes/lec6.pdf)
- [斯坦福大学凸优化课程课件](https://www.stat.cmu.edu/~ryantibs/convexopt-F13/) - [7. Subgradient method (Ryan)](https://www.stat.cmu.edu/~ryantibs/convexopt-F13/scribes/lec7.pdf)