---
title: mysql
comments: true
date: 2017-04-15 12:25:46
tags:
---

# 使用MySQL数据库
	登录
		MySQL运行时 可以通过命令行 mysql -h 主机名 -u 用户名 -p
			-h 制定要登录的主机名，登录当前及其该参数可以省略
	创建一个数据库
		create database 数据库名[其它选项就]
		例如：create database samp_db character set gbk;
		(为了便于在命令提示符下显示中文character set gbk 将数据库字符编码指定为gbk)
		(创建成功时会得到 Query OK, 1 row affected(0.02 sec) 的响应)