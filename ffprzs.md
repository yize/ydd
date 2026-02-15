---
title: Drawer 组件
url: https://docs.aliwork.com/docs/yida_support/_8/zqpbaq/ffprzs
source: docs.aliwork.com
---

# Drawer 组件

| **能力** | **免费版** | **轻享版** | **专业版** | **专属版** |
|---|---|---|---|---|
| Drawer组件 | 不支持 | 不支持 | 支持 | 支持 |
## 1. 使用场景[​](#rOMvg)
需要给用户一个提示需要用户进行确认操作需要用户处理事务，又不希望跳转页面以致打断工作流程组件属性以及使用和示例请** **[**点击此处**](https://yida-developer.gitee.io/docs/components/basic/drawer)** **查看
## 2. 视频展示[​](#cBeaY)
## 3. Drawer 组件的基本使用方法[​](#j0lxy)
### 3.1 拖动 Drawer 组件到自定义页面中，并在属性中配置 Drawer 组件的样式	[​](#Zn8Cs)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1622551893881-ecf7997e-851c-4bcc-b34c-29750f534dfe.png)
自定义页面
### 3.2 Drawer 组件默认是隐藏的，可以通过以下 API 显示 Drawer[​](#nTHRk)
```
`export function showDrawer() {
this.$('drawer1').show();
}
`
```
******举例：**给按钮组件添加点击事件，点击按钮时显示 Drawer 组件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1622552238508-20722ce7-56d5-4e94-801d-a575f65a977f.png)
展示效果：
### 3.3 可以通过配置属性中的高宽来控制 Drawer 的大小，并且可以控制组件的弹出位置以及退出方式[​](#uZGeZ)
如图所示：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1622552428675-739ef6d2-8d37-4aea-a280-6d37e7baa06f.png)
### 3.4 可以通过配置底部按钮来配置按钮的位置、排列、内容以及动作事件[​](#twnB6)
如图所示：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1622552557972-77df65fd-2539-4de0-b007-f7a2d4aadc96.png)
--------------------欢迎关注我们--------------------![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/jpeg/1631861711706-8b6b606d-26db-4978-8416-d588b2d155c9.jpeg)
