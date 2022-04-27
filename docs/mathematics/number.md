# 数论

## 中国剩余定理

$\left\{\begin{matrix}x\equiv a_1\bmod m_1\\ x\equiv a_2\bmod m_2\\ ... \\x\equiv a_n\bmod m_n\end{matrix}\right.$

其中 $m_i$ 两两互质

$M=\prod_{i=0}^{n}m_i, M_i=\frac{M}{m_i}$
$x=\sum_{i=0}^{n}a_i M_i M_i^{-1}\pmod {m_i}$

## 扩展中国剩余定理

模数不互质的时候
$x\equiv a_1\bmod m_1$
$x\equiv a_2\bmod m_2$

也就是
$x=k_1m_1+a_1=k_2m_2+a_2$
$\therefore k_1m_1=(a_2-a_1)+k_2m_2$

即 $k_1m_2\equiv (a_2-a_1)\bmod m_2$

让 $d=(m_1,m_2)$

即 $k_1\frac{m_1}{d}\equiv \frac{(a_2-a_1)}{d}\bmod {\frac{m_2}{d}}$

这样就可以得到$k_1=k' \frac{m_2}{d}+\frac{a_2-a_1}{d}(\frac{m_1}{d})^{-1}\pmod {\frac{m_2}{d}}$

令 $t=\frac{a_2-a_1}{d}(\frac{m_1}{d})^{-1}\pmod {\frac{m_2}{d}}$
带回原式得 $x=(k'\frac{m_2}{d}+t)m_1+a_1$

即可并成 $x=k'\frac{m_1m_2}{d}+tm_1+a_1$

即 $x\equiv a\bmod m$，其中$a=tm_1+a_1, m=\frac{m_1m_2}{d}$

## 欧几里得算法

Let $\gcd(a,b)=\left( a, b\right)=r$

Then $a=pr, b=qr, a \pmod b=a-kb=pr-kqr \mid r$
$\Rightarrow \gcd(a,b) = \gcd(b, a\%b)$

Then we prove that the gcd is max gcd.(Oh, my poor English.)
There are two ways to prove it.

First Way:

Presume that $r$ is the maxium $\gcd(a,b)$, and $r$ is different from $r'$ which is the maxium $\gcd(b, a\% b)$.

It means $r > r'$.

$$a=pr, b=qr, a\% b=pr-kqr$$
$$r\mid b, r\mid (a\% b), r>r'$$

so $r$ is maxium $\gcd(b, a\% b)$, it's against to the condition which we presumed.
so $r$ is the maxium $\gcd(a, b)$ and $\gcd(a, a\% b)$.

Second Way:

Let set $A$ be all factor of $\gcd(a, b)$, and let set $B$ be all factor of $\gcd(b, a\% b)$.

1. if $d\in A$, $a=pd, b=qd, a\% b=pd-kqd$
   so $d\mid (a\% b), d\in B$

2. if $d\in B$, $b=pd, a\% b=qd, a=kqd + pd$
   so $d \mid a, d\in A$

It means $A=B$, so $\gcd(a,b)_{max}=\gcd(b, a\% b)_{max}$

```python
def gcd(a, b):
    if(b==0):
        return a
    return gcd(b, a%b)
```

```c++
int gcd(int a, int  b) {
    return b?gcd(b, a%b):a;
}
```

## 扩展欧几里得算法

$$xa + by = r$$
$$x(\left \lfloor \frac{a}{b} \right \rfloor\times b + a\% b) + yb = r$$
$$(x\left \lfloor \frac{a}{b} \right \rfloor+y)b + xa\% b=r$$
$$\left\{\begin{matrix} x'=x\left \lfloor \frac{a}{b} \right \rfloor+y\\ y'=x\end{matrix}\right.\Rightarrow \left\{\begin{matrix}x=y'\\ y=x'-y'\left \lfloor \frac{a}{b} \right \rfloor\end{matrix}\right.$$

```python
def exgcd(a, b):
#    if(a<b):
#        a, b = b, a
    if(b==0):
        return 1, 0, a
    x1, y1, r = exgcd(b, a%b)
    x = y1
    y = x1-(a//b)*y1
    return x, y, r
```

```c++
int exgcd(int a, int b, int &x, int &y) {
    if(!b) {
        x=1, y=0;
        return a;
    }
    int d = exgcd(b, a%b, y, x);
    y-=(a/b)*x;
    return d;
}
```
