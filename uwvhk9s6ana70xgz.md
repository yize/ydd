---
title: AI生成组件
url: https://docs.aliwork.com/docs/yida_support/_13/uwvhk9s6ana70xgz
source: docs.aliwork.com
---

# AI生成组件

## 功能简介[​](#Un5JY)
AI生成组件，集成DeepSeek等AI大模型能力，支持灵活搭建AI生成类场景应用，助力企业数字化、智能化。默认为钉钉自带大模型，可输入DeepSeek账号即可使用DeepSeek服务。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1738840647198-a1ac5de2-c5cc-44ea-b07a-f74713238365.png)
## 适用场景[​](#u6llO)
适用于制作一些基于生成式AI，结合提示词工程的小应用，例如问答、翻译、拜年祝福或其他生成符合要求的文案。
## 安装步骤[​](#RggHQ)
进入[宜搭插件中心](https://www.aliwork.com/pluginCenter?spm=a2q5o.26874317.0.0.170d5bcdLpNVfP)。选择**DeepSeek生成**插件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1738843076865-04ebec79-bae9-4d09-98c0-98d411b21ac0.png)
3.在右侧单击**安装插件**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1738843298877-44c4a3c3-5a4c-4382-8bee-8f92163112af.png)
插件安装成功后，你可以在钉钉工作台 > 平台管理页面管理插件。**说明：**详情请参考[插件管理](https://www.yuque.com/yida/test/uguu1s8arfqim7kt)。
## 操作步骤[​](#sln7Z)
#### 【基础操作】[​](#lGKqG)
1）入口：进入表单设计-基础组件-AI生成组件。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1738842093055-c38f3959-e371-47a7-a637-ebe4379ab7eb.png)
2）将AI生成组件拖入至画布中，右侧配置AI生成的所需参数。3）配置系统提示词(注意：此处就是下达给AI的指令)，提示词中可以使用{{表单组件唯一标识ID}}使用表单字段。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1738842220056-d08cc7fb-fd5a-4709-a089-78c03fd23a1a.png)
表单组件唯一标识ID的获取方式：选中表单组件>高级>唯一标识。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1738842276017-79ff4a64-d394-4207-9446-cb90c80b17e7.png)
4）若选择使用deepseek模型，则需填写deepseek api key、选择模型类型。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1738842375927-65de73b4-039b-4ef3-b080-e4670ca292d6.png)
5）若需要访问者自行输入提示词，可开启“用户输入提示词输入框”，提示词即可由使用者自定义。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1738842476898-b523ef57-96d0-4bf1-a36e-f0a4c53903fd.png)
#### 【AI组件】操作[​](#Iw0LZ)
想要设置上述示例场景类似的AI生成组件，无需代码即可解锁DeepSeek的推理、编码、分析等专业能力。仅需以下四步即可掌握让工作效率翻倍的AI实战秘籍！（1）进入表单页面-基础组件-AI生成组件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1739511121977-f8875a55-837d-4df4-8799-5afea28d8b4e.png)
（2）将AI生成组件拖入至画布中，右侧配置AI生成的所需参数（3）配置系统提示词(注意：此处就是下达给AI的指令)，提示词中可以使用{{表单组件唯一标识ID或组件别名}}使用表单字段![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1739511122082-c1595583-3d17-4edc-991e-19b735a99b78.png)
（4）表单组件唯一标识ID的获取方式：选中表单组件>高级>唯一标识![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1739511121983-b311d758-91e3-452e-a0dc-6cd08b466664.png)
（5）若选择模型类型：宜搭，则可直接使用官方部署的DeepSeek模型
| **选择模型** | **配置参数** |
|---|---|
（6）若选择使用deepseek模型，则需填写deepseek api key、选择模型类型⚠️ 注意这里输入的 API KEY 请勿线上使用，仅供预览和调试使用，待稳定的插件版本放出后，KEY 的配置会放在插件配置中，受到保护。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1739511125158-9ea41dec-cdfd-4010-b074-8525630b8440.png)
（6）若需要访问者自行输入提示词，可开启“用户输入提示词输入框”，提示词即可由使用者自定义![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1739511125606-03476536-ec1b-4129-a82a-2cec7fe09871.png)
