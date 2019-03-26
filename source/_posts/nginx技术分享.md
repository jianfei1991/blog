---
title: linux && nginx技术分享
comments: true
date: 2018-10-23 13:16:32
tags:
---



### 技术分享背景

​	前端开发人员成长的必经之路

​	与运维合作更顺畅

​	在业务场景下，可以想到ngixn等解决方案，找ops帮忙解决

### 前端开发可以用nginx做什么


### 操作系统概述

Windows -  x shell、git bash

mac 基于unix

linux 特指内核，常见发行版：ubuntu、CentOS



### ssh远程登陆

服务器生成

-p、-i

### linux 使用

文件操作
​	chmod
​	scp
alias 快捷设置 .bashrc .zshrc
top
ctrl+s 暂停屏幕输出
ctrl+q 恢复屏幕输出
ctrl+a、ctrl+e

服务管理命令 systemctl

systemctl status nginx
systemctl enable nginx 开机启动nginx


ps aux | grep nginx
kill (-9) pid

## Nginx
ip_hash
upstream
gzip:on 



### samba 

局域网资源共享