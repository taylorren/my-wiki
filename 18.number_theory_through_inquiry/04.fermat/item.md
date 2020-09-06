---
title: 费马小定理和欧拉定理
visible: false
---

数学就是对熟悉的数学对象进行抽象、改变或一般化，然后看看会发生什么。抽象代数也是如此，其中会引入诸如“群”、“环”以及“域”的对象。我们在[第3章](../modulo)看到的模运算也是如此。

求解同余方程$ax\equiv b\pmod{n}$意味着找到一个数（$x$），它累加$a$次后对$n$的模是$b$。如果对$x$进行$a$次的自乘，我们就得到幂的求模。我们在本章将对幂的求模进行探索。

## 整数对$n$求模的秩

**练习4.1**：令$i=0, 1, 2, ..., 6$，在标准余数集中找出$2^i$对$7$的模。

*解*：

$2^0=1\equiv 1\pmod{7}\\2^1=2\equiv 2\pmod{7}\\2^2=4\equiv 4\pmod{7}\\2^3=8\equiv 1\pmod{7}\\2^4=16\equiv 2\pmod{7}\\2^5=32\equiv 4\pmod{7}\\2^6=64\equiv 1\pmod{7}$

**定理4.2**：令$a, n\in \mathbb{Z}, (a, n)=1$。那么$\forall j\in\mathbb{N}, (a^j, n)=1$。

*证明*：（略）。（提示：可以用到唯一分解。）

**定理4.3**：令$a, b, n\in\mathbb{Z}, n\gt 0, (a, n)=1$，那么$a\equiv b\pmod{n}\implies (b, n)=1$。

*证明*：

由$(a, n)=1$可知，存在$x, y$使得$ax+ny=1$。又由$a\equiv b\pmod{n}\implies a=kn+b$。因此$1=ax+ny=(kn+b)x+ny=knx+bx+ny=bx+(kx+y)n\implies (b, n）=1$。QED。

**定理4.4**：令$a, n\in\mathbb{N}$，那么存在$i, j\in\mathbb{N}, i\ne j$使得$a^i\equiv a^j\pmod{n}$。

*证明*：

$a^i$对$n$求模可以得到一个标准完全余数集，这个余数集中元素的个数是有限的，而$j$可以取无限多值，所以根据鸽笼原理，一定存在至少一个$j$使得$a^i\equiv a^j\pmod{n}$。QED。

我们来回顾一些老（[第一章](../divide)）的定理。

**定理4.5**（定理1.45）：令$a, b, c, n$为整数，$n\gt0$，如果$ac\equiv bc\pmod{n}, (c, n)=1$，则$a\equiv b\pmod{n}$。

下面这个定理告诉我们，如果我们取一个与模$n$互质的自然数，那么这个数进行幂运算后总归会得到对$n$求模为1。这个定理的一个自然推论是，之后这个数的幂运算对$n$求模就开始循环。

**定理4.6**：令$a, n\in\mathbb{N}, (a, n)=1$，那么存在一个$k\in\mathbb{N}\:s.t.\:a^k\equiv 1\pmod{n}$。

*证明*：

如果$a\equiv 1\pmod{n}$，定理成立。以下假定$a\not\equiv 1\pmod{n}$。

根据定理4.4，我们知道存在$i, j\:s.t.\:a^i\equiv a^j\pmod{n}\implies a^{i-j}a^j\equiv 1\times a^j\pmod{n}$。结合定理4.6，$(a, n)=1\implies (a^j, n)=1$。再根据定理4.5，得出$a^{i-j}\equiv 1\pmod{n}$。QED。

这个定理告诉我们，一个自然数如果和一个模数互质，那么一定存在一个最小的幂次，使得这个自然数的该次幂对该模数的模为1。这个概念很重要，值得被定义：

**定义**：令$a, n\in \mathbb{N}, (a, n)=1$。那么使得$a^k\equiv 1\pmod{n}$的最小的那个自然数$k$被称为$a$对$n$求模的秩（`order`），并记为$ord_n(a)$。

## 费马小定理

本节的终极定理是所谓的“费马小定理”（`Fermat's Little Theroem`）。它告诉我们，**一个数字的某次方会与1同模于某个素数**。

以下我们进行一些练习，来对这个定理有一些概念。

**练习4.7**：选择一些互质的数字$a, n$，并计算$ord_n(a)$。看看是否能进行一些猜想。

*解*：

1. $a=2, n=3$

$a^1=2\equiv 2\pmod{3}\\a^2=4\equiv 1\pmod{3}\implies ord_3(2)=2$。

1. $a=3, n=11$

$a^1=3\equiv 3\pmod{11}\\a^2=9\equiv 9\pmod{11}\\a^3=27\equiv 5\pmod{11}\\a^4=81\equiv 4\pmod{11}\\a^5=243\equiv 1\pmod{11}\implies ord_{11}(3)=5$。

在练习中，我们会注意到，在余数为1之前，对$n$的余数一定不会重复。这个观察直接导致如下定理：

**定理4.8**：令$a, n\in\mathbb{N}, (a, n)=1, k=ord_n(a)$，那么$a^1, a^2, ..., a^k$两两一定与$n$不同模，也就是$a_i\not\equiv a_j\pmod{n}, i\ne j$。

*证明*：

假定存在$a^i\equiv a^j, i\ne j\in [1, k]$。不妨假定$i\gt j$，我们得到$a^{i-j}\equiv 1$。所以$k=ord_n(a)=i-j$。但$i-j\lt k$，与题设矛盾。QED。

如果一个自然数取大于其秩$k$的幂，那么对$n$的模肯定不会不同于$[1, k]$之间幂对$n$的模。

**定理4.9**：令$a, n\in\mathbb{N}, (a, n)=1, k=ord_n(a)$。那么对于任何自然数$m$，$a^m$一定与$\{a^1, a^2, ..., a^k\}$中的某个数对$n$同模。

*证明*：（略。可以用到除法算法。）

**定理4.10**：令$a, n\in\mathbb{N}, (a, n)=1, k=ord_n(a)$。令$m$为任一自然数，那么$a^m\equiv 1\pmod{n} \iff k\mid m$。

*证明*：

由$a^m\equiv 1\pmod{n}$及除法算法可知：

$a^m=a^{qk+r}=a^{qk}a^r=(a^k)^qa^r\equiv 1^qa^r\equiv a^r\pmod{n}$。

所以，$a^r\equiv 1\pmod{n}, 0\le r\lt k$。但$k$已经是最小的那个幂指数（因为$k$是秩），所以$r=0\implies k\mid m$。反之，从$k\mid m$也可以得出$a^m\equiv 1\pmod{n}$。QED。

**定理4.13**：令$p$为整数，而$p\nmid a, a\in\mathbb{Z}$，也就是说$(a, p)=1$。那么$S=\{a, 2a, 3a, ..., pa\}$构成对$p$求模的完全余数集。

*证明*：

我们要用到`定理3.17`：

>令$n$为自然数。任何$n$个整数的集合$a_1, a_2, ..., a_n$，如果其中没有两个整数对$n$同模，那么它就是对$n$求模的完全余数集。

我们在集合$S$中任取两个元素$k_1a, k_2a$。考虑到$|k_1-k_2|\lt p$，而$p$是一个素数，所以$p\nmid (k_1-k_2)$，所以任意两个$k_i, k_j$都不会对$p$同模。再根据$(a, p)=1\implies k_ia\nmid k_ja\pmod{p}$。根据定理3.17，显然$S$构成了一个对$p$求模的完全余数集。

（**接近了！非常接近了！**）

**定理4.14**：令$p$为一个素数，而$a$是一个不能被$p$整除的整数（$(a, p)=1$），那么$a\times 2a\times 3a\times ... \times (p-1)a\equiv 1\times 2\times 3 \times ... \times (p-1) \pmod{p}$

*证明*：

根据`定理4.13`，$\{a, 2a, 3a, ..., pa\}$构成$p$的完全余数集，其中的$pa\equiv 0\pmod{p}$，所以集合$S=\{a, 2a, 3a, ..., (p-1)a\}$必然与$p$同模于$\{1, 2, ..., p-1\}$（虽然顺序不必如此）。

所以$a\times 2a\times 3a\times ... \times (p-1)a\equiv 1\times 2\times 3 \times ... \times (p-1) \pmod{p}$。QED。

从定理4.14出发经整理得到：

$a^{p-1}(p-1)!\equiv (p-1)!\pmod{p}\implies a^{p-1}\equiv 1 \pmod{p}$。

>$a^{p-1}\equiv 1 \pmod{p}$

这就是“费马小定理”。

以下两个定理是费马小定理的两个等价描述：

**定理4.15**：如果$p$是一个素数，而$a$是一个与$p$互质的整数，那么$a^{p-1}\equiv 1 \pmod{p}$。

**定理4.16**：如果$p$是一个素数，而$a$是一个与$p$互质的整数，那么$a^p\equiv a \pmod{p}$。

**定理4.17**：定理4.16和4.17是等价的，两者可以互相推导出另一个。

费马小定理告诉我们，一定存在一个数字（$p-1$）可以使得$a^{p-1}\equiv 1\pmod{p}$。联系到“秩”的定义，我们有下面的定理将这两者关联：

**定理4.18**：令$p$为一个素数，而$a$是一个整数，如果$(a,p)=1$，那么$ord_p(a)\mid p-1$。

*证明*：（略）

费马小定理有很多令人印象深刻的应用，其中之一就是让我们进行一些非常困难的模运算，可以让你的朋友们对你Orz不已。

**练习4.19**：进行下列运算

1. $512^{372}\pmod{13}$

首先，$(512, 13)=1$，根据费马小定理，$512^{12}\equiv 1\pmod{13}\implies 512^{372}=(512^{12})^{31}\equiv 1^{31}\equiv 1\pmod{13}$。

1. $3444^{3233}\pmod{17}$
1. $123^{456}\pmod{23}$
1. $314^{159}\pmod{31}$

费马小定理讲述了对素数求模的信息，但如果我们要对合数求模又该如何？

**定理4.21**：令$m, n\in\mathbb{N}, (m, n)=1, a\in\mathbb{Z}$。$x\equiv a\pmod{m} \& x\equiv a\pmod{n}\implies x\equiv a\pmod{mn}$。

*证明*：

由题设可以得到：$m\mid (x-a), n\mid(x-a)$。

从素数分解唯一性可知，$m=p_1^{q_1}p_2^{q_2}...p_m^{q_m}, n=r_1^{s_1}r_2^{s_2}...p_n^{s_n}$。根据题设，由于$(m, n)=1$，所以任意$p_i\ne r_j$。而既然$m\mid(x-a), n\mid(x-a)$，所以$(x-a)$中要同时包含$p_1^{q_1}p_2^{q_2}...p_m^{q_m}$以及$r_1^{s_1}r_2^{s_2}...p_n^{s_n}$。所以$mn\mid(x-a)\implies x\equiv a\pmod{mn}$。QED。

**练习4.22**：求$4^{72}$对$91(=7\times 13)$的模。

*解*：

首先注意到$91=7\times 13$，而$(7, 13)=1$，所以可以分别计算$4^{72}$对$7$和对$13$的模。

再根据费马小定理：

$4^6\equiv 1\pmod{7}\implies 4^{72}\equiv 1\pmod{7}$

$4^{12}\equiv 1\pmod{13}\implies 4^{72}\equiv 1\pmod{13}$

综上，$4^{72}\equiv 1\pmod{91}$。

**练习4.23**：找到一个自然数$k\lt 117$，使得$2^{117}\equiv k\pmod{117}$。

*解*：

注意到$117=3\times 3\times 13=9\times 13$，而$(9, 13)=1$。

2的各次幂对9和13的模如下：

幂次|模9|模13
:--:|:--:|:--:
1   |2   |2
2   |4   |4
3   |8   |8
... |... |...
12  |1   |1

所以$2^{12}\equiv 1\pmod{9}\equiv1\pmod{13}\implies 2^{12}\equiv 1\pmod{117}$。

因此，$2^{117}=(2^{12})^9\times 2^9\equiv 2^9=512\equiv 44\pmod{117}$。所以$k=44$。

## 费马小定理的另一种证明

和很多别的定理一样，费马小定理也有很多证明方法，其中之一就是用到所谓的“二项式定理”（`Binomial Theorem`）。首先引入定义。

**定义**：如果$n, m$为自然数，且$m\le n$，那么$\binom{n}{m}=\frac{n!}{m!(n-m)!}$。

我们特别约定$0!=1$。

**定理4.24**：令$a, b\in\mathbb{R}, n\in\mathbb{N}$，那么$(a+b)^n=\sum_{i=0}^n\binom{n}{i}a^{n-i}b^i$。

*证明*：

用数学归纳法很快可以证明。

**引理4.25**：如果$p$是一个素数，而$i$是一个小于$p$的自然数，那么$p\mid\binom{p}{i}$。

**证明**：

从$\binom{p}{i}$的定义可知：$\binom{p}{i}=\frac{p!}{i!\times (p-i)!}=\frac{p(p-1)(p-2)...(p-i+1)}{i!}$。注意，$p$是一个素数，而$i\lt p$，这表明$i!$中的每一项都不能整除$p$，也就是说$p$必然是$\binom{p}{i}$的倍数。QED。

我们可以用这个引理来证明费马小定理。此处略去。

## 欧拉定理和威尔逊定理

费马小定理的限制在于它要求模数为素数。如果我们取一个与模数不互质的数字，那么这个数字的任何幂次都不会与1同模于这个模数。所以我们还是要关注于模数互质的数字。

首先我们引入所谓的欧拉$\phi$函数，它是一个函数，用来计算有多少互质的数字。

**定义**：对于一个自然数$n$，欧拉$\phi$函数$\phi(n)$等于小于等于$n$且与$n$互质的自然数的数量。我们特别定义$\phi(1)=1$。

**练习4.27**：1/5/7/11都是小于12且与12互质的自然数，所以$\phi(12)=4$。试计算$\phi(7), \phi(15), \phi(21), \phi(35)$。

*解*：

$\phi(7)=6, \phi(15)=8, \phi(21)=12, \phi(35)=24$。

（网上有一些很贴心的小工具，可以帮助我们计算$\phi(n)$，比如[这里](http://www.javascripter.net/math/calculators/eulertotientfunction.htm)）。

让我们再回顾一些定理。

**定理4.28**：令$a, b, n\in\mathbb{Z}$，那么$(a, n)=1, (b, n)=1\implies (ab, n)=1$。

**定理4.29**：令$a, b, n\in\mathbb{Z}$，如果$a\equiv b\pmod{n}, (a, n)=1\implies (b, n)=1$。

**定理4.30**：令$a, b, c, n\in\mathbb{Z}, n\gt 0$。如果$ab\equiv ac\pmod{n}, (a, n)=1\implies b\equiv c\pmod{n}$。
