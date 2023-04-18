---
title: Few-shot Prompt使用案例
tags:
  - Prompt
  - Midjourney
postId: '27'
categories:
  - 5
---

> 今日冥想：15分钟
> 单词学习：plasticine，橡皮泥；isometric，等距；hasty，匆忙的
> 今日运动：引体向上7个

如果用ChatGPT做信息格式化处理，few-shot 比 zero-shot 效果好很多。
few-shot就是给出示例，zero-shot 就是直接问。

分享两个使用案例：

① 把ChatGPT变成Todolist助手
```
你是一位20年经验的项目管理大师，帮我组织管理每天工作计划。 每天当我输入任务信息，根据艾森豪威尔矩阵原则重排任务优先级，重要紧急任务加上🔥标签。 每当我添加新任务或修改任务状态，重排优先级并返回当前的Todolist。 

e.g. 输入：冥想15分钟，竞品调研报告，整理Twitter书签 

输出代码块： 
- [ ] 🔥 竞品调研报告 
- [ ] 冥想15分钟 
- [ ] 整理Twitter书签

如果觉得我讲清楚了，请回复OK
```

经过测试，这种few-shot写法，AI处理非常稳定，比一堆文字描述效果好很多。

② 按指定格式处理文本
```
你是一个专业的翻译和编辑，我输入一段内容，你按指定格式翻译和重组编辑，用代码块展示Markdown语法标签。 

e.g. 输入：→ Art movement: Identifying the art movement in the prompt will introduce its style and techniques. Examples: “Impressionism”, “Surrealism”, or “Pop Art”. 

输出： 
## 艺术运动（Art movement） 
在提示中确定艺术运动将介绍其风格和技巧。
> 例如：印象派（Impressionism）, 超现实主义（Surrealism）或 波普艺术（Pop Art） ``` 

如果听懂请回复ok
```

想整理一份Midjourney关键词表，发现Twitter上有不少好教程，但格式五花八门。
通过类似上面的Prompt提示，可以很好的按Markdown语法格式化。

另外技巧，用Chrome审查元素查找复制HTML内容节点，加上Prompt，可以从HTML代码中找到需要的文本并格式化。

最终成果如下：
https://bytedance.feishu.cn/docx/TNVVdS7eYorWLlx4SmOcfmQAn7e
