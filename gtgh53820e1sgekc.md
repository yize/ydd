---
title: 日志
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/rhg7w5n7la2t69bv/qaghpy2gu779gi1l/gtgh53820e1sgekc
source: docs.aliwork.com
---

# 日志

## 1. 使用场景[​](#Rkwd7)
在宜搭表单内选择成员提交后即可查询该员工在钉钉日志内的未读条数，便于统计。
## 2. 操作步骤[​](#o4Pfp)
### 2.1 步骤一：表单设计[​](#lVmo3)
#### 2.1.1 创建并配置「未读日志查询表」表单[​](#nJhe8)
用于提交数据时，触发连接器动作，发起查询。**操作步骤：**新建表单，命名为「未读日志查询表」。添加成员组件，命名为「选择员工」，设置为必填项。（操作如图2.1-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638155752485-9ed70b1e-0592-47f4-9846-9a253ae13996.png)
图2.1-1 添加并配置成员组件点击页面右上角「保存」按钮，即可。
#### 2.1.2 创建并配置「日志查询记录」表单[​](#WM41a)
用于接收连接器返回的数据，并进行展示。**操作步骤：**新建表单，命名为「日志查询记录」。添加单行文本组件，命名为「未读条数」，状态设置为「只读」。（操作如图2.1-2 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638155873073-cb1e37ba-ffa1-48f7-9b0d-d757ea716929.png)
图2.1-2 添加并配置单行文本组件点击页面右上角「保存」按钮，即可。
### 2.2 步骤二：配置连接器[​](#TKg5j)
宜搭连接器详细介绍，请参见：[集成&自动化-连接器](https://www.yuque.com/yida/support/zevvr1)
用于集成钉钉日志数据。**操作步骤：**后台管理页面「未读日志查询表」>>「集成&自动化」>>「新建集成&自动化」。（操作如图2.2-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638155982983-b2413069-9b1b-459b-aa1b-293103d3854e.png)
图2.2-1 连接器入口将连接器命名为「查询员工未读日志条数」，选择「表单事件触发」类型>>点击「确定」按钮。（操作如图2.2-2 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638156123780-7ccc60b7-d9e8-4439-905c-81b87944f05b.png)
图2.2-2 新建连接器配置表单事件触发：触发条件设置为「创建成功」，数据过滤设置为「全部数据」。（操作如图2.2-3 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638156225909-3b3d697e-b2af-4a00-b3e5-cd3939a17bb8.png)
图2.2-3 配置表单触发事件选择连接器应用：选择连接器应用为「日志」，点击「下一步」按钮。（操作如图2.2-4 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638156325186-47693934-990d-426b-9b8e-0348d6995b65.png)
图2.2-4 选择连接器应用选择连接器执行动作：选择「获取未读日志数」执行动作，点击「下一步」按钮。（操作如图2.2-5 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638156430407-37975950-dbf1-4a7a-afb4-5ee80c8f8639.png)
图2.2-5 选择连接器执行动作配置连接器执行动作，点击「保存」按钮。（操作如图2.2-6 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638156532962-91bf556d-2648-47f3-87b7-f4297c173e3e.png)
图2.2-6 配置连接器执行动作添加「新增数据」数据节点。（操作如图2.2-7 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638156609247-c5afe577-7371-48d8-98d7-42259972e33f.png)
图2.2-7 添加「新增数据」节点配置「新增数据」数据节点。（操作如图2.2-8 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638156716342-13c78472-610f-4450-a22a-27e48b5932d9.png)
图2.2-8 配置「新增数据」节点点击页面右上角「保存」按钮后，点击「发布」按钮，即可。
### 2.3 步骤三：提交表单数据[​](#dfuRN)
用于触发连接器��并接收连接器返回结果。**操作步骤：**填写「未读日志查询表」表单数据，并提交。（操作如图2.3-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638156842836-697eac1c-0fd8-49a4-bf7c-1769887774aa.png)
图2.3-1 提交表单
## 3. 效果展示[​](#N4aMo)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1638157041600-c030a651-b146-44b7-9336-edbbcdc92e98.png)
图3.1 效果展示
