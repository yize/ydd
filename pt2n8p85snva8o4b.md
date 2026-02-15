---
title: 手动触发
url: https://docs.aliwork.com/docs/yida_support/_3/yovph5uaoyxb6f02/yl45mtqgbwewybhk/pt2n8p85snva8o4b
source: docs.aliwork.com
---

# 手动触发

本文介绍如何通过自定义按钮触发集成&自动化。使用自定义按钮触发集成自动化流程如下：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1730428520953-8f1fef57-8d15-497a-b907-ae12331ca4d5.png)
## 配置集成自动化[​](#kL9E8)
你可以参考以下步骤配置手动触发集成&自动化。登录[宜搭工作台](https://www.aliwork.com/myApp.html)，单击**我的应用**。选择需要创建集成&自动化的应用，进入**应用设置**页。单击集成&自动化，依次选择**新建集成&自动化** > **从空白新建**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1730185684286-302518c6-e4bf-4ff4-9a04-0bd5813e1c69.png)
在弹窗内设置集成&自动化名称，选择触发事件为**手动触发** > **自定义按钮触发**，选择触发的表单，单击**确定**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1730424187499-e92b5106-ca95-4cb9-a237-f2f24fca28fc.png)
进入集成&自动化编辑页，添加一个流程节点并完成配置。例如：添加一个���息通知节点，通知类型为工作通知，通知人为钉三多，通知内容为test。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/gif/1730430478238-0b74ec6f-3334-413f-9d28-f0ee9a0fa309.gif)
配置完成后，单击右上角**发布**按钮完成配置。
## 配置自定义按钮[​](#zbSgb)
进入应用的表单编辑页，选择触发集成&自动化的表单，单击有上角**编辑流程表单** > **页面设置**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1730424912066-69f2c4ec-b23b-420b-8503-e46aad9a4e0d.png)
单击**自定义按钮** > **新建自定义按钮**，在弹窗内设置自定义按钮名称，**可用条件**选择**全部数据**，**动作类型**选择**执行自动化流**，流程设置为创建完成的集成自动化流。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1730425187000-fc49a77f-7fab-4627-8a53-66ec2ddbab21.png)
单击**确定**完成配置。 在页面设置页，依次选择**自定义详情页** > **新建自定义详情页**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1730431400496-2b07894e-571a-4252-9600-9d90ba41b748.png)
在自定义详情页编辑页，选择**操作栏**组件，在右侧属性栏单击**添加一项**，添加上一步触发集成自动化的**自定义按钮**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1730431917800-215433e2-4354-422d-a955-b3fa5f3ac127.png)
单击右上角**发布**完成配置。
## 调试[​](#genVF)
进入表单的数据管理页，新增一条数据。数据添加完成后，在操作列单击**详情**按钮，单击创建的自定义按钮。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1730433647759-3d0a03cb-fc38-4402-bdb1-9197ae3b5a4d.png)
打开钉钉聊天窗口，查看消息。如下图所示，通过自定义按钮触发的集成自动化发送消息已成功触发。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1730433904548-3ce52fa0-b66f-434d-9cd1-2d51e9dc22dc.png)
## 相关内容[​](#u25rb)
[自定义按钮](https://www.yuque.com/yida/support/ohyllrtgx9v5opox)[自定义详情页](https://www.yuque.com/yida/support/ngdnrlxfchrtr0la)
