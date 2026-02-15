---
title: 时间偏移
url: https://docs.aliwork.com/docs/yida_support/_5/ox8nu4/eapslkef3y6zbbod
source: docs.aliwork.com
---

# 时间偏移

## 介绍[​](#nEAOq)
时间偏移是在聚合字段类型的基础上显示不同时间点数据的能力，一般用于做不同时期的数据对照显示。**说明**：
设置了时间偏移的报表中，一次最多只能查询一万条数据。
## 配置面板[​](#zAtRS)
在数据设置面板的时间偏移选项卡下有如下配置：时间偏移：是否开启时间偏移时间维度：偏移的时间的粒度偏移量：根据时间维度会有不同的偏移量，可以自定义配置偏移![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1678266495161-c293c24d-ac28-4af2-9f1f-04c2ff4d94eb.png)
## 具体配置[​](#xHajr)
时间偏移的数据需要建立在时间基础上，在不同的组件上面，我们需要配置相应的时间字段。
### 柱状图[​](#VEX1H)
添加时间字段![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1678266420108-d34ec68f-d13f-4447-afb7-7cbac7e3ef96.png)
配置偏移字段![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1678266420129-733a0d63-57bf-4abf-adcb-f759fa49227a.png)
其中：id数量为原始字段，上月id数量为偏移到上个月的
### 表格[​](#eNBel)
表格与**柱状图**的配置过程类似![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1678266420612-5a399b43-abad-4420-8dac-9acaea7cc55c.png)
### 指标卡[​](#YWU5j)
在**标题**部分添加时间字段，然后可以**辅助指标**下添加带有时间偏移的参考数据。指标卡更多配置介绍见：[基础指标卡](../aii2tp/wq6oap/mtmqkn/vn761o)![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1678266420128-7fea52ba-6331-4d36-95a1-d8e9cddbc6bc.png)
