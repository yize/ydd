---
title: 消息通知
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/rhg7w5n7la2t69bv/qaghpy2gu779gi1l/bivkrlpcbnhzxids
source: docs.aliwork.com
---

# 消息通知

注意：当前该功能仅能够将消息发送到通过连接器创建的群聊天内。通过连接器创建钉钉场景群方法请参考：[使用宜搭连接器自动建群](https://www.yuque.com/fuqiang-lg6nm/bmno0y/sruegk)
## 使用场景[​](#EY217)
当用户在宜搭上完成某项任务，或通过数据分析后发现达到某项指标，需要发送群消息通知群成员时，我们就可以通过宜搭连接器实现向钉钉群内发送消息。
## 操作步骤[​](#a2Dhb)
### 步骤一：创建数据底表[​](#WUCCb)
创建表单，用于记录通过连接器创建的群聊信息，包括群名与群ID等。**操作步骤：**新建普通表单，命名为「群信息记录表」。添加两个单行文本组件，分别命名为「群名」与「群ID」。（操作如图2.1-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650332143901-3623d9b5-8323-4511-b7ec-f7dd0479ba7d.png)
图2.1-1 群信息记录表单设计点击页面右上角「保存」按钮，即可。
### 步骤二：获取群聊信息[​](#if90r)
通过步骤一，我们已经完成数据底表即「群信息记录表」，接下来我们将对创建群聊的连接器进行改造，目的是将其创建完成的群聊信息自动录入到「群信息记录表」中。**操作步骤：**编辑名为「创建群聊」的集成&自动化流程，在流程内添加「新增数据」的数据节点，并进行配置。（操作如图2.2-1 所示）说明：该步骤的作用是，每当通过「创建群聊」表单新建一个场景群，都会将该群的信息自动添加到「群聊信息录入」表单中，为后续操作提供数据来源。
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637549041259-b7e4f04c-bda2-4438-ae32-ad3da3ceedc6.png)
图2.2-1 添加「新增数据」数据节点配置「新增数据」节点：将新增方式设置为「在表单中新增」，并将表单选择为「群信息记录表」；将新增数据设置为「新增单条数据」；最后，进行字段设置。（操作如图2.2-2 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637549324936-7a3b15cd-b43b-4ac4-93f7-c45fe31ee000.png)
图2.2-2 配置「新增数据」数据节点点击页面右上角，保存按钮后，再点击发布按钮。通过「创建群聊」表单提交数据备用。（操作如图2.2-3 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637549852346-5c866d3f-15e5-4808-a2c9-4b600a06e56b.png)
图2.2-3 提交「创建群聊」表单数据
### 步骤三：创建发送群消息表单[​](#GwrS3)
创建一个名为「群消息内容录入表」的表单，用于录入消息内容。**操作步骤：**新建表单，命名为「群消息内容录入表」。添加一个多行文本组件，命名为「消息内容」，设置为必填项。（操作如图2.3-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650348503743-45fd7dce-4607-42c9-905c-78d8859af8dd.png)
图2.3-1 添加并配置多行文本添加下拉单选组件，命名为「选择群聊」，并将选项类型设置为「关联其他表单数据」，表单数据选择为「群信息记录表-群名」。（操作如图2.3-2 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650348437805-37fb23da-64c7-408a-8d80-b53dd632c279.png)
图2.3-2 添加并配置下拉单选组件添加单行文本组件，命名为「群ID」，组件状态设置为「只读」，默认值配置为「数据联动」，用于关联「群信息记录表」，实现当「群名选择」组件的值等于「群信息记录表」表单内「群名」时，「群消息内容录入表」的「群ID」组件的值等于「群信息记录表」的「群ID」值。（操作如图2.3-3 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650348374498-7dddd632-a846-4c51-b49f-28c133dc7796.png)
图2.3-3 添加并配置单行文本组件点击右上角「保存」按钮，即可。
### 步骤四：创建集成&自动化[​](#Nmjlc)
连接器的相关介绍请参见文档：[集成&自动化-连接器](https://www.yuque.com/yida/support/zevvr1)
为实现提交表单时，系统自动发起群聊需求。我们需要给「群消息内容录入」表单配置连接器。**操作步骤：**在后台管理界面，点击页面上方「集成&自动化」，最后点击「新建集成&自动化」的从空白新建。（操作如图2.4-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650348650248-0c2bb631-ad1d-4f90-a9f6-0d9c878316bb.png)
图2.4-1 连接器入口配置集成&自动化名称为「发送群消息」，触发类型为「表单事件触发」，点击确认，即可。（操作如图2.4-2 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650348918949-e869207d-d9f8-48e4-bfef-471c33e46885.png)
图2.4-2 新建连接器
### 步骤五：配置集成&自动化[​](#BRJwc)
**操作步骤：**点击选中「表单事件触发」节点，右侧触发事件选择「创建成功」，数据过滤选择「全部数据」，最后点击保存。（操作如图2.4-3 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650348855516-d17bc6f6-9332-46fa-bb65-b578a95a843a.png)
图2.4-3 配置「表单事件触发」节点点击选中「连接器」节点，右侧选择「消息」钉钉官方应用，点击下一步。（操作如图2.4-4 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650349017823-605e1204-e0b0-4bde-b5b2-c237ff1e770e.png)
图2.4-4 配置「连接器」节点--选择应用执行动作选择「发送消息到企业群」，点击下一步。（操作如图2.4-5 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650349073964-5b5ea4fc-2938-4a8c-80f9-089140727c3e.png)
图2.4-5 配置「连接器」节点--选择执行动作配置执行动作后，点击保存。（操作如图2.4-6 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1650349141803-fa6c8129-eeb4-4f2f-9fac-ec985d9c03c3.png)
图2.4-6 配置「连接器」节点--配置执行动作点击页面右上角保存按钮后，点击发布，即可。
### 步骤六：填写并提交群消息内容[​](#zb4Jb)
通过上述步骤，我们实现功能的配置工作及数据准备已经完成，接下来，只需提交表单即可触发连接器，从而向指定群聊发送消息。**操作步骤：**填写表单内容，点击提交，即可。（操作如图2.5-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637551520275-70eb81f6-4766-4c17-9ddb-ee8a3877943f.png)
图2.5-1 录入表单信息并提交
## 实现效果[​](#biwT0)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637551707568-2a38d206-b225-453a-bbd5-611e548e2663.png)
图3-1 通过连接器向场景群内发送消息效果展示
