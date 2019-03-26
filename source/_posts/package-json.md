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

指定版本号
（1）指定版本：比如"classnames": "2.2.5"，表示安装2.2.5的版本

（2）波浪号~+指定版本：比如 "babel-plugin-import": "~1.1.0",表示安装1.1.x的最新版本（不低于1.1.0），但是不安装1.2.x，也就是说安装时不改变大版本号和次要版本号

（3）^+指定版本：比如 "antd": "^3.1.4",，表示安装3.1.4及以上的版本，但是不安装4.0.0，也就是说安装时不改变大版本号。