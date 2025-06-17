---
title: "使用postman测试websocket协议,多个数据包保存在saved messages列表"
date: 2023-08-24
categories: 
  - "other"
---

### 测试工具 postman [https://www.postman.com/](https://www.postman.com/)

#### 当前使用版本 Version 10.17.3[Windows]

以前使用postman测试，主要是测试http接口，本次因为在线平台后端go和前端 js通讯，协议为websocket，所以，也需要测试ws协议，postman同样可以胜任

![](https://poker-x-studio.github.io/images/image_2023-08-24_11-34-17.png)

- 创建好websocket协议请求之后，可以点击connect进行连接，
- ws的测试，通常包含多个数据包，可以保存在 saved messages 列表里面
- saved messages 可以新增和删除 数据包
- 点击 saved messages 列表，选择某个 message，然后点击 send，就可以发送一个数据包

--the end
