---
title: 搭自己的Telegram ChatGPT机器人
date: 2023-03-07 11:26 
category: "日志"
tags: ["工具教程"]
---

> 今日冥想：10分钟
> 影子跟读：20分钟
> 单词学习：wrath，愤怒；quandary，窘境；duress，胁迫
> 今日运动：引体向上6个


用开源代码搭了一个专属 ChatGPT Telegram机器人：不用自己的域名、服务器，支持创建多个机器人角色，方便日常使用。

代码和教程：[https://github.com/TBXark/ChatGPT-Telegram-Workers/blob/master/DEPLOY.md](https://github.com/TBXark/ChatGPT-Telegram-Workers/blob/master/DEPLOY.md)

整体思路：
① 创建 Telegram 机器人，获取机器人Token
② 获取 OpenAI API-key，[访问](https://platform.openai.com/account/api-keys)
③ 注册 [Cloudflare](https://dash.cloudflare.com/?to=/:account/workers)，创建服务，设置OpenAI key、TG机器人key等环境变量
④ 访问服务网址初始化机器人

搭建过程几个注意事项：

1. 创建TG机器人，打开 [https://t.me/BotFather](https://t.me/BotFather) 输入 "/newbot"，机器人名字必须以bot结尾，多试几个名字，很多都被占用了。
2. 教程里的Cloudflare界面跟实际上的不一样，需要仔细找按钮位置。
3. 各种API key 环境变量需要自己手动添加， CHAT_WHITE_LIST 白名单按教程找不到自己的ID，所以增加参数 I_AM_A_GENEROUS_PERSON ，值设置为true
4. Cloudfare生成的服务地址（.dev结尾）被DNS劫持，需要换好用的代理访问。记住，能访问cloudfare，不见得能访问生成的服务地址。


为什么用Telegram做一个ChatGPT机器人？
- TG是一个好用的App，对话式自然舒适，比第三方 ChatGPT 客户端更靠谱。
- 支持多轮对话和上下文记忆，也方便内容转发复制。
- 可定制不同机器人类型，如翻译机器人、脑暴机器人等，互相不干扰。
- Cloudflare服务本身在海外，避免高墙对网页版ChatGPT的影响。
- 让先进生产力工具无处不在，降低门槛，增强提示触发。

下一步计划，搭自己的飞书ChatGPT机器人。






