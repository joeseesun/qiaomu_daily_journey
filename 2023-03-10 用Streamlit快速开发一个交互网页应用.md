---
title: 用Streamlit快速开发一个交互网页应用
date: 2023-03-10 06:09 
category: "日志"
tags: ["教程"]
---

> 今日冥想：15分钟
> 影子跟读：10分钟
> 单词学习：1个
> 今日运动：引体向上5个

经常想一个问题，如何把本地运行Python代码，快速做成网站给大家使用？

最近了解到[Streamlit](https://share.streamlit.io/)，非常适合做这件事情。

Streamlit是一个开源的Python库，旨在使数据科学家能够快速构建交互式网页应用程序。提供了一个便捷的云端部署平台，使用户可以轻松地将他们的应用程序部署到Web上。

做好的网站：[https://robothere.streamlit.app/](https://robothere.streamlit.app/)

整体流程：
- 创建Github私有仓库
- 完成代码开发，Push到私有仓库
- Streamlit基于Github仓库生成网站

前置知识：
- 学会Github的基础用法
- 学习Streamlit的API写法，[地址](https://docs.streamlit.io/library/api-reference)

过程中可以多借助ChatGPT和Google找答案，分析错误代码。

最终做了一个摘要、脑暴、扩写机器人。

角色定义和Prompt如下：

```
# 总结摘要
system role：你是一个擅长整理摘要的助手
Prompt：请你使用简体中文，将这段文字去除不重要的形容词与修饰文字，只留下重要的信息，并且以列点的方式提供"

# 提问高手
system role：你是一个擅长提问的助手
Prompt：针对这段内容，提出可能的疑虑或问题，以促进我进行更完整的思考

# 脑暴助手
system role：你是一个擅长产生想法的助手，你会把一个主题拆解成相关的几个子议题
Prompt：你使用简体中文，针对下列主题，提供相关的子议题：

# 扩写助手
system role：你是一个20年经验的专业编辑
Prompt：用专业、清晰易懂的中文语言，扩展这些内容：

# 简化解释
system role：你是一个擅长解释复杂文字的助手，你会将一段比较难理解的文字，转化成简单的句子与概念，以让读者更容易理解内容。你的目标受众是12岁的学生。
Prompt：你使用简体中文，避免使用专业术语，尽量通过举例与比喻，解释下列这段文字在说什么：

```
