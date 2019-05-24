---
title: GitHub访问异常缓慢的处理办法
date: 2019-5-24
tags: [GitHub]
---

#####  GitHub访问速度满的解决方案
>  因为github是一个国外网站，所以访问速度有所缓慢，但是我们可以通过一些技术，让我们能友好的进行github访问操作。

##### 首先点击以下的DNS解析地址

[ipaddress](https://www.ipaddress.com)


在这个地址上搜索 www.github.com 
                assets-cdn.github.com
                github.global.ssl.fastly.net


#####  然后在系统Hosts文件里新增以上地址搜索出的ip地址的内容

(windows系统是在，其他系统还没研究呢)一般Hosts文件是在系统盘的 C:\Windows\System32\drivers\etc 这个路径下


注意：打开系统hosts文件(需管理员权限)。
      末尾添加三行(方便识别)


##### 最后一步 刷新系统的DNS缓存

(系统管理员)打开系统命令行，运行 ipconfig /flushdns 手动刷新系统DNS缓存即可。
