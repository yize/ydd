---
title: 官方数据互联
url: https://docs.aliwork.com/docs/yida_support/_11/xm7x0w/yvp9hw/_1/rgtg45e6z9vwlgso
source: docs.aliwork.com
---

# 官方数据互联

| 能力 | 免费版 | 轻享版 | 专业版 | 专属版 |
|---|---|---|---|---|
| 连接钉钉数据 | 不支持 | 不支持 | 部分支持 | 支持 |
## 功能介绍[​](#uvKjg)
宜搭平台的数据准备功能具备出色的数据整合能力，全面支持对宜搭内部、Excel表格以及各类数据库（外部数据源）的数据进行深度组合加工。该功能实现了与钉钉的官方服务数据的无缝互联，涵盖花名册、OA审批流程、智能人事系统（包括但不限于入职离职管理、转正调岗操作）以及各项业务通用指标等核心数据源。借助这一特性，企业能够在宜搭平台上高效地推动低代码开发与企业全方位数据资源的深度融合分析，进而显著提升企业在数据驱动决策层面的效率与效能。支持的数据源权益如下。before通用指标业务在线概览花名册组织在线明细OA审批审批实例数据智能人事入职+离职+转正+调岗考勤到岗信息数据时效性次日更新次日更新实时数据次日更新实时数据宜搭专业版✅✅❌❌❌钉钉专业版 + 宜搭专业版✅✅✅✅✅宜搭专属版✅✅✅✅✅after通用指标业务在线概览花名册组织在线明细OA审批审批实例数据智能人事入职+离职+转正+调岗考勤到岗信息数据时效性次日更新次日更新实时数据次日更新实时数据宜搭免费版❌❌❌❌❌宜搭轻享版❌❌❌❌❌宜搭专业版✅✅❌❌❌钉钉专业版 + 宜搭专业版✅✅✅✅✅钉钉专属版 + 宜搭专业版✅✅✅✅❌宜搭专属版✅✅✅✅❌各数据源支持数据字段如下。数据源数据时效性字段通用指标次日更新通讯录人数、日志提交人数、日志提交率、发DING总数、群聊总数、报销单数、近一天创建文档数等。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1709780931829-3a680bf8-4b85-43fe-b3aa-2a5ba27e5f5d.png)
花名册次日更新员工姓名、职位、工号、部门名称、试用期类型、入职时间、转正时间等。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1709781020493-39e592c2-cfff-4df8-8fc9-0946f9b982bf.png)
OA审批实时更新表单自定义业务字段、提交人、提交时间、审批人、审批状态、审批完成时间、审批记录等。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1709781064946-0e6569fc-02ff-4750-81e6-f50cbc401ac1.png)
智能人事次日更新入职时间、岗位职级、转正时间、转正职级、离职时间、离职原因等。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1709781109403-a0fcc6ca-1b05-4fb5-aa19-b7d98c2c7ec7.png)
考勤（半年内）实时更新人员姓名、部门、打卡时间、是否加班、是否应到、考勤组名称、是否外勤、是否缺卡等。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1709783136141-0a54cb06-abab-4e20-97c0-9da6e98444ed.png)
## 申请权限[​](#KYZnR)
使用官方数据互联时，应用中应用主管理员需要先获取对应相应数据的管理权限。例如，在使用员工花名册数据时，需要获取智能人事的子管理员权限。操作步骤如下：钉钉主管理员登录[OA管理后台](https://open.dingtalk.com/document/orgapp/obtain-developer-permissions)。单击安全与权限 > 权限管理 > 子管理员 > 添加子管理员。选择需要添加的成员，然后配置所需要的权限。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1709808535130-a40070a3-f3ae-4453-8eae-328df802c25a.png)
配置完成后单击保存。
## 数据集权限[​](#rlXU7)
宜搭新增对所有数据集的独立权限控制，设置了权限的数据集在数据使用消费场景中，会实时进行数据的人员（哪些人可看）、行权限（规则配置）、列权限（字段范围）进行过滤管控。随着宜搭内对数据更丰富的场景使用，报表、大屏等消费场景的数据权限管控将十分必要。你可以在数据工厂 > 数据集列表页面，选择具体的数据集，进行权限设置。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1710241996554-63d5a980-624b-4b29-902e-52de520c0493.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1710242001938-84febdf2-fa32-4fb0-95e0-4fdf205d20d1.png)
