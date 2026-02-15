---
title: 视频会议（发起）
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/rhg7w5n7la2t69bv/qaghpy2gu779gi1l/ahnex56mzi8f2gl8/zx7hyx0awsq2zfb9
source: docs.aliwork.com
---

# 视频会议（发起）

[上一篇文档](https://www.yuque.com/yida/support/tly5l0)我们学习了**如何通过宜搭表单的提交触发连接器从而进行视频会议的预约**，解决了会议开始前的流程繁琐问题。那么，你是否也遇到过到达约定的会议时间，但作为组织者的你忘记发起会议？时间紧急时邀请参会人步骤出现人员的错选漏选？现在，通过视频会议连接器的第二个执行动作——发起视频会议，上述痛点将不再能对你造成困扰，快乐工作，拒绝社死！
## 实现效果[​](#oyvs6)
发起视频会议时，会先邀请会议发起人加入会议，接听后，再邀请会议参与人加入会议。若发起人拒绝，则不会继续邀请参与人。
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/gif/1632624950040-2f663b08-b1c7-462c-afb3-3a71d9093880.gif)
## 操作视频[​](#DJcxC)
## 步骤一：创建并配置表单[​](#sLzrh)
搭建「发起视频会议」表，其中主要设置会议参与人（成员组件可多选），会议主题（单行文本组件）。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652413709619-d0798bfa-c27f-4ea8-999f-5fdd480cdf83.png)
设置发起视频会议表
## 步骤二：新建并配置连接器[​](#K68Jd)
**扩展阅读：**连接器功能介绍可参考文档：[集成&自动化-连接器](https://www.yuque.com/yida/support/zevvr1)
**新建连接器：**点击后台管理界面上方「集成&自动化」导航进入功能分区，点击「新建集成&自动化」按钮选择「从空白新建」，在弹出的对话框中，将连接器命名为「创建视频会议」，在表单事件触发中选择「发起视频会议」表单。点击确认。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652414066254-c1401200-86e0-4793-b19d-5caa9ffed581.png)
新建集成&自动化**配置表单触发事件：**将触发事件选择为「创建成功」，数据过滤选择「全部数据」，点击保存。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652414264638-e0fa224c-da67-45cb-a574-54471a0169ac.png)
**配置表单事件触发****配置连接器：**添加连接器节点，通过搜索找到执行动作为 「创建视频会议」的连接器，点击即可进行连接器执行动作的配置。将连接器所需字段与表单字段一一对应，然后点击保存，最后点击页面右上角的「保存」及「发布」即可。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652414482309-b130024c-db79-41a0-8552-fc777fedc196.png)
配置连接器执行动作
