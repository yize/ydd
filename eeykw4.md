---
title: 自动审批规则
url: https://docs.aliwork.com/docs/yida_support/_2/ef8e88/eeykw4
source: docs.aliwork.com
---

# 自动审批规则

宜搭审批流程支持配置自动审批规则，你可以通过配置自动审批规则简化审批流程，解决因重复审批而导致的流程效率低下问题。
## 功能说明[​](#NZz8w)
宜搭目前支持三种自动审批规则。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1721915329368-2f3d1817-3970-4151-9bfc-758acee552e2.png)
**所有发起人合并**：该自动审批规则表示如果在流程中，有审批人或执行人节点是当前流程发起者时，那么流程运行到该节点时，将自动通过审批。即当前审批或执行节点为发起人时，自动通过审批。如下图所示：节点审批人为宜小搭时，审批任务自动执行。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1721905419756-be5423d5-e3b9-4f2c-9e94-53e8863c55ea.png)
**相邻审批人合并**：该自动审批规则表示，如果当前审批或执行节点人员与上一个节点人员一致，那么当前节点将自动通过审批。如下图所示：相邻节点的审批人一致时，将自动完成审批。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1721915241720-8d0c6940-1d97-4aa2-b776-3e12e40d9b58.png)
**审批人自动去重**：该自动审批规则表示，如果流程中出现了审批人重复的情况，那么该审批人仅需审批一次，后续节点将自动通过审批。如下图所示，后面的**钉多多**审批人自动���成审批。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1721907202691-bd009dda-9919-4c21-b672-db14332adc40.png)
## 注意事项[​](#BKyfp)
相邻节点指的是流程设计页面中相邻的审批人或执行人节点，而不是流程发起后，流程中的相邻审批人，且抄送人不占用相邻节点份额。例如：在下图所示的流程中，所有`审批人①`都为相邻节点。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1721915721711-53cb000a-0f7e-4c89-b403-d8c5bde83c52.png)
审批人和执行人可配置是否允许审批人为空。除了在流程节点配置自动审批规则之外，你还可以配置全局审批规则，全局审批规则优先级小于节点自动审批规则。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1721910924525-013c374a-52f5-4f90-8cbb-1900b863473b.png)
