---
title: webpack踩坑记
comments: true
date: 2018-11-04 02:30:57
tags:
---

#### 问题描述

项目中的某个依赖包引用了base58,base58引用了base-x

    "bs58": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/bs58/-/bs58-4.0.1.tgz",
      "integrity": "sha1-vhYedsNU9veIrkBx9j806MTwpCo=",
      "requires": {
        "base-x": "^3.0.2"
      }
    },
    
    "base-x": {
          "version": "3.0.5",
          "resolved": "https://registry.npmjs.org/base-x/-/base-x-3.0.5.tgz",
          "integrity": "sha512-C3picSgzPSLE+jW3tcBzJoGwitOtazb5B+5YmAxZm2ybmTi9LNgAtDO/jjVEBZwHoXmDBZ9m/IELj3elJVRBcA==",
          "requires": {
            "safe-buffer": "^5.0.1"
          }
        }
突然有一天base-x升级到了3.0.5后，项目编译代码中base-x部分 编译出的为es6



思路一：通过package.json把base-x固定在3.0.2

思路二：把编译后的dist目录通过gulp等手段再次编译为es5
思路三：通过polifile