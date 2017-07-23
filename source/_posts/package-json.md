---
title: package.json
comments: true
date: 2017-03-18 15:20:56
tags:
---

### --save-dev && --save
package.json 中有dependencies和devDependencies<br/>
dependencies是用在开发完上线模式的，<br/>
devDependencies是用在开发模式<br/>

### 依赖的版本控制
  
  有的时候看到package.json中安装的模块版本号前面有一个波浪线。例如: ~1.2.3 这里表示安装1.2.x以上版本。但是不安装1.3以上。