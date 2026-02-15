---
title: 节点连线
url: https://docs.aliwork.com/docs/yida_support/_2/lgrp0w/qnsnyk/wpqkpqd1eqvlyr5w
source: docs.aliwork.com
---

# 节点连线

节点连线是高级流程各个节点之间的连接线，用于配置各节点的流程流转规则。
## 操作步骤[​](#NnqHe)
进入高级流程设计器。选择两个配置完成但还未链接的节点。选择其中的一个节点，然后单击任意方向的箭头，将其连接至下一节点。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/gif/1729072868864-a3f9df72-f315-4702-ba80-24bc375c9820.gif)
单击连接线，选择线执行规则。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1729072968747-cdcfd6d7-4ec2-40c5-aa85-870f7f06989d.png)
在弹出的对话框内，配置线执行规则。
| **规则** | **说明** |
|---|---|
| **按条件配置** | 支持使用表单内的字段和系统字段设置条件规则，只有满足配置的条件才会经过该连接线进入下一节点。 |
| **代码模式** | 支持直接输入参数值或使用Groovy表达式。**说明**：默认值为**true**，表示任何情况下流程运行到此条线路都会直接进入下一节点。 |
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1729073941472-83b4fa7b-d7c6-4288-a959-19f8bcf3511f.png)
## 使用示例[​](#r4z0K)
当表单组件「报销费用」小于 1000 的时候到「主管」审批，大于 1000 的时候到「财务」审批。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1639445602743-e92c4665-e92f-4d00-b1fc-29843f58d147.png)
如下图所示，报销费用500时，到主管审批。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1639445616506-835f7261-8e46-4725-b372-d221efc346e8.png)
报销费用2000时，到财务审批。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1639445629832-18bbe92a-26f0-4a64-ae2a-9c934340a69b.png)
