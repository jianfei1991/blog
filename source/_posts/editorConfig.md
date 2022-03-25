---
title: editorConfig
comments: true
date: 2019-07-04 17:04:05
tags:
---

### 属性
属性 | 释义
 :-: | :-: 
root | 表明是最顶层的配置文件，发现设为true时，才会停止查找.editorconfig文件。
indent_style | 设置缩进风格，tab或者空格。tab是hard tabs，space为soft tabs。
indent_size  | 缩进的宽度，即列数，整数。如果indent_style为tab,则此属性默认为tab_width。
tab_width  | 设置tab的列数。默认是indent_size。
end_of_line |  换行符，lf、cr和crlf
charset |  编码，latin1、utf-8、utf-8-bom、utf-16be和utf-16le，不建议使用utf-8-bom。
trim_trailing_whitespace |  设为true表示会除去换行行首的任意空白字符。
insert_final_newline | 设为true表明使文件以一个空白行结尾

vscode + prettier
首先安装prettier
格式化快捷键 alt + shift + f


保存自动格式化功能
* cmd + , 唤起设置 
* 搜索 " editor.formatOnSave " 
* 设置为true


### 在vscode中使用editorconfig的正确姿势

#### 如何使用
* 在当前项目根目录下添加.editorconfig(定义格式化规则,不会直接被vscode直接解析)
* 安装EditorConfig扩展(读取editorconfig文件中定义的规则,并覆盖user/workspace settings中的对应规则)
* 安装editorconfig依赖包 (npm i -g editorconfig | npm i -D editorconfig) (不安装的可能会导致editorConfig无法正常解析我们在第一步定义的editorconfig文件)
* 手动格式化代码( alt + shif + f ) (让经过EditorConfig扩展覆盖后的user/workspace settings生效)
	