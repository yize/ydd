# 宜搭插件开发指南

## 1、前言​

宜搭插件是用于扩展和增强宜搭平台功能的工具，允许根据自身需求定制和添加新的功能。宜搭插件是对平台既有功能的扩展，是宜搭个性化的重要基础能力。
当前宜搭支持的扩展能力：平台功能扩展（如自定义报表、数据集成、权限管理）、组件扩展（如图表组件、表单组件、地图组件）、流程节点扩展（如审批节点、通知节点、执行节点）。
本文旨在帮助各位开发者快速理解并运用宜搭插件开发的能力。
### 1.1什么是连接类组件？​

本质是对API的封装，出入参会映射成页面组件，通过按钮或者入参组件的onChange来触发调用API，返回参数会自动填充到出参组件中。

例如：宜搭的官方AI控件就是一种连接组件

## 2、开发步骤​

### 2.1开发入口​

插件开发者入驻申请通过后，平台会为您开通插件开发入口，您可以在平台管理>插件管理>开发插件操作；

### 2.2开发链路​

从创建一个新的插件开始，经过类型选择、服务注册、参数配置、前后端开发，再到测试和最终发布的一系列步骤，具体如下：新建插件选择插件类型注册插件服务配置插件参数测试（发布到组织）发布到插件中心

### 2.3连接类组件开发​

以下以**查询天气组件demo**为例，简述整个组件开发过程。
**查询天气组件demo**2.3.1 创建一个新的连接类插件**​

**2.3.2 进入插件开发页面**​

**2.3.3 注册插件服务**​
对于连接类的组件，
一般要注册1-2个服务。
一个是组件本身用到的业务API服务，另一个可选的是用于入参数据源。当入参需要从API获取数据源，如下拉单选的选项是动态获取的，此时需要配置。
完成查询天气需要注册两个服务，可按照如下示例填写：
（1）服务一：根据城市名称模糊查询城市id服务（作为入参数据源）。

（2）服务二：根据城市id查询当前天气的服务（业务API服务）。

值得注意的是查询天气的url中使用了path变量的方式创建，在插件服务调用请求处理中会演示如何使用这个{cityId}变量。
https://weather.cma.cn/api/now/{cityId}

**2.3.4 进入设计视图**​
**点击去设计创建一个连接类组件并进入设计视图：**

**2.3.5 连接类组件开发**​**编辑基本信息**​**编辑连接类组件的基本信息，**点击设置连接组件，可以编辑连接类组件的基本信息：

编辑连接类组件基本名称和图标url

效果图：

连接类组件开发：连接类组件主要包括三部分内容：输入组件，输出组件和按钮，在插件设计器中主要的设计目标是完成基础组件与插件服务的输入输出的映射关系绑定。根据需求设计决定输入组件和输出组件的个数，本次开发示例中查询天气的入参为1个：城市id，出参共6个分别为：当前降水量，当前温度，当前湿度，当前气压，风速，
上次更新时间地址。打开组件面板，拖入输入和输出组件分别置入参和出参中。

点击组件，在右侧属性面板完成组件名字编辑。

设置调用服务的必填值，运行服务时会检查是否填写。

**服务调用**​点击设置连接类组件，在设置面板中选择一个插件服务作为连接类组件的调用服务。

目前完成对连接类组件与服务的绑定，如何去构建执行服务的入参和出参？由于服务的输入结构是不统一的，所以在连接类组件设置面板提供了处理输入参数和输出结果结构的方式——请求处理函数和数据处理函数。**构建执行服务的入参（请求处理函数）：**通过在请求处理函数中编写JavaScript代码完成对组件值的获取和其他参数，示例如下：

示例代码如下：

function willFetch(vars) {  var cityId = vars.data.textField_m7a2rpim;  vars.data.input = JSON.stringify({    "path":{      "cityId": cityId    }  });}

**获取表单组件的值：**在请求处理函数中，vars.data.textField_m7a2rpim能够获取到表单中组件的值，其中textField_m7a2rpim为组件的唯一标识（如下图所示）。

**构建插件服务的入参（适用于faas的插件服务）：**在请求处理函数中，vars.data.input的值最终会作为插件服务的入参，所以将构建的入参赋值给vars.data.input即可。例如：
function willFetch(vars) {    vars.data.input = JSON.stringify({        "arg0": {            "name": ""        },        "arg1": {            "id": "",            "xx": ""        }    });}最终传递给服务的输入则为下列对象：{    "arg0": {        "name": ""    },    "arg1": {        "id": "",        "xx": ""    }}

**构建外部请求类型的插件服务（适用于Http和Https的插件服务）：**同上，vars.data.input的值最终会作为插件服务的入参，所以将构建的入参赋值给vars.data.input，由于Http和Https类型的插件服务在发起请求时根据不同的API接口可能需要构建不同的请求参数部分如：查询参数Query、请求体参数Body、请求头参数Header、路径参数Path，构建示例代码如下：
{    "query": {        "corpId": "ding12345",        "uid": "9527",        "pageSize": "100",        "bizType": "test"    },    "body": {        "name": "bob"    },    "header": {        "Content-Type": "application/json"    },    "path": {        "id": "123"    }}入参解释：-- query: 此部分构成请求的查询参数。-- body: 此部分构成请求的请求体部分，用于在 HTTP 请求中载入需要提交的数据。-- header: 此部分构成请求头信息，
为服务器提供额外的上下文。-- path: 此部分构成路径参数，位于 URL 中，通常用于直接定位请求的特定资源。-- 对于API接口https://xxx.com/query/{id}/test，调用服务时会转变为https://xxx.com/query/123/test?corpId=ding12345&uid=9527&pageSize=100&bizType=test其中请求体参数为{  "name": "bob"}请求头参数为：{  "Content-Type": "application/json"}

本次demo中查询天气的服务api接口带有path变量的api，无查询参数，请求体参数，请求头信息，如下示例代码构建即可：
function willFetch(vars) {  var cityId = vars.data.textField_m7a2rpim;  vars.data.input = JSON.stringify({    "path":{      "cityId": cityId    }  });}//代码解释：运行时路径参数的值来自于组件textField_m7a2rpim

**3）处理执行服务的出参：**通过在数据处理函数中编写JavaScript代码完成对服务调用结果处理和赋值给组件值，示例如下：

示例代码如下：

function didFetch(content) {  content.textField_m7a2rpiw = content.outputs;  return content;}

**获取服务结果：**在数据处理函数中，可以通过content.outputs可以获取执行服务获取到的结果，如示例代码中所示。**赋值给组件：**在数据处理函数中，可以通过赋值给content.textField_m7a2rpiw，从而给组件textField_m7a2rpiw进行赋值回显。**预览页面：**点击预览按钮，并在新窗口打开可以调试连接类组件。

测试运行：打开浏览器控制台，输入参数，点击按钮调试，运行连接类组件。

运行结果会回显到组件中，如果执行有问题，可查看右侧testConnectorComponent.json请求的响应体的报错信息检查代码并进行修改。

{"msg":"success","code":0,"data":{"now":{"windDirectionDegree":169,"precipitation":0,"temperature":6.3,"humidity":77,"pressure":879,"windDirection":"东南风","windSpeed":0.5,"windScale":"微风"},"lastUpdate":"2025/02/18 16:55","alarm":[],"location":{"path":"中国, 贵州, 贵阳","name":"贵阳","id":"57816"}}}

**进一步处理服务执行结果：**回到插件设计器页面，根据运行结果可以自定义编写处理代码并赋值给不同的组件，完成连接类组件的开发示例代码如下：
function didFetch(content) {  var serviceOutput = content.outputs;       if (serviceOutput.msg !== 'success') {         return content;       }       var path = serviceOutput.data.location.path;               path = path.replace(/,/g, '-');        var lastUpdateAndAdress = path + '  ' + '上次数据更新时间：' + serviceOutput.data.lastUpdate;    content.textField_m7a2rpiw = serviceOutput.data.now.temperature;       content.textField_m7a2rpix = serviceOutput.data.now.precipitation;       content.textField_m7a2rpiy = serviceOutput.data.now.humidity;       content.textField_m7a2rpiz = serviceOutput.data.now.pressure;       content.textField_m7a2rpj0 = serviceOutput.data.now.windDirection + ' ' + serviceOutput.data.now.windSpeed;       content.textField_m7a2rpj1 = lastUpdateAndAdress;       return content; }

**保存预览：**

上面的示例中需要输入城市的id才能够查询，使用并不方便，因此可以通过动态数据源的方式接入API来查询城市id来简化查询。**扩展：通过动态数据源获取城市id**​
某些场景下，需要使用查询动态数据源来作为输入，如在查询天气中可以通过接入API接口作为动态数据源来获取不同的城市id。注册查询城市Id服务，在3.1节中已完成了注册。在插件设计器中拖入一个下拉单选组件，编辑如图：

在下拉单选组件的设置面板中可以设置使用搜索数据源

类型使用JSONP，URL地址填入/query/publicService/invokeExtService.json。

编写请求处理函数和数据处理函数来调用插件服务完成数据源的注入。这里由于复用了宜搭表单基础组件的能力，动态数据源的请求处理函数与连接类组件的服务请求处理函数规则稍有不同，请求函数的示例代码如下：
function willFetch(params) {  var serviceInputs = {    serviceUuid: 'PSVC-XH6664C12O0TLYO1DX2M2CRCJUU331CGP2A7M0',    input: JSON.stringify({    "query": {      'q': params,      'limit': 10,      'timestamp': Date.now()    }  }),    pluginId: 'PLUGIN-XH6664C10K0TJA8XAPWDJBDM4XOM2GO20X97M0',    extensionId: null  }  return serviceInputs;}

其中params是下拉单选框的输入值，调用插件服务需要如示例代码中构建serviceInputs来调用，需配置服务id，插件id，插件服务入参。
{    serviceUuid: '插件服务Uuid',    input: '插件服务的入参',    pluginId: '插件id',    extensionId: null  }

服务id和插件id可到插件创建页面查询，如下：

**注意：此处代码安装插件的用户能够看到，请勿填写秘钥等信息。**数据处理函数中需处理结果并将值设置为下拉单选组件的可选项中，示例代码如下：
插件服务返回结果为：
{    "msg": "success",    "code": 0,    "data": [        "57816|贵阳|Guiyang|中国",        "57973|桂阳|Guiyang|中国",        "58626|贵溪|Guixi|中国",        "59249|贵港|Guigang|中国",        "52955|贵南|Guinan|中国",        "57824|贵定|Guiding|中国",        "52868|贵德|Guide|中国",        "G05023|乔治敦|乔治敦|圭亚那",        "006240|阿姆斯特丹|阿姆斯特丹|圭亚那",        "086580|蒙得维的亚|蒙得维的亚|乌拉圭"    ]}

数据处理函数：
function didFetch(content) {  if (content.outputs.data === "") {    return [];  }    const options = content.outputs.data.map(i => {    let parts = i.split('|');    let cityId = parts[0];    let name = parts[3] + parts[1];    return {      value: cityId,      text: name    };  });  return options;}

其中下拉单选框组件的选项集为一个列表，列表中每一个选项具有两个属性text和value，text表示的选项展示名字，value表示该选项的真实值。
示例代码中将动态数据源的结果转换为下拉单选框的选项结构，实现的效果如下：

当选择“中国贵阳”时，选择的真实值是城市代码57816。至此，完成了将返回结果处理并转化下拉单选组件中。
8）将连接类组件中的请求处理函数修改为下拉单选框的唯一标识，完成新的输入绑定并保存。

由于预览页面暂不支持调试动态数据源（后续会支持该功能），需要将插件发布到组织内查看效果，发布后到安装插件页面启用插件。

10）进入宜搭的任意应用的表单下，在自定义组件栏中可以看到刚创建的连接类组件，将其拖入表单设计器中。

点击配置控件字段，勾选显示按钮，则会生成一个点击执行按钮，当点击按钮才会触发连接类组件服务调用，反之当组件改变时，则自动触发连接类组件服务调用：

点击确定后，表单设计器中就会自动生成对应组件。

点击预览：

下拉单选框中输入贵阳：

选择中国贵阳并点击按钮执行：

至此，完成了天气查询的连接类组件demo演示。
如果到这步开发仍有错误，可在当前表单修改请求处理函数和数据处理函数, 在预览页面继续进行调试。

在当前表单预览调试完成后，回到插件页面创建一个新版本，版本号需满足x.x.x的格式。

创建完成后，回到插件设计器页面，将修改后的代码拷贝到插件设计器中下拉单选框对应的请求处理函数和数据处理函数中即可。

### 2.4插件参数配置​

插件参数会在用户启用插件时进行配置，可用于配置如AK、SK和token等秘钥参数，也可以用于在连接类组件执行服务时作为全局常量使用。

**2.4.1 连接类组件中的全局常量使用示例**​
新增一个参数配置表示查询数量，变量名为limit，设置默认值为10。

在**构建服务的输入体**时可通过构建字符串'$'+变量名的方式使用，如下示例代码：
function willFetch(params) {  var serviceInputs = {    serviceUuid: 'PSVC-XH6664C12O0TLYO1DX2M2CRCJUU331CGP2A7M0',    input: JSON.stringify({    "query": {      'q': params,      'limit': '$limit',//执行服务时会将$limit替换为参数中的默认值10      'timestamp': Date.now()    }  }),    pluginId: 'PLUGIN-XH6664C10K0TJA8XAPWDJBDM4XOM2GO20X97M0',    extensionId: null  }  return serviceInputs;}

**请注意，只有在服务的输入体参数中使用才有效。**
除此之外还内置了一些系统字段提供使用，调用服务时如果需要使用系统参数，可以在输入参数中填入对应的字符串值即可。

|
系统常量
字符串值
备注
|
CorpId
$CORP_ID
当前登陆corpId
|
UserId
$USER_ID
当前登陆userId
|
OrgID
$ORG_ID
当前登陆组织Id
|
DingUid
$DING_UID
当前登陆人钉钉Uid

**输入示例：**
{  "arg0":{    "corpId":"$CORP_ID",    "uid":"$DING_UID"  }}

运行时会被替换为当前登陆人的企业Id。
{  "arg0":{    "corpId":"dingxxxx",    "uid":"xxxx"  }}

**http插件服务输入示例：**
{  "query": {        "corpId":"$CORP_ID",        "uid":"$DING_UID"    }  }

**最终的转换效果为：**
https://xxxx?corpId=dingxxxx&uid=xxxx

**2.4.2 秘钥参数配置**​

新增一个token参数，请注意秘钥类的参数配置要**勾选加密，防止泄密**，使用方式同上。
**输入示例：**
{  "hearder":{    "token":"$token"//请求头中携带token  }}

**2.4.3 参数配置发布和安装说明**​参数配置中设置默认值后，其他用户安装开发的插件后会使用开发者设置的默认值，所以如果不想用户使用自己的验权方式，请将默认值清空，如果需要让用户使用自己的验权方式，请注意勾选加密，防止泄露。用户启用插件后，可以重新配置参数覆盖开发者的默认值使用。
### 2.5注册http服务的登陆方式开发说明​

**2.5.1 类型说明**​

|
身份验证类型
说明
|
无身份验证
无身份验证就是不需要任何验证信息，直接调用的接口，通常用于访问一些公开的接口。
|
基本身份验证
即基本的HTTPAuthorization的验证，请求消息头含有服务器用于验证用户代理身份的凭证，在 Header 中加入如Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l的 Base64 编码后账号密码信息。
加密格式：账号:密码。
你只需要配置账号密码的提示标签，用于提示使用者在注册鉴权信息知道填写什么内容。username 标签password 标签
|
API 密钥
即APIKey鉴权方式，该APIKey长期有效（请开发者妥善保管），访问者在待访问的系统中创建生成秘钥，开发者可直接通过此凭证调用支持此类鉴权的公开 API。参数标签：用于配置鉴权信息时提示。参数名称：系统需要的 apiKey 名称。参数位置：可以选择把鉴权信息附加在查询参数或者 header 里，根据请求的系统需要选择。
|
阿里云 API 网关
即连接器创建完成之后添加鉴权模板时，模板填写 App Code 后可调用对应的阿里云API。
更多内容请参考，使用认证 App Code 方式调用API。
|
钉钉开放平台验证
创建完连接器后添加鉴权模板，模板填写App Key、App Secret后可调用钉钉开放平台API（含宜搭部分API）。
添加鉴权模板后宜搭会通过鉴权自动生成鉴权参数access_token，在请求时添加到Header参数x-acs-dingtalk-access-token中，无需再次生成。
更多内容，请参考钉钉应用开发流程。
**2.5.2 使用方式**​**基础认证方式**​

其中，用户名标签和密码标签填写的是配置该服务认证时使用的用户名和密码的字段名称，需在参数配置中填写相关信息，即可正常使用该服务。

**API认证方式**​

其中，参数标签对应于参数配置中的字段名称。需在参数配置中填写相关信息，即可正常使用该服务。需要注意的是，参数填写的是认证所需的 key：

当最终发起请求时，系统将把 serviceToken 对应的配置值（例如：123456）添加到服务请求的头部（header）中，具体格式为：
Authorization: token 123456

**阿里云API网关**​

其中，AppCode填写的是配置该服务在阿里云API网关认证需要使用的AppcCode的字段名称，需到参数配置中填写进行配置即可正常使用：

**钉钉开放平台认证方式**​

其中，AppKey和AppSecret填写的是配置该服务在钉钉开放平台认证需要使用的AppKey和AppSecret的字段名称，需到参数配置中填写进行配置即可正常使用：

### 2.6上架插件​

填写插件的基本信息：

提交插件上架流程

## 附录-组件传值结构示例​

单行文本
{    "componentName": "TextField",    "fieldId": "textField_m69bngjh",    "label": "单行文本",    "fieldData": {        "value": "测试数据"    }}//fieldData.value为组件的输入值和输出值,类型为字符串

多行文本
{    "componentName": "TextareaField",    "fieldId": "textareaField_m7e5qi0o",    "label": "多行文本",    "fieldData": {        "value": "测试数据"    }}//fieldData.value为组件的输入值和输出值,类型为字符串

数值
{    "componentName": "NumberField",    "fieldId": "numberField_m7e65mu0",    "label": "数值",    "fieldData": {        "value": 2    }}//fieldData.value为组件的输入值和输出值,类型为数值

下拉单选
{        "componentName": "SelectField",        "fieldId": "selectField_m7e65mu3",        "label": "下拉单选",        "fieldData": {            "value": "选项二",            "text": "选项二"        },        "options": [            {                "defaultChecked": false,                "disable": false,                "text": "选项二",                "value": "选项二",                "sid": "serial_khe7yak5"            }        ]    }//fieldData.value为组件的输入值和输出值,类型为列表

通过动态数据源构建下拉单选框的选项，示例代码如下：
function didFetch(content) {  const options = content.outputs.data.map(i => {    return {      value: i.a,      text: i.b    };  });  return options;}

其中下拉单选框组件的选项集为一个列表，列表中每一个选项具有两个属性text和value，text表示的选项展示名字，value表示该选项的真实值。
下拉复选
{    "componentName": "MultiSelectField",    "fieldId": "multiSelectField_m7e65mu4",    "label": "下拉复选",    "fieldData": {        "value": [            "选项三",            "选项一"        ]    },    "options": [        {            "defaultChecked": false,            "disable": false,            "text": "选项一",            "value": "选项一",            "sid": "serial_khe7yak4"        },        {            "defaultChecked": false,            "disable": false,            "text": "选项三",            "value": "选项三",            "sid": "serial_khe7yak6"        }    ]}//fieldData.value为组件的输入��和输出值,类型为列表

通过动态数据源构建下拉复选框的选项，示例代码如下：
function didFetch(content) {  const options = content.outputs.data.map(i => {    return {      value: i.a,      text: i.b    };  });  return options;}

其中下拉复选框组件的选项集为一个列表，列表中每一个选项具有两个属性text和value，text表示的选项展示名字，value表示该选项的真实值。单选
{        "componentName": "RadioField",        "fieldId": "radioField_m7e65mu1",        "label": "单选",        "fieldData": {            "value": "选项二",            "text": "选项二"        },        "options": [            {                "defaultChecked": false,                "disable": false,                "text": "选项二",                "value": "选项二",                "sid": "serial_khe7yak5"            }        ]    }//fieldData.value为组件的输入值和输出值,类型为对象

复选
{        "componentName": "CheckboxField",        "fieldId": "checkboxField_m7e65mu2",        "label": "复选",        "fieldData": {            "value": [                "选项一"            ]        },        "options": [            {                "defaultChecked": false,                "disable": false,                "text": "选项一",                "value": "选项一",                "sid": "serial_khe7yak4"            }        ]    }//fieldData.value为组件的输入值和输出值,类型为列表

日期
{        "componentName": "DateField",        "fieldId": "dateField_m7e65mu5",        "label": "日期",        "fieldData": {            "value": 1740067200000        },        "format": "yyyy-MM-dd"    }//fieldData.value为组件的输入值和输出值,类型为时间戳数值

成员
{        "componentName": "EmployeeField",        "fieldId": "employeeField_m7e65mu6",        "label": "成员",        "fieldData": {            "value": [                {                    "deep": 0,                    "value": "023947",//userID                    "label": "宜小搭",                    "avatar": "",                    "businessWorkNo": "",                    "corpId": "ding5d17e",                    "deptDesc": "宜搭",                    "deptEnName": "",                    "deptFullPath": {                        "en_US": "宜搭",                        "key": "",                        "pureEn_US": "宜搭",                        "type": "i18n",                        "value": "",                        "zh_CN": "宜搭"                    },                    "deptId": "-1",                    "dingUid": "",                    "email": "",                    "emplId": "023947",                    "hrStatus": "",                    "id": null,                    "jobDesc": "",                    "jobSubCount": 0,                    "locationCountry": "",                    "locationEnName": "",                    "locationName": "",                    "locationNo": "",                    "name": "宜小搭",                    "nickNameCn": "",                    "orderNum": "",                    "pinyin": "",                    "pinyinNick": "",                    "workId": "023947",                    "workNo": "023947",//不一定等于userId 客户可以自定义                    "displayName": "宜小搭",                    "postName": "",                    "deptName": "宜搭",                    "key": "023947"                }            ]        }    }//fieldData.value为组件的输入值和输出值,类型为对象列表

部门
{        "componentName": "DepartmentSelectField",        "fieldId": "departmentSelectField_m7e65mu7",        "label": "部门",        "fieldData": {            "value": [                {                    "value": "-1",//departmentId                    "text": {                        "en_US": "宜搭",                        "key": "",                        "pureEn_US": "宜搭",                        "type": "i18n",                        "value": "",                        "zh_CN": "宜搭"                    }                }            ]}  //fieldData.value为组件的输入值和输出值,类型为列表

## 参考文档​