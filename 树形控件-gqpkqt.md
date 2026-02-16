# 树形控件

|
**能力**
**免费版**
**轻享版**
**专业版**
**专属版**
|
树形控件
不支持
不支持
支持
支持

## 1. 使用场景​

当使用一个种类想要查看子类的时候，可以使用自定义页面里的树形控件
组件属性以及使用和示例请**点击此处**查看
## 2. 视频展示​

## 3. 操作步骤​

### 3.1 创建普通表单​

新建一个普通表单，表单里可以放置多个单行文本，在右边属性界面可以修改标题名称，点击保存

### 3.2 创建自定义页面​

在选择模板页面可以选择直接跳过，进入自定义编辑页面，拖拽一个树形控件和按钮组件

### 3.3 新建远程 API ​

在自定义页面点击左边的数据源，新建一个远程 API，修改名称、请求地址、请求参数以及数据处理
请求地址：宜搭平台接口（页面数据源可直接调用）
例：https://www.aliwork.com/dingtalk/web/APP-XXXXXX/v1/form/searchFormDatas.json
请求参数里的 formUuid 在首页右上角的应用设置里，每个表单都有唯一的 ID，直接复制放到请求参数里

在数据处理里找到请求完成回调函数下面的代码，修改 dataMap 后面的唯一标识，唯一标识在表单里的单行文本里，复制进去之后点击保存
function didFetch(content) {  const data = content.data.map(item => {    let dataMap = item.formData;    return {      label: dataMap['textField_kplzoi0z'],      key: dataMap['textField_kplzoi0z'],      children: [{        label: dataMap['textField_kplzoi10'],        key: dataMap['textField_kplzoi10'],        children: [{          label: dataMap['textField_kplzoi11'],          key: dataMap['textField_kplzoi11']        }]      }]    }  })  content = data;  console.log("item=====>", data)    function findItem(item, arr) {    console.log("item........", item)    console.log("arr........", arr)    return arr.findIndex(value => value.key === item.key);  }  function recursion(arr) {    console.log("判断是否重复的", arr)    const newArr = [];    arr.forEach((item) => {      let index = findItem(item, newArr);      if (index !== -1) {              } else {        newArr.push(item);      }    })    return newArr;  }  let newArr = recursion(content);  console.log("newArr========>", newArr)  content = newArr;  console.log("content========>", content)  // return item;  // console.log('data:', data)  // this.setState({  //   tree: data  // })  return content; // 重要，需返回 content}

点击左边 JS 动作面板，复制以下代码

export function onEditFinish(key, label, node) {  console.log('key: ', key, ' label: ', label, ' node: ', node);}/*** Tree onSelect* @param selectedKeys 选中节点key的数组* @param extra 额外的参数*/export function onSelect(selectedKeys, extra) {  console.log('选中节点key的数组: ', selectedKeys, ' 额外参数：', extra);}/** * menu onItemClick * 参数配置参考这里：https://fusion.design/pc/component/menu */export function onItemClick(key, item, event) {  console.log(key, item, event);}/*** button onClick*/export function onClic() {  console.log(this.$('tree_kne7wdg0').get('dataSource'));}/*** button onClick*/export function onClick(){  console.log('onClick');}

### 3.4 绑定变量​

点击右边的节点数据，变量绑定选择刚才创建的远程 API 的变量，点击确定

在右下角的新建动作可以设置动作，这里选择编辑节点内容时完成

### 3.5 新拖入一个按钮组件​

选择按钮组件，找到右下角的新建动作，选择内置动作，打开 URL，网站地址为刚才设置单行文本的页面（务必是访问或者新增数据的页面地址才行）

点击保存，返回首页，这个时候可以去测试一下，树形控件就已经配置完成了

--------------------欢迎关注我们--------------------