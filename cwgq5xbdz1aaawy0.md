---
title: 签到
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/rhg7w5n7la2t69bv/qaghpy2gu779gi1l/cwgq5xbdz1aaawy0
source: docs.aliwork.com
---

# 签到

宜搭与连接器结合可实现提交表单查询员工签到情况，包括是否签到，签到时间，签到地点等信息。本文介绍如何通过表单查询员工签到信息。
## 准备工作[​](#ibARq)
在开始之前，你需要先创建一个应用，操作步骤请参考[创建应用](https://www.yuque.com/yida/support/oncnoy)。
## 流程总览[​](#acWiw)
在本文中，你将创建两张普通表单，其中一张用于记录查询结果，一张用于触发连接器。本文操作步骤如下：[步骤一：创建查询结果表](cwgq5xbdz1aaawy0#HvrSd)[步骤二：创建查询签到记录表](cwgq5xbdz1aaawy0#SQkgL)[步骤三：配置集群自动化](cwgq5xbdz1aaawy0#b1bv9)[步骤四：在查询结果表中接收数据](cwgq5xbdz1aaawy0#gw4Ob)[步骤五：测试验证](cwgq5xbdz1aaawy0#yGghi)
### 实现效果[​](#skVKc)
本文最终实现效果如下：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/gif/1715766129583-5e72b4cd-b5d6-4d8b-bfa2-8cb49a550f53.gif)
## 步骤一：创建查询结果表[​](#HvrSd)
登录[宜搭工作台](https://www.aliwork.com)，选择目标应用，单击进入应用编辑页。依次单击 **+** > **新建普通表单**，选择**新建空白页面**，修改表单名称为**查询结果**。在中央画布区分别拖入一个**单行文本**组件、一个**子表单**组件和一个**成员**组件。将**成员**组件命名为**签到人**。将**单行文本**组件命名为**暂存连接器数据**，并将可见状态设置为隐藏。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1715766334061-d2af3d36-b752-4fa5-8554-344bf7bd21de.png)
将**子表单**组件命名为**签到记录**。在**子表单**组件内分别拖入三个**单行文本**组件。将**单行文本**组件分别命名为**签到时间**、**签到地点**和**签到备注**。单击右上角保存，完成配置。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1715766407385-cfc7ca52-377d-4474-8dbc-3c3126805b33.png)
## 步骤二：创建**查询签到记录表**[​](#SQkgL)
在应用编辑页，依次单击 **+** > **新建流程表单**，选择**新建空白页面**，修改表单名称为**查询签到记录**。在中央画布区拖入两个**日期**组件、一个成员组件。将**日期**组件分别命名为开**始时间**和**结束时间**，设置校验规则为**必填**，设置格式为**年-月-日 时:分:秒**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1715655670646-f5c3416d-9db8-4aa7-a32f-dd542dc2e257.png)
将**成员**组件命名为**签到人**，并设置校验规则为**必填**。单击右上角**保存**，完成表单基本配置。
## 步骤三：配置集成自动化[​](#b1bv9)
返回应用编辑页，单击顶部**集成&自动化**。单击新建**集成&自动化**，选择**从空白新建**。在对话框内设置集成自动化名称，选择触发类型为**表单事件触发**，表单为步骤二创建的查询签到记录表。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1715753429960-6c3d618f-ffc3-45eb-a391-2e5f01bfbb09.png)
单击**表单事件触发**，选择触发事件为**创建成功**，单击**保存**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1715753722146-6c42a368-6df5-4420-9c14-375569c25a98.png)
单击表单触发事件下方`**+**`加号，选择**连接器**。**说明**：将光标移动刀触发事件下方即可看到`**+**`加号。
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1715753818236-c43d1c7e-995c-4be4-8cc3-48aa48362ecb.png)
参考以下步骤，配置**连接器**节点。在输入框内搜索**签到**，选择**获取个人签到记录**连接器。将**开始时间**、**结束时间**、**查询用户列表**的值设置为**字段**。配置字段的值为当前表单提交后的数据值。**开始时间**对应表单提交后的**开始时间**，**结束时间**对应表单提交后的**结束时间**，**查询用户列表**对应表单提交后的**签到人**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1715755305231-5449b5ba-ffb2-4849-be77-33d21cc8696f.png)
单击**连接器**节点下方`**+**`加号，添加**脚本**节点。参考以下步骤，配置脚本节点。添加Input对象为`checkinRecord`，类型设置为**字段**，值设置为连接器返回的**分页列表**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1715757277834-4d9fda17-feaa-4638-b4ed-f4f7ba7a3b51.png)
在代码块位置，添加以下代码，并根据代码中注释修改代码参数。```
var checkinRecordJson = checkinRecord?JSON.parse(checkinRecord):[];
var tableData = checkinRecordJson.map(function(item) {
return {
// 将textField_lw5sacjg修改为查询结果表中签到时间的组件ID
textField_lw5sacjg: item.checkin_time,
// 将textField_lw5sacji修改为查询结果表中签到地点的组件ID
textField_lw5sacji: item.detail_place,
// 将textField_lw5sacjk修改为查询结果表中签到备注的组件ID
textField_lw5sacjk: item.remark
};
});
outputs.add("签到","tableData",JSON.stringify(tableData))
```
单击**下一步**，测试代码。设置数据类型为**String**，在输入框内输入以下JSON内容，单击**测试**。```
[
{
"checkin_time": 1715582068000,
"detail_place": "浙江省杭州市余杭区高教路959号",
"remark": "简单签到",
"place": "三维未来park",
"userid": "123456789",
"image_list": []
}
]
```
测试通过后，单击**保存**。
单击**脚本**节点下方 **+** 号，添加**新增数据**节点，然后参考以下步骤，进行配置。选择新增方式为**在表单中新增**，表单选择**查询结果**。选择**新增单条数据**。选择新增字段**暂存连接器数据**，类型设置为**字段**，数据为脚本生成的**签到**数据。选择新增字段**签到人**，类型设置为**字段**，数据为**当前表单提交后的数据** > **签到人**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1715763438917-9e6c379e-6967-4172-8cb8-2763adb3d0d4.png)
单击右上角**发布**按钮，完成配置。
## 步骤四：在查询结果表中接收数据[​](#gw4Ob)
进入查询结果表单编辑页。打开**JS动作面板**，添加以下代码，并根据代码注释修改代码内容。```
export function didMount() {
// 修改textField_lw4ffhbf为暂存连接器数据组件的组件ID。
const str = this.$("textField_lw4ffhbf").getValue();
const value = JSON.parse(str);
// 修改tableField_lw5sacjc为子表单的组件ID。
this.$('tableField_lw5sacjc').setValue(value);
}
```
单击右上角**保存**，完成配置。
## 步骤五：测试验证[​](#yGghi)
进入应用编辑页，单击查询**结果表单**，单击右侧生成数据管理页。设置数据管理页的**页面名称**和**分组**。单击右上角**访问**，访问应用。单击**查询签到记录**，输入需要查询的签到人信息和时间，单击**提交**。进入结果表单的数据管理页进行查看。如下图所示，已成功查询用户的签到记录。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/gif/1715766129583-5e72b4cd-b5d6-4d8b-bfa2-8cb49a550f53.gif)
## 相关文档[​](#rsjMx)
[集成&自动化](https://docs.aliwork.com/docs/yida_support/wtwabe/zevvr1)[新建表单](https://docs.aliwork.com/docs/yida_support/wtwabe/ybuoxl/mff60m)[表单组件](https://docs.aliwork.com/docs/yida_support/wtwabe/gdi5p8)[获取用户签到记录](https://open.dingtalk.com/document/orgapp/obtain-the-check-in-records-of-multiple-users)[脚本节点](https://docs.aliwork.com/docs/yida_support/wtwabe/oihk8g/qgaxvq/trbqg6/ywnn9itpk2e52332)
