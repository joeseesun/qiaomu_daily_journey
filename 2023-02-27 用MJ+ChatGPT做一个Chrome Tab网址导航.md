---
title: 用MJ+ChatGPT做一个Chrome Tab网址导航
date: 2023-02-27 09:28 
category: "日志"
tags: ["创造工具"]
---

> 今日冥想：15分钟
> 单词学习：oblivion，遗忘；alleviate，减轻；blunder，失误
> 今日运动：引体向上5个

学习最好的方式是基于项目的学习（PBL） 
今天给自己出了个题目：如何借助Midjourney 和 ChatGPT做一个Chrome插件。

耗时2小时完成，记录下核心步骤：

一、Midjourney制作一个Logo，Prompt:
```
clean,minimalist,emblem for a tech company, A letter F can fly,vector logo,basic,low detail,smooth,attractive,masterpiece,Desaturated,flat,UI,UX --no shadowing
```

二、Logo去背景做成透明图
https://www.remove.bg/zh

三、各种Logo规格处理

上传Logo生成多种Favicon格式
https://www.logosc.cn/logo/favicon

缺48px和128px Logo，在线处理
https://www.gaituya.com/daxiao/

四、制作Chrome插件

向ChatGPT提问：如何制作Chrome插件，替代默认Tab，给出实现代码。
ChatGPT会给出三个文件的写法：manifest.json、background.js、newtab.html

第一个是插件配置文件
第二是个JS脚本，作用是监听Tab点击事件，打开指定HTML文件
第三个就是Tab页面，用HTML实现

第一个文件中，填写Logo地址和插件名称。
第二个文件不用修改。
第三个文件修改需要HTML知识，向ChatGPT提问、加上Google搜索完善。


让ChatGPT参考Tailwind Css的样式，给出谷歌搜索框代码、网址卡片代码。

最终实现效果如下：

![[Pasted image 20230227223233.png]]