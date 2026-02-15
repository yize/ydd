---
title: 待办任务
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/rhg7w5n7la2t69bv/qaghpy2gu779gi1l/vs2cqwywsanvmg3o
source: docs.aliwork.com
---

# 待办任务

待办任务连接器是当用户在宜搭內填写表单之后，可以实现自动在钉钉内为指定成员创建钉钉待办消息且执行人点击待办查看表单详情。发起强有力的消息提醒，做到件件有着落，事事有回音。
## 实现效果[​](#E3VSK)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1645612512815-b81730e2-bc85-4325-9d6e-e9682b5ed4ed.png)
图3-1 连接器实现自动创建待办任务
## 操作步骤[​](#q9Bab)
## 步骤一：表单的创建与配置[​](#vP4YD)
创建表单，用于录入待办消息相关信息及触发连接器效果。**操作步骤：**创建表单并命名为待办2.0。添加**日期组件**，命名为**发起待办任务时间**并设置其格式为`年-月-日 时:分`，并设置为**必填项**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733823741829-8d43c05d-d9e1-417b-ae35-c99d5f8b4fcc.png)
添加两个成员组件，分别命名为**发起人**及**执行人**，并设置为必填项。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733824461103-a004facb-286c-4aef-a8b5-e90e9409d774.png)
添加**单行文本**组件，命名为**待办标题**.。添加多行文本组件，命名为**待办内容**，设置为必填项。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733824566125-39fe9ac4-6701-4eda-88c8-f08af92c841f.png)
## 步骤二：新建集成&自动化[​](#n8lB3)
应用管理后台 > **集成&自动化** > **新建集成&自动化** > **从空白新建**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1645608036584-e8ed55dc-ee15-44a5-983e-bbe9cb99ff7b.png)
在弹出的**新建集成&自动化**对话框中，将连接器命名为**待办任务**并在表单事件触发类型下选择**待办2.0**表单，点击**确认**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1645608195495-e2d6a5cf-2581-4edc-b84a-90677c5d6052.png)
## 步骤三：配置集成&自动化[​](#kuvjf)
配置表单触发事件。点击选中表单事件触发，在触发事件中选择创建成功， 数据过滤选择全部数据。最后，点击右下角保存按钮，即可。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637308043553-8a3b8e36-6e9d-46bc-8e2a-c0089104e675.png)
配置连接器节点，在选择应用中选中钉钉待办1.0，并点击下一步按钮。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637308117266-6da57e3b-77d3-47cd-bfc3-62e64690d2f6.png)
在选择执行动作中选中创建待办任务执行动作，点击下一步按钮。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637308194254-9ef16eef-bdfb-4d63-9e70-53a2f27f27ba.png)
在配置执行动作中对各个配置项进行配置，点击保存。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1645608462693-31b50ed0-37cd-44a1-a4a9-bf23a4df0686.png)
**说明：**连接器执行动作中待办事项的跳转链接字段选择公式公式配置如图所示![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1645609145943-988a6b1f-c89a-4647-b0f2-d69d7c932bec.png)
其中：`https://www.aliwork.com/APP_YYJLRRMCI0XP4J1Y2O4W/formDetail/FORM-S2A66LA1041YXTNSW16AKYR75COY1RKAZAZZKA2?formInstId=`可以从当前应用表单的详情页进行复制。
点击页面右上角保存后，点击发布即可。
## 步骤三：配置待办任务内容[​](#lRVOp)
通过上述两个步骤，我们实现功能的配置工作已经完成，接下来，只需提交表单即可触发连接器，从而自动发起待办任务。**操作步骤：**填写表单内容，点击提交，即可。（操作如图2.3-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1645612421699-e7d75b70-9998-43c4-bb33-78a7bae9913a.png)
图2.3-1 录入表单信息并提交
## 附录[​](#gkuwp)
连接器执行动作参数说明
| **名称** | **页面组件** | **是否必填** | **描述** |
|---|---|---|---|
| 待办时间 | 日期组件 | 是 | 待办的发起时间，格式为YYYY-MM-DD HH:mm:ss。 |
| 发起人 | 成员组件 | 是 | 待办任务的发起人，可根据userId()公式获取。 |
| 内容 | 文本组件 | 是 | 待办信息的内容描述。 |
| 待办事项的标题 | 文本组件 | 是 | 待办信息的标题���要求最多五十个字符，可通过校验-最大长度进行限制。 |
| 任务的执行人 | 成员组件 | 是 | 待办任务的执行者。 |
| 待办事项的跳转链接 | 文本组件 | 是 | 待办任务点击跳转地址，跳转至表单提交详情页可通过CONCATENATE()公式进行拼接；跳换至其他页面可以自行输入。 |
