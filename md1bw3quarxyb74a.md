---
title: FaaS连接器
url: https://docs.aliwork.com/docs/yida_support/_10/md1bw3quarxyb74a
source: docs.aliwork.com
---

# FaaS连接器

| **功能** | **免费版** | **轻享版** | **专业版** | **专属版** |
|---|---|---|---|---|
| FaaS连接器调用量 | 100 次 | 1000 次 | 1000 次 | 5000 次 |
宜搭为每个宜搭组织都免费赠送了调用次数，如果使用次数用尽，你可以在[宜搭平台管理](https://www.aliwork.com/platformManage/basicInfo)页进行增购。详细定价策略可参考[增值服务包](https://www.yuque.com/yida/support/gksb65)。
宜搭FaaS连接器依托阿里云函数计算 FC，使开发人员可以只需关注业务处理代码的编写，无须关注服务器的部署、运维、扩容和缩容，直接赋予开发者**云开发能力**。开发人员可以在**WebIDE**编辑代码，使宜搭连接器更加贴合自身业务，**灵活可定制**。
## 步骤一：新建连接器[​](#g9afi)
使用管理员身份登录[宜搭工作台](https://www.aliwork.com/workPlatform)。单击右上角**平台管理**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703646834204-6f254b32-698e-4f8d-ac24-49bc23b25e45.png)
按钮，进入平台管理页面。单击左侧菜单栏**连接器工厂**，然后单击**新建连接器**，选择FaaS连接器。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703666148281-1b705bd7-8625-4393-87e5-59e8b848f4a3.png)
设置**连接器名称**、**连接器图标**和**开发语言**，然后单击**下一步**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703666771109-5154e0cb-172c-420a-8ae4-d820fc1d2426.png)
在执行动作页面，配置执行动作的**基本信息**、**接口请求**和**接口返回**，然后单击**保存**。**说明**：接口请求和接口返回支持使用JSON数据进行解析，你可以先输入对应Body的数据结构，再单击解析Body按钮进行解析。
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703667748731-0e63b367-26c5-4be3-bf35-09cb219ed35e.png)
## 步骤二：开发连接器[​](#COWFI)
FaaS连接器的开发和使用，可参考[集成&自动化 - FaaS（云）连接器](https://docs.aliwork.com/docs/yida_subject/_2/zbqlbk0sd2f6z74q#Cu4nk)。
