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
> ## \# 1.
> April 4th,2017   Tuesday   Mostly Cloudy


### **脚本元素**

**有三个基本的脚本元素，作用是使JAVA代码可以直接插入servlet.**

*    一种是声明标签，在JAVA SERVLET的类体中放入一个变量的定义。静态的数据成员也可以如此定义。  
        `<%! int serverInstanceVariable = 1; %>`
*    一种是脚本标签，在JAVA SERVLET的类的_jspService()方法中放入所包含的语句。  
        `<% int localStackBasedVariable = 1; out.println(localStackBasedVariable); %>`
*    一种是表达式标签，在JAVA SERVLET的类中放入待赋值的表达式，表达式注意不能以分号结尾。  
        `<%= "expanded inline data " + 1 %>`

***

### **项目导出及部署**

**IntelliJ IDEA 将项目导出为 war(Web Archive) 包**

1. Project Structure *(项目结构)* --> Artifacts *(构件)* --> Add *(添加)* --> Web Application: Archive *(网络应用：存档文件)* --> For 'Project Name' *(给‘项目名’)*
2. 设置好Name *(名称)* 和Output directory *(输出路径)* 。Include in project build *(包括在项目构建)* 选项可选可不选。如果选择了，那么每次在运行项目时都会生成war包。如果不勾选则可以在后续的步骤中手动生成war包。
3. 点击加号选择Directory Content *(目录内容)* ，选择你当前项目的web目录，之后保存就可以啦。
4. 如果前面勾选了Include in project build *(包括在项目构建)* 选项，可以在运行项目时生成war包。如果没有勾选，可以通过Build *(构建)* -->Build Artifacts *(构建构件)* 来生成war包。

**使用 jar 命令将项目导出为 war(Web Archive) 包**

1.进入项目的 web 目录。  
`cd web目录路径`  
2.使用 jar 命令。   
`jar -cvf 文件名.war *`

**项目部署到 Tomcat 服务器**

1.把 war(Web Archive) 包拷贝到 Tomcat/webapps 目录下。  
2.启动 Tomcat 服务器。  
`cd Tomcat/bin目录路径`  
`startup.sh`

Tomcat 服务器会自动将 war(Web Archive) 包解压到 Tomcat/webapps 目录下。

***

### **JSP 注释**

**HTML 注释**  

* HTML 注释可以用于注释 HTML 代码，并和其他 HTML 代码一起被返回到浏览器上，对用户可见。  
`<!-- HTML 注释内容 -->`
* 在 JSP 文件中的 HTML 注释可以使用合法的 JSP 表达式。  
`<!-- Today is <%= new java.util.Date().toString() %> -->`

**JSP 注释**

* JSP 注释只会在 JSP 代码编辑的时候可见。  
`<%-- JSP 注释内容 --%>`

**JSP 程序段中的注释**

* 单行注释  
`<% // 单行注释内容 %>`
* 多行注释  
`<% /* 多行注释内容 */ %>`
