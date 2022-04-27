# 概率论

## 概率分布

概率分布中，离散的概率分布叫**概率质量函数**，连续的叫**概率密度函数**

## 边缘概率

边缘概率也就是知道一个联合概率$P(x,y)$，求$P(x)$的过程，其实就是对另一个变量求和

$$
\forall x \in \text{x}, P(\text{x}=x)=\sum_{y}P(\text{x}=x,\text{y}=y)
$$

连续的自然积分就可以

$$
\int p(\text{x}=x,\text{y}=y)\mathrm{d}y
$$

## 条件概率

条件概率公式就是，联合概率，除上单个随机变量的概率

$$
P(\text{y}=y | \text{x}=x)=\frac{P(\text{y}=y, \text{x}=x)}{P(\text{x}=x)}
$$

## 链式法则

公式

$$
P(\text{x}^{(1)}, \cdots, \text{x}^{(n)})=P(\text{x}^{(1)})\Pi_{i=2}^{n}P(\text{x}^{(i)}|\text{x}^{(1)},\cdots,\text{x}^{(i-1)})
$$

那么这个是什么，那就是提出来一个$P(\text{x}^{(1)})$之后，所有变量都要以$\text{x}^{(1)}$和其之前的所有变量为条件的概率之积。<br/>
因为在逐步累乘的过程中，先前的所有都是已经发生的事实，因此直接乘上条件概率即可。

换一个思路，从条件概率公式入手的话，就会发现，如果把所有的条件概率都去掉，变成上下两个联合概率的形式，其实就是前一项的分母和后一项分子是相同的，越到最后其实就剩下了一个所有变量的联合概率了。

这个比较常用的就是联合概率的分解了比如$P(a,b,c)=P(a|b,c)P(b|c)P(c)$

## 独立性和条件独立性

如果两个随机变量的联合概率等于各自概率的乘积，那么两个变量独立，即

$$
\forall x \in \text{x},y\in \text{y}, p(\text{x}=x,\text{y}=y)=p(\text{x}=x)p(\text{y}=y)\Leftrightarrow \text{x}\perp \text{y}
$$

特殊的，如果有个条件变量，那么则变成

$$
\forall x \in \text{x},y\in \text{y},z\in \text{z}, p(\text{x}=x,\text{y}=y | z=\text{z})=p(\text{x}=x | \text{z}=z)p(\text{y}=y|\text{z}=z)\Leftrightarrow \text{x}\perp \text{y}|\text{z}
$$

## 期望、方差、协方差

期望反映的是随机变量的平均值
方差反映的是对随机变量采样时，随便变量的函数值呈现的差异
协方差反映的是两个变量线性相关性的前度及变量的尺度

期望的公式

$$
\mathbb{E}_ {\text{x}\sim P}[f(x)]=\sum_{x}P(x)f(x)
\mathbb{E}_ {\text{x}\sim p}[f(x)]=\int p(x)f(x)\mathrm{d} x
$$

期望是线性的

$$
\mathbb{E}_ {\text{x}}[\alpha f(x)+\beta g(x)]=\alpha\mathbb{E}_ {\text{x}}[f(x)]+\beta\mathbb{E}_ {\text{x}}[g(x)]
$$

概率论中的方差公式，注意这里外层的期望，其实就是随机变量与其均值之差平方的**平均值**(最后这个平均值值得注意一下，其实是有两个均值的)

$$
\text{Var}(f(x))=\mathbb{E}[(f(x)-\mathbb{E}[f(x)])^2]
$$

统计中的方差公式，其实就是离散的情况

$$
\sigma^2(x)=\frac{\sum_{i=1}^{n}(x_i-\bar{x})^2}{n}
$$

协方差公式

$$
\text{Cov}(f(x),g(y))=\mathbb{E}[(f(x)-\mathbb{E}[f(x)])(g(y)-\mathbb{E}[g(x)])]
$$

协方差矩阵是一个$n\times n$的矩阵

$$
\text{Cov}(\textbf{x})_ {i,j}=\text{Cov}(\text{x}_ i, \text{x}_ j)
$$

特殊的，

$$
\text{Cov}(\text{x}_ i, \text{x}_ i)=\text{Var}(\text{x}_ i)
$$

## 常见的概率分布

这里就不过多赘述了，一般表述的时候$p(x;a,b)$中，分号后面的$a,b$表示的是参数

### Bernoulli 分布

定义

$$
P(\text{x})=\left\{\begin{matrix}
1-\phi,&\text{x}=0 \\
\phi, &\text{x}=1
\end{matrix}\right.
$$

性质

$$
P(\text{x}=x)=\phi^{x}(1-\phi)^{1-x}
\mathbb{E}_ {\text{x}}[x]=0\cdot (1-\phi)+1\cdot \phi=\phi
\text{Var}_ {\text{x}}(\text{x})=(1-\phi)(0-\phi)+\phi(1-\phi)=\phi(1-\phi)
$$

### Multinoulli 分布

也叫多项式分布，就是 Bernoulli 分布的扩展

### Gasussian 分布

也叫高斯分布、正态分布

$$
\mathcal{N}(x;\mu,\sigma^2)=\frac{1}{\sqrt{2\pi\sigma^{2}}}\exp(-\frac{1}{2\sigma^2}(x-\mu)^2)
$$

标准正态分布中，$\mu=0,\sigma=1$

一种常用的替换方法是$\beta^{-1}=\sigma^2$，便于控制参数

> 挖个坑，求正态分布的积分，和后面提到的先验知识量最小

根据**中心极限定理**，正态分布更贴近真实的分布
另外，在具有相同方差的所有可能的概率分布中，正态分布在实数上具有最大的不确定性，因此，我们可以认为正态分布是对模型加入的先验知识量最小的分布

多维正态分布

$$
\mathcal{N}(\mathbf{x};\mathbf{\mu},\mathbf{\Sigma})=\frac{1}{\sqrt{(2\pi)^n\det{(\mathbf{\Sigma})}}}\exp(-\frac{1}{2}(\mathbf{x}-\mathbf{\mu})^{T}\mathbf{\Sigma}^{-1}(\mathbf{x}-\mathbf{\mu}))
$$

## 结构化概率模型 | 图模型

在有向图中，如果$a$影响$b$的取值，则从$a$到$b$画一条有向的线。跟确切的来说，有向模型对于分布中的每一个随机变量$x_{i}$，都包含一个影响因子，这个组成$x_i$条件概率的影响因子被称作为$x_i$的父节点，记为$P_{a_{G}(x_i)}$

$$
p(x)=\Pi_{i}p(x_i | P_{a_{G}(x_i)})
$$

## References

- 《深度学习》，Ian Goodfellow,Yoshua Bengio,Aaron Courville，人民邮电出版社
