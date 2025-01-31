---
title: 哥德尔的发现
visible: false
---

## 哥德尔的发现

### A． 哥德尔岛

在本章结尾我们要讨论数理逻辑学家科特・哥德尔[^1]发现的著名定理。这一节的谜题是根据那条定理改写的。

[^1]: Kurt Gödel词条见http://en.wikipedia.org/wiki/Kurt_Gödel。译者注。另见[《上帝创造了整数》之“哥德尔”篇](../../gcti/godel)。


**264. 岛G**

在某座岛G上住着永远讲真话的君子和永远讲假话的小人。不仅如此，有一些君子被称为“定位君子”（在某种意义上说，是那些“身份已经明确”的君子），有一些小人被称为“定位小人”。岛上的居民构成各式各样的俱乐部。一个居民有可能属于多个俱乐部。给出任一居民X和任一俱乐部C，X要么声明他是俱乐部C的成员，要么声明他不是。

我们有下面四个条件，E1，E2，C，G：

>E1：所有定位君子的集合构成一个俱乐部；

>E2：所有定位小人的集合构成一个俱乐部；

>C（互补条件）：给出任一俱乐部，所有不是C的成员的居民集合构成他们的俱乐部。这个俱乐部称为C的补，记为C’。

>G（哥德尔条件）：给出任一俱乐部C，岛上至少有一个居民声明他是该俱乐部成员。（当然，他的声明可能是假的，因为他可以是个小人）。

**264a.**

（仿哥德尔）

>(i) 证明岛上至少有一个未定位的君子。

>(ii) 证明岛上至少有一个未定位的小人。

**264b.**

（仿塔尔斯基[^2]）

[^2]: Alfred Tarski词条见http://en.wikipedia.org/wiki/Tarski。译者注。

>(i) 岛上所有小人的集合是不是构成一个俱乐部？

>(ii) 岛上所有君子的集合是不是构成一个俱乐部？

264a的答案：

按照条件E1，所有定位君子的集合E构成一个俱乐部。因此按照条件C，岛上所有未定位的君子的集合E’也构成俱乐部，再按照条件G，岛上至少有一个人声明他是E’俱乐部的成员，换句话说，他声明他是一个未定位的君子。

小人不可能这么声明他不是个未定位的君子（因为小人不是定位君子这个陈述为真），因此说话者必定是个君子。既然他是个君子，那他说的是实话，所以他不是个定位君子。所以说话者是君子，但不是个定位君子。

按照条件E2，所有定位小人的集合构成一个俱乐部。因此（按照条件G）岛上至少有一个人声明是个定位小人（他声明他是定位小人俱乐部的成员）。此人不会是个君子（因为没有君子会声称他是任何哪一类的小人），所以他是个小人。因此他的陈述为假，他不是个定位小人。这意味着他是小人，但不是定位小人。

264b的答案：

如果所有小人的集合构成一个俱乐部，那至少有一个居民要声称自己是小人，而无论君子还是小人都不会这么做。所以，所有小人的集合不会构成俱乐部。

如果君子的集合构成一个俱乐部，那么小人的集合也得构成俱乐部（按照条件C），因此君子也不能构成俱乐部。

附注：

(1) 264b给出了264a的另外一种解法。这种解法虽然是非构造性的，但也许稍微简单一些。

如果每个君子都已经定位，那么君子的集合和定位君子的集合就一样了，但这是不可能的。因为定位君子的集合构成一个俱乐部（条件E1），但是君子的集合构不成俱乐部（264b）。所以，假定所有君子都已经定位将导致矛盾，所以必然至少有一个未定位的君子。类似的，如果所有小人都定位，那么定位小人的集合和小人集合一样，这也不可能，因为定位小人集合构成一个俱乐部而小人集合构不成。

和这个证明不同的是，我们的第一个证明明确的告诉我们，谁声明他不是个定位君子，他必定是个未定位君子；谁声明他是个定位小人，他必定就是个未定位的小人。

(2) 我们证明小人集合构不成俱乐部只用到了条件G，而没有用到E1、E2和C。因此条件G本身就蕴含了小人构不成俱乐部。实际上，条件G等价于小人构不成俱乐部的陈述。如果给我们的条件是小人集合构不成俱乐部，我们可以推导出条件G。论证如下：

任意选取一个俱乐部C。既然小人集合构不成俱乐部，所以C不是所有小人的结合。要么C里有君子，要么在C外有小人。如果C里有君子，那他肯定会声明在C俱乐部里（因为他说实话）。如果C外有小人，他也会声明在C里（因为他撒谎）。所以，无论哪种情形，某人总会声称他是C俱乐部的。

**265. 哥德尔岛泛论**

现在考虑任意一个有俱乐部的君子小人岛（我们说君子小人岛时，意思当然是说岛上只住着君子和小人）。如果条件G成立，即对于每个俱乐部，至少有一个居民声明他是该俱乐部的成员，那么这个岛我们称它为哥德尔岛。

克雷格探长有次访问了一个设有俱乐部的君子小人岛。顺便说一句，克雷格是为受过良好教育的绅士，他对理论方面的兴趣丝毫不亚于他在实践方面。他很想知道他是不是在一个哥德尔岛上。他获知了如下的情报。

每个俱乐部都以一个岛民命名，而每个居民也有一个俱乐部以他命名。一个居民不一定是挂他名字的俱乐部的成员。如果他是，他被称为合群的；如果不是，他被称为离群的。如果X声称Y是合群的，那么X被称为是Y的朋友。

克雷格还是不知道他是否在一个哥德尔岛上，直到他发现这座岛还满足如下的条件，我们称为条件H：

H：对于任意一个俱乐部C，还有一个俱乐部D。D中的每个成员在C中都有一个朋友，凡不是D的成员都至少有一个朋友不在C中。

由条件H，克雷格可以判断这个岛是不是哥德尔岛了。

是吗？

答案：是的，是哥德尔岛。任取一个俱乐部C，令D是按条件H成立的俱乐部。这个俱乐部D以某人命名――比如说约翰。约翰要么属于俱乐部D要么不属于。

假定他属于。那么他有一个朋友――比如说杰克――在俱乐部C中，杰克会声明约翰是合群的。既然约翰属于D，那么约翰确实是合群的，所以杰克是君子。因此杰克是一个属于C俱乐部的君子，杰克会声明他属于俱乐部C。

假定约翰不属于俱乐部D。那么约翰有一个朋友――比如说吉姆――不在俱乐部C中，而吉姆会声称约翰是合群的。由于约翰不是俱乐部D的成员，约翰实际上是离群的，所以吉姆是个小人。所以吉姆是个不在俱乐部C中的小人，所以吉姆会撒谎并声称自己在俱乐部C里。所以，无论约翰属于俱乐部D还是不属于，都有一个居民申明自己是俱乐部C的成员。

附注：把264题和265题的结论结合起来，我们可以看到，给定任一岛屿满足条件E1、E2、C和H，岛上必定存在未定位的君子和未定位的小人。这个结论其实就是著名的哥德尔不完备性定理的改装形式。我们在C小节还将再次讨论这个定理。

顺便说一句，如果你想给你的哪位朋友出一道确实有难度的题目的话，你就给他一个满足E1、E2、C和H的岛（不要提G），然后提出264题里的问题。看看他能不能自己推出条件G，会是蛮有趣的一件事。

### B． 双重哥德尔岛

这一小节的题目比较偏，最好是等到C小节后再做。

所谓“双重哥德尔岛”是指这样一个设有俱乐部的君子小人岛，并满足下面的条件GG：

GG：给出任意两个俱乐部C1和C2。存在着居民A和B，A声称B是C1的成员，B声称A是C2的成员。 据我所知，条件GG并不蕴含条件G，条件G也不蕴含条件GG。它们好像是完全独立的。因此（据我所知），一个双重哥德尔岛不一定就是一个哥德尔岛。

双重哥德尔岛的话题是我的一个爱好。谈及的谜题和尤丹双面纸牌悖论（参见前一章中的254题）之间的关系，和哥德尔岛谜题和撒谎者悖论的关系一样。

**266. 双重哥德尔岛S**

有次我运气真是不错，发现了一座双重哥德尔岛，并满足G岛中的E1、E2、C条件。

>(a) 能否断定S岛上一定有一位未定位的君子？未定位的小人呢？

>(b) 能否断定S岛上所有君子成立了一个俱乐部？小人呢？

答案：首先我们考虑(b)部分。如果君子的集合够成一个俱乐部，那么所有小人的集合也构成俱乐部（根据条件C），而如果小人集合组成俱乐部，君子集合也如此（还是根据条件C）。所以如果它们两个中哪个集合构成俱乐部，就都可以构成。假定它们都可以构成。这是，按照条件GG，必定有岛民A和B作如下的陈述：

>A：B是小人。

>B：A是君子。

这是不可能出现的情形。上一章259题中我们已经看到了证明。于是结论就是，无论君子集合还是小人集合都不能构成俱乐部。

至于(a)部分，我们可以用两种方法中的任意一种来证明。第一种简单些，因为我们已经解决了(b)；第二种更有启发性。

方法一：既然君子集合不能构成俱乐部，而定位君子的集合可以，所以这两个集合不一样，所以不是所有的君子都已经定位。小人的情形与此类似。

方法二：既然定位君子集构成一个俱乐部，那么所有不是定位君子的集合也构成一个俱乐部。我们将这两个俱乐部称为C1和C2。根据条件GG，会有居民A和B做如下的陈述：

>A：B是个定位君子。

>B：A不是个定位君子。

我们让读者去证明A和B两人中必定至少有一个是未定位的君子。更具体的说，如果A是君子，那么他肯定就是未定位君子；如果A是小人，那B必定是个未定位君子。有趣的是，尽管我们知道A和B中有一个未定位君子，但是我们不知道究竟是谁。这一情形和134题，即贝里尼和切里尼双盒问题完全一样。两个盒子中必定有一个是贝里尼制作的，但是我们不知道是哪个。

与之类似，既然所有定位小人构成一个俱乐部，所有非定位小人的居民集合也构成一个俱乐部。所以还是根据条件GG，必定有两个人A和B说：

>A：B是个定位小人。

>B：A不是个定位小人。

由此可以推断，如果B是个小人，那他是个未定位的小人；如果B是君子，那A是个未定位的小人。我们还是让读者去证明这一点。所以，无论哪种情形，要么A要么B是个未定位的小人，但我们不知道是哪个。这题和贝里尼和切里尼双盒问题135题完全一样。

**267. 岛S1**

由此我发现了另外一个双重哥德尔岛，让我更感兴趣。在岛上，条件E1和E2还是成立的，但不知道条件C是否成立。我们应该还记得，条件C说的是，对于任一俱乐部C，非C成员的集合构成一个俱乐部。 要证明岛S1上有一个未定位君子，或者证明岛S1上有一个未定位小人，看起来都是不可能的。要证明君子不构成俱乐部，或者证明小人不构成俱乐部，看起来也不可能。但是，还是能够证明下面的两条：

>(a) 证明岛上要么由一个未定位君子，要么由一个未定位小人。

>(b) 证明所有君子和所有小人不能同时构成他们各自的俱乐部。

答案：我们先证明(b)。假定君子构成一个俱乐部而且小人构成一个俱乐部。于是就有居民A和B，A声称B是小人而B声称A是君子。我们已经知道这是不可能的（见前一题或者上一章的259题）。所以，不可能君子构成一个俱乐部同时小人构成一个俱乐部。要么君子不能构成俱乐部，要么小人不能构成俱乐部。如果君子构不成俱乐部，那必定有一个未定位的君子（因为定位的君子确实能构成俱乐部）；如果小人构不成俱乐部，那必定有一个未定位的小人。我们不知道是哪种情况。这也证明了(a)。

另一种解法更有趣，可以用来证明岛上必定要么有个未定位君子要么有个未定位小人。是这样的：

既然定位君子构成一个俱乐部，定位小人也构成一个俱乐部。于是就有居民A和B说：

>A：B是定位小人。

>B：A是定位君子。

如果A是个君子，那么他的陈述为真，所以B是个定位小人。B的陈述为假，A不是个定位君子。所以在这种情况下，A是个未定位君子。如果A是小人，那B的陈述为假，所以B是个小人。同样，A的陈述也假，因此B不是个定位小人。在这种情况下，B是个未定位小人。

所以，要么A是未定位君子，要么B是未定位小人。但我们还是不知道是哪种情况。

这题又类似一个双盒问题（第九章第136题）。两个盒子中的一个（我们不知道是哪个）是由贝里尼或者切里尼制作的（我们也不知道是谁）。

**268. 几道未解的题目**

我想出了几道关于哥德尔岛和双重哥德尔岛的题目，我还没有尝试去解决。我认为让读者尝试进行一些原创的工作，应该是件有趣的事情。

**268a.**

我说过，就我所知，条件G和GG互相不蕴含。你能证明我的猜想吗？（或者否证它，不过我觉得那应该希望不大。）要做到这点，你必须构造一个岛，G成立而GG不成立，再构造一个岛，GG成立而G不成立。所谓构造一个岛，是说指定所有的居民，指定哪些是君子、哪些是小人，哪些人的集合构成俱乐部、哪些构不成。（君子和小人是否定位和本题无关。）

**268b.**

我的猜想是S1岛上不一定有未定位君子也不一定有未定位小人（当然，必定有一种，非此即彼），你能证明或者否证它吗？也就是说，你能够构造一个岛，满足E1、E2和GG，而岛上只有君子而没有未定位君子？你能构造一个岛，只有小人但没有未定位小人？（这次构造这样的岛，你不仅要指定君子、小人、俱乐部，还要指定哪些君子和小人是定位了的。）

**268c.**

假定这些岛都可以构造出来――尽管我没有加以验证，但是我心里确定是可以的――每种情况下每个岛上居民数量最少是几个？你能证明在各个情况下，居民数再少就不可能了吗？

### C． 哥德尔定理

**269. 这个系统完备吗？**

有这么位逻辑学家保存了一本书，叫做《语句之书》。书里的页都是顺序编码的，每页上正好写了一句话。没有一句话出现在两页以上。任意给出一句话X，书写它那一页的页码被称为X的页数。

当然，书上的每句句子要么真要么假。对这位逻辑学家而言，某些真句子简直就是自明的，于是他将这些自明的真理作为他逻辑系统的公理。这个系统还包含一些推理的规则使得他能根据公理证明各种真句子，否证各种假句子。逻辑学家很有信心的认为他的系统是正确的，也就是系统中每个可以证明的句子确实都是真句子，每个可以否证的句子都是假句子。但是他不确定他的系统是否已经完备，也就是所有真句子都可以证明，所有假句子都可以否证。他的系统中所有真句子都可以证明吗？所有假句子都可以否证吗？这些都是这位逻辑学家想要回答的问题。

哦，这位逻辑学家还有另外一本书，叫做《集合之书》。这本的每页也是顺序编号的，每页上都有一个数的集合的描述。（我们这里用字“数“来表示正整数1、2、3、……，n……。）这本书上某个地方描述了的数集，我们称之为已列集。

任给一数n，有可能《集合之书》第n页上列的那个集合正好包含n自身作为一个元素。如果真这么凑巧，我们称n为异常数。同时，给定任意两数n和h，如果《集合之书》第h页上的句子断言n是异常数，那么h就被称为n的伙伴数。

我们还知道如下四个条件是成立的：

>E1：所有可证明的句子的页码集合是一个已列集。

>E2：所有可否证的句子的页码集合是一个已列集。

>C：对于任何已列集A，不在A里的所有数字的集合A’也是个已列集。

>H：指定任一已列集A，必有另外一个已列集B，其中B中的每个元素在A中有个伙伴数，而B外的每个元素在A外有个伙伴数。

有了这四个条件，就足以回答那位逻辑学家的问题了：系统中每个真句都可以证明吗？系统中每个假句都可以被否证吗？也可以确定，所有真句页码的集合是否是一个已列集，所有假句页码的集合是否是一个已列集。

如何做到呢？

答案：这个问题不过就是A小节中哥德尔岛谜题换了个包装。在我们现在的场景中，所有真句页码扮演了君子的角色，所有假句页码是小人。可证明句子是定位君子，可否证句子是小人。已列集扮演了俱乐部的角色。而一个集合被列在某个页码的页上的概念就是扮演了一个俱乐部以某个居民命名的角色。因此，异常数就是合群人士的角色，而“伙伴数”的概念就是“朋友”的角色。

要解决目前的这个问题，我们首先必须要证明条件G的一个相似条件，也就是：

>条件G：对于任一已列集A，有一句话为真当且仅当它的页码存在于A中。

要证明条件G，我们任选一个集合A。令B为由条件H给出的集合。令n为集合B所列页的页码。根据条件H，如果n在B内，那么n在A中有个伙伴数h；如果n不在B内，那么n在A外有个伙伴数h。我们断定页h上的句子X是我们要找的那个句子。

句子X说n是异常数，换句话说，n在B中（因为B是在n页上的已列集）。如果X为真，那么n确实在B中，所以h在A中。所以，如果X为真，那它的页码h确实在A中。如果X为假，那n不在B中，所以h在A外。因此X为真当且仅当它的页码在A中。

我们已经证明了条件G，逻辑学家的问题就可以很容易的回答了。我们已经知道，所有可证明句子的页码构成的集合A是已列集，所以根据条件C，存在一个结合A’，它是除掉所有可证明句子的页码所构成的集合。因此，根据条件G，有这么一句话X为真当且仅当X的页码属于A’。如果说X的页码属于A’，就是说X的页码不属于A，也就是说X不可证（因为A中包含了所有可证句子的页码）。因此X为真当且仅当X不可证。这意味着要么X为真但不可证，要么X为假但可证。我们已经知道系统中不存在可证的假命题，所以X必定为真但是在系统中不可证。

要得到一个不可否证的假命题，我们令A是所有可否证的句子页码的集合。应用条件G，我们得到一个句子为真当且仅当它的页码是一个可否证句的页码。换句话说，Y为真当且仅当Y可否证。这意味着，要么Y为真但可否证，或者为假但是不可否证。第一个可能不存在，因为没有一个可否证的句子是真的。所以Y必定为假但是在系统中不可否证。

至于另外两个问题，如果所有假句子的页数的集合是个已列集，那就会有这么句话Z，它为真当且仅当它的页码是一个假句子的页码。换句话说，Z为真当且仅当Z为假，而这是不可能的。（这就类似这句话：“这句话是假的。”）因此所有假句子的页码的集合不是个已列集。那根据条件C，所有真句子的页码的集合也不会是个已列集。

**270. 哥德尔定理**

上面这个谜题其实就是著名的哥德尔不完备性（`Godel's Incompleteness Theorem`）定理的一种形式。

1931年，科特・哥德尔提出了他令人惊愕的发现。他发现在一定意义上，数学真理是不能被完全形式化的。他表明，对于形形色色的数学系统――这些系统都满足特定的、有充足理由成立的条件――其中总存在一些真句子却无法根据系统的公理加以证明！因此，无论一个形式化的真理系统构造的有多么精致，都不足以证明所有的数学真理。哥德尔首先是在怀特海和罗素那著名的《数学原理》系统中证明这个结论的。不过，我也说了，这个证明使用于很多别的系统。在所有这些系统中，有一个良好定义的表述的集合，称为句子，也有一个分类将所有句子分成真句子和假句子。某些真句子被作为系统的公理，并有着精巧的推理规则让人证明某些句子或者否证某些句子。除了句子以外，系统还包含各种（正整）数的集合的名字。任何数集，如果在系统中有一个名字，被称为该系统的可命名集或者可定义集（这就是上题中我们称为的“已列集”）。关键在于，有可能给所有的句子编上号，并以某种方式列出所有的可定义集，满足谜题中的E1、E2、C和H条件。我们给每个句子编的号，称为“页码”，在技术上称为该句子的哥德尔数。要建立条件C和H其实是件很容易的事情，但是要建立条件E1和E2是很耗时的工作，虽然在原则上说只是初级的工作[^3]。无论如何，只要这四个条件成立，它们就将导致能构造一个句子，它为真但是在系统中无法被证明。

[^3]: 考虑条件H：对于每个数n，有一句话断言n为异常数。这句句子（和其他所有句子一样）有一个哥德尔数――不妨称为n。对于任何可定义集A，那么n在A中的所有数n也构成一个集合B，而它也是可定义集。既然n*是n的伙伴数，条件H已经满足了。原注。 

要找的那句话X可以被理解为断言它自身的不可证明性。这句话事实上必定为真，但是不可证明。这就像G岛上的一个人说他不是个定位君子一样。事实上，他肯定是个君子，但是不是个定位君子。

也许有人会问：既然哥德尔的句子X断言它自身的不可证明性而且又是真的，为什么不把它作为一个新的公理加入到系统中呢？你当然可以这么做了，但是我们会得到一个更大的系统，新的系统还是满足条件E1、E2、C和H。因此可以得到另一句话X1，它在大系统中为真但是无法证明。因此在扩大了的系统中，可以比在老系统中证明更多的真句子，但还不是所有的真句子。

要提醒大家的是，我对哥德尔方法的说明和他原始的说明略微有些偏差。主要在于我使用了真的概念，而哥德尔没有。事实上，哥德尔定理的原型并没有说有一句句子为真但不可证明，而是说在系统合乎某些理由充足的假定下，系统中必然存在一句话既不可证明又不可否证。哥德尔确实构造出了这样一句话。

“真”这个概念的严格形式化由逻辑学家阿尔弗雷德・塔斯基完成。正是他证明了，对于这些系统而言，真句子的哥德尔数集合在系统中不可定义。有时这个定理可以改称为：“对于一个足够强的系统而言，系统中句子的真实性在系统中不可定义。”

**271. 写在最后**

考虑下面这个悖论：

>这句句子永远无法被证明。

悖论在于：如果该句子为假，那么它不可被证明就为假，所以它可以被证明，所以意味着它必定为真。所以，如果它为假，我们会得到矛盾。它必定为真。

好，我刚证明这句话为真。由于句子为真，那它所说的确实为真，意味着它不能被证明。那我又是如何证明它的？

上面的推理错在哪里？问题在于可证明这个概念不是良定义的。所谓“数理逻辑”这个领域中有一个重要目标就是给出可证明概念的精确定义。但是，至今还没有给出一个绝对意义上的“证明”的完全严格的定义。说可证明的时候都是在一个给定系统中。假定我们有一个系统S，在这个系统中，“系统S中可证明”的概念是明确定义了的。再假定系统S是正确的，也就是说，可以在系统中证明的一切都确实是真的。那么考虑下面这个句子：

>这句话在系统S中无法被证明。

我们就不会遇到任何悖论了，反而得出了一个有趣的真理。有趣的真理就是，上面这句话在系统S中必定为真，但无法证明。事实上，它就是哥德尔的句子X的一个粗糙的表现。它可以被看做在断言自身的不可证明性，但不是以绝对的方式，而是说在一个给定的系统内。

我还要再稍微说说我在B节中分析过的“双重哥德尔”的条件。事实上，哥德尔的结论可以适用的各种系统不仅仅是“哥德尔式”的，亦即，给定任一可定义集A，有一句话为真当且仅当它的哥德尔数在A内，而且还可以用到我所谓的“双重哥德尔式”上去。意思是说，给出任意两个可定义集A和B，有句子X和Y，X为真当且仅当Y的哥德尔数在A中，且Y为真当且仅当X的哥德尔数在B中。由此出发，并使用条件E1、E2和C，我们可以构造一对句子X和Y，X断言Y可证明（亦即X为真当且仅当Y可证明），而Y断言X不可证明。其中之一（我们不知道是哪句）必定为真但是不可证明。或者，我们可以构造这样一对句子X和Y，X断言Y可否证，而Y断言X不可否证。从中可以得出至少有一句（我们不知道是哪句）必定为假但是不可否证。或者，我们甚至不用条件C，可以构造一对句子X和Y，X断言Y可证而Y断言X可否证。其中之一（我们不知道哪句）要么为真但不可证，要么为假但不可否证（我们也不知道是何种情形）。

哦，还有最后一件事，免得我忘了。这本书叫什么？呵呵，这本书的名字就是“这本书叫什么？”