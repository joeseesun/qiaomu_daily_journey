---
title: 如何用Telegram机器人获取Twitter账号发布的信息
tags:
  - Telegram
  - Twitter
  - 信息处理
postId: '21'
categories:
  - 5
---

> 今日冥想：0分钟
> 单词学习：inundate，淹没；antithesis，对立面；devise，设计
> 今日运动：引体向上5个

做了个Telegram机器人，用于获取自己最关注的Twitter账号发布的信息。

步骤如下：
① 创建Telegram机器人，获取秘钥

打开 https://t.me/botfather 输入 \/start

按引导流程，先输入机器人名字，然后输入想要ID（必须以bot结尾），比如telegram_rss_bot
创建后会给秘钥，类似这种结构：5987500169:AAEBqLx7OWmK6ne9pIfHhrgMktDmq_VcsSQ

② 获取自己的Telegram ID

打开 https://t.me/userinfobot 输入 \/start，拿到自己的ID，类似结构：1293676963

③ 私有化部署一套RSShub
可以直接用Rsshub提供的Twitter RSS订阅地址，本步骤可跳过。
如果有github和vercel账号，自己搭一套也不难，访问下面地址，点蓝色Deploy按钮就行。

https://docs.rsshub.app/install/#bu-shu-dao-vercel-zeit-now

④ ChatGPT互动问答开发

本次不同于开发Chrome插件，未知信息比较多，也不是很好调试。
所以，先让ChatGPT写基础功能：实现发送一句话给自己的Telegram账号。

其中，会用到之前获取的Telegram机器人秘钥和自己的ID
调试通过后，再要求ChatGPT从发一句话改成抓取RSS文件格式化后发送。

为了让机器理解需要采集什么字段，先打开RSS文件，复制一些样例，然后告诉他想要抓什么字段。
https://rsshub.app/twitter/keyword/RSSHub

比如告诉它我需要description、pubdate、link这几个字段，让他写代码。
调试通过后，然后是图片、视频发送、还有一些HTML过滤等样式优化，比较琐碎，挺花时间的。

⑤ 部署到服务器端
本地运行通过后，为了让机器人持续工作，建议部署到服务器端。
这期间的工作主要是Python3环境配置，因为默认的VPS系统只有Python2，代码运行会出错。

最后用了conda这个虚拟环境和安装包管理工具，可以降低不少麻烦。

放一张Telegram机器人效果
![imgbb](https://i.ibb.co/r2Ng3Gp/image.png)

一些想法和感受：
- 假如有更多编程知识，调试估计会更快，否则只能来回粘出错代码问ChatGPT。
- Telegram机器人创建过程超级顺滑，建议飞书bot学习下，对生态发展很有好处。
- 如何让自己的工作流更自动化、AI化，是个值得持续研究的方向。
- 下一步计划先让ChatGPT总结摘要，然后一次性发送。



