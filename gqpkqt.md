---
title: 树形控件
url: https://docs.aliwork.com/docs/yida_support/_8/zqpbaq/gqpkqt
source: docs.aliwork.com
---

# 树形控件

| **能力** | **免费版** | **轻享版** | **专业版** | **专属版** |
|---|---|---|---|---|
| 树形控件 | 不支持 | 不支持 | 支持 | 支持 |
## 1. 使用场景[​](#rh7C1)
当使用一个种类想要查看子类的时候，可以使用自定义页面里的树形控件组件属性以及使用和示例请** **[**点击此处**](https://yida-developer.gitee.io/docs/components/advanced/tree)** **查看
## 2. 视频展示[​](#ZrXxr)
## 3. 操作步骤[​](#ZLwbJ)
### 3.1 创建普通表单[​](#QHi74)
新建一个普通表单，表单里可以放置多个单行文本，在右边属性界面可以修改标题名称，点击保存![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1639550258633-c0818ae8-dde5-4008-8aa0-887eba95deaa.png)
### 3.2 创建自定义页面[​](#AdQKJ)
在选择模板页面可以选择直接跳过，进入自定义编辑页面，拖拽一个树形控件和按钮组件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1639550322117-7b32f33e-b3f1-4c74-bd4a-88574b217ed2.png)
### 3.3 新建远程 API [​](#U3ykG)
在自定义页面点击左边的数据源，新建一个远程 API，修改名称、请求地址、请求参数以及数据处理请求地址：[宜搭平台接口（页面数据源可直接调用）](https://www.yuque.com/yida/support/aql605#936pox)例：[https://www.aliwork.com/dingtalk/web/](https://www.aliwork.com/dingtalk/web/)APP-XXXXXX/v1/form/searchFormDatas.json请求参数里的 formUuid 在首页右上角的应用设置里，每个表单都有唯一的 ID，直接复制放到请求参数里![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1623051274060-8e39b714-6a17-415b-8692-2f2ae7d3b3c5.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1623050906526-c2e98032-9a8f-45ed-b4bd-bd1ec162b58b.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1623118810097-24093c0a-d9ec-44c7-8561-2fb466aef5cd.png)
在数据处理里找到请求完成回调函数下面的代码，修改 dataMap 后面的唯一标识，唯一标识在表单里的单行文本里，复制进去之后点击保存```
`function didFetch(content) {
const data = content.data.map(item => {
let dataMap = item.formData;
return {
label: dataMap['textField_kplzoi0z'],
key: dataMap['textField_kplzoi0z'],
children: [{
label: dataMap['textField_kplzoi10'],
key: dataMap['textField_kplzoi10'],
children: [{
label: dataMap['textField_kplzoi11'],
key: dataMap['textField_kplzoi11']
}]
}]
}
})
content = data;
console.log("item=====>", data)
function findItem(item, arr) {
console.log("item........", item)
console.log("arr........", arr)
return arr.findIndex(value => value.key === item.key);
}
function recursion(arr) {
console.log("判断是否重复的", arr)
const newArr = [];
arr.forEach((item) => {
let index = findItem(item, newArr);
if (index !== -1) {
} else {
newArr.push(item);
}
})
return newArr;
}
let newArr = recursion(content);
console.log("newArr========>", newArr)
content = newArr;
console.log("content========>", content)
// return item;
// console.log('data:', data)
// this.setState({
//   tree: data
// })
return content; // 重要，需返回 content
}
`
```
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1639550359519-a5299f1d-bf26-4b7a-8b9e-7919c7861d90.png)
点击左边 JS 动作面板，复制以下代码![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1623051765072-f5f25088-52e7-4e13-a03d-f7cd16aa0b28.png)
```
`export function onEditFinish(key, label, node) {
console.log('key: ', key, ' label: ', label, ' node: ', node);
}
/**
* Tree onSelect
* @param selectedKeys 选中节点key的数组
* @param extra 额外的参数
*/
export function onSelect(selectedKeys, extra) {
console.log('选中节点key的数组: ', selectedKeys, ' 额外参数：', extra);
}
/**
* menu onItemClick
* 参数配置参考这里：https://fusion.design/pc/component/menu
*/
export function onItemClick(key, item, event) {
console.log(key, item, event);
}
/**
* button onClick
*/
export function onClic() {
console.log(this.$('tree_kne7wdg0').get('dataSource'));
}
/**
* button onClick
*/
export function onClick(){
console.log('onClick');
}
`
```
### 3.4 绑定变量[​](#WW4jv)
点击右边的节点数据，变量绑定选择刚才创建的远程 API 的变量，点击确定![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1623119114846-097659fc-c995-414f-997d-5a22def8c678.png)
在右下角的新建动作可以设置动作，这里选择编辑节点内容时完成![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1623051972421-92f59760-e4fd-4d21-80f3-d91cb452febe.png)
### 3.5 新拖入一个按钮组件[​](#yRaFV)
选择按钮组件，找到右下角的新建动作，选择内置动作，打开 URL，网站地址为刚才设置单行文本的页面（务必是访问或者新增数据的页面地址才行）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1623052264813-e90c763e-b45e-42f0-8b29-aa6618a5e432.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1623119345610-5ad7be78-2e4d-4956-a17d-d1eaceda3a54.png)
点击保存，返回首页，这个时候可以去测试一下，树形控件就已经配置完成了
--------------------欢迎关注我们--------------------![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/jpeg/1631861711706-8b6b606d-26db-4978-8416-d588b2d155c9.jpeg)
