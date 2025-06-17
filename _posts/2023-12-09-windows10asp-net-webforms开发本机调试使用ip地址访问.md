---
title: "Windows10,ASP.NET webforms开发,本机调试使用IP地址访问"
date: 2023-12-09
categories: 
  - "asp-net"
---

近期在Windos系统下，熟悉接手一个 ASP.NET webforms开发模式的web项目，IDE开发环境是Visual Studio 2015，遇到需要IP访问的需求。

```
ASP.NET 提供了三种用于创建 Web 应用程序的框架：Web Forms、ASP.NET MVC 和 ASP.NET 网页。
```

### 一 参看资料链接

```
http://blog.baibaota.com/1415.html
```

大体思路是:

- 修改 IIS Express 的配置文件 applicationhost.config【最好是关闭掉 IIS Express 进程之后，修改后保存】。
- 重新开启Visual Studio，特别需要留意，必须是 管理员身份 开启 Visual Studio【在 Visual Studio 快捷方式上右键】。
- 然后再次运行项目，使用IP地址访问。

![](https://poker-x-studio.github.io/images/Snipaste_2023-12-09_15-02-46-1.png) 
![](https://poker-x-studio.github.io/images/Snipaste_2023-12-09_15-08-20-1.png)

### 二 如果需要使用公网IP进行访问

[https://ngrok.com/](https://ngrok.com/) 可以使用ngrok软件的反向代理功能，实现外网访问内网网站服务 免费试用

### 三 开发中如果需要升级.net framework版本

在新建项目的时候，可以点击 更多Framework... 链接，跳转到 官方下载 framework 开发这工具包 
![](https://poker-x-studio.github.io/images/Snipaste_2023-12-09_15-20-02.png)

--the end
