---
title: 'java相关命令小记(jstack,jstat,jmap,jps)'
categories: java
abbrlink: d089d8a4
date: 2018-02-08 09:50:24
---

>  简单记录一下相关命令，有些博客写的不错的就直接引用了

jstack(查看线程)、jmap(查看内存)、jstat(性能分析)

<!-- more -->

1.jstat -gc pid time (jstat -gc 12538 5000)
&emsp;&emsp;5秒一次显示进程号为12538的java进程的GC情况
&emsp;&emsp;&emsp;S0C：年轻代中第一个survivor（幸存区）的容量 (字节) 
&emsp;&emsp;&emsp;S1C：年轻代中第二个survivor（幸存区）的容量 (字节) 
&emsp;&emsp;&emsp;S0U：年轻代中第一个survivor（幸存区）目前已使用空间 (字节) 
&emsp;&emsp;&emsp;S1U：年轻代中第二个survivor（幸存区）目前已使用空间 (字节) 
&emsp;&emsp;&emsp;EC：年轻代中Eden（伊甸园）的容量 (字节) 
&emsp;&emsp;&emsp;OC：Old代的容量 (字节) 
&emsp;&emsp;&emsp;OU：Old代目前已使用空间 (字节) 
&emsp;&emsp;&emsp;PC：Perm(持久代)的容量 (字节) 
&emsp;&emsp;&emsp;PU：Perm(持久代)目前已使用空间 (字节) 
&emsp;&emsp;&emsp;YGC：从应用程序启动到采样时年轻代中gc次数 
&emsp;&emsp;&emsp;YGCT：从应用程序启动到采样时年轻代中gc所用时间(s) 
&emsp;&emsp;&emsp;FGC：从应用程序启动到采样时old代(全gc)gc次数 
&emsp;&emsp;&emsp;FGCT：从应用程序启动到采样时old代(全gc)gc所用时间(s) 
&emsp;&emsp;&emsp;GCT：从应用程序启动到采样时gc用的总时间(s) 
		
 相关内容：http://www.importnew.com/3146.html
		
2.jps -lm 查看java进程pid、主类的名称、程序参数

  
3.jstack pid
  相关内容：http://guafei.iteye.com/blog/1815222
