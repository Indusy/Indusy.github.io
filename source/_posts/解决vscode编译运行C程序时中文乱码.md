---
title: 解决vscode编译运行C程序时中文乱码
tags: 踩坑
categories: Windows
keywords: 'Vscode,乱码'
toc: false
cover: /img/vscode.png
abbrlink: 32775
date: 2020-04-28 22:47:22
description:
---
# 解决vscode编译运行C程序时乱码


---   

如题，由于Windows控制台的GBK编码，很多程序的中文乱码现象在Windows下很常见。今天在用vscode运行C代码的时候发现中文会乱码，因为之前有过乱码的经验就重装了系统。    

---    

重装后现象依旧如此，于是在网上找到了解决办法：其实很简单，换编译器就行了。   
之前用的MingGW和VS自带的编译器都会乱码，换到CygWin就可以了，正常输出中文无乱码。   

---    

链接：<http://www.cygwin.com>   
安装过程中为了加速可以选择国内源：<http://mirrors.163.com/cygwin>
