---
title: "在manjaro & arch 上使用坚果云"
date: 2020-10-07
categories:
  - 常用工具
tags:
  - manjaro
  - 坚果云
---

#前言
最近在找可以在manjaro下用的画图软件，vscode的Draw.io插件很好用，在线的用过ProcessOn,非常好用！但免费的有数量限制，偶然在网上看到坚果云上的画图功能可以白嫖～～～，于是上官网看到居然还有Linux下的客户端  
要知道很少有软件会出linux版本的客户端，看到有linux版本的客户端，好感度+1。而官网给的只有Ubuntu/Fedora/Debian的说明，而不幸，我用的Manjaro就没有。

## 方法一（推荐）
其实万能的arch库中是能坚果去的包的，可以直接使用pacman或者yay安装
![](../assets/images/jianguo1.png)

``` shell
sudo pacman -S nutstore
```

``` shell
yay -S nutstore
```
## 方法二
[官网](https://www.jianguoyun.com/s/downloads/linux#install_for_kdexfce)提供了KDE/XFCE桌面系统的安装方法,以及从源代码编译安装的方法，但也没有提供manjaro或者是arch系统的安装方法，我用的manjaro的kde版本.但参照对应的流程就可以直接安装


- 安装依赖的软件包（主要是这里有区别，其它按照官网的来就行了）
坚果云Linux客户端依赖于这些包: glib2.0-dev, gtk2.0-dev, libnautilus-extension-dev, gvfs-bin. 可以用pac命令安装

``` shell
sudo pacman -S glib2 gtk2 libnautilus-extension gvfs
```

- 下载坚果云的二进制组件
``` shell
 wget https://www.jianguoyun.com/static/exe/installer/nutstore_linux_dist_x64.tar.gz -O /tmp/nutstore_bin.tar.gz
 ```
 - 解压缩二进制组件包
 ``` shell
 mkdir -p ~/.nutstore/dist && tar zxf /tmp/nutstore_bin.tar.gz -C ~/.nutstore/dist
 ```

 - 安装坚果云菜单及图标
 ``` shell
  ~/.nutstore/dist/bin/install_core.sh
 ```

 安装完后可以直接在系统启动的 应用-->网络-->坚果云打开
