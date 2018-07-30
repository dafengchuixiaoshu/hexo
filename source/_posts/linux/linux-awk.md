---
title: linux awk
categories:
  - linux
tags:
  - linux
  - awk
toc: true
comments: true
date: 2018-07-25 17:40:42
---

### 命令格式

- awk [options] 'script' var=value file(s) 
- awk [options] -f scriptfile var=value file(s)

### 描述


### 参数

- -F fs fs 指定输入分隔符，fs可以时字符串或正则表达式
- -v var=value 赋值一个用户定义变量，将外部变量传递给awk
- -f scriptfile 从脚本文件中读取awk命令