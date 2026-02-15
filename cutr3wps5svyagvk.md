---
title: 签到
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/rhg7w5n7la2t69bv/qaghpy2gu779gi1l/cutr3wps5svyagvk
source: docs.aliwork.com
---

# 签到

## 1. 使用场景[​](#LtvAJ)
在宜搭内实现提交表单即可查询员工签到情况，包括是否签到，签到时间，签到地点等信息。
## 2. 操作步骤[​](#DtFDB)
### 2.1 步骤一：创建表单[​](#bd8Gw)
创建两个普通表单，其中，「签到查询表」用于触发连接器，进行查询；「查询结果记录」用于接收连接器返回的结果，便于查看。
#### 2.1.1 创建查询表单[​](#MmOgy)
**操作步骤：**创建普通表单，命名为「签到查询表」。添加两个日期组件，分别命名为「查询起始日期」及「查询截止日期」，格式设置为「年-月-日 时:分」，设置为必填项。（操作如图2.1-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637139124214-98ad31bb-6d82-4d24-899a-c07bd843d243.png)
图2.1-1 添加并配置日期组件添加成员组件，命名为「待查询员工」，设置为必填项。（操作如图2,1-2 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637139935581-60253675-d207-4285-91be-29620b2fdc8b.png)
图2.1-2 添加并配置成员组件点击页面右上角「保存」按钮，即可。
#### 2.1.2 创建结果记录表单[​](#W2dpI)
**操作步骤：**新建普通表单，命名为「查询结果记录」。添加 4 个单行文本组件，分别命名为「连接器执行状态」、「是否签到」、「签到时间」以及「签到地点」。（操作如图2.1-3 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637140341704-4b52cd6c-8189-47ba-b953-6d35bbd74b41.png)
图2.1-3 添加并配置单行文本组件点击右上角「保存」按钮，即可。
### 2.2 步骤二：配置「签到查询表」表单连接器[​](#WmIff)
连接器相关介绍请参考[集成&自动化-连接器](https://www.yuque.com/yida/support/zevvr1)
通过对「签到查询表」表单连接器的配置，实现签到查询功能，并且将查询结果自动添加到「查询结果记录」表单中。**操作步骤：**后台管理页面点击选中「签到查询表」表单，并选择「集成与&自动化」Tab分页，点击页面中「新建集成&自动化」按钮。（操作如图 2.2-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637144329062-5b77f9ac-1680-4458-9ec3-8e83ff079ade.png)
图2.2-1 连接器入口将连接器命名为「签到查询」，触发类型选择为「表单事件触发」，点击「确定」按钮。（操作如图2.2-2 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637144477117-f20471d4-270d-4f6f-af75-e50f30fbb24b.png)
图2.2-2 新建连接器点击「表单事件触发」节点，并将触发事件选择为「创建成功」，数据过滤选择为「全部数据」。（操作如图2.2-3 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637200800315-88f64528-d24e-4e18-aa32-b6de68c24570.png)
图2.2-3 配置表单事件触发点击「连接器」节点，选择「签到」应用，点击「下一步」按钮。（操作如图2.2-4 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637200890712-24733bca-ced0-44c6-9067-8cf18179eabe.png)
图2.2-4 选择连接器应用选择执行动作为「获取个人签到记录」，点击「下一步」按钮。（操作如图2.2-5所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637200974447-956829f9-a121-4b21-8868-f86e0bccb768.png)
图2.2-5 选择连接器执行动作配置执行动作，点击「保存」按钮。（操作如图2.2-6 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637201064153-453a7c6c-8eea-4a2f-a8ec-f29c99eafcf4.png)
图2.2-6 配置连接器执行动作将光标悬停到「连接器」节点下方，点击「＋」，选择「新增数据」节点。（操作如图2.2-7 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637201149062-19290844-f3f4-4a44-a7e1-fb870a4d49c3.png)
图2.2-7 添加「新增数据」数据节点配置「新增数据」节点。新增方式：选择为「在表单中新增」，并将表单选择为「查询结果记录」；新增数据：选择为「新增单条数据」；进行字段设置；点击保存。（操作如图2.2-8 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637202193663-d1a41438-c482-47f6-a97b-e270172d2f47.png)
图2.2-8 配置「新增数据」节点「新增数据」节点字段设置中「连接器执行状态」的配置。（如图2.2-9 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/jpeg/1713409292745-d11c2aa5-a510-49cc-b8d8-1c0f41b833fc.jpeg)
图2.2-9 配置「连接器执行状态」字段公式「新增数据」节点字段设置中「是否签到」的配置。（如图2.2-10 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/jpeg/1713409344233-365342af-1cca-48dc-94bb-2138482382c5.jpeg)
图2.2-10 配置「是否签到」字段公式「新增数据」节点字段设置中「签到时间」的配置。（如图2.2-11 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/jpeg/1713409388012-e22cbc47-1ba6-4e84-bcca-0a9412733127.jpeg)
图2.2-11 配置「签到时间」字段公式「新增数据」节点字段设置中「签到地点」的配置。（如图2.2-11 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/jpeg/1713409461295-e72893a6-99a0-47ff-a0cc-ab7a9e974246.jpeg)
图2.2-12 配置「签到地点」字段公式点击页面右上角「保存」按钮后点击「发布」按钮，即可。
### 2.3 步骤三：提交「签到查询表」表单，触发连接器[​](#iuhWQ)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637205114533-8af1ca5f-6a72-4740-8655-acc67cbd2d37.png)
图2.3-1 提交表单
## 3. 效果展示[​](#yrg7g)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637205283428-db987faf-437d-40d3-b554-34e6fbb98ec9.png)
图3-1 效果展示
