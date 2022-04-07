# 收敛率

## 基本概念


## 梯度下降收敛分析 (Gradient Descent Convergence Analysis)

假设函数 $f: \mathbb{R}^{d}\to \mathbb{R}$ 是凸且可微分的，梯度满足 $l$-Lipschitz 连续，经过 $k$ 轮迭代，步长为 $t\leqslant \frac{1}{l}$，则解满足
$$
f(x^{(k)})-f(x^{\ast})\leqslant \frac{\|x^{(0)}-x^{\ast}\|}{2tk}
$$

收敛率为 $O(\frac{1}{t})$

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
&= \frac{1}{2t}\left (\|x^{(0)}-x^{\ast}\|_2^2 - \|x^{(k)}-x^{\ast}\|_2^2\right ) \\
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



## References

- 《机器学习理论导引》- 周志华
- [斯坦福大学凸优化课程课件](https://www.stat.cmu.edu/~ryantibs/convexopt-F13/)