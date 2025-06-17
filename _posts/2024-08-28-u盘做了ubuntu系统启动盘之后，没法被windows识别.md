---
title: "U盘做了Ubuntu系统启动盘之后，没法被Windows识别"
date: 2024-08-28
categories: 
  - "linux"
---

#### 一 使用U盘制作Ubuntu系统启动盘之后，安装完，然后用于Windows copy文件的时候，不被识别。

#### 二 方法如下：【参看网络资料】

- 1.1、下载DiskGenius Version: 5.6.1.1580 工具

下载地址：[https://www.diskgenius.com/dyna_download/?software=DGEng5611580_x64.zip](https://www.diskgenius.com/dyna_download/?software=DGEng5611580_x64.zip)

或 官网下载页 [https://www.diskgenius.com/download.php](https://www.diskgenius.com/download.php)

- 2.2、点击DiskGenius.exe，启动进程
    
- 2.3、在DiskGenius主界面，右键点击不被识别的U盘，Erase Sectors[清除扇区]
    

等待20分钟左右，直到完成清除 
![](https://poker-x-studio.github.io/images/image_2024-08-28_10-35-06.png)

- 2.4、然后U盘就可以被格式化了

--the end
