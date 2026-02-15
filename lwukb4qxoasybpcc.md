---
title: 企业模糊搜索组件
url: https://docs.aliwork.com/docs/yida_support/_13/lwukb4qxoasybpcc
source: docs.aliwork.com
---

# 企业模糊搜索组件

## 1、简介[​](#wBcbQ)
### 1.1功能简介[​](#U22sB)
**企业模糊搜索组件**是一种用于快速、准确地查找和识别企业的工具，支持通过不完全或部分匹配的方式进行查询。该组件特别适用于需要频繁查询企业信息的场景，如市场调研、客户管理、供应链管理等。
### 1.2应用场景[​](#OCqr2)
**客户信息补充**：在CRM系统中集成企业模糊搜索组件，帮助销售人员快速补充和完善客户全称
## 2、操作步骤[​](#pTMhG)
### 2.1 入口[​](#ijSQn)
**组织管理员**安装组件，进入表单页面，选择【企业模糊搜索】组件，在右侧进行组件配置。组织内**应用���辑者**，进入表单页面，选择【企业模糊搜索】组件，在右侧进行组件配置。组织内**应用访问者**，进入表单页面，输入关键词直接使用组件。
### 2.2 配置组件参数[​](#mCpD0)
**组织管理员**拖拽组件，并进行组件基础信息配置。
| **图例** | **参数名称** | **基本说明** |
|---|---|---|
| **组织管理员未安装组件**先安装：组件中心-企业模糊搜索-安装**组织管理员已安装组件**安装后需配置AppCode平台管理-组件管理-已安装组件-组件配置-查看帮助文档并填写AppCode | AppCode | 该组件由**杭州安那其科技**上架，需要配置阿里云对应api的AppCode。1、点击链接[https://market.aliyun.com/apimarket/detail/cmapi00047982?spm=5176.api_collection.collection-page.4.591d63a7h8q3Bb#sku=yuncode4198200008](https://market.aliyun.com/apimarket/detail/cmapi00047982?spm=5176.api_collection.collection-page.4.591d63a7h8q3Bb#sku=yuncode4198200008) 2、点击免费试用或者接口购买。 3、前往控制台，复制AppCode，如下图所示： |
**应用编辑者**拖拽组件，并进行组件基础信息配置。**图例****参数名称****基本说明**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1740482053398-90e503f4-0b3d-4b55-8a18-5b71ce1bbeaa.png)
标题默认为企业模糊搜索数据源 默认为阿里云-聚美智数选择模式可选择单选/多选占位提示选择框提示，默认为请输入关键词搜索企业描述信息默认无。可输入提示则显示在输入框下方状态可选择普通、禁用、只读、隐藏校验可选择校验是否必填/自定义校验函数输入关键字后触发搜索，接口返回选项列表：tips：为防止多次触发消耗api次数，触发时机目前默认为输入暂停1s后
### 2.3预期结果[​](#lyxQO)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1740478097218-a94a2dd7-b57c-4253-b46a-63bb0659bcaa.png)
