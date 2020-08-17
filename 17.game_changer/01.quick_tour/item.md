---
title: A quick tour of computer chess competition
---

以下对局来自World Computer Championship，Stockholm，1974，**Kaissa**（最后的冠军）执白对阵**Chaos**。

1. e4 c5 2. Nf3 Nc6 3. c3 d5 4. exd5 Qxd5 5. d4 Bg4 6. Be2 e6 7. 0-0 Nf6 8. Be3 cxd4

[fen]r3kb1r/pp3ppp/2n1pn2/3q4/3p2b1/2P1BN2/PP2BPPP/RN1Q1RK[/fen]

到目前为止，一切都很不错。

9. Bxd4

这一手很奇怪。要么是9. cxd4（接Nc3攻击黑后）或者9. Nxd4（攻击黑方没有保护的g4象而迫使黑方反应）。

9. ... e5

完全失误了。

10. h3

白方也错过了10. Nxe5 Nxe5 11. Bxe5 Qxe5 12. Bxg4而获得一兵的走法。

10. ... exd4 11. hxg4 Bd6 12. cxd4

12. g5也许更强，准备吃掉d4兵而不让黑后来到h5。

12. ... Nxg4 13. Nc3 Qh5 14. g3

[fen]r3k2r/pp3ppp/2nb4/7q/3P2n/2N2NP1/PP2BP2/R2Q1RK1[/fen]

关键时刻到了。对黑方来说，短易位是常规的做法。但黑方开始进入疯狂阶段。

14. ... Kd7 15. Nh4 f5

现代引擎已经判断白方大优。

[fen]r6r/pp1k2pp/2nb4/5p1q/3P2nN/2N3P1/PP2BP2/R2Q1RK1[/fen]

16. Qb3会对黑更加不利，但Kaissa选择了更优美的下法。

16. d5 Nce5 17. Qc2 Rhf8 18. B3

稍缓，黑有反击机会。

18. Nxd 19. Qxd3 Rae8

19. ... g5 20. Nf3 Qh3更有威胁，强制走出21. Bxg3而逼和。

20. Nb5

好棋。

20. ... f4 21. Nxd6 Kxd6 22. Qa3+ Kc7 23. Qxa7

Kaissa虽然错过最快赢棋路线，但已经不会输了。

23. ... Qf7 24. Rfc1+ Kd6 25. Qc5+ Ke5 26. d6+ Ke6 27. Re1+ Ne3 28. gxf4 Qd7 29. f5+ Kf6 30. Rxe3 Rd8 31. Re7 Qa4 32. Qe5+ Kg5 33. Nf3+ Kg4 34. Rxg7+ Kh5 35. Qh2+ Qh4 36. Qxh4# 1-0

[fen]3r1r2/1p4Rp/3P4/5P1k/7Q/5N2/PP3P2/R5K1[/fen]

对于1974年的引擎来说，能下到这样已经很不错了。

书中接着提到（p28）：引擎可以给出要下的、能击败你的走法，但你不一定能就当前局面得到明确的指示。而另外一个问题在于，[Stockfish](https://stockfishchess.org/)对局面给出+1.00的判断可能意味着明确的优势，但也可能只是给出了一系列复杂走法的第一步。前一种情况是人类可以下的，但后一种则更困难。

### 引擎对引擎

2010年开始，计算机国际象棋引擎大战转到了TCEC（[Top Chess Engine Championship](https://tcec-chess.com/)）。30个等级分2800以上的引擎（包括著名的Stockfish，[Houdini](http://www.cruxis.com/chess/houdini.htm)，[Komodo](https://komodochess.com/)）分成5个级别进行比赛并有升降级机制，最后还有所谓的Superfinal（超级总决赛），在第1级别的两台最强引擎中展开。

比赛时，所有引擎使用的硬件配置一样。在超级总决赛时，两个引擎进行100场的比赛，限时120分钟，15秒延长。在这100场比赛中，会选定50个开局，双方交替执白进行比赛。

引擎间比赛常常给人太长、无趣以及无法理解的感觉。双方交替移动棋子可以长达49回合，然后才有一方动兵以避免50回合和棋规定——然后再重新开始！[^1]

下面这场比赛由Stockfish（260318，等级分3546）执白对Houdini（6.03，等级分3489），TCEC第11赛季，2018超级总决赛第5场。

1. d4 Nf6 2. c4 g6 3. Nc3 Bg7 4. e4 d6 5. f3 0-0 6. Be3 e5 7. d5 Nh5 8. Qd2 Qh4+ 9. g3 Nxg3 10. Qf2 Nxf1 11. Qxh4 Nxe3

[fen]rnb2rk1/ppp2pbp/3p2p1/3Pp3/2P1P2Q/2N1nP2/PP5P/R3K1NR[/fen]

这个开局由俄罗斯著名棋手[大卫·布龙斯坦](https://zh.wikipedia.org/wiki/%E5%A4%A7%E5%8D%AB%C2%B7%E5%B8%83%E9%BE%99%E6%96%AF%E5%9D%A6)首创，理论评价一直不高。看到TCEC比赛中出现这样的开局，很有意思。

黑方用后换了白方两个兵、两个象，自己保留了双象，兵型比白方好很多，但子力出动落后，e3马孤军深入，迟早会成为攻击目标。

12. Qf2

这手已经很不寻常。卡尔波夫对卡斯帕罗夫曾走出另外一条路线。但Stockfish的路线也很强。

12. ... Nxc4 13. h4 h5 14. Qe2 Nb6 15. Nb5

[fen]rnb2rk1/ppp2pb1/1n1p2p1/1N1Pp2p/4P2P/5P2/PP2Q3/R3K1NR[/fen]

Stockfish在这里的下法和俄罗斯大师Yuri Razuvaev一样，只是次序有些变化。黑方现在有三个弱点：1. g6兵，白马可以在g5占据重要位置；2. c7兵；3. b6黑马。

15. ... Na6 16. Nh3 Bh6 17. a4

[fen]r1b2rk1/ppp2p2/nn1p2pb/1N1Pp2p/P3P2P/5P1N/1P2Q3/R3K2R[/fen]

这一手十分有力，目标直指b6黑马。黑方为了防止白马来到g5，必须牺牲双象中的黑格象。

17. ... Bxh3 18. Rxh3 Nd7 19. a5 Ndc5 20. Qc4

[fen]r4rk1/ppp2p2/n2p2pb/PNnPp2p/2Q1P2P/5P1R/1P6/R3K3[/fen]

白方准备Ke2，然后b2-b4。

20. ... f5 21. Kf1 fxe4 22. b4 Nd7 23. Nc3!!

[fen]r4rk1/pppn4/n2p2pb/P2Pp2p/1PQ1p2P/2N2P1R/8/R4K2[/fen]

强有力的一步！一旦白马来到e4，白后到b5就会对b7兵和d7黑马造成骚扰，而一旦b7兵被吃，a6黑马也将没有根。但白方为此付出了两个兵的代价。

23. exf3 24. Ne4 Nf6 25. b5 Nc5 26. Nxc5 dxc5 27. d6+ Kh7 28. dxc7 e4

[fen]r4r2/ppP4k/5npb/PPp4p/2Q1p2P/5p1R/8/R4K2[/fen]

局面异常激烈，但Stockfish胸有成竹。

29. Re1 Rae8 30. Rxf3 Rc8 31. Rf2 Rxc7 32. Ke2 e3 33. Rf3 Bg7 34. Ref1 Rd7 35. Rd1 Re7 36. Rf4 Ne4

[fen]5r2/pp2r1bk/6p1/PPp4p/2Q1nR1P/4p3/4K3/3R4[/fen]

很了不起的防守！

37. Rxe4 Rf2+ 38. Kxe3 Ref7

[fen]8/pp3rbk/6p1/PPp4p/2Q1R2P/4K3/5r2/3R4[/fen]

黑方威胁R7f3叫杀。

39. Re8 R7f3+ 40. Ke4 Rf4+ 41. Kd5 Rxc4 42. Kxc4 Rc2+ 43. Kd3 Ra2 44. Re7 Kh6 45. Rf1 c4+ 46. Kxc4 Ra4+ 47. Kc5 Bd4+ 48. Kd5 Bc3 49. Rxb7 Rd4+ 1-0

[fen]8/pR6/6pk/PP1K3p/3r3P/2b5/8/5R2[/fen]

终局。白方子力占优，后翼连兵的威力太大。黑方已经无法抵挡。







[^1]: 50回合规则：从对局的某一回合开始，连续的50回合内，双方没有吃过一个棋子，并且所有的兵都没动过，可以由一方提出，经裁判核准后判为和棋。规则见[此处](https://jingyan.baidu.com/article/148a1921a2b0c94d71c3b1f8.html)。