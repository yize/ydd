---
title: 流程节点介绍
url: https://docs.aliwork.com/docs/yida_support/_2/trbqg6
source: docs.aliwork.com
---

# 流程节点介绍

对流程表单审批人、执行人、抄送人、分支节点的配置及介绍，如下表：
| **节点类型** | **说明** |
|---|---|
| [**发起节点**](https://www.yuque.com/yida/ugc9hx/zdwn7glrto9pi2ye) | 发起节点是一个流程的开始，每个审批流程都会默认拥有一个发起节点，该节点不可删除，可配置流程发起人所拥有的表单字段权限。 |
| **人工节点** | 人工节点包括审批人节点、执行人节点和抄送人节点。[**审批人节点**](https://www.yuque.com/yida/support/rq8i94)：审批人的职责是处理该节点上的审批任务，需要做出「同意」、「拒绝」等决策，一个流程至少包含一个审批节点。[**执行人节点**](https://www.yuque.com/yida/support/bl1oq2)：执行人不需要作出决策，只需要去执行工作，然后返回流程审批人继续处理，执行人做的工作与审批无关。[**抄送人节点**](https://www.yuque.com/yida/support/cntvp8)：用于在审批人审批后给抄送人发送消息提醒，抄送人不需要审批和执行。 |
| **分支节点** | 分支节点包括条件分支节点、并行分支节点和子流程节点。[**条件分支节点**](https://www.yuque.com/yida/support/yv8dnv)：条件分支节点可以将一个流程设计分成多个分支，只要是满足规则条件，相关的不同分支节点的执行动作都将完整执行。[**并行分支节点**](https://www.yuque.com/yida/support/row1axsz4s0ix2vl)：并行分支节点可以同时并行的执行两条及以上的分支任务，与条件分支不同，提交数据时，只要是满足条件规则，逻辑分支下的所有任务线都将被触发执行。[**子流程节点**](https://www.yuque.com/yida/support/xgy1wgc95g65fusy)：宜搭流程支持用户在设计当前流程过程中，添加「子流程」节点。子流程节点是一种特殊的节点，它可以支持多种特定参数触发模式的方式，触发另一现有的审批流程表单，实现审批流的解耦和组织。 |
| [**数据节点**](https://www.yuque.com/yida/support/mmwrzb5agf5i9lvb) | 流程表单中的数据节点与集成自动化内的数据节点一致，详情请参考[数据节点](https://www.yuque.com/yida/support/nl4abrm791inlvm2#ho8Xr)。 |
| [**脚本节点**](https://www.yuque.com/yida/support/ywnn9itpk2e52332) | 宜搭流程支持用户在设计当前流程、集成自动化的过程中，添加「脚本」类型的开发者节点。 |
| 消息节点 | 消息节点分为消息通知节点个邮件通知节点两种。[消息通知](https://www.yuque.com/yida/support/kvm0wu)：消息通知用于在流程执行到某个节点时，通过已经配置完成的通知类型，向指定人员发送钉钉工作通知或群通知。[邮件通知](https://www.yuque.com/yida/support/obvnvx)：邮件通知用于在流程执行到某个节点时，通过已经配置完成的邮件模板，向指定人员发送邮件通知。 |
