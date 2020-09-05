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