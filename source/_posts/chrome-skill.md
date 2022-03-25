---
title: chrome skill
comments: true
date: 2019-06-25 20:17:24
tags:
---

## copying && saving

	1. copy(location.href) ==> ctrl + v
	2. console出来的对象,通过右键==》Store as global variable 来保存为全局变量

## 快捷键和通用技巧

 <!-- more -->
|快捷键 | 用途
 :- | :-: | :-:
 | cmd + option + I | 打开控制台
 | cmd + option + U | 查看源码
 | cmd + shift + D  | 底部-右部切换控制台窗口
 | cmd + [ or ]     | 左右切换控制台面板
 | cmd + shift + M | 切换手机模拟模式和普通模式
css 数字值调试 | |
 | cmd + ⬆or⬇ | 100
 | shift + ⬆or⬇ | 	10
 | option + ⬆or⬇ | 0.1
debugger | |
 | cmd + \ | resume/pause script execution <br>恢复/暂停脚本执行 
 | cmd + ' | step over next function call <br>跨过，实际表现是不遇到函数时，执行下一步。遇到函数时，不进入函数直接执行下一步。
 | cmd + ;	| step into next function call <br>跨入，实际表现是不遇到函数时，执行下一步。遇到到函数时，进入函数执行上下文。
 | cmd + shift + ; | step out of current function <br> 跳出当前函数



## 使用Command(命令)

在控制台中使用 CMD + shift + P 调用命令面板

cmd | 用途
:-: | :-:
show timestamps | 控制台显示输出时间
capture full size screenshot | 截屏(包括滚动区域)

## 代码块的使用

Sources面板 =》 Snippets中可以保存代码
> **用途** 比如你需要经常在某一个项目中执行某一些代码,这些代码又不能放进仓库上线
> **应用场景** 对一个有大量照片和身份证数据的后台,想去看美女照片,这种代码不可能发版,存到snippets中,打开后台,执行保存好的代码块………………………………………………
> **代码块快捷查找** CMD + p => 输入“!”+snippet名称

## console

### console.assert
> 当我们传入的第一个参数为 假 时，console.assert 打印跟在这个参数后面的值。
```javascript
value = null
if(!value){
	console.log("value"+'为空')
}
```
```javascript
value = null
console.assert(value,"value"+'为空')
```
通过它，你可以摆脱令人讨厌的 if 表达式，还可以获得堆栈信息。
> NodeJS 版本 ≤ 10.0 ， console.assert 可能会中断后面代码的执行，但是在 .10 的版本中被修复了(当然，在浏览器中不存在这个问题)

### console.log

let a = 1, b = 2;
console.log({a,b})
console.table({a,b})
打印dom使用 console.dir
console.log('%c123',"font-size:50px;color:red;") //%c是关键


### console中的"$"

$0 dom选择
$_ 对上次的结果进行饮用
$i 控制台安装npm 包 \_进行调用 （需要安装Console Importer插件）

### console的"bug"

let obj = {a:1,b:2};
console.log(obj)
obj.a=2
console.log(obj)

> **原因** console 中打印出的对象，在你打印出他内容之前，是以引用的方式保存的。



### 异步的console

