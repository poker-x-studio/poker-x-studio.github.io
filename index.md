
## 一 博客地址: [https://pokerxstudio.blogspot.com/](https://pokerxstudio.blogspot.com/) 关注扑克类游戏


|时间[倒序]|博客主题|
|---|---|
|||
|||
|||
|||
|2023-7-14|[德州扑克中的底池赔率pot odds](https://pokerxstudio.blogspot.com/2023/07/pot-odds.html)|
|2023-7-13|[终极德州扑克Ultimate Texas Holdem，7张牌出现一对的概率](https://pokerxstudio.blogspot.com/2023/07/ultimate-texas-holdem7.html)|
|2023-7-13|[Blackjack-21点 庄家闲家胜率统计](https://pokerxstudio.blogspot.com/2023/07/blackjack-21.html)|

## 二 更新历史[时间倒序]


---
- 2023-7-x:统计部分扑克类游戏的概率
  - 开发语言:go
  - 开发环境:vscode/windows/ubuntu
  - 10个goroutine,每个goroutine循环1万次,一共是循环10万次(10*10000)
  - Blackjack 21点
    - 6副牌[去掉大小鬼],游戏完6副牌算一次,最小压注10,最大压注1000,初始筹码10000
    - 玩法策略为标准策略,可Surrender,分牌后可Double down
    - 下注策略为5种策略[全下,固定额度,马丁格尔策略,斐波那契策略,凯利策略]
    - 庄家胜率为51%,push概率为8%,闲家胜率为41%
  - Texas holdem 德州扑克
    - 5张公共牌在flop,turn,river圈各牌型出现的概率 
  - Ultimate Texas holdem 终极德州扑克 
    - 5张公共牌+2张手牌组合成至少一对的概率[应用场景为river圈,当玩家没有组合成一对的时候,是否应该下注] 
  
- 2023-6-29:建立poker-x-studio.github.io

---
- 2023-6-x:Telegram游戏机器人-百家乐
  - 开发语言:go
  - 开发环境:vscode/windows/ubuntu
  - Telegram前端展示
  - 每次结果由加密货币trx交易hash值,按固定规则,提取最多6张牌,按百家乐规则补牌
  - 玩家可以押注庄,闲,对子,和等
  - 游戏中有三种角色:闲家,庄家,平台
    - 闲家:获得盈利的方式是压注和返水
    - 庄家:按不同组合定式赔率进行赔付,负责闲家返水
    - 平台:无论是庄家还是闲家,赢了就扣除千分之五[可配置]服务费
  - 充值货币当前支持usdt-trc20,usdt-erc20
  - 机器人测试telegram群: 

--- 
- 2023-5-x:Telegram游戏机器人-骰子快三
  - 开发语言:go
  - 开发环境:vscode/windows/ubuntu
  - Telegram前端展示,
  - 每次结果由加密货币trx交易hash值,按固定规则,提取三颗骰子
  - 玩家可以押注骰子的一颗[单骰],两颗[对子],三颗[豹子],三颗和值[大,小,单,双，和值]等不同组合定式，对应不同的赔率
  - 游戏中有三种角色:闲家,庄家,平台
    - 闲家:获得盈利的方式是压注和返水
    - 庄家:按不同组合定式赔率进行赔付,负责闲家返水
    - 平台:无论是庄家还是闲家,赢了就扣除千分之五[可配置]服务费
  - 充值货币当前支持usdt-trc20,usdt-erc20
  - 机器人测试telegram群: 

---