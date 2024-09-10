---
title: NAS教程|飞牛云入门篇：VMware 安装FNOS
date: 2024-09-10T09:56:21Z
lastmod: 2024-09-10T11:17:00Z
tags: [NAS,虚拟机,飞牛云]
---

## 一、概述

> 标签：#NAS# 、 #飞牛云#  、#虚拟机#
>
> 名称：飞牛云入门篇：VMware 安装FNOS
>
> 作用简述 ：最近在NAS圈新出了一个飞牛云的NAS系统，得到各大博主的推荐，自己也试用了一段时间飞牛云，觉得非常不错，目前功能方面还是相较群辉等成熟NAS系统有差距，但是也是值得期待和试玩，本人的生产平台暂时未迁往飞牛云，网上也没有太多类似的教程，为了避免生产数据产生损坏，以VMware作为底层，开展系列教程。

## 二、前言

[飞牛云](https://www.fnnas.com/)在其官网也有一些入门级教程，安装系统也非常简单，我在本机就已经安装过，接下来我会一步步教大家如何安装。另外官网有详细的教程：[飞牛云官方教程](https://help.fnnas.com/ "飞牛云官方教程")

![image-20240910100629-sab8m83](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101110178.png)

## 三、主要流程目录

1. 飞牛云ISO下载
2. VM创建虚拟机
3. 飞牛云系统安装
4. 飞牛云系统初始化
5. 安装总结

## 四、教程实践

##### 飞牛云ISO下载

> 可以前往官网将ISO下载，并放置在本地文件夹中，建议放置在一个英文目录下（个人习惯，一些软件在中文目录下会产生一些问题），目前还是公测版本，附加官网下载地址：[飞牛云官方下载地址](https://www.fnnas.com/download "飞牛云官方下载地址")

![image-20240910101553-v7kfaw4](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101110670.png)

---

##### VM创建虚拟机

> 通过VM创建，其中要选择Debian系统（飞牛云原生基于Debian系统）

![image-20240910101736-fy9lhzt](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101110995.png)

![image-20240910101843-3h4kshc](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101110295.png)

![image-20240910101907-zu5wv4s](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111063.png)

![image-20240910102020-gzlk7y0](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111332.png)

> 此处选择64G硬盘作为系统安装，系统安装和文件存储分开是最好的，虚拟磁盘存储为单文件方便后续转移

![image-20240910102118-vmdut4u](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111230.png)![image-20240910102134-fqokjyl](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111769.png)

> 新增硬盘作为存储空间，选择SATA类型，磁盘大小建议不低于100GB，不用立即分盘磁盘空间，这样就不会占用过多本地磁盘空间

![image-20240910102305-h7ostdo](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111365.png)

![image-20240910102338-os6sx1w](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111521.png)

![image-20240910102353-ew2hawe](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111163.png)

![image-20240910102431-liwhjvi](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111714.png)

> 选择官网下载的ISO镜像作为安装文件

![image-20240910102544-pny6kth](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111956.png)

> 根据自己的设备性能，适当增加内存、处理器的大小，其中建议网络适配器默认即可。

![image-20240910102622-1dple4u](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111706.png)

---

##### 飞牛云系统安装

> 直接启动虚拟机开始安装系统，等待几秒跳过启动界面，来到初始安装界面，选择系统安装磁盘。

![image-20240910102709-qh4o4ng](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111944.png)

![image-20240910102730-dl633nv](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111485.png)

![image-20240910102746-s7069dc](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111857.png)

> 选择完磁盘后等待安装，直接下一步即可。

![image-20240910102758-5hcu9ie](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111335.png)

![image-20240910102845-263d1wp](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111746.png)

> 选择网卡，因为是虚拟机安装系统，默认即可，如果是硬件安装，需要选择对应的网卡。

![image-20240910102932-zkr3li2](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101111908.png)

> 结束系统安装，获取到飞牛云IP。

![image-20240910103009-bkxm8me](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112275.png)

---

##### 飞牛云系统初始化

> 在网页端地址栏输入之前得到的IP+端口，回车就可以访问到飞牛云网页管理界面。

![image-20240910103137-lq88njt](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112385.png)

> 创建管理员账号，用于后续对整个NAS系统的管理。

![image-20240910103214-nah16am](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112666.png)

![image-20240910103241-esnf4by](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112927.png)

> 创建存储空间，选择之前添加的100GB，因为是虚拟机演示教程，就没有必要组RAID，直接无脑选择Basic创建存储空间。

![image-20240910103302-qnw93gk](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112128.png)

![image-20240910103343-jo3pfp1](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112686.png)

![image-20240910103402-xovo93d](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112685.png)

![image-20240910103410-8jy7iqh](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112672.png)

![image-20240910103425-st4y8id](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112211.png)

![image-20240910103432-js6jg2k](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112491.png)

![image-20240910103441-hhx4q5a](http://image.nasklog.com/image/飞牛云入门篇：VMware%20安装FNOS/202409101112812.png)

---

## 五、总结

至此教程完整结束，可以愉快的玩耍，总结来说飞牛云的安装相对于群辉（嘿嘿嘿）的安装相对简单一点，不需要各种洗白，现阶段官网也说基础功能免费使用，后续有什么发展变化也很难说，大家可以按照此教程，先玩耍起来，不建议将生产系统迁移至此系统，毕竟还只是一个公测版本，各种BUG还是有的，基础功能也不完善，等待后续优化。

---

## 六、参考

> 知识源于总结

* 官网教程
* VM基础教程
* 巴拉巴拉乱七八糟的简单基础知识



---