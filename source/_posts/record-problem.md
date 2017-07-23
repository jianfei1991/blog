---
title: record problem
comments: true
date: 2017-01-13 17:22:30
tags:
---


## iphone webview 调试

一切调通后 safari里面点击对应需要调试的页面 手机页面顶部显示“此网页出现问题，已重新载入”并重新加载，safari出现inspector后自动关闭
>短期解决方案：安卓+weinre


![图片测试](record-problem/Mobile-debug.png)


## weinre
1、安装
2、执行weinre --boundHost -all-
3、打开localhost:8080 找到页面中的 Target Script
4、把Target Script 粘贴到需要调试的html中（注：如果是localhost需要换成本机的IP）
开始调试