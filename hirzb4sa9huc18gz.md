---
title: 专属安全
url: https://docs.aliwork.com/docs/yida_support/_15/kgriw0e3g3rs19bg/hirzb4sa9huc18gz
source: docs.aliwork.com
---

# 专属安全

## 1、应用保护箱[​](#AGGBc)
应用保护箱开关:特定应用开启后，应用实现完全的业务数据保护，平台管理员不再能直接访问应用后台及查看应用敏感数据。启用后IT等其他平台管理员对该应用不可查看，适用于薪酬、算薪等涉及商业机密/敏感数据等的应用。配置入口：后台管理-应用设置-应用权限；![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1702001538824-a39704bb-d93e-4d0b-8c5c-53750d6f6b76.png)
## 2、零信任防火墙[​](#gP2nw)
云上的宜搭需要连接企业内网 集成自动化（https）、外部数据源JDBC(TCP/IP)  服务时，默认需要企业将service暴露在公网互联网中。宜搭支持配合钉钉零信任企业网关技术，避免相关服务直接暴漏于公网，采用零信任网络穿透技术，在保障业务互联互通的业务要求的情况下， 依然保障企业核心服务安全。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1702901854218-f59b3855-11b6-4f95-b5c4-0adf7518bd06.png)
## 3、IP网络围栏[​](#U0Jwd)
管理员可以基于网络地址段或应用，对员工登录钉钉、上传、下载文件等行为进行管控。你可以通过[OA配置后台](https://oa.dingtalk.com/vip2.htm#/securityGate) > **专属钉** > **专属安全 > 安全准入 > IP围栏**，针对宜搭不同应用灵活控制宜搭附件安全下载。**说明**：在 IP 围栏配置的 IP 网段，需要公网 IP ，而不是私内 IP。
| **Before** | **After** |
|---|---|
| 只能整体禁用宜搭的附件下载或运行附件下载，无法按应用维度控制。 | 可以根据**特定网络IP区段**、**特定组织人群**、**特定宜搭应用**不同条件组合，灵活配置附件管控。 |
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1702902641719-853fb285-30c3-4ae6-899c-cf957833489e.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1717583556327-a2c9c6ca-4131-4104-a1e1-3bf895b7a35f.png)
## 4、网络专线模式[​](#KX96J)
专属钉钉对网络专线提供专业的网络代理功能，和实现在身份可信的情况下，在专线及公网间进行通讯。专属宜搭支持专属钉的“网络专线代理模式”能力。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1702902770069-fdd87891-a3c7-4fd4-a1d8-3bf8b8f3ea41.png)
