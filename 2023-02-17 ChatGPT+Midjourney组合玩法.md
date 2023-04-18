---
title: ChatGPT+Midjourney组合玩法
date: 2023-02-17 02:36 
category: "日志"
tags: ["工具分享"]
---

> 今日冥想：3分钟
> 单词学习：ventilate，通风；consent，同意；expedite，加快
> 今日运动：引体向上5个

最近订阅刘飞的Midjourney小报童专栏，看到群友分享的AI合成图，很是惊叹。
心动后，忍不住充值订阅了 Midjourney 乞丐版，体验两种玩法：

一、ChatGPT生成Prompt

参考下面文章，给ChatGPT喂词，学习生成Prompt
https://muyjazngod.feishu.cn/docx/VyHmdL3pHobyH6xQGbMcRFn9noh?from=space_home_recent

给ChatGPT单独开个会话线程，用来合成MJ的Prompt

二、词表组合生成Prompt

根据刘飞提供的词表，做成飞书表格，用下拉菜单选择风格、流派，组合成Prompt
https://bytedance.feishu.cn/sheets/shtcnoJ7Yh5bfheVAp6IIn8sShc?sheet=42KP1X


表格制作过程：
- 让ChatGPT格式化文本为CSV格式，按风格、流派分表导入飞书表格。
- 用飞书表格自带的textjoin命令把风格、流派组成Prompt（问ChatGPT学到）

尝试组合一个Prompt：
```
crystal bottles,hyperdetailed,Frank Frazetta,Yoshitomo Nara,Chinese Paper Art
```

预览图如下：
![[Pasted image 20230217211942.png]]






