---
title: vue中给svg组件的dom元素绑定点击事件
comments: true
date: 2018-01-13 02:26:46
tags:
---


### 问题描述:在vue中 给svg组件绑定dom元素，因为元素太多，用的jquery或者js原生绑定事件
测试过程中，复用svg组件分别为 A、B
如果用dom元素绑定点击事件，触发A或者B中任意一个点击事件，会同时触发A和B两个相同元素绑定的点击事件

暂无解决方案！！！难道要给众多的g标签分别添加绑定事件？


g标签内很多重复的东西，难道要把众多的g标签用v-for循环出来？


https://stackoverflow.com/questions/25886802/svg-path-convert-into-json


var d = "M 93.00,444.00\
       C 93.00,444.00 114.00,506.00 114.00,506.00\
         102.30,512.28 100.00,518.71 100.00,531.00\
         100.00,531.00 86.00,534.00 86.00,534.00\
         86.00,534.00 68.95,485.00 68.95,485.00\
         68.95,485.00 58.00,452.00 58.00,452.00\
         58.00,452.00 93.00,444.00 93.00,444.00 Z\
       M 75.00,458.00\
       C 75.00,458.00 79.00,458.00 79.00,458.00\
         78.99,466.29 79.26,463.93 76.00,471.00\
         76.00,471.00 86.00,471.00 86.00,471.00\
         82.12,462.60 83.00,464.37 83.00,455.00\
         83.00,455.00 75.00,458.00 75.00,458.00 Z"


         

d = d.replace(/\s{2,}/g, ' '); // Remove multiple spaces
d = d.replace(/([a-zA-Z])\s[0-9]/g, '$1,'); // Add letters to coords group
d = d.split(" "); // Split on space

var coords = [];

for (var i = 0; i < d.length; i++) {
    var coordString = d[i];
    var coordArray = coordString.split(",");
    
    var coord = {
        x: coordArray[coordArray.length - 2],
        y: coordArray[coordArray.length - 1]
    };
    
    if (coordArray.length > 2) {
        coord.path = coordArray[0];
    }
    
    coords.push(coord);
    
}

console.log(coords);