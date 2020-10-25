---
title: "如何为没有目录的 PDF 电子书添加目录"
date: 2020-10-25T14:31:12+08:00
draft: false
tags:
  - PDF
gitinfo: true
---

### 前言

经常买书的小伙伴们，大概都知道，有些纸质书籍价格比较贵，而且买的书籍比较多了，比较占用家里的空间，如果要搬家，也挺难受的。

现在大部分的纸质版书籍的电子版基本上都可以在网上找到，有高清版的，有彩印版的，也有扫描版的，但避免不了有些电子书籍没有目录，这样就很难受了。但是，自我感觉还是实体书的手感比较好，阅读起来的感觉也很不错，而且较使用电脑，手机，阅读器来说，对人体的伤害还是比较小的。

> 注意：此工具需要 Java 运行环境，我的 jdk 版本为 1.8.0_202，大家都可以在网上搜索到安装包与安装教程。 

首先看下没有目录的电子书。

![没有目录，导致有时阅读体验直线下降](https://cdn.jsdelivr.net/gh/Kanna-jiahe/blogimage/img/20201024224516.png)

阅读起来真难受啊，真难受😂

打开 ifnoelse 大佬的 GitHub 仓库：https://github.com/ifnoelse/pdf-bookmark

![仓库主页展示](https://cdn.jsdelivr.net/gh/Kanna-jiahe/blogimage/img/20201024224504.png)

下载地址：https://github.com/ifnoelse/pdf-bookmark/releases

在这里，提供网络上的一个下载速度比较快的链接，安装包分为 Windows 版的和 Mac 版的

这里的下载链接来自网络（侵权删）

* Windows 版：https://yafine.lanzous.com/ii5Eeeevywf
* Mac 版：https://yafine.lanzous.com/iDa5Meevyad

下载好对应的 jar 包后，双击即可打开，界面图如下：

### 如何使用

1. 打开 jar 包应用程序后，点击选择文件，选择要生成目录的电子书；

2. 打开互动出版网，然后进行书籍的搜索，以《啊哈！算法》为例，搜索出结果后，然后将地址栏中的链接进行复制操作，然后粘贴到请在此填入目录内容，然后点击获取目录；

3. 页码偏移量就是上图所说，电子书中页数的显示，与电子书阅读器中的页数显示之差即为页码偏移量，如上图所示，页码偏移量为 85-73=12；

4. 然后点击生成目录即可。生成的带有目录的电子书会与要获取目录的电子书在用一个目录下。
5. 相关的效果图如下所示。

![](https://cdn.jsdelivr.net/gh/Kanna-jiahe/blogimage/img/20201024224336.png)

![](https://cdn.jsdelivr.net/gh/Kanna-jiahe/blogimage/img/20201024224323.png)

![生成带有目录的电子书](https://cdn.jsdelivr.net/gh/Kanna-jiahe/blogimage/img/20201024224308.png)




> 查阅电子书目录不止局限于互动出版网，只要可以搜索到电子书籍的目录，都可以进行使用。

