---
title: git相关操作
comments: true
date: 2019-03-25 15:05:06
tags:
---


### gitignore 添加已经被跟踪的文件、文件夹
* .gitignore只能忽略那些原来没有被track的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。
* 解决方法就是先把本地缓存删除（改变成未track状态），然后再提交:
* git rm -r --cached .
* git add .
* git commit -m 'update .gitignore'


### 实用技巧
```shell
#查询a.vue文件的提交历史记录
git log --stat | grep -B 6 a.vue  

## git log 配置
git config --global alias.lm  "log --no-merges --color --date=format:'%Y-%m-%d %H:%M:%S' --author='你的名字！自己修改！' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Cblue %s %Cgreen(%cd) %C(bold blue)<%an>%Creset' --abbrev-commit"


git config --global alias.lms  "log --no-merges --color --stat --date=format:'%Y-%m-%d %H:%M:%S' --author='你的名字！自己修改！' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Cblue %s %Cgreen(%cd) %C(bold blue)<%an>%Creset' --abbrev-commit"


git config --global alias.ls "log --no-merges --color --graph --date=format:'%Y-%m-%d %H:%M:%S' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Cblue %s %Cgreen(%cd) %C(bold blue)<%an>%Creset' --abbrev-commit"


git config --global alias.lss "log --no-merges --color --stat --graph --date=format:'%Y-%m-%d %H:%M:%S' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Cblue %s %Cgreen(%cd) %C(bold blue)<%an>%Creset' --abbrev-commit"
```
 <!-- more -->


##  git 对比两个分支差异
- [git 对比两个分支差异](https://blog.csdn.net/u011240877/article/details/52586664)

##  git 小游戏
- [githug](https://www.jianshu.com/p/482b32716bbe)
- [git在线学习](https://learngitbranching.js.org/?demo)

## git学习笔记
- [git tag相关](https://www.cnblogs.com/wufangfang/p/6086239.html)
- [更改git log展示](https://www.cnblogs.com/bellkosmos/p/5923439.html)
 