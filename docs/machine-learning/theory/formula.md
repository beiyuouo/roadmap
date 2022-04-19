# 常用公式及约定

## Lp 范数

$$
    \|x\|_p = \left (\sum_{i=1}^n |x_i|^p \right )^{\frac{1}{p}}
$$

## 约定

- 通常 $\left < a,b\right >$ 表示 $a^{T}b$

## 交叉熵

$$
H(P, Q) = -\sum_{i=1}^n P_i \log Q_i
$$

二分类的交叉熵（BCE）就是

$$
H(P, Q) = -( P \log Q + (1-P) \log (1-Q))
$$

## DICE

DICE coefficient 是一种用于评估两个样本的相似性的度量函数，取值范围在 0 到 1 之间，取值越大表示越相似。DICE coefficient 定义如下:

$$
DICE = \frac{2 \|A \cap B\|}{\|A\| + \|B\|}
$$

DICE loss 则是 1 - DICE，即 DICE loss 取值范围在 0 到 1 之间，取值越小表示越相似。
