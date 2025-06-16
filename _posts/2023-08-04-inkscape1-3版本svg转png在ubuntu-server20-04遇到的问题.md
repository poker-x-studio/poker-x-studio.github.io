---
title: "Inkscape1.3版本,svg转png在Ubuntu Server20.04遇到的问题"
date: 2023-08-04
categories: 
  - "linux"
---

### 一 Inkscape程序

[https://inkscape.org/](https://inkscape.org/)

Inkscape是矢量图形编辑器，以自由软件许可发布与使用。该软件的开发目标是成为强大的绘图软件，且能完全遵循与支持XML、SVG及CSS等开放性的标准格式，而且是跨平台的应用程序，支持Windows、Mac OS X、Linux及类UNIX版等操作系统。\[维基百科\]

### 二 开发的后端go程序，需求svg转png，刚好选用Inkscape程序。在Windows10，Ubuntu桌面版\[Ubuntu 22.04.2 LTS\]运行都是ok的，但是 Ubuntu Server 上运行会出错。

```
glibmm-WARNING Failed to wrap object of type 'GtkRecentManager'
```

Ubuntu Server 版本

```
Distributor ID: Ubuntu
Description:    Ubuntu 20.04.5 LTS
Release:    20.04
Codename:   focal
```

Ubuntu Server 版本上安装的Inkscape版本是1.3的，错误和这个url地址错误一样 [https://gitlab.com/inkscape/inbox/-/issues/6903](https://gitlab.com/inkscape/inbox/-/issues/6903)

```
Version info
    Inkscape 1.3-dev (8a0d19d550, 2022-05-02, custom) Linux Mint 20
    Inkscape 1.2-beta (0d9a0fea06, 2022-04-08) Linux Mint 20

Doesn't occur in Inkscape 1.1.2 (ccedf6bf22, 2022-02-24) Linux Mint 20
```

根据这个帖子的内容，所以，卸载1.3新版本,改安装 1.1 版本。

```
apt purge inkscape  
apt list | grep inkscape 
```

查看可以安装的版本，选择1.1版本安装。

```
apt install inkscape=1:1.1+rc+202105240936+c4e8f9ed74~ubuntu20.04.1
```

安装完成，后端就可以正常从svg转到png了。

Inkscape也支持svg转pdf格式。

\--the end
