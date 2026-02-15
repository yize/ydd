---
title: Groovy 脚本
url: https://docs.aliwork.com/docs/yida_support/_2/lgrp0w/qnsnyk/qg2xfw
source: docs.aliwork.com
---

# Groovy 脚本

在高级流程设��器里，人工节点的审批人规则，在选择其他规则的时候会有一个选项是**Groovy 请求**，你可以按照业务需求通过写 Groovy 脚本去控制审批人。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1639377858933-9fdb3187-6d2d-4504-8171-1adb089d969c.png)
## 前提条件[​](#BIZgN)
在使用 Groovy 脚本之前，你需要先了解什么是Groovy，详情可参考[W3C-Groovy教程](https://www.w3cschool.cn/groovy/groovy_overview.html)和[Apache Groovy简介](http://www.groovy-lang.org/)。
## 操作步骤[​](#Cmd3N)
按照输入框里的数字判断指定谁来做财务审批的审批人，小于 100 的单子由某人审批，大于 100 的话由另一人审批。首先在流程表单编辑页面，我们可以使用一个单行文本框，并复制单行文本框的唯一标识。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1639377945156-9ded5bc3-b226-4bcf-b9ef-2d9b254b1aeb.png)
然后设置审批流程，选择审批节点 >> 审批人规则 >> 其他规则 >> Groovy 规则![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1635153257618-5a567335-11b0-4d06-9c72-173c7fcbb0b3.png)
财务审批节点的审批人使用「Groovy 请求」。textField_kov80fx9  是表单里单行输入框的唯一标识。**注：**在编辑「Groovy请求」脚本时，需要使用到 toInteger() 方法，因为内部流程变量是字符串形式的。toInteger() 方法是默认需要使用的，以下格式可直接参考使用：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1623834317046-fae43dfa-952f-4ae2-ba1a-57f3cffcbcd4.png)
以下代码可直接复制使用：```
`if(单行文本框的唯一标识.toInteger()<100  {
return['审批人userid']
}  else  {
return['审批人userid']
}
`
```
这段代码的意思是：当单行文本框内的数字小于 100 时，则让 xxx 审批，其他情况则让另一人审批。返回审批人时，可以返回多个审批人。
