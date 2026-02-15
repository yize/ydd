---
title: 视频会议（预约）
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/rhg7w5n7la2t69bv/qaghpy2gu779gi1l/ahnex56mzi8f2gl8/qwlh57zqlr4e7047
source: docs.aliwork.com
---

# 视频会议（预约）

在发起会议之前，既要与各位参会人进行时间上的确认，又要提醒参会人进入会议，流程繁琐怎么办？宜搭连接器通过表单信息的填写，提交后即可为参会人创建日程，实现会议的预约。
## 效果展示[​](#mCOo7)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637553665915-1c527de9-408c-4f5b-a099-d5d4f7ec6622.png)
## 操作视频[​](#YPYS2)
## 步骤一：创建并配置表单[​](#KmExX)
创建表单，作为预约会议信息的填写入口，并为后续创建连接器做好数据准备。**操作步骤：**新建表单，命名为「视频会议预约」。添加单行文本组件，命名为「会议主题」，设为必填项。（操作如图2.1-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652149094122-0b8ef775-5cc3-4b8f-9ee8-e18ede2c9138.png)
图2.1-1 添加并配置单行文本组件添加成员组件，命名为「参会人员选择」，设为必填项，开启多选模式。（操作如图2.1-2 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652149177421-a271d080-7c1d-4cf4-b2fa-b279ef094cd4.png)
图2.1-2 添加并配置成员组件添加两个日期组件，分别命名为「开始时间」和「结束时间」，设为必填项，并将组件格式设置为「年-月-日 时:分」。（操作如图2.1-3 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652149239955-6ada0af5-a25d-4003-a474-ddf45ccf19c7.png)
图2.1-3 添加并配置日期组件添加多行文本组件，命名为「会议备注」。（操作如图2.1-4所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652149286041-c415a898-032c-4ed5-a501-75f5bfc2c513.png)
图2.1-4 添加并配置多行文本组件点击表单右上角「保存」按钮，即可。
## 步骤二：创建并配置连接器[​](#MYDEG)
宜搭连接器介绍，请参见[集成&自动化-连接器](https://www.yuque.com/yida/support/zevvr1)
通过步骤一，我们已将发起视频会议预约的入口搭建完毕，接下来，我们需要对「预约视频会议」表单进行连接器的配置，以达到自动预约的目的。**操作步骤：**在后台管理页面，点击页面上方「集成&自动化」进入功能分区，点击「新建集成&自动化」按钮下的「从空白新建」。（操作如图2.2-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652149454180-45374d0f-c952-4213-8615-763fe3c084b0.png)
图2.2-1 连接器入口将连接器命名为「预约视频会议」，触发类型选择为「表单事件触发」，并将触发表单选择为「视频会议预约」表单，点击「确认」按钮。（操作如图2.2-2 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652149561478-285e1603-762e-4a89-bde5-70e4ade1e46c.png)
图2.2-3 创建连接器
## 步骤三：配置连接器[​](#DUKFS)
**操作步骤：**点击选中「表单事件触发」，触发事件选择「创建成功」，数据过滤选择「全部数据」，点击保存按钮。（操作如图2.2-4 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652149677659-ad57b40a-f816-43ba-b1c4-b7f3a97601cf.png)
图2.2-4 配置表单事件触发点击选中「连接器」，选择「视频会议」应用的「预约视频会议」动作。（操作如图2.2-5 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652153447225-e2f07de9-de12-46f7-b0e5-fe8bb8d4179c.png)
图2.2-5 选择「视频会议」应用选择执行动作中点击选中「预约视频会议」执行动作后进行执行动作的配置，配置完成后点击「保存」即可。（操作如图2.2-6 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1652153577229-4c2bcba3-4c57-475a-8ed4-72b938cc9b2c.png)
图2.2-6 选择执行动作点击页面右上角「保存」按钮后，点击「发布」按钮，即可。
## 步骤四：提交表单数据[​](#tt07U)
通过上述两个步骤，我们已经完成了连接器的相关配置，现在只需提交「预约视频会议」表单数据，即可调用连接器，实现自动预约视频会议的功能。（操作如图2.3-1 所示）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1637553304554-cbb03372-04bc-495f-a6b5-9382993dbb14.png)
