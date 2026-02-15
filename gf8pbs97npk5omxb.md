---
title: Prompt PaaS说明
url: https://docs.aliwork.com/docs/yida_support/_12/gf8pbs97npk5omxb
source: docs.aliwork.com
---

# Prompt PaaS说明

## 1、PromptPaaS 概述[​](#ToRZf)
**Prompt（提示词）作为大语言模型的核心输入指令，直接决定了模型对任务的理解深度与输出质量。**
高质量的 Prompt 能显著提升模型在复杂任务中的表现，例如逻辑推理、多步分解、上下文理解等关键能力。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1768876753970-295f94af-5559-4d0a-9046-afe01cb76e01.png)
**钉钉AI宜搭自研PromptPaaS ，提供覆盖 Prompt 全生命周期的智能优化平台**，集生成、调优、评估与管理于一体，助您高效构建并持续迭代最优提示方案。随着大模型能力不断演进，实际应用场景日益复杂，单一 Prompt 的调优已难以满足需求。解决方案正逐步从“单点优化”迈向“系统化协同”——即对融合多步骤、多工具及多个智能体（Agent）参与的完整 Workflow 进行端到端优化。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1768876739137-988055e4-07bf-4018-a0f4-1a3bd11e9a77.png)
**PromptPaaS 深度依托大模型能力**，可自动拆解用户问题、智能规划执行流程，结合可用工具链动态生成多样化解决方案，并基于真实用户反馈持续闭环优化，最终一键生成可部署代码，让复杂任务轻松落地。
| **产品地址** | **支持模型** |
|---|---|
| PromptPaaS | 千问、DeepSeek 等预置模型 |
## 2、功能详解[​](#3e23bd20)
PromptPaaS支持 Prompt 生成和调优两种任务，下表为详细介绍。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1768877228341-15c4b518-93ac-414c-9a1f-d9908f1d0092.png)
**任务分类****任务场景****说明****示例**Prompt生成文本理解/单轮对话任务多轮对话任务视觉理解任务将简短的「任务描述」拓展为结构相对完整的「初始Prompt」。判断舆论的内容对出行行业的影响。Prompt调优文本理解/单轮对话任务用户输入包含「变量（文本）」的「Prompt」，与模型进行一轮问答，以解决用户定义的任务。Prompt 里变量的占位符为{{变量名}}。起草邮件、文档总结。例如：引导大模型「起草回复客户投诉及提供解决方案电子邮件」的Prompt，包含{{客户投诉}}和{{解决方案}}这两个变量。
多轮对话任务适用于需要与模型助手进行多轮次对话的任务。用户设置「系统Prompt」并输入「用户内容」，模型以「助手」身份与之开展多轮交流。客服对话、角色扮演。视觉理解任务适用于包含图片信息的任务。用户输入包含「变量（文本/图像）」的「Prompt」，与模型进行一轮问答，以解决用户定义的任务。拍照解题、作业批改
