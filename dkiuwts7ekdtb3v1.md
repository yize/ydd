---
title: 消息通知
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/gilxm02v9uel919u/dkiuwts7ekdtb3v1
source: docs.aliwork.com
---

# 消息通知

消息通知用于在流程执行到某个节点时，通过已经配置完成的通知类型，向指定人员发送钉钉工作通知或群通知。你可以参考本文操作了解如何配置消息通知节点。
## 添加消息通知[​](#LrYVz)
你可以通过配置消息通知节点，实现流程流程结束、开始或需要同步流程审批进度的目的。登录[宜搭工作台](https://www.aliwork.com/myApp.html)，单击**我的应用**。选择需要的应用，进入**应用设置**页。单击**集成&自动化**，选择已经创建的集成自动化流，单击**编辑**。将光标移动至流程节点的连接线位置，会弹出`**+**`按钮，单击`**+**`，选择**消息节点** > **消息通知**节点。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733713396323-f673a358-3856-45ab-ae98-aade82678170.png)
## 配置消息通知[​](#hGxn3)
选择消息通知节点，在右侧节点配置弹窗中，选择**通知类型**和**通知人员**。
| **通知类型** | **说明** |
|---|---|
| **工作通知** | 工作通知消息是以某个应用的名义推送到员工的工作通知消息，例如生日祝福、入职提醒等。**指定成员**：可以选择企业通讯录内的员工。**指定角色**：可以选择钉钉中的角色或宜搭角色，选择角色后，企业内拥有该角色的成员都将收到消息通知。**指定成员字段**：可以选择表单内的成员字段和流程相关成员。**说明**：工作通知类型的消息支持MarkDown语法，支持的语法类型可参考[钉钉消息通知类型](https://open.dingtalk.com/document/orgapp/message-types-and-data-format#title-afc-2nh-5kk)。 |
| **群通知** | 群通知是指通过群机器人发送流程消息到群，支持使用**小钉机器人**和**自定义机器人**发送。通过小钉发送：通过默认群机器人小钉推送消息，消息内容不支持折行展示，不支持MarkDown。 通过群机器人发送：通过在群设置中添加的自定义机器人发送消息，使用机器人的webhook地址推送，消息内容支持MarkDown语法。 |
设置消息通知内容，支持**自定义**通知内容和使用已有**通知模板**两种方式。**使用通知模板**：使用通知模板是复用你在**宜搭平台管理**页内配置消息通知模板，在此处修改模板内容不会影响源模板。如何配置消息通知模板，可参考[消息通知模板](https://www.yuque.com/yida/support/fkfhud)。**自定义通知内容**：你可以自定义卡片通知内容，支持上传卡片封面图片、标题、内容（支持Markdown）。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1727416199835-ab55e0fa-ad39-4e53-8636-a8779ed8f07f.png)
配置卡片下方按钮跳转位置，支持跳转到当前表单的详情页或自定义链接，支持在自定义链接中携带表单字段作为参数。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1727416427190-5cf9b086-d411-4f59-8ad0-a185e60fd0eb.png)
确认配置完毕后，单击**保存**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733713542705-346bda04-8da7-4762-93e0-0a9edc1707e2.png)
## 常见问题[​](#oIHFf)
**Q：设置了消息通知为什么没有生效？**流程表单若新增、修改、删除了消息模板，需要点击页面蓝色字体【点击此处】，将会自动创建新流程版本进行生效。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1654827861264-ad482856-479e-40be-bc10-3bea1f97e8d6.png)
**Q：宜搭实例详情链接格式是什么？****流程实例详情链接格式**```
https://www.aliwork.com/APP_xxx/processDetail?procInsId=7e03d424-xxxx-8080
```
```
宜���域名/应用AppType/固定参数(processDetail)?procInsId=数据对应的实例ID
```
```
`${location.origin}/${window.pageConfig.appType || window.g_config.appKey}/processDetail?procInsId=${procInsId}`
```
**表单实例详情链接格式**```
https://www.aliwork.com/APP_xxx/formDetail/FORM-xxx?formInstId=FINST-xxx
```
```
宜搭域名/应用AppType/固定参数(formDetail)/数据所在表的formUuid?formInstId=数据对应的实例ID
```
```
`${location.origin}/${window.pageConfig.appType || window.g_config.appKey}/formDetail/${formUuid}?formInstId=${formInstId}`
```
