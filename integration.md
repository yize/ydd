# 集成中心

## 功能介绍​

在通过宜搭的流程页面提交数据后，会在应用维度、组织维度的任务中心产生任务数据，按任务的状态分为「我创建的」、「待我处理」、「我已处理」、「抄送我的」，这些数据随着流程的流转在宜搭通过自身的服务进行存储、更新、查询。

宜搭专属版的企业/组织，可以通过集成中心的集成企业审批任务消息功能，的功能实现和企业/组织自己的任务中心或者待办系统做服务对接，当应用的流程产生任务、更新任务时将会调用企业/组织的服务进行数据推送。
连接器配置成功后，本组织内每个宜搭应用的审批的每个任务（所有任务），都将自动推送至下图中注册上来的服务地址，企业在对应的服务回调中，可自行决定对宜搭的审批相关事件进行选择性处理和消费。
## 如何使用​

### 前置条件​

企业/组织是宜搭专属版自身具备服务系统，并且可以提供HTTP类型的服务供宜搭调用需要满足宜搭的服务回调格式网络可访问
### 接入过程​

**创建HTTP连接器**​
在需要的企业/组织内创建HTTP连接器，在连接器中配置要对接的服务，如下图所示：

可以为每个接口服务单独创建一个连接器，每个连接器配置一个动作，也可以在同一个连接器中创建多个动作，分别表示不同的接口服务。配置5个连接动作，分别对应审批任务的创建、结束、取消、删除、抄送。类似与webhook，当这些事件触发时，宜搭系统会自动回调注册上来 www.yourCorpService.com/xx-interface

**添加连接器动作**​
连接器动作的创建请查看：
wtwabe.md/zevvr1/_1/zbq17y
注意：在对专属任务中心回调服务调用时，接口本身已经具备验签功能，所以在创建连接器动作时可以选择“无身份认证”，如果仍要求连接器的身份验证，可按连接器文档操作。
以下内容主要描述专属任务中心需要的信息：**连接器动作：创建任务**​

请求方式：POST请求入参：task：任务详情，数据格式为JSON字符串，包括了应用appType，企业corpId，任务标题、任务ID、实例ID、创建人、审批人、审批地址等关键信息sign: 参数签名，通过对入参按照一定的要求进行加密，供服务提供方验签，验签方式见下文dateTime: 当前的会到时间戳字符串请求结果：暂无具体要求
在我创建任务时，task任务详情返回的数据示例：{  "actionerId": null,  "actionerName": null,  "appType": "APP_RY60OCRF33Z7534***",  "createTime": 1693462062502,  "currentActivityInstances": null,  "dataMap": {    "cascadeDateField_l4sbkqco": null,    "selectField_l523dlqi_value": null,    "selectField_l523dlqi_value_en_us": null,    "multiSelectField_l523dlqk": null,    "numberField_l4s57vma": "1",    "selectField_l523dlqi": null,    "imageField_llyrklcy": "**",    "textareaField_l4s57vmf": "",    "textField_l4s57vm9": "",    "tableField_l4s57vmb": "[{\"numberField_li9yr6gs\":\"\",\"textField_l4s57vmc\":\"\",\"textField_l4s57vmd\":\"\",\"textField_l51tzkqs\":\"\"}]"  },  "dataType": "pinst",  "deep3": true,  "finishTime": null,  "formInstanceId": "65ab8549-aa06-486a-b5b7-8abe845303a5",  "formUuid": "FORM-MT866EA1X3N9W79GDQM2HB400M413OS76A2GL51",  "instValue": "***"  "modifiedTime": 1693462062502,  "modifyUserAvatar": "",  "modifyUserDisplayName": "",  "modifyUserId": "01690741902689",  "openAvatar": "",  "openId": "",  "openNickname": "",  "openSource": "",  "originatorAvatar": "https://static.dingtalk.com/media/lALPDfJ6d8zhRL_NAbjNAbg_440_440.png",  "originatorCorpId": "ding5d17e3add038d44535c2f4657eb6378f",  "originatorCorpName": "",  "originatorDisplayName": "张红",  "originatorId": "01690741902689",  "processApprovedResult": "",  "processApprovedResultText": "",  "processCode": "TPROC--9BC6687125N9XAJ8873I0864QY122BZ96A2GL1",  "processId": 0,  "processInstanceId": "",  "processInstanceStatus": "",  "processInstanceStatusText": "",  "processName": "",  "serialNo": "",  "title": "**的1位访客申请",  "version": 10}

**连接器动作：完成任务**​

请求方式：POST请求入参：appType：应用标识corpId：企业标识taskId：任务IDactualWorkId：实际处理人formInstId:  实例IDsign: 参数签名，通过对入参按照一定的要求进行加密，供服务提供方验签，验签方式见下文dateTime: 当前的会到时间戳字符串请求结果：暂无具体要求连接器动作：取消任务​

请求方式：POST请求入参：appType：应用标识corpId：企业标识taskId：任务IDactualWorkId：实际处理人formInstId:  实例IDsign: 参数签名，通过对入参按照一定的要求进行加密，供服务提供方验签，验签方式见下文dateTime: 当前的会到时间戳字符串请求结果：暂无具体要求**连接器动作：删除任务**​

注意：目前删除任务只会发生在实例删除，因此回调服务时会将实例ID作为入参请求方式：POST请求入参：appType：应用标识corpId：企业标识formInstId:  实例IDsign: 参数签名，通过对入参按照一定的要求进行加密，供服务提供方验签，验签方式见下文dateTime: 当前的会到时间戳字符串请求结果：暂无具体要求**签名过程**​
服务回调的接口签名采用对入参进行MD5的方式加密，加密结构通过sign参数传给服务提供方，加签过程中需要有宜搭应用的systemToken作为加签密钥对所有入参的参数key通过String.CASE_INSENSITIVE_ORDER进行排序按照key的排序将对应的参数值拼接成加密前的字符串将systemToken拼接在第二步得到的字符串之后通过MD5算法对第三步得到的字符串进行加密，加密时需要采用UTF-8字符集
⚠️注意：systemToken即为应用密钥，查找位置：应用设置-部署运维-应用密钥

### 配置同步策略​

在集成中心中配置某个已创建的审批连接器

## 实现效果​

举例，
下图是某行业客户根据专属宜搭的集成开发能力，将审批任务汇总至自建的审批任务中心，解决了宜搭各类系统应用，企业自有业务系统、生产系统、行政系统等多平台BPM流程统一聚合。

## 常见问题​

**Q：集成中心配置成功后，是否会对历史的数据生效？**
A：不会，仅针对新增数据生效。
**Q：集成中心推送的服务如果因为客户系统故障导致报错时，宜搭有没有提供查询相关日志的功能，以及如果推送失败是否会有兜底重试的机制？**
A：宜搭集成中心基于事件驱动实现的，暂时未提供兜底方案，系统暂时没有做重试等相关逻辑。