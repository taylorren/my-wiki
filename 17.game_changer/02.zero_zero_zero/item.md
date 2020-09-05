---
title: ZeroZeroZero
---

2017年底，有10盘对局记录被公开。对阵双方是代表着超人战力的Stockfish以及DeepMind出品的AlphaZero。比赛结果？AlphaZero的压倒性胜利。

但比起胜利而言，更令人瞩目的是AZ教会自己求胜的方式。计算机第一次通过自学的方式达到了这个水平，而没有学习人类已经建立起来的象棋战略。它让人想起了[卡斯帕罗夫](https://en.wikipedia.org/wiki/Garry_Kasparov)的黄金时代：从开局就开始攻王，并通过“随意”的弃子来达成这个目标。对棋手而言，这些对局为人们提供了具有启发性的思考：一种新的着法风格已经形成了——或者更精确地说，现有的着法得到了更新和扩展——足以击败当时世界上最强的国际象棋引擎。

若果如此，那么当前对某些复杂开局变例以及中局形势的判断可能就要被推翻。

2018年初，我得到了210盘对局。其中的110盘没有任何开局定式，另外100盘有开局定式。

前10盘虽有亮点但不够令人瞩目。从11盘开始，情况就不一样了。其中的第11盘的引人瞩目之处在于，作为黑方的AZ已经牺牲了3个兵，然后在22步悄悄地下出了`22. ... h6`。

### “象的扫射”

1. e4 e5 2. Nf3 Nc6 3. Bc4 Nf6 4. Ng5 d5 5. exd5 Na5 6. Bb5+ c6 7. dxc6 bxc6 8. Bd3 Nd5 9. Nf3 Bd6 10. 0-0 Nf4 11. Re1 Nxd3 12. cxd3 0-0 13. Nxe5 c5 14. Nc3 Bb7 15. b3 Re8 16. Nc4 Nxc4 17. Rxe8+ Qxe8 18. bxc4 Qe6 19. Bb2 Rb8 20. Nb5 Qg6 21. Qf1 Bf4 22. Nxa7 h6

[fen]1r4k1/Nb3pp1/6qp/2p5/2P2b2/3P4/PB1P1PPP/R4QK1[/fen]

这局棋的结果是AZ在第48步取胜。在第25步时，Stockfish走出了败着25. Qd1而不是25. Nb5以保持子力优势，原因不明。

23. Bc3 Qh5 24. h3 Ra8

[fen]r5k1/Nb3pp1/7p/2p4q/2P2b2/2BP3P/P2P1PP1/R4QK1[/fen]

25. Qd1 Qxd1+ 26. Rxd1 Rxa7 27. Ra1 Bc6 28. a4 Rxa4 29. Rxa4 Bxa4 30. Kf1 Bb3 31. Ke2 Bd6 32. Ke3 Be7 33. Be5 f6 34. Bc7 Kf7 35. Bb6 Ke6 36. Ke2 Kd7 37. Ke1 Kc6 38. Ba5 h5 39. Kf1 Kd7 40. Bb6 Bc2 41. Ke2 Kc6 42. Ba5 Bd6 43. d4 cxd4 44. d3 Ba4 45. h4 Kb7 46. Kf1 Bd7 47 Ke2 Ka6 48. Bd8 Bf5

[fen]3B4/6p1/k2b1p2/2P2b1p/3p3P/8/3PKPP1/8[/fen]
**棋谱下载**

1. [Raking Bishops: Stockfish 8 - AlphaZero, London 2018, Game 11](./Raking_Bishops_Stockfish_8_AlphaZero_London_2018_Game_11.pgn)
