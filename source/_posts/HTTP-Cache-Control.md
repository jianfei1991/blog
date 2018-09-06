---
title: HTTP Cache-Control
comments: true
date: 2018-08-09 15:49:49
tags:
---

Cache-Control指定了请求和响应遵循的缓存机制。好的缓存机制可以减少对网络带宽的占用，可以提高访问速度，提高用户的体验，还可以减轻服务器的负担。

https://www.cnblogs.com/chinajava/p/5705169.html

#### no-cache和no-store的区别
网上有好多关于no-cache和no-store的区别，但是长篇大论，感觉也没有怎么讲清楚。

最近看了《图解HTTP》这本书，书上讲到了这两者的区别：

no-cache从字面意义上很容易误解为不缓存，但是no-cache代表不缓存过期的资源，缓存会向服务器进行有效处理确认之后处理资源，更确切的说，no-cache应该是

```nginx
do-not-serve-from-cache-without-revalidation
```

而no-store才是真正的不进行缓存。

使用no-cache的目的就是为了防止从缓存中获取过期的资源。



<!-- more -->

Cache-Control主要有以下几种类型：

(1) 请求Request：

[1] no-cache  ---- 不要读取缓存中的文件，要求向WEB服务器重新请求

[2] no-store    ---- 请求和响应都禁止被缓存
[2] max-age： ---- 表示当访问此网页后的max-age秒内再次访问不会去服务器请求，其功能与Expires类似，只是Expires是根据某个特定日期值做比较。一但缓存者自身的时间不准确.则结果可能就是错误的，而max-age,显然无此问题.。Max-age的优先级也是高于Expires的。
[3] max-stale  ---- 允许读取过期时间必须小于max-stale 值的缓存对象。 
[4] min-fresh ---- 接受其max-age生命期大于其当前时间 跟 min-fresh 值之和的缓存对象

[5] only-if-cached ---- 告知缓存者,我希望内容来自缓存，我并不关心被缓存响应,是否是新鲜的.

[6] no-transform   ---- 告知代理,不要更改媒体类型,比如jpg,被你改成png.



(2) 响应Response：

[1] public    ---- 数据内容皆被储存起来，就连有密码保护的网页也储存，安全性很低
[2] private    ---- 数据内容只能被储存到私有的cache，仅对某个用户有效，不能共享
[3] no-cache    ---- 可以缓存，但是只有在跟WEB服务器验证了其有效后，才能返回给客户端

[4] no-store  ---- 请求和响应都禁止被缓存

[4] max-age：   ----- 本响应包含的对象的过期时间
[5] Must-revalidate    ---- 如果缓存过期了，会再次和原来的服务器确定是否为最新数据，而不是和中间的proxy

[6] max-stale  ----  允许读取过期时间必须小于max-stale 值的缓存对象。 

[7] proxy-revalidate  ---- 与Must-revalidate类似，区别在于：proxy-revalidate要排除掉用户代理的缓存的。即其规则并不应用于用户代理的本地缓存上。

[8] s-maxage  ---- 与max-age的唯一区别是,s-maxage仅仅应用于共享缓存.而不应用于用户代理的本地缓存等针对单用户的缓存. 另外,s-maxage的优先级要高于max-age.

[9] no-transform   ---- 告知代理,不要更改媒体类型,比如jpg,被你改成png.