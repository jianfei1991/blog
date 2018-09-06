---
title: hexo介绍
date: 2017-01-03 16:43:19
tags:
---
>https://www.kancloud.cn/wizardforcel/hexo-doc/101374

* 需要安装Node.js、Git

* hexo init <folder> //进行初始化会自动生成下面这样的目录结构
<!-- more -->
```
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

* ## \_config.yml
配置文件，可以配置title、author、日期格式、deplpy--关联github的配置信息

* ## scaffolds
模板文件夹，新建文章的时候，Hexo会根据scaffold来建立文件

* ## source
资源文件夹。 除了\_post 文件夹之外，开头命名为\_的文件或文件夹和隐藏的文件将会被忽略。
Markdown和html文件会被解析并放到public文件夹，而其他文件会被拷贝过去

* ## themes
主题文件夹。Hexo会根据主题来生成静态页面
  - huno
    * 首页效果 看着还不错
  - yilia
    * 综合效果不错
    * 头像需要在yilia文件夹下的\_config.yml里面设置avator参数

* ## 开始写文章
$ hexo new "文章名"------通过这个命令来创建一篇新文章
