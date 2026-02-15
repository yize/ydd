---
title: 条件分支&并行分支
url: https://docs.aliwork.com/docs/yida_support/_3/nl4abrm791inlvm2/ybagk4dyzisgfkmb/cc725o4agmwbyi2g
source: docs.aliwork.com
---

# 条件分支&并行分支

分支节点能实现不同的条件执行下面不同的规则配置、同时满足多个条件同时进行执行规则配置。条件分支间有优先级，只执行优先级最高的分支；并行分支间无优先级，满足条件的分支都会执行。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1671445193296-03268973-1119-4c0f-a6de-01de490be607.png)
### 条件规则[​](#Y9Ppi)
分支节点能实现不同的条件执行下面不同的规则配置、同时满足多个条件同时进行执行规则配置。支持条件分支的组件有：表单事件触发人、表单事件触发人所属组织 ID、单行文本、多行文本、单选、复选、下拉单选、下拉复选、数值、日期、附件、成员、部门。**条件分支**：条件分支间有优先级，只执行优先级最高的分支。**并行分支**：并行分支间无优先级，满足条件的分支都会执行。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1630898251113-eb05eab0-781d-4e34-b955-080eed3c2838.png)
### 公式[​](#PDsO3)
将当前表单的字段进行公式编辑作为条件分支，需使用** **[**逻辑函数**](https://www.yuque.com/yida/support/mnx96u) 中的函数公才能判断条件是否成立，示例如下：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1630898492952-604f6cc9-d2c4-4313-bf18-32e8d06d0021.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1631072958866-db62501d-7afa-4005-b195-3eb711cf895f.png)
**说明：**更多内容请参考[流程分支节点](https://www.yuque.com/yida/support/yv8dnv)。
