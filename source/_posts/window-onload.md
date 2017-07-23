---
title: window onload
comments: true
date: 2017-03-09 13:24:32
tags:
---

## window.onload &&DOMContentLoaded
一般情况下，DOMContentLoaded事件要在window.onload之前执行，当DOM树构建完成的时候就会执行DOMContentLoaded事件，而window.onload是在页面载入完成的时候，才执行，这其中包括图片等元素。大多数时候我们只是想在DOM树构建完成后，绑定事件到元素，我们并不需要图片元素，加上有时候加载外域图片的速度非常缓慢。


随便照了几张大图简单测试了一下在几种方法第一行执行debugger
- window.onload 在图片资源加载完会后才出debugger
- DomContentLoaded、$(function(){})和$(document).ready(function(){})一样图片没有没有加载完就会出debugger