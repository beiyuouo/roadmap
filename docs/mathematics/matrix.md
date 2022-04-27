# 矩阵论

这里主要是矩阵微积分，写的并不全，随便挑选了几个性质证明了一下，而且并不是非常严谨的证明，详细内容请参考[1].

这里强烈推荐一下[4]中的关于矩阵微分的 PPT，比较容易理解，再此之后有[5]和对应的[arXiv 版本](https://arxiv.org/abs/1802.01528)。

在矩阵微分中，其实是有两种形式，一种是基于分子的，一种是基于分母的[4]，但是大部分文献中都是没有说明，默认是基于分子的，即分母在求偏导时会转置。

# Basic

1. $(AB)^{-1}=B^{-1}A^{-1}$
   _Proof_. $(AB)^{-1}(AB)=I=A^{-1}A=B^{-1}A^{-1}AB \Rightarrow(AB)^{-1}=B^{-1}A^{-1}\text{A,B可逆}$

2. $(A^{T})^{-1}=(A^{-1})^{T}$

   _Proof_. $(AA^{-1})^{T}=(A^{-1})^{T}A^{T}=I=(A^{T})^{-1}A^{T} \text{A可逆}$

# Differential of Matrix

> 实际上，矩阵的微分就是把变量的微分写成矩阵的形式而已，下面摘录几个我觉得当时想了挺久或者觉得比较重要的公式。

1. $\partial(X^{-1})=X^{-1}\partial (X)X^{-1}$

   _Proof_. $$\partial(X^{-1}X)=\partial(I)=0$$
   $$\partial(X^{-1}X)=\partial(X^{-1})X+X^{-1}\partial (X)$$
   $$\Rightarrow \partial(X^{-1})X+X^{-1}\partial(X)=0$$
   $$\Rightarrow \partial(X^{-1})=-X^{-1}\partial(X)X^{-1}$$

矩阵微分依然满足求导中的规则，但在一下情况下有所变化

2. $\frac{\partial \text{u}^{T}}{\partial \text{x}}=(\frac{\partial \text{u}}{\partial \text{x}})^{T}$

   我觉得，这个我当时挺难能理解的，如果按照之前的理论，这个求出来的偏导应该是一个行向量，但其实他求出来还是一个矩阵，因为实际在做的时候，其实是忽视了分母的形式，而是一个未进行转置的分母列向量来求的。但是这确实是这么定义的，不然后面很多公式其实是没法算出来的...我就在这卡了好久，不知道自己想的对不对了

3. $\frac{\partial \text{x}}{\partial \text{x}}=\frac{\partial \text{x}^{T}}{\partial \text{x}} =I$

   按照上面一个公式，这个很容易就推导出来了。

4. $\frac{\partial{a^{T}\text{x}}}{\partial{\text{x}}}=\frac{\partial{\text{x}^{T}a}}{\partial{\text{x}}}=a^{T}$

   这里需要注意的就是顺序，首先$a^{T}\text{x}$是一个标量，所以$a^{T}\text{x}=(x^{T}a)^{T}=\text{x}^{T}a$

5. $\frac{\partial{(\text{x}^{T}a)^{2}}}{\partial{\text{x}}}=2\text{x}^{T}a\text{x}$

   这里其实就是一个简单的复合函数求导了，先整体求导得到$2\text{x}^{T}a$，在做一步$\frac{\partial{\text{x}^{T}a}}{\partial {\text{x}}}$就可以了。

6. $\frac{\partial{\text{x}^{T}A\text{x}}}{\partial \text{x}}=\text{x}^{T}(A+A^{T})$

   ~~说实话这个我也想了挺久~~

   先把分子$\text{x}^{T}A\text{x}$看成$\text{x}^{T} \times A\text{x}$（或者你把$A$放在左边其实也是一样的），这样就是导的乘积，注意不要调换矩乘的顺序

$$
\frac{\partial{\text{x}^{T}A\text{x}}}{\partial \text{x}}=(A\text{x})^{T}\frac{\partial{\text{x}^{T}}}{\partial \text{x}}+\text{x}^{T}\frac{\partial{A\text{x}}}{\partial \text{x}}=\text{x}^{T}A^{T}+\text{x}^{T}A=\text{x}^{T}(A+A^{T})
$$

    注意这里其实还涉及一个公式$\frac{\partial{u^{T}v}}{\partial \text{x}}=u^{T}\frac{\partial v}{\partial \text{x}}+v^{T}\frac{\partial u}{\partial \text{x}},u=u(x),v=v(x),u,v\text{ is vector}$，这里出现这样的公式的结果主要是因为上面是一个标量，最后求出来的应该是一个行向量，所以才需要加上转置保证结果的形式正确。

> 这里我插一嘴，我觉得这个结果的形状真的是玄学，虽然你都可以通过展开公式进行证明，但是都感觉怪怪的...

7. $\frac{\partial a^{T}Xb}{\partial X}=ba^{T}$

8. $\frac{\partial a^{T}X^{T}b}{\partial X}=ab^{T}$

后面关于 Trace 的用到了再搞。

# Reference

- [1] Petersen, K.B. and Pedersen, M.S., 2008. [The matrix cookbook](https://ece.uwaterloo.ca/~ece603/MISC/matrixcookbook.pdf). Technical University of Denmark, 7(15), p.510.
- [2] [Wikipedia - Matrix Calculus](https://en.wikipedia.org/wiki/Matrix_calculus)
- [3] CS289, Berkeley, [http://people.eecs.berkeley.edu/~jrs/189/](http://people.eecs.berkeley.edu/~jrs/189/)
- [4] CS5240, NUS, [https://www.comp.nus.edu.sg/~cs5240/index.html](https://www.comp.nus.edu.sg/~cs5240/index.html)
- [5] [https://explained.ai/matrix-calculus/](https://explained.ai/matrix-calculus/)
- [6] CPSC540, UBC, [https://www.cs.ubc.ca/~schmidtm/Courses/540-W18/](https://www.cs.ubc.ca/~schmidtm/Courses/540-W18/)
- [7] [http://www.matrixcalculus.org/](http://www.matrixcalculus.org/)
