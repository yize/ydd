---
title: HTTP连接器
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/rhg7w5n7la2t69bv/pvwgxx4gyhmsk5g1
source: docs.aliwork.com
---

# HTTP连接器

| **功能** | **免费版** | **轻享版** | **专业版** | 专属版 |
|---|---|---|---|---|
| HTTP连接器 | 1 个 | 1个 | 不限数量 | 不限数量 |
如果当钉钉官方连接器无法满足你的需求，但又急需打通钉钉应用、自建系统或者第三方应用系统时，你可以通过宜搭连接器工厂进行自定义连接器。
## 步骤一：新建连接器[​](#g9afi)
使用管理员身份登录[宜搭工作台](https://www.aliwork.com/workPlatform)。单击右上角**平台管理**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703646834204-6f254b32-698e-4f8d-ac24-49bc23b25e45.png)
按钮，进入平台管理页面。单击左侧菜单栏**连接器工厂**，然后单击**新建连接器**，选择HTTP连接器。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703648508494-bad3a8e1-03e2-481d-ba5d-ce866cf8e249.png)
参考以下信息配置连接器的基本信息，配置完成后单击**下一步**。**连接器显示名称：**自定义连接器的名称**图标图片地址：**连接器显示的 icon，不填会显示默认 icon**连接器描述：**连接器的基本描述**域名：**请求的 host 地址，不需要带上“http://”或“https://”协议头，同时也不需要“/”结尾**请求协议：**协议类型**Base URL：**可以配置请求地址中的基本前缀 URL，没有可以直接填写 “/”![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703655701005-3c99d0e4-7d70-4ee9-bca4-0eb07a206f41.png)
参考以下内容，配置**身份验证类型**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703663002197-035664f4-2f14-40d8-a16c-6833d6350cc9.png)
**身份验证类型****说明**无身份验证无身份验证就是不需要任何验证信息，直接调用的接口，通常用于访问一些公开的接口。基本身份验证基本身份验证是指基于的 HTTP请求中 Authorization 请求头的验证。请求消息头含有服务端用于验证用户代理身份的凭证。**格式为**：`Authorization: Basic <密文>`。例如：你可以在 Header 中加入`Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l` 的Base64 编码后账号密码信息。你只需要配置账号密码的提示标签，用于提示使用者在注册鉴权信息知道填写什么内容。例如：**username 标签****password 标签**API 密钥即 **APIKey** 鉴权方式，该APIKey长期有效（请开发者妥善保管），访问者在待访问的系统中创建生成秘钥，开发者可直接通过此凭证调用支持此类鉴权的公开 API。**参数标签**：用于配置鉴权信息时提示。**参数名称**：系统需要的 apiKey 名称。**参数位置**：可以选择把鉴权信息附加在查询参数或者 header 里，根据请求的系统需要选择。阿里云 API 网关即连接器创建完成之后添加鉴权模板时，模板填写 App Code 后可调用对应的阿里云API。更多内容请参考，[使用认证 App Code 方式调用API](https://help.aliyun.com/document_detail/115437.html)。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1653272675853-1924c0b8-8f7a-4071-953f-747fc32b8da9.png)
钉钉开放平台验证创建完连接器后添加鉴权模板，模板填写 `App Key` 、`App Secret` 后可调用钉钉开放平台API（含宜搭部分API）。添加鉴权模板后宜搭会通过鉴权自动生成鉴权参数 `access_token` ，在请求时添加到 `Header` 参数 `x-acs-dingtalk-access-token` 中，无需再次生成。更多内容，请参考[钉钉应用开发流程](https://open.dingtalk.com/document/orgapp/overview-of-development-process)。钉钉零信任网关如何使用钉钉零信任网关，可参考[钉钉开放平台-零信任网关鉴权](https://open.dingtalk.com/document/connector/untitled-document-4)。
## 步骤二：创建执行动作[​](#tGezK)
在执行动作页面，单击**新增执行动作**，然后根据以下信息进行配置。**名称****描述**基本信息配置当前执行动作的基本信息。**唯一标识**：用于识别不同的操作。动作名称：执行动作的名称。动作描述：执行动作的描述信息。接口请求配置当前执行动作触发时，对哪个接口发起请求。**请求地址**：接口请求链接，请求域名会自动填充为连接器的域名。**请求方式**：支持GET、POST、DELETE、PUT、HEAD、OPTIONS、PATCH等请求方式。**Query**：代表请求的参数，通常指的是 URL 的问号`?`后面附加的参数，单击加号新增。**Body**：如果是 POST 请求之类的情况，可能还有 Body 字段，支持使用请求JSON进行解析。**Headers**：可以在此处自定义额外的请求头信息，目前仅支持静态配置。**Path**：代表 URL 中配置的带大括号的变量，比如`{pathParam}`，其中`pathParam`会作为变量名。**说明**：请求参数支持配置系统字段登录人ID和组织ID。
接口返回用于配置接口调用成功后，预期的返回结果，支持使用JSON进行解析。**说明：**如果接口返回非JSON对象，则不支持在集成自动化中直接使用，需在脚本节点自行解析。
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703665595707-59ddd128-e037-492a-ad61-6eab670fb676.png)
## 步骤三：鉴权配置[​](#EEwvu)
所有的自定义连接器都需要建立对应的请求鉴权方案，即使是「**无身份验证**」也需要创建。新建账号已设置好的连接器点击测试则会出现选择鉴权账号，此时也可以新增鉴权账号。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1653271348654-3c1908f7-8f6e-4c34-ae11-33aa5b6e8644.png)
输入**账号显示名称**、**App Key**、**App Secret** 等信息，然后单击**确认**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1653271469186-06ad8b35-268a-4c10-a9da-f38bf1a4ecad.png)
## 步骤四：测试连接器[​](#Op4cL)
在连接器详情页，单击右上角**测试**按钮。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1703665664686-bb99ad10-c5b9-4f6a-b3b1-78d0cd44b3e1.png)
选择使用的鉴权，配置测试的参数。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1653271984053-6a9c9250-892c-44b0-89b9-ecca29c3b996.png)
单击**测试**，出现预期结果即为配置成功。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1653272026007-900807cf-c724-4d91-a02d-ec5f45680557.png)
