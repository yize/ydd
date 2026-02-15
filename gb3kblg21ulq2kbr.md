---
title: 宜搭高级数据报表
url: https://docs.aliwork.com/docs/yida_support/_11/xm7x0w/yvp9hw/gb3kblg21ulq2kbr
source: docs.aliwork.com
---

# 宜搭高级数据报表

| **能力** | **免费版** | **轻享版** | **专业版** | **专属BI版** |
|---|---|---|---|---|
| 高级数据报表 | 不支持 | 不支持 | 不支持 | 支持 |
## 1、简介[​](#wBcbQ)
### 1.1 功能简介[​](#U22sB)
随着企业数字化转型的加速，对数据处理和分析的需求日益增长。传统的报表工具在面对大规模数据量和复杂业务逻辑时逐渐显现出不足，特别是在以下几个方面：**性能瓶颈**：传统工具在处理大规模数据时容易出现性能下降，影响用户体验和工作效率。**灵活性不足**：难以满足多样化的报表需求，特别是对于需要定制化开发的复杂报表。**维护成本高**：频繁的手动操作和复杂的配置增加了系统的维护难度和成本。
### 1.2 应用场景[​](#OCqr2)
**财务报表与分析**：财务部门需要定期生成各类报表，如利润表、资产负债表、现金流量表等。通过QBI，可以实现自动化的数据采集和报表生成，提高准确性和效率。**销售与市场分析**：销售团队需要了解市场动态、客户行为和销售趋势，以优化销售策略。QBI可以帮助他们快速获取这些信息，并进行深入分析。**运营绩效监控**：运营部门需要实时监控各项指标，如生产效率、库存水平、供应链状态等。QBI可以提供实时数据展示和预警功能，帮助及时发现问题并采取措施。
## 2、操作步骤[​](#pTMhG)
### 2.1 开启高级数据报表[​](#VJOBD)
#### 2.1.1 已有应用开启[​](#Fvu3U)
客户在权益中心下单后，宜搭小二手动在后台开启或关闭高级数据报表项目。**位置：**平台管理-基本信息-高级功能。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741225853994-8da5f17c-167d-4170-8b0f-eccfcf8f6a76.png)
#### 2.1.2 新建应用开启[​](#P5ORq)
进入宜搭应用管理后台，点击“新建应用”。在弹窗中填写应用基本信息。新建弹窗中，点击更多应用配置，开启应用专属存储、应用专属物理列、应用专属环境、高级报表隔离库。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741240952636-db74cf03-59b4-46b6-9f8c-59dd629877bc.png)
应用专属存储开启后，应用数据将存至专属存储模式且不支持回退。应用专属物理列开启后，应用发布支持物理列。应用专属环境开启后，应用发布将支持独立环境部署以及多版本沙箱能力。高级报表隔离库开启后，“高级报表隔离库”将独立支持高级报表能力。
### 2.2 权限设置[​](#WN5DJ)
**位置**：开通本功能后，点击某个应用进入宜搭应用管理后台 > 高级数据工作台。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741225971953-56c9ab5f-0934-4762-8383-e5502f7332b1.png)
**操作步骤**：**申请权限**：平台管理员：点击“加入应用主管理员”。非平台管理员：点击“申请加入应用主管员”。**权限授予**：进入“宜搭平台管理 > 权限管理”，授予高级数据管理权限。
### 2.3 升级框架配置[​](#G3q6C)
**位置**：**方式一：**宜搭应用管理后台 > **高级数据工作台。**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741226678086-734459b0-c6fd-430b-91f4-1e9bf1ca9e66.png)
**方式二：**宜搭应用管理后台 >**应用设置>基础设置>专属****配置-应用基础框架配置**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741244017514-a123e4a8-c5a8-4db5-9460-0cfb6ee4712c.png)
**操作步骤**：**升级**[**专属存储**](https://docs.aliwork.com/docs/yida_support/ifpp7g/tymkt6?spm=a2q5o.26728408.0.0.663c1b535MBrTh)**（必选）**：客户自行配置专属宜搭数据库，用于存储和计算宜搭应用数据。**升级**[**物理列**](https://docs.aliwork.com/docs/yida_support/ifpp7g/tymkt6/txlxfn3g729wxdt0?spm=a2q5o.26728408.0.0.663c1b535MBrTh)**（必选）**：已开启专属存储的客户必须选择开启物理列，才能使用Q项目（高级数据报表项目）。[**数据隔离库**](https://docs.aliwork.com/docs/yida_support/_4/xm7x0w/yvp9hw/evqw9zgzrsba9udg)**（可选）**：设置数据隔离库，用于高级报表功能查询计算，避免高级报表查询造成专属存储过载。可选择“升级”或“暂不升级”。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741227090920-163d9d42-3204-4a10-8c7d-d7f1ddc6c6eb.png)
完成上述配置后，进入高级数据工作台。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741227473746-deb49da4-ba4e-474b-8d08-5de6ddb8dae1.png)
### 2.4 管理数据源[​](#A14Ve)
**位置**：宜搭应用管理后台 > 高级数据工作台 > 数据构建>数据源。**选择数据源：**点击我的数据源——当前默认为本应用——点击应用中的某个表单数据源，如下图所示：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741231597563-5322b7de-3f0c-40f7-8bde-77a64c864a60.png)
**新建数据源**：点击“新建数据源”-选择数据源，当前支持的数据源类型包含：各类数据库、应用服务数据。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741227940583-fd9b2676-dceb-4fbb-8917-1fba6df2c1e6.png)
配置数据源：各类数据库配置方式可查看[**创建数据库数据源**](https://qbi.data.aliwork.com/docs/topics/t2285240)**。**应用数据源配置方式可查看[**创建应用数据源**](https://qbi.data.aliwork.com/docs/topics/t2810091)**。**经过上述配置，宜搭数据源会自动同步到Q高级报表。数据源添加完成后，选择数据源进行数据合并/关联处理，完成数据集建设。
### 2.5 管理数据集[​](#Dfo9L)
**位置**：宜搭应用管理后台 > 高级数据工作台 > 数据构建>数据集-新建数据集。**新建数据集：**选择数据源——选择数据表——配置数据，如下图所示：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741232986579-a6cc6a56-7915-4588-b932-6e1c937c2e0a.png)
**保存数据集：**配置完成后，点击保存，输入名称及保存位置，点击确定。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741233103942-1ceabbad-1004-4c97-a288-10cc7a559c7d.png)
### 2.6 应用数据[​](#ckqv8)
#### [2.6.1 搭建仪表盘](https://qbi.data.aliwork.com/docs/topics/t2282706)[​](#cUcJb)
**位置**：宜搭应用管理后台 > 高级数据工作台 > 仪表板>新建仪表板。**新建仪表盘**：点击“新建仪表盘”。根据需求搭建仪表盘内容，操作步骤参考[**仪表盘**](https://qbi.data.aliwork.com/docs/topics/t2282706)**。****配置图表：**选择数据集，新增对应维度、度量字段。例如：通过设备编号统计设备数量。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741239350482-7693bf32-0ce9-4009-89c0-6f17bae63135.png)
将字段拖入对应维度、度量区域，点击更新数据。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741234303152-b7ba2ae9-fd64-462e-888e-3ab685db6c7f.png)
**发布仪表盘**：仪表盘搭建完成后，点击“发布”。发布后点击【查看】，跳转至仪表盘访问页。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741239640519-fd842c95-ec5d-48c7-8a08-1951ef3845e5.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741239719417-9ff1734b-67ae-465b-85ef-2daee7a3eb93.png)
#### [2.6.2 创建数据门户](https://qbi.data.aliwork.com/docs/topics/t2280585)[​](#yDD03)
**位置**：宜搭应用管理后台 > 高级数据工作台 >数据门户。**新建数据门户**：根据需求搭建仪数据门户内容，操作步骤参考[**数据门户**](https://qbi.data.aliwork.com/docs/topics/t2280585)**。**
#### [2.6.3 创建电子表格](https://qbi.data.aliwork.com/docs/topics/t2280568)[​](#nkz9I)
**位置**：宜搭应用管理后台 > 高级数据工作台 >数据分析-电子表格。**操作步骤**：操作步骤参考[**电子表格**](https://qbi.data.aliwork.com/docs/topics/t2280568)**。**
#### [2.6.4 创建自助取数](https://qbi.data.aliwork.com/docs/topics/t2280589)[​](#l3tSI)
**位置**：宜搭应用管理后台 > 高级数据工作台 >数据分析-自助取数。**操作步骤**：操作步骤参考[**自助取数**](https://qbi.data.aliwork.com/docs/topics/t2280589)**。**
### 2.7 发送仪表盘到宜搭[​](#AiipE)
**位置**：宜搭表单页面 > 新增页面**操作步骤**：复制已发布的仪表盘链接。在宜搭表单新建页面-外部链接，将仪表盘链接粘贴至表单页面。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741240051050-957370db-2c46-4e0d-8a61-afc08fc6d304.png)
点击确定后，将在左侧边栏中，查看仪表盘页面。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1741240120448-640fdde0-f08f-4d36-90ce-9aeecb9d0091.png)
## 3、常见问题[​](#fIJYT)
**Q：升级专属存储/物理列/数据隔离库等失败是什么原因？应该怎么办？**答：网络等环境不稳定导致升级失败，可稍后再试，如仍有问题可联系宜搭对接人。
