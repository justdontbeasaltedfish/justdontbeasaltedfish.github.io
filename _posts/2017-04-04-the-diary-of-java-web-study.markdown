---
layout:     post
title:      "The diary of java web study"
subtitle:   " \"zero to one\""
date:       2017-04-04 17:04:00
author:     "justdontbeasaltedfish"
header-img: "./img/p551789496.jpg"
tags:
    - Diary
---
> ### \# 1.
> April 4th,2017   Tuesday   Mostly Cloudy


脚本元素
有三个基本的脚本元素，作用是使JAVA代码可以直接插入servlet.

*    一种是声明标签，在JAVA SERVLET的类体中放入一个变量的定义。静态的数据成员也可以如此定义。
        '<%! int serverInstanceVariable = 1; %>'
*    一种是脚本标签，在JAVA SERVLET的类的_jspService()方法中放入所包含的语句。
        '<% int localStackBasedVariable = 1; out.println(localStackBasedVariable); %>'
*    一种是表达式标签，在JAVA SERVLET的类中放入待赋值的表达式，表达式注意不能以分号结尾。
        '<%= "expanded inline data " + 1 %>'
