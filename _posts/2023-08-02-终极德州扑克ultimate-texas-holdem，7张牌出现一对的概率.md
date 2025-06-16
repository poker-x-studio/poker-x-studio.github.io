---
title: "终极德州扑克Ultimate Texas Holdem，7张牌出现一对的概率"
date: 2023-08-02
categories: 
  - "go"
  - "linux"
  - "texas_holdem"
---

在youtube上常看一个华人朋友在美国赌场里玩这个终极德州扑克游戏，看的多了，总觉得有一个场景是值得深思一下的，所以，才就确认一下概率。

这是 youtube 用户 杨洋 [https://www.youtube.com/@payme1314](https://www.youtube.com/@payme1314) 的赌场视频。有兴趣的朋友可以看看。

### 一 开发的go程序，用于计算终极德州扑克，在最后一轮river圈下注play的时候，如果自己没有一对的情况下，是否应该下注

- 运行环境:vscode/ubuntu,32G内存
- 运行条件:
- 开启50个goroutine,每个goroutine循环10000次,也就是一共运行50万次
- 每循环1次就是，牌靴中有1副牌的游戏流程\[去掉大小鬼,每副牌52张\]
- 运行时间:2023-07-18 20:35:31
- 运行时长:3:19(3分19秒)
- 运行结果:

```
msg="3,total_item_cnt:500000,牌张数:2, 牌型:至少一对,个数:29666,百分比:5.93"
msg="3,total_item_cnt:500000,牌张数:3, 牌型:至少一对,个数:86543,百分比:17.31"
msg="3,total_item_cnt:500000,牌张数:4, 牌型:至少一对,个数:161674,百分比:32.33"
msg="3,total_item_cnt:500000,牌张数:5, 牌型:至少一对,个数:246208,百分比:49.24"
msg="3,total_item_cnt:500000,牌张数:6, 牌型:至少一对,个数:327822,百分比:65.56"
msg="3,total_item_cnt:500000,牌张数:7, 牌型:至少一对,个数:394692,百分比:78.94"
```

![](https://poker-x-studio.github.io/images/2023-07-18-20-35-31-336676936.png)

### 二 运行结果解释

终极德州扑克是闲家和庄家对赌【和德州扑克 Texas Holdem不同，德州扑克是闲家之间的对赌】，和庄家比大小。庄家2张牌，闲家2张牌，5张公共牌。直到闲家三次下注结束，庄家才会亮牌，在此之前，庄家为暗牌。

终极德州扑克中，闲家会有三次下注机会

2.1 看到自己的2张牌，但没有看到公共牌的时候，pre flop 圈，可以下注3倍或4倍 ante 的筹码 2.2 看到3张公共牌了之后，flop圈，可以下注2倍的 ante筹码 2.3 看到所有5张公共牌之后，river圈，可以下注1倍的ante筹码，或者fold 放弃

这里要讨论的，就是 这个 river圈，第三次下注。

在闲家没有拿到任何对子，也没有比对子更大的牌型的情况下，是否应该下注1倍的ante筹码到play区，和庄家比大小。

根据程序运行10万次的结果，如果自己没有对子，庄家手里的2张牌和5张公共牌，组成对子的概率为78%。

在river圈，还没有下注play的时候，闲家在ante和blind位都会有1倍的筹码。

假设我们下注1倍的ante筹码在play位， 庄家2张牌+5张公共牌组合的最大牌型 闲家2张牌+5张公共牌组合的最大牌型 进行比较 来计算一下底池赔率，我们需要拿1倍的ante筹码下注到play区域，去赢取 play+ante+blind【如果在我们预设的场景下，庄家输了，说明庄家一定是 not qualify，在庄家not qualify的时候，不赔付ante区】，用1倍的筹码去赢取3倍的筹码，底池赔率就是25%

如果胜率大于底池赔率，则长期是 正ev 如果胜率小于底池赔率，则长期是 负ev

所以，闲家需要至少25%的胜率，才可以下注play区。现在来看，闲家胜率最大也就22%，所以，根据理论， 在终极德州扑克中，在river圈，当闲家没有拿到一对的时候，不应该选择下注，而应该fold。 P.S. 如果游戏规则为，没有这个qualify的限制，只要庄家输了，都会赔付ante区域的筹码，那么，闲家在river圈，任何情况下下注play区域都是正ev的。

### 三 网络上找到的规则链接，原地址

[https://www.onlineunitedstatescasinos.com/games/casino-texas-holdem-poker/ultimate-texas-holdem/](https://www.onlineunitedstatescasinos.com/games/casino-texas-holdem-poker/ultimate-texas-holdem/)

![](https://poker-x-studio.github.io/images/ultimate_texas_holdem_table_layout-2.png)

\--the end
