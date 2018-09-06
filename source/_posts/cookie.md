---
title: cookie
comments: true
date: 2017-04-15 10:55:13
tags:
---


## setCookie方法在localhost域名下不能存，在127.0.0.1下确可以存取

```
something that wasn't made clear to me here and totally confused me for a while was that domain

names must contain at least two dots (.),

hence 'localhost' is invalid and the browser will refuse to set the cookie!

instead for localhost you should use false.

to make your code work on both localhost and a proper domain, you can do this:
```

## 解决方案一： localhost指向127.0.0.1

## 解决方案二： 改hosts

## 三：php解决方案（网上搜的，看不明白php还。。。。）
```
<?php  
$domain = ($_SERVER['HTTP_HOST'] != 'localhost') ? $_SERVER['HTTP_HOST'] : false;  
setcookie('cookiename', 'data', time()+60*60*24*365, '/', $domain, false);  
?> 
```