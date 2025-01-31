---
title: 素数时间
visible: false
---

这一章我们要讲述将自然数“分成”各个部分。

`1`是所有自然数的基本组成元素。所有自然数都不过是若干个`1`加起来得到的结果。这个性质是归纳过程的核心。

但是通过“加法”得到数字比较慢，有没有比较快的方法？我们马上会想到乘法，但马上有一个问题自然而然地出现：**有没有什么自然数无法通过两个较小的数相乘而得到呢？**这类数就是所谓的素数（或者叫质数，prime numbers）。[^1]

数论中的一个主要核心就是对素数的研究。我们将证明，任何大于1的自然数要么是素数，要么可以表示为素数的乘积（BTW，这样的数被称为合数）。素数是所有自然数的构建基石。

我们还将证明，素数有无穷多个，但它们在自然数中的分布如何？比一个自然数$n$小的素数有几个？如何找到它们？又如何使用它们？……从古到今，这些问题驱动了数论的发展并将我们引向众多美妙的数学发现。

**定义**：自然数$p\gt 1$为素数，当且仅当$p$不是小于$p$的自然数的乘积。

**定义**：自然数$n$为合数，当且仅当$n$是小于$n$的自然数的乘积。

**定理2.1**：$\forall n \in N, n\gt1, \exists p, s.t\: p|n$。[^2]

**练习**：试着写下小于100的所有素数。不要用计算器或其他的帮助。

**定理2.3**：自然数$n$为素数，iff对于所有的素数$p\lt \sqrt n$，$p\nmid n$[^3]

**练习**：用上面的定理证明101是个素数。

寻找下一个素数永远是一个正在进行的任务，因为素数在通讯加密方面具有不可替代性。目前数学家找到的最大素数是$2^{77,232,917}-1$，一个23,249,425位数，同时也是一个梅森素数。[^4]

数学家有很多先进的方式来找素数，不过现在我们要看一种古老的方式，它可以追溯到[埃拉托色尼](https://en.wikipedia.org/wiki/Eratosthenes)（公元前三世纪的希腊天文学家、数学家和地理学家）发明的筛法（Sieve of Eratosthenes）。

筛法的过程非常直观简单，简述如下（假定我们要求100以内的素数）：

1. 在一张纸上写下1-100这100个数字。把它们写成一个10*10的矩阵可能好一些。
2. 把`2`圈出来，这是第一个素数。
3. 将所有`2`的倍数划掉。
4. 把`3`圈出来，这是下一个没被划掉的数字，也是下一个素数。
5. 将所有`3`的倍数划掉。
6. 圈出那个没被划掉的最小的数（下一个素数），并把它的倍数划掉。重复这个过程。

大家可以想一想，为什么经过这些步骤后，可以得到小于100的所有素数列表呢？

我自己做了一个这样的练习，截图如下（我用Excel做的，绿色是圈出来的、“留下来”的素数，其他的是合数）：

![Primes less than 100](./primes_less_than_100.jpg)

**练习**：对于自然数$n$，定义$\pi (n)$为小于等于$n$的素数的数量。

1. 做出$n=1, 2,..., 100$时$\pi (n)$的图像。
2. 做出一个有关$\pi (n) \sim n$之间关系的猜想。特别地，$\frac{\pi (n)}{n}$是一个递增函数还是递减函数？会不会存在一个极限呢？

高斯提出，$\pi (n) \sim \frac{n}{ln(n)}$，然后进一步精细地定义为$\pi (n) \sim Li(n)$，也就是$\lim_{n\to\infty}\frac{\pi (n)}{Li(n)}=1$，而其中$Li(n)=\int_2^n\frac{dx}{ln(x)}$。（参见[《上帝创造整数：高斯》](../../gcti/gauss)）

## 算术基本定理

在数学领域中，数学家很少给一个定理加上“基本”找个前缀，因为这样的定理太少。我们一生之中可能也只会碰到其中的一两个，比如：[代数基本定理（Fundamental Theorem of Algebra）](https://en.wikipedia.org/wiki/Fundamental_theorem_of_algebra)，[微积分基本定理（Fundamental Theorem of Calculus）](https://en.wikipedia.org/wiki/Fundamental_theorem_of_calculus)等。

我们很有幸地马上开始接触一个基本定理：**[算术基本定理（Fundamental Theorem of Arithmetic）](https://en.wikipedia.org/wiki/Fundamental_theorem_of_arithmetic)**。

这个定理分两部分，一部分证明存在性，一部分证明唯一性。

**定理2.7（算术基本定理之存在性部分）**：所有大于1的自然数要么是一个素数，要么可以表示为素数的有限乘积。也就是说，对于大于1的自然数，存在各异的素数$p_1, p_2, ..., p_m$和一系列自然数$r_1, r_2, ..., r_m$，s.t$n=p_1^{r_1}p_2^{r_2}...p_m^{r_m}$。

*证明*：（略）。提示：可以用数学归纳法。

**引理2.8（欧几里得引理，用于证明唯一性）**：令$p, q_1, q_2, ..., q_n$为素数，而$k$为一个自然数，s.t $pk=\prod_{i=1}^n q_i$，那么$p=q_i$对于某个$i$成立。

*证明*：（略）。

**定理2.9（算术基本定理之唯一性部分）**：令$n$为自然数，令$\{p_1, p_2, ..., p_m\}$以及$\{q_1, q_2, ..., q_m\}$是素数的集合，且$p_i\ne p_j, q_i\ne q_j (i\ne j)$。令$\{r_1, r_2, ..., r_m\}$以及$\{t_1, t_2, ..., t_m\}$是自然数的集合，s.t $n=\prod_{i=1}^{m}p_i^{r_i}=\prod_{j=1}^{s}q_j^{t_i}$。那么，$m=s,\:\{p_1, p_2, ..., p_m\}=\{q_1, q_2, ..., q_s\}$。也就是说，素数集合相等，但顺序不一定相同，也就是$p_i$不一定等于$q_i$。但如果$p_i=q_j$，那么$r_i=t_j$。换句话说，如果我们将一个自然数表述为一系列各异的素数的乘积，那么表达方式是一致的，而只有素数出现的次序会不同。

*证明*：假定$n=p_1p_2...p_k=q_1q_2...q_l$。我们这里不写出指数项是因为我们将列出所有的（包括重复的）素数因子，比如对于$2^2$我们写成$2*2$。这两个素数集合的乘积是相同的，根据引理2.8，我们可以得到：任意一个乘积中的因子可以整除另一个乘积，也就是$\forall p_i\mid q_1q_2...q_l, 1\le i \le k$。根据欧几里得引理，$\exists p_i=q_j, 1\le j\le l$。在$p$和$q$的乘积中约去这个公因子并重复这个过程。

如果$k\ne l$，那么我们要么得到$p_{i_1}p_{i_2}...p_{i_r}=1\:(k\gt l)$，要么得到$q_{j_1}q_{j_2}...q_{j_s}=1\:(k\lt l)$。但是由于所有的$p, q$都是一个素数，素数最小就是2，所以其乘积不可能等于1。因此$k=l$。这两种乘积表达式具有相同数量（但不一定各异）的素数因子，而我们的消去过程消去的都是相等的质因子。因此这两种表达是相同的，只是质因子顺序有可能不同。QED。

结合定理2.8和2.9，我们得到完整的**算术基本定理**：

>所有大于1的自然数要么是素数，要么可以表述为有限素数的乘积且这样的表述是唯一的而只有因子排列顺序的差异。

考虑一下我们对素数的定义中，刻意排除了`1`。如果`1`被认定为一个素数，算术基本原理还能成立吗？

**练习2.10**：将$n=12!$表示为一系列素数的乘积。

**练习2.11**：对于$25!$，确定它在末位有几个0？

*解*：素数相乘中，只有$2*5=10$能在乘积的末位加上1个0。对于$25!$，将其进行因子分解后，可以看到具有$5$这个因子的只有$5, 10, 15, 20, 25$这五个数，一共提供了6个5，具有$2$因子的数量肯定比6多，所以，$25!$的末位有6个0。

从**算术基本定理**，我们可以定义，如果$p_i$得到排序，s.t $p_1\lt p_2 \lt...\lt p_m$，那么我们说$p_1^{r_1}p_2^{r_2}...p_m^{r_m}$是自然数$n$的唯一素数分解式。

## 算术基本定理的应用

**定理2.12**：令$a, b$是大于1的自然数，而且$a, b$可以分别用唯一素数分解式表达为：$p_1^{r_1}p_2^{r_2}...p_m^{r_m}$和$q_1^{t_1}q_2^{t_2}...q_m^{t_m}$。那么$a\mid b\iff \forall i\le m, \exists j\le s, s.t\:\:p_i=q_j, r_i\le t_j$。

*证明*：

（充分性）假定$a\mid b$，那么$b=ak$。根据算术基本定理，等式两边的素数分解式是一致的。因此，对于$i\in [1, m]$，$a$中出现的$p_i^{r_i}$和$k$中出现的$p_i^{u_i}$要与$b$中的某个$q_j^{t_j}$对应。因此一定存在$q_j=p_i$，而且$r_i+u_i=t_j$，也就是$r_i\le t_j$。

（必要性）假定对于所有的$i\le m$，存在$j\le s, s.t\:\:p_i=q_j, r_i\le t_j$，那么对于$b$中的每个素数因子项，可以将其改写成$p^r*q^t$。其中的$p^r$与$a$的分解式一一对应，所有的$q^t$项相乘会得到一个数（$\ge 1$），这个数就是$k$。所以$b=ak \implies a\mid b$。

**定理2.13**：令$a, b$为自然数，且$a^2\mid b^2$，那么$a\mid b$。

*证明*：

根据算术基本定理，$a, b$有各自的唯一分解式：

$a=\prod_{i=1}^{m}p_i^{q_i}, b=\prod_{j=1}^{n}r_j^{s_j}$

因此$a^2=\prod_{i=1}^{m}p_i^{2q_i}, b^2=\prod_{j=1}^{n}r_j^{2s_j}$。根据定理2.12，我们知道，因为$a^2\mid b^2$，所以$2r_i\le 2s_j \implies r_i\le s_j$。再根据定理2.12，得到$a\mid b$。QED。

素数唯一分解式可以帮助我们去找两个自然数的最大公约数和最小公倍数。例如：

**练习2.14**：找到$(3^{14}*7^{22}*11^5*17^3, 5^2*11^4*13^8*17)$。

*解*：观察这两个数的素数唯一分解式，可以看到其中唯一相同的部分是$11^4$和$17$。所以这两个数的GCD就是$11^4*17$。

**练习2.15**：找到上面这两个数的lcm。

*解*：我们知道，$lcm(a, b)=\frac{ab}{gcd(a,b)}$。

所以上面两数的$lcm=\frac{(3^{14}*7^{22}*11^5*17^3)*(5^2*11^4*13^8*17)}{11^4*17}=3^{14}5^27^{22}11^513^817^3$。

**定理2.18**：若$a_1, a_2, ..., a_{n+1}$是小于等于$2n$的数，那么在这些数中一定存在一对数字，比如说$a_i, a_j\:(i\ne j)$，使得$a_i\mid a_j$。

*证明*：每个$a_i$都可以写成$a_i=2^{\alpha_i}*\beta_i$，其中$\alpha_i$为0或自然数，而$\beta_i$是一个奇数。$\beta_i$有$n+1$个，但取值范围只有$n$个，也就是$1, 3, 5, ..., 2n-1$。根据鸽笼原理，对某个$i, j$而言，一定存在$\beta_i=\beta_j$。对应的，$\frac{a_i}{a_j}=2^{\alpha_i-\alpha_j}$，可以合理假定$\alpha_i\ge \alpha_j$（如果不是，则交换$i, j$），由此$a_j\mid a_i$。QED。

**定理2.19**：不存在任何自然数$m, n$，s.t $7m^2=n^2$。

*证明*：

对于任何自然数$m, n$而言，它们的分解式是唯一的。特别地，我们关注它们分解式中7的指数，令其为$p, q$。那么在$m^2, n^2$中，7的指数就是$2p, 2q$。注意，等式两边7的指数的奇偶性肯定不会一样：必然一个是偶数一个是奇数。所以等式不能成立。QED。

也许有人会说，这个证明太麻烦。我知道$\sqrt 7$是个无理数，所以$\sqrt 7m \ne n$。所以证毕。但是，**基于我们现在的知识**，我们还没法证明$\sqrt 7$是无理数——因为我们还没有给出有理数、无理数的定义！同学，你超前了！

**定理2.20**：不存在任何自然数$m, n$，s.t $24m^3=n^3$。

*证明*：（略）。提示：用两边3的指数项来得出矛盾。

用分解式的唯一性可以来证明一些牵涉到有理性/无理性的有趣问题。

**定义**：有理数（`rational number`）是这样的数字，它可以表示为$\frac{a}{b}$，其中$a, b$为整数且$b\ne 0$。

**定义**：不是有理数的数字就是无理数（`irrational number`）。

**练习2.21**：证明$\sqrt 7$是无理数。

**练习2.22**：证明$\sqrt{12}$是无理数。

**练习2.23**：证明$7^{\frac{1}{3}}$是无理数。

有了算术基本定理，我们可以回头来证明[第一章](../divide)中的一些定理。

**定理2.25**（定理1.42）：令$a, b, n$为整数，如果$a\mid n, b\mid n, (a,b)=1$，则$ab\mid n$。

*证明*：

在第一章中我们没有用算术基本定理来证明。现在我们用算术基本定理来证明。

首先排除一些特殊情况。

1. 如果$a=0$或者$b=0$，所以$ab=0$，0可以整除任何不为0的整数，而$a\mid n$以及$b\mid n$已经表明$n$不能为0，所以$ab=0\mid n$。
2. 如果$a=1, b\ge 1$，那么$b\mid n \implies ab\mid n$。
3. 如果$b=1, a\ge 1$，那么$a\mid n \implies ab\mid n$。

所以我们考虑一般情况，也就是$a\ge 2, b\ge 2$。

首先，由于$a\mid n, b\mid n$，所以$a, b$的分解式中的每一项都在$n$中出现，并且$n$中对应素数因子的指数不会小于$a, b$中对应的素数因子的指数。

但由于$(a, b)=1$，因此$a, b$没有相同的素数因子，也就是说不存在一个素数$p, s.t. p\mid a, p\mid b$。$ab$的分解式就是$a, b$分解式的乘积。所以$ab$中的每个素数因子也都出现在$n$中，且$n$中对应的素数因子的指数不会小于$ab$中对应的素数因子的指数。因此$ab\mid n$。QED。

**定理2.26**：令$p$为一个素数而$a$为一个整数，那么$p\nmid a\iff\: (a,p)=1$。

*证明*：（略）

**定理2.27**：令$p$为一个素数，而$a,b$为整数。如果$p\mid ab$，那么$p\mid a$或者$p\mid b$。

注意，如果$p$不是一个素数，那么这个定理不一定成立。比如：$9\mid (6*12)$，但是9既不整除6，也不整除12。

*证明*：

出于分解式的唯一性，$ab$的分解式一定可以写成$\prod_{i=1}^nq_i^{a_i+b_i}$的形式，其中的$q_i$是各个素数因子，而$a_i, b_i$则是它们在$a, b$的分解式中的指数项。因为$p\mid ab$，所以$\exists i, s.t\:\: p=q_i$。而$q_i$要么在$a$、要么在$b$的分解式中（也可以同时存在），但无论如何，总有$p\mid a$或者$p\mid b$。QED。

下面这些定理讨论了最大公约数和别的数学运算之间的关系，它们都可以用算术基本定理以及我们在第一章中学到的定理进行证明。

**定理2.28**：令$a, b, c$为整数，如果$(b, c)=1$，那么$(a, bc)=(a,b)*(a, c)$

*证明*:

我们借助定理1.54，即$(ka,kb)=k(a, b)$。

$(a, b)*(a, c)=(a(a, c), b(a,c))=(aa, ac, ab, bc)=(a(a, b, c), bc)$，由$(b, c)=1\implies (a, b, c)=1$，所以$(a, b)*(a, c)=(a, bc)$。

另外一个证明请自行完成。

**定理2.29**：令$a, b, c$为整数，若$(a, b)=1, (a, c)=1$，那么$(a, bc)=1$。

*证明*：

由题设，可有：$ax+by=1 \implies by=1-ax$以及$ax'+cy'=1 \implies cy'=1-ax'$。两式左右各自相乘得到：

$bc(yy')=(1-ax)(1-ax')=1-ax-ax'+a^2xx'$

整理后可以得到：

$a(x+x'-axx')+bc(yy')=1$$

QED。

**定理2.30**：若$(a, b)=d$，那么$(\frac{a}{d}, \frac{b}{d})=1$。

*证明*:

令$(\frac{a}{d}, \frac{b}{d})=x$，于是有：$\frac{a}{d}=xm, \frac{b}{d}=xn \implies a=xmd, b=xnd$。因此说，$a, b$都有一个公因子是$xd$。但既然$d$已经是$a, b$的最大公约数，所以$x$只能等于1，也就是说$\frac{a}{d}, \frac{b}{d}$的最大公约数是1。QED。

**定理2.31**：令$a, b, u, v\in Z$，如果$(a, b)=1, u\mid a, v\mid b$，那么$(u, v)=1$。

*证明*：

由$(a, b)=1\implies ax+by=1$。又因为$u\mid a, v\mid b\implies a=k_1u, b=k_2v\implies u*k_1x+v*k_2y=1$。QED。

素数问题中最基本的一个问题是：**素数到底是不是无限多个？**我们将证明素数有无限多个。

## 素数的无限性

**定理2.32**：对于所有的自然数，$(n, n+1)=1$。

*证明*：

因为有$(-1)n+1(n+1)=1$，所以$(n, n+1)=1$，也就是说任意两个相邻的自然数一定互质。

**定理2.33**：令$k$为一个自然数，一定存在一个自然数$n$（它比$k$大很多），s.t 在$\gt 1$和$\lt k$的区间里，不存在任何自然数使之能整除$n$。

*证明*：

我们可以构造这么一个数字：$n=k!+1$。我们可以声明在2到$k$的区间中的任何一个数字$m$都无法被$n$整除。否则，如果$m\mid n$，那么$m\mid k! \implies m\mid (n-k!) \implies m\mid 1 \implies m=1$。和$m\in [2, k]$矛盾。QED。

**定理2.34**：令$k$为一个自然数，那么存在一个素数大于$k$。

*证明*：（略）

**定理2.35**：素数有无限多个。

*证明*：（略）

**定理2.37**：如果$r_1, r_2, ..., r_m$是自然数，且它们对4的模都等于1，那么这些自然数的乘积$r_1r_2...r_m$对4的模也是1。

*证明*：

$r_i\equiv 1\pmod{4} \implies r_i=4k_i+1$，因此$r_1r_2...r_m=(4k_1+1)(4k_2+1)...(4r_m+1)=4x+1$，也就是乘积对4的模也是1。QED。

**定理2.38**：存在无数多个形如$4k+3$的素数。

*证明*：

我们假定只有有限个形如$4k+3$的素数，它们是$S=\{p_1, p_2, ..., p_n\}$。

构造一个$n=4p_1p_2...p_k-1$。这是一个对4的模为3的数字。

首先，所有的$p_i \nmid n$。因为$p_i\mid (n+1)$，而根据定理2.32，两个相邻的自然数互质，既然$n+1$包含了所有$p_i$作为质因子，$n$就不能包括$p_i$为质因子。所以$n$的质因子不在$S$中。

同时，$n$是个奇数，所以它的质因子不能是偶数。

$n$的质因子根据对4求模的结果可以分为四种，我们已经排除了两种（因为$n$不是偶数），还有两种：形如$4k+3$或者$4k+1$。如果$n$的质因子形如$4k+1$，那么根据定理2.37，$n$也一定形如$4k+1$，但显然不是。

所以，$n$要么本身就是一个形如$4k+3$的素数，要么其中一定存在一个质因子$p$，s.t $p\equiv 3\pmod{4}$，但它不是$S$中的任何一个。所以，我们的假设不成立，也就证明存在无限多个形如$4k+3$的素数。QED。

我们还能证明类似的定理吗，还能不能证明存在无数多个某种形式的素数？

可以的，比如我们可以证明，存在无数多形如$6k+5$这样的素数。

另外，著名的大数学家狄利克雷（Dirichlet，1805-1859）证明了如下定理：

如果$a, b$是两个互质的正整数，那么存在无数个形如$ak+b$这样的素数。

从这个出发，我们之前证明的$4k+3$或者$6k+5$形式的素数有无数多个这样的定理就可以被视为该定理的特例。

不过这个定理的证明太复杂，需要更高深的数学。这里不进行展开，也没法进行展开。

另外，Ben Green和陶哲轩在2005年证明，存在任意长度的素数等差数列。也就是说，对于任意给定的自然数$n$，一定可以找到$n$个素数，它们构成了形如$p, p+a, p+2a, p+3a, ..., p+na$的等差数列。

值得一提的是，陶哲轩部分凭借此项证明获得了菲尔兹奖。

## 特定形态的素数

首先，我们来进行一个小小的练习，进行多项式的长除计算：$(x^m-1)/(x-1)$。

这个不是很难。我们可以很快得到这个长除法会得到：$x^{m-1}+x^{m-2}+x^{m-3}+...+x+1$。

我们用这个练习来证明：

**定理2.42**：如果$n$是自然数，而$2^n-1$是一个素数，那么$n$一定是个素数。

*证明*：

我们还是用反证法。

假定$2^n-1$是个素数，而$n$不是一个素数。$n$既然是一个合数，那么它可以被写成$n=xy$。于是$2^n-1=2^{xy}-1=(2^x)^y-1$。根据刚才的练习，这个式子可以进行因式分解，有$2^x-1$成为其因子。这么一来，$2^n-1$就不是一个素数了。因此，$n$必然是一个素数。QED。

**定理2.43**：如果$n$为自然数，而$2^n+1$是素数，那么$n$一定是2的幂的形式（即形如$2^k$）。

*证明*：

假定$n$是一个整数，但不是$2^k$的形式，那它一定有一个奇数因子$s (\gt 2)$。因此$n=rs, 1\le r \lt n$。

我们可以知道$(a-b)\mid (a^n-b^n)$[^5]，令$a=2^r, b=-1, m=s$，得到：$(2^r+1)|(2^{rs}+1) \implies (2^r+1)\mid 2^k+1$。与题设矛盾。所以，$n$必然是2的幂的形式。QED。

我们已经知道，形如$2^p-1$这样的素数称为`梅森素数`。而形如$2^{2^k}+1$这样的素数被称为`费马素数`。

**练习2.45**：证明梅森素数（或者费马素数）只有有限个（或者无限个）。奖励：**本学科满分毕业，并获得数学博士学位**。

## 素数的分布

观察素数的分布，可以注意到如下两个有趣的点：

1. 素数越来越“少”，或者说越来越稀疏。换句话说，合数越来越“多”。
2. 但是，还是会有素数“靠在”一起。

由此可以得到一个定理和一个猜想：

**定理2.46**：存在任意长度的连续合数。也就是说，对于任意一个自然数$n$，一定至少存在$n+1$个连续的合数。

*证明*：（略）

**猜想2.47（孪生素数猜想）**：存在无数多对素数，它们间相差2。（简单的例子如：11/13，29/31等）。

这个猜想目前还没有被证明。美籍华裔数学家张益唐对此作出了巨大的贡献。他于2013年4月17日在《数学年刊》发表《质数间的有界间隔》，首次证明了存在无穷多对间隙为有限的质数（具体间隙小于7000万，具体写为：$\lim_{n\to \infty} inf(p_{n+1}-p_n)\lt 7·10^7$），从而为孪生素数猜想做出了本质性的贡献。张益唐论文发布后，数学家们像开了挂一样地刷新“下限”。一年内，素数间间隔已经被刷到了`246`。如果采纳`Elliott-Halberstam`猜想和这个猜想的一般形式，那么素数间隔已经被分别刷到了`12`和`6`。普遍认为，证明这个猜想中用到的一些技术对证明[黎曼](../../gcti/riemann)猜想也会有重要的作用。

我们之前约略看到过$\pi(n) \sim Li(n)$，下面我们做一张表格，来看看一些具体的数字。

$n$|$\pi(n)$|$\frac{n}{ln(n)}$|$\frac{\pi(n)}{n}$|$\frac{1}{ln(n)}$|$\frac{\pi(n)/n}{1/ln(n)}=\frac{\pi(n)}{n/ln(n)}$
:--:|:--:|:--:|:--:|:--:|:--:
$10$  |4   |4.3...|.4    |.43429...|0.92104...|
$10^2$|25  |21.7..|.25   |.21714...|1.15133...|
$10^3$|168 |144.7... |.168  |.14476...|1.16054...|
$10^4$|1229|1085.7...|.1229 |.10857...|1.13199...|
$10^5$|9592|8685.8...|.09592|.08685...|1.10443...|
$10^6$|78498|72382.4...|.078498|.07238...|1.08452...|
$10^7$|664579|620420.7...|.0664579|.06204...|1.07121...|
$10^8$|5761455|5428681.0...|.05761455|.05428...|1.06144...|
$10^9$|50847534|48254942.4...|.050847534|.04825...|1.05385...|

可见，素数的分布越来越稀疏（$\frac{\pi(n)}{n}$越来越小）。

19世纪初期，[高斯](../../gcti/gauss)和勒让德（Legendre）对素数进行了研究并提供了洞见：即使素数的出现没有任何模式可循，但素数的分布（$\frac{\pi(n)}{n}$）与自然对数有关联。他们的猜想是，$\frac{\pi(n)}{n}$与$\frac{1}{ln(n)}$成正比。

**定理（素数定理）**：当$n \to \infty$，小于等于$n$的素数的比例（$\frac{\pi(n)}{n}$）接近于于$\frac{1}{ln(n)}$，特别地：

$\lim_{n\to\infty}\frac{\pi(n)/n}{1/ln(n)}=1$，或者说：

$\lim_{n\to\infty}\frac{\pi(n)}{n/ln(n)}=1$。

这个定理证明太复杂了。

最后，讲到素数就必然会讲到`哥德巴赫（Goldbach）猜想`。这个猜想说的是：

**猜想**：任何大于2的偶数都可以表示为两个素数的和。

目前，哥德巴赫猜想还没有证明，最好的成绩是陈景润证明了所谓的`1+2`，也就是说任何一个足够大的偶数都可以表示为两个素数的和（`1+1`）或者一个素数加上一个由两个素数相乘得到的合数（`1+2`）。

[欧几里得](../../gcti/euclid)对素数进行了很深入的研究，部分是因为古希腊人对所谓的`完全数`很感兴趣。所谓的完全数是指这样的一些数，它的所有因子（不一定是质因子，且包括1）加起来等于这个数。前四个完全数如下：

$6=1+2+3=2^{2-1}(2^2-1)$

$28=1+2+4+7+14=2^{3-1}(2^3-1)$

$496=1+2+4+8+16+31+62+124+248=2^{5-1}(2^5-1)$

$8128 =1+2+4+8+16+...+2032+4064=2^{7-1}(2^7-1)$

欧几里得证明，如果$2^n-1$是素数，那么$2^{n-1}(2^n-1)$就一定是完全数。于是在完全数和形如$2^n-1$（也就是梅森素数）之间建立了联系。

欧拉最终证明，所有偶的完全数一定具有欧几里得给出的那种形式。而到目前，还没有发现奇的完全数。

对梅森素数的探索一直在进行。到目前，找到的最大的梅森素数是： $2^{82,589,933}−1$，一个24,862,048位的庞然大物。（2018年12月21日，The Great Internet Mersenne Prime Search ([GIMPS](https://www.mersenne.org/))项目找到了这个素数。）

**小结**：

这一章讲素数，并介绍了数学中为数不多的基本定理之一：`算术基本定理`。

本章难度适中，证明方法多变但总体可控并可理解。

[^1]: 在我的这些笔记中，可能会混合使用“素数”、“质数”，以后不再说明。

[^2]: `s.t`是`such that`的缩写，可以翻译为“使得”。其他数学符号（$\forall, \exists$）的说明在此不赘述。

[^3]: `iff`是`if and only if`的缩写，也就是“当且仅当”，一般用$\iff$来表示。

[^4]: 梅森素数（Mersenne prime）是形如$2^n-1$这样的素数。见[维基词条](https://en.wikipedia.org/wiki/Mersenne_prime)。

[^5]: 请自己证明：$a^n-b^n=(a-b)\sum_{k=0}^{n-1}a^kb^{n-1-k}$
