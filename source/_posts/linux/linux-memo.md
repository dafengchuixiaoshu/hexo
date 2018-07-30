---
title: linux 备忘
categories:
  - linux
tags:
  - 备忘
toc: true
comments: true
date: 2018-07-30 16:04:08
---

### 1. 非root启动80端口

- 1、首先修改文件所属用户为root：
	
		chown root nginx #这一步是必须的。否则即使u+s，也不管用哦。。

- 2、然后再加上s权限：
		
		chmod u+s nginx #添加S位的目的是让程序以root权限起，即使你用的不是root帐号。它也会以root帐号名义起。这时候就绕开端口BIND权限的问题。

- 3、再次查看权限描述的时候：

	-rwsr-xr-x 1 root root 2408122 Sep  5 16:01 nginx #这个时候切换到普通用户下再启动就没问题了。

### 2. 获取时间-精确到纳秒

	date "+%Y-%m-%d %H:%M:%S.%N" #可以结合管道cut,awk来保留几位小数点
	
### 3. 磁盘占用 du/df

- du -h --max-depth=2 | grep "G"

### 4. 文本操作

- awk -F ‘\”user_id\”:’ ‘{print $2}’ | awk -F ‘,’ ‘{print $1}’  | sort | uniq
- find ./ -name "*.cc" | xargs sed -i 's/\->ToString/\.ToString/g'

### 5. mysql文本：mysql_escape_string