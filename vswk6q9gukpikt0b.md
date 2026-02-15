---
title: 应用分发概述
url: https://docs.aliwork.com/docs/yida_support/_11/_2/ymt5eevh432paorp/vswk6q9gukpikt0b
source: docs.aliwork.com
---

# 应用分发概述

应用分发是宜搭低代码平台面向服务商提供的一种应用售卖方式，它可以帮助服务商快速地将本组织开发完成的商品应用，部署到客户组织中，并且服务商开发人员可以通过专用通道进入到客户组织，完成一些定制化功能的开发和属性配置。
## 准备工作[​](#LjSqw)
在使用宜搭应用分发功能进行售卖之前你需要先完成以下准备工作：成为[钉钉合作伙伴](https://www.aliwork.com/o/aliwork_partner)。申请[应用分发权限](https://www.aliwork.com/APP_GW50R8NFINN7EC8COT25/custom/FORM-7D966WA1DTGPZEVR0QC9R4RKZZF53S67VTSNKH8?processCode=TPROC--7D966WA1DTGPZEVR0QC9R4RKZZF53U67VTSNKI8&corpid=ding77a7af8924a84af0&dd_addcookie=true&null=&dtcode=c69a0f7d8aa93354b8f8d982b4cfe6b7&code_type=jsapi&dd_enable_replace=true&ddtab=true)。（可选）成为[宜搭高级合作伙伴](https://www.aliwork.com/o/aliwork_partner)。
## 功能介绍[​](#O6J9w)
宜搭应用分发是为服务商伙伴提供的一种敏捷交付的交付方式，当服务商与他的客户达成售卖协议之后，可以使用宜搭应用分发的功能，快速将商品应用交付到客户组织。应用分发功能目前已支持分发应用内所有表单页面、自定义页面、门户、AI 助理、数据准备、酷应用、自定义组件、宜搭角色和接口人信息、集成自动化、连接器、消息通知、待办通知等。并且还支持增量、存量分发，用以升级客户应用。
### 首次分发[​](#jqdlQ)
在分发应用时，除数据大屏外，其他的所有页面在首次分发时会默认发送至目标应用，且页面中配置的关联规则（如数据联动等）、公式、前端代码等都会随页面一起发送至目标应用，此外还支持宜搭 AI 助理、数据准备、集成自动化、连接器、消息通知&待办消息等能力分发。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1732595297466-78e49083-3bac-4638-9e1f-3d9874229c67.png)
分发到客户组织的应用，支持携带示例数据，每个页面可携带15条，并且应用分发到客户组织之后，支持一键删除示例数据。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1732590650653-296f15bf-432c-4933-a543-13b4d63bec80.png)
分发到客户组织的应用，在关闭**编辑**权限的情况下，允许客户对**应用权限**和**页面权限**进行自定义编辑。即，客户可以自由决定，哪些企业内用户可以使用该应用。
| 关闭编辑权限 | 客户失去了编辑权限 |
|---|---|
|  |  |
分发应用时会先校验客户组织是否符合应用的相关权益，如客户组织的权益不满足应用的某个功能权限（如数据量撞墙等），则会分发失败，并有提示报错内容。
### 二次分发[​](#VufEP)
**增量分发**增量分发是指服务商在应用添加新的功能页后，对已经分发的客户应用进行升级的能力。增量分发的页面，将出现在客户目标应用的目录最下方，系统自动创建对应新文件夹，并将本次新分发页面都放在该文件夹内。
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1732537107151-b49e3727-e707-4b3f-aa73-44aa1d685f62.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1732537787870-5cfdde15-5a52-4252-bbaa-97e68dff002f.png)
**存量分发**存量分发是指服务商对应用中已有功能页，进行升级优化改造后，对已经分发的客户应用进行升级的能力。存量分发时不会覆盖用户自定义的**应用权限**、**页面权限**以及**流程设计**。
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1732537964450-90043676-538d-44fb-823e-3cc9b987b0a3.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1732537964447-e437f285-fb72-4cba-bfa0-2e4c3169006f.png)
**注意：**存量分发会对已分发过的客户目标页面进行覆盖更新，因此在进行存量分发时，需提前与客户确认并谨慎操作。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1732594540756-407029c5-18fe-4a0a-b6ac-b2d5248ff904.png)
## 页面关联能力分发[​](#wfb3K)
因角色、接口人、AI 助理、数据准备、自定义连接器等功能具有组织关联性，所以你需要在应用分发成功后，通过远程维护进入到客户组织内，对这些功能进行配置和启用。
### 宜搭角色、接口人[​](#SH0Km)
应用分发支持分发应用内的角色和接口人信息，应用分发成功后，你需要在客户的组织重新维护角色和接口人列表，然后就可以在客户组织里正常使用。**普通表单**：页面消息通知、集成自动化（消息通知等节点）。**流程表单**：页面消息通知 、集成自动化（消息通知等节点）、流程设计器。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1732536339429-f7ed8151-ac7f-4e97-83eb-78ceae4688ce.png)
