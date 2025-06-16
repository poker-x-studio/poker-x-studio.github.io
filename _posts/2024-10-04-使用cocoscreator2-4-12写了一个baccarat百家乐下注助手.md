---
title: "使用CocosCreator[2.4.12]写了一个Baccarat百家乐下注助手"
date: 2024-10-04
categories: 
  - "baccarat"
  - "cocos-creator"
---

#### 记录一下整个过程

#### 一 Go后端起源

最初是使用Go计算了一下百家乐的各种概率，然后想探索一下 下注区策略/下注额策略，或者可以找到一种更加接近盈利的办法。 根据计算的结果来看，下注额的策略，其实归根到底就是 倍投。但因为赌场限额的问题，所以，全局倍投肯定是行不通的。只能使用局部倍投。 至于下注区策略，无论怎么下注，排除掉和的样本，胜率都只是接近50%，想在下注区就战胜赌场，个人感觉是不太可能。

#### 二 JavaScript前端\[开发IDE:Cocos Creator\]，打包Android APK

过程中，使用的工具以及可能需要留意的地方

- 2.1 工具Cocos Creator\[官网 [https://www.cocos.com/creator](https://www.cocos.com/creator)\] ，编码语言JavaScript
    - Cocos Creator最新版本3.8.3，我使用的版本 2.4.12
    - 首先需求大致确定，然后开始规划布局/场景/视图，再就是编码
    - 区分 节点和脚本
    - Scene除非必要，尽量少一些
    - 资源需要预加载
- 2.2 工具Visual Studio Code
    - 主要是脚本的编码和功能测试
    - 使用 Chrome浏览器调试
- 2.3 工具Android Studio
    - 打包APK，这部分比较繁琐，安装NDK\[Native Development Kit\],ADK\[Andorid Development Kit\]，JDK\[Jave Development Kit\],gradle等工具包。最好是有vpn，否则下载也许会有麻烦
    - 使用android模拟器查看日志
        
        ```
        1、打开夜神的安装目录：D:\Program Files\Nox\bin
        2、在安装目录空白处按住shift+鼠标右键,然后点击在“此处打开命令行”或者“在此处打开Powershell窗口”（win10）
        3、然后在命令行中输入命令 .\nox_adb logcat > log.txt
        4、日志就会不断输出到log.txt
        ```
        

#### 三 github项目baccarat\_helper

```
开源,地址:https://github.com/poker-x-studio/baccarat_helper 
```

![](https://poker-x-studio.github.io/images/baccarat_helper_2024-10-9.png) --the end
