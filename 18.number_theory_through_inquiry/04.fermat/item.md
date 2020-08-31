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
