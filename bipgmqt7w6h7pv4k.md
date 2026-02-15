---
title: OA 审批
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/rhg7w5n7la2t69bv/qaghpy2gu779gi1l/bipgmqt7w6h7pv4k
source: docs.aliwork.com
---

# OA 审批

OA审批连接器的接入目前仅支持**钉钉专业版**+**宜搭专业版（尊享版）**以上的版本。
本文以通过宜搭表单触发OA审批的付款申请为例，介绍如何在宜搭内使用 OA 审批连接器。
## 审批连接器简介[​](#YO8sw)
支持表单事件触发当宜搭表单被创建、编辑、删除、评论时系统自动调用连接器，从而实现宜搭与钉钉OA的数据传递支持应用事件触发当应用产生新的事件时，如某员工通过钉钉OA审批发起新的加班申请时触发应用事件触发支持在钉钉 OA 审批内，填写并发起审批。通过**应用事件触发**的配置，将钉钉 OA 审批与宜搭表单进行绑定，当申请发起时，宜搭表单内会自动新增一条数据。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1655200512386-208b73ce-96ec-4463-9f1e-b599d0d30166.png)
**配置说明：****选择连接器动作：**可通过输入名称搜索或点击选择找到所需的连接器执行动作**选择流程表单：**首先需要选择钉钉内审批应用，（如上图中的OA审批），此应用需用户自行在钉钉中创建；然后需要进行宜搭内表单选择（如上图中的加班审批测试）**配置动作：**即通过点选将宜搭表单与钉钉应用进行绑定
## 操作步骤[​](#SGNCJ)
### 步骤一：在OA审批创建付款申请流程[​](#IlrQX)
登录[钉钉后台](https://oa.dingtalk.com)。依次选择**工作台** > **应用管理**，在搜索框内搜索**审批**，选择 **OA 审批**，单击操作列**进入**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733716651086-a07907b9-b043-4c1b-aa96-f1a848215f00.png)
在 OA 审批管理后台，单击**创建新表单**，选择**流程表单**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733717126725-8d3e0614-8fd3-4fdd-b319-0b22b82d8f94.png)
设置表单名称为**付款审批**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733717171223-effc9d90-7e75-4a0b-93d7-4246acd19482.png)
单击**表单设计**，在表单内添加**联系人**、**金额**组件。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733798119749-d094471c-ac4a-46a3-8f45-cd93326430c6.png)
单击右上角**发布**表单。
### 步骤二：在集成&自动化配置连接器[​](#QfsQo)
登录[宜搭工作台](https://www.aliwork.com/workPlatform)。选择目标应用，进入应用的**集成自动化**页。选择已经创建的集成自动化流，单击**编辑**。将光标移动至流程节点的连接线位置，会弹出`**+**`按钮，单击`**+**`选择**连接器**。在右侧属性栏搜索并选择**发起实例**连接器。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733822132570-60e439a6-7ae9-43c8-9ed6-045f71380df6.png)
选择**应用名**为 **OA 审批**，选择**流程表单**为上一步创建的审批表单。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733822257495-621cf02b-026e-41dd-9d27-1a7502d84fda.png)
配置执行动作。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733822323028-09d304db-386f-4bec-817c-9754e4fd5750.png)
配置完成后，单击**保存** > **发布**。
