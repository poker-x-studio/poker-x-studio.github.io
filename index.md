
## 博客地址: [https://pokerxstudio.blogspot.com/](https://pokerxstudio.blogspot.com/)


## 更新历史

- 2023-7-7:【go后端】编码blackjack庄家优势统计
  - 10个goroutine,每个goroutine循环1000次,一共是循环10000次(10*1000)
  - 6副牌游戏,游戏完6副牌算一次,闲家每手押注额为1
  - 规则为标准策略,可Surrender,分牌后可Double down
  - 结果输出:"player_min_profit:-36.00,player_max_profit:31.50,sum_round:560060,sum_score:-13006.00,avarg_score:-0.0232,"
  - 结果解析:每次循环大约56手牌[560060/10000],闲家最多输36,最多赢31.5,平均每手输0.0232,按每次闲家押注100算的话,闲家每把都输2.32
- 2023-6-29:建立poker-x-studio.github.io
- 2023-5-x:编码Telegram游戏机器人百家乐
  - Telegram游戏机器人,游戏逻辑百家乐规则
  - 可以押注，结算
  - 测试群??? 
- 2023-5-x:编码Telegram游戏机器人骰子快三
  - Telegram游戏机器人,游戏逻辑骰子快三
  - 可以押注，结算
  - 测试群??? 
