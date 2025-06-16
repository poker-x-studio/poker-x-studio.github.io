---
title: "网络上其他资料上的Blackjack庄家爆牌率比较"
date: 2024-07-27
categories: 
  - "blackjack"
---

这几天经常回顾默想Blackjack中庄家爆牌率，然后发现，上次的文章中缺少了明牌为A的爆牌率，所以又增加了A的情况，更新了文章。 还搜索了一下网络上关于Blackjack中庄家爆牌率的其他资讯。

发现还有两篇文章可以比对查看。

#### 一 Blackjack Dealer Bust Percentages

[https://www.liveabout.com/blackjack-dealer-bust-percentages-537109#:~:text=When%20the%20dealer%20is%20showing,Ace%2C%2010%2C%20and%209](https://www.liveabout.com/blackjack-dealer-bust-percentages-537109#:~:text=When%20the%20dealer%20is%20showing,Ace%2C%2010%2C%20and%209).

文章中的数据如下

##### Blackjack Dealer Bust Percentages

| Dealer Card | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | Ace |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Bust % | 35% | 37% | 40% | 42% | 42% | 26% | 24% | 23% | 23% | 17% |

```
这个数据中A的爆牌率显示的是17%，个人观感，应该是有一点差错。
```

#### 二 Blackjack Odds and Probability

[https://www.onlineblackjackrealmoney.org/strategy/blackjack-odds-probability](https://www.onlineblackjackrealmoney.org/strategy/blackjack-odds-probability)

文章中的数据如下

##### Dealer Bust Out Rate

| Dealer Card | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | Ace |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Bust % | 35.30% | 37.56% | 40.28% | 42.89% | 42.08% | 25.99% | 23.86% | 23.34% | 21.43% | 11.65% |

```
这个数据基本和我运算的结果一致
```

文章中还有一个数据值得一说，当前牌值点数，如果需要再次hit的时候，对应的爆牌率

##### Busting when Hitting

| Cards | 20 | 19 | 18 | 17 | 16 | 15 | 14 | 13 | 12 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Bust % | 92% | 85% | 77% | 69% | 62% | 58% | 56% | 39% | 31% |

```
其实这个表值不需要记忆，可以推算出来，在Blackjack中的牌类型，A,2,3,,,,10,J,Q,K一共13张。
任意一种牌类型出现的概率就是1/13=7.69%
如果手里现在20点，那么只有拿到A才不会爆牌，所以，有12种牌类型会导致爆牌，12/13≈92%
如果手里现在19点，那么只有拿到A，2才不会爆牌，所以，有11种牌类型会导致爆牌，11/13≈85%
其他依次类推

可以简化记忆一下，每一种牌类型出现的概率为8，直接计算就好。
比如拿到16的爆牌率，就是6，7，8，9，T,J,Q,K 一共8张，则爆牌率就是64%。
```

\--the end
