---
title: 简单定位线上java服务cpu100%问题
categories: java
abbrlink: fbc89d93
date: 2018-02-08 11:43:41
---

1、**找到最耗cpu的进程**
&emsp;<font color="#FF0000">top -c </font> 显示进程信息
&emsp;按下大写 <font color="#FF0000"> P </font> 按照cpu使用率排序
&emsp;找到最耗cpu的进程pid为：109878

2、**找到最耗cpu的线程**
&emsp;<font color="#FF0000">top -Hp 109878 </font> 显示线程信息
&emsp;按下大写 <font color="#FF0000"> P </font> 按照cpu使用率排序
&emsp;找到最耗cpu的线程id为：109921

<!-- more -->

3、**线程id转为16进制**
&emsp;printf "%x\n" 109921
&emsp;1ad61

4、**查看堆栈信息**
&emsp;<font color="#FF0000">jstack 109878 | grep "0x1ad61" -C5 --color</font>

**显示结果**：
"Log4j2-AsyncLoggerConfig-2" daemon prio=10 tid=0x00007fb808672000 nid=<font color="#FF0000">0x1ad61</font> runnable [0x00007fb862ffe000]
&emsp;&emsp;java.lang.Thread.State: TIMED_WAITING (parking)

github上有老哥整理了一些常用的脚本，可以参考参考.
https://github.com/oldratlee/useful-scripts