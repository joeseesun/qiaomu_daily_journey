---
title: Prompt Engineering学习总结
date: 2023-03-08 03:30 
category: "日志"
tags: ["技巧分享"]
---

> 今日冥想：15分钟
> 影子跟读：15分钟
> 单词学习：暂无
> 今日运动：引体向上5个

Prompt Engineering是一种人工智能技术，通过优化智能系统的指令来提高系统表现。这种技术可以提高智能系统的效率和可靠性，并有助于它们顺利地完成特定任务。

按Sam Altam说法，这个技能有效性大约在在1-5年，据说市场上已经有这个岗位的招聘。

对个体来说，了解一些基础写法，能更好发挥ChatGPT的价值。

网上看了一些资料，总结下：

- 赋角色
	- 给Prompt增加角色定义，能让生成内容更符合要求。比如文本处理，让AI扮演工作20年的专业编辑。最新3.5模型，可在system prompt里加角色设定。
- 给示例
	- 如果无法用文字准确解释问题，可以在Prompt里加一些示例。
	- 给出指定格式，可以做数据抽取格式化，比如生成json代码，Markdown表格等。
- 结构化/数字化
	- AI经常不知道什么是指令，什么是待处理的内容，用符号区分开处理会更准确。比如 冒号，前后三个引号 ““” 包住内容、双右斜线等。
	- 可以在Prompt引入运算代码（比如四则运算等），让输出结果更准确。
	- 不要说给我几个例子，最好写出明确的个数要求。
- Prompt 写作框架
	- [Elavis Saravia](https://github.com/dair-ai/Prompt-Engineering-Guide/blob/main/guides/prompts-intro.md)的Prompt撰写框架：指令（做什么任务）、背景信息（上下文信息）、输入数据（待处理的数据）、输出指示器（输出的类型和格式）。除了指令，都是选填。按这个框架写，返回质量基本不会太差。
	- [Matt Nigh](https://github.com/mattnigh/ChatGPT3-Free-Prompt-List) 的Prompt撰写框架：能力与角色、背景信息、指令（做什么任务）、个性（用什么风格回复）、尝试（要求提供 x 个答案）
- 其他小技巧
	- ChatGPT是基于概率模型，容易跳步骤，让模型按步骤推演更容易获得高质量答案。实操就是在Prompt结尾加一句“Let‘s think step by step”（让我们一步步的思考）
	- “简明扼要” 是一个好词，能让输出结果更精炼。还有 “解释给 x 岁/几年级的孩子”，让内容更易懂。“ A1 level” 让输出的英文句子更简单。

关键：赋角色、给示例、结构化（数字化）。

其中，结构化很重要。比如让 ChatGPT总结（Summarize），长内容会容易漏重点，如果给出参考格式，列出主题、观点等，生成质量会更高。
```
Summarize the main points of the following speech
Use the following format:
Topic 1: <topic_name_1>
- <point_1>
..
Topic 2: <topic_name_2>
- <point_1>
..
Topic 10: ..

Text: """
Thank you so much, Fred, for that lovely introduction. And thanks to the Atlantic Council for hosting me today.

The course of the global economy over the past two years has been shaped by COVID-19 and our efforts to fight the pandemic. It’s now evident, though, that the war between Russia and Ukraine has redrawn the contours of the world economic outlook. Vladimir Putin’s unprovoked attack on Ukraine and its people is taking a devastating human toll, with lives tragically lost, families internally displaced or becoming refugees, and communities and cities destroyed.
...

"""
```


附录：ChatGPT Playground参数说明

- **Model:** 切换不同模型，根据场景选对模型能省成本
	- Ada：适合解析文本、简单分类、地址更正等
	- Babbage：适合分类、语义搜索等
	- Curie：擅长文字类的任务、比如写文章、语言翻译、撰写总结等
	- Davinci：最强，适合有复杂意图、因果关系的场景，还有创意生成、搜索、段落总结等。
- **Temperature:** 控制生成结果随机性，温度调高，结果更出人意料，调低时更明确、固定。范围0-1，一般设置为0.5-0.8 
- **Maximum length:** 设置单次生成内容的最大长度，gpt-3.5-turbo，最大2048字符
- **Stop Sequence:** 在生成文本中设置停止生成文本的特定字符串序列，当生成文本包含该序列时，模型停止生成更多文本。gpt-3.5-turbo没有这个设置项。
- **Top P:** 用Nucleus采样的一种技术，可以控制模型生成文本的概率分布，从而影响模型生成文本的多样性和确定性，可以根据需要调整值，范围0-1。
- **Presence Penalty:** 控制模型生成文本时是否避免使用特定单词或短语，比较适合审查过滤场景。
- **Best of:** 选项允许你设置生成多少个文本后，从中选择最优秀的文本作为输出。
- **Injection start text:** 在输入文本的开头添加自定义文本，从而影响模型的生成结果。
- **Injection restart text:** 在中间某个位置添加自定义文本，从而影响模型继续生成的结果。
- **Show probabilities:** 查看模型生成每个单词的概率，每个生成的文本单词后面跟着一串数字，表示模型生成该单词的概率大小。
