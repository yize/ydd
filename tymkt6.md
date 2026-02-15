---
title: 存储配置
url: https://docs.aliwork.com/docs/yida_support/_15/tymkt6
source: docs.aliwork.com
---

# 存储配置

专属版专享
| **能力** | **免费版** | **轻享版** | **专业版** | **专属版** |
|---|---|---|---|---|
| 专属存储&专属安全 | 不支持 | 不支持 | 不支持 | 支持 |
在宜搭专属版中，我们对业务的数据存储进行了定制能力增强，大家可以选择更自主安全可控的方式，实现业务数据的私有化存储。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1657005014705-b3cd4b13-4c6f-4431-98b6-28955f6fa457.png)
## 按需开通（应用级）：[​](#dQrSg)
### 1、新建应用 可选开启：[​](#TjU8u)
在新建应用时，可选择此应用的业务数据是存在公有云（默认），还是专属的混合云数据库仓库中（核心重要数据）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1656640766967-ee75bc09-2583-4187-aba6-8030134f5cbe.png)
### 2、历史应用 可手动开启：[​](#bCTSm)
应用管理员可在应用后台的-应用设置-基础设置-专属配置，应用专属存储进行选择开启。开启后该应用的历史数据及未来新增数据，将会存储平台管理中的专属数据库(PostgresSQL)及专属附件OSS 中升级期间应用功能暂停使用，推荐业务低峰时段操作，开启过程预计耗时3-10分钟，升级后不可取消。升级过程中可以手动中止。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1714014989950-fc544b8f-d615-49db-941d-bced9f052b2e.png)
### 3、升级操作与终止操作：[​](#sRidd)
应用基础框架配置的变更是一个耗时操作，需要花费一定时间，在过程中若需要终止操作，可进行手动停止。终止升级后，应用的基础配置项将恢复原有云端存储的原始配置和运行模式。升级的时长的影响因素：应用数据量（业务实例数据总量、附件总量）专属存储的上下行网速及带宽本地的专属存储性能（数据库 、OSS）是否是业务高峰时段![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1714015312609-eacadaba-2fee-4e35-afe6-50f617d32d3e.png)
