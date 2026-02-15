---
title: 脚本节点
url: https://docs.aliwork.com/docs/yida_support/_2/trbqg6/ywnn9itpk2e52332
source: docs.aliwork.com
---

# 脚本节点

宜搭流程支持低代码开发者在设计当前流程或集成自动化的过程中，添加**脚本**类型的开发者节点。通过脚本节点，使用 JS 的开发脚本，可在业务逻辑中手动在业务流中插入一些静态变量，或对上游节点返回数据做格式化处理，方便业务流程的灵活配置。
## 使用场景[​](#ivIrP)
在设计期中，添加脚本节点，通过编写JS代码，可以实现对 input 数据的取值，以及对中间数据加工处理，最终通过 output 的内置对象的数据注入，实现在业务流编排中的脚本化的数据处理能力。
## 使用脚本节点[​](#MdVIQ)
**使用方式一**：编辑流程表单 > 进入流程设计页面 > 选择**开发者节点 **> **脚本节点**。**使用方式二**：编辑应用 > 集成与自动化 > 选择��体的自动化流并进入设计配置，选择添加脚本节点。
## 使用脚本节点[​](#IbUt1)
添加脚本节点。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1686218099564-59ff5e37-cb7a-47a1-8c22-697bdd6fa47c.png)
编写JS脚本**Input对象**：可以选取当前上下游的字段或静态值。所有手动设置的InputObj可以在代码块面板中进行引用及处理。**output对象**：当前节点的数据输出载体对象，可以基于object对象的方法进行数据操作。**代码块**：这部分是脚本编写区域，可以理解为一个JavaScript代码编辑器插件，配合内置的input和output对象，可以使用代码进行逻辑拼装。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1686219266806-32e7b841-d6db-41bf-adf1-b8a4774a36a5.png)
测试代码可以在inputObj中输入测试数据，点击测试按钮，可以获得测试的输出数据。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1686219897978-3695152b-f976-4f49-9331-0980fdf2075a.png)
## 消费脚本数据[​](#PhIk0)
在脚本节点下方的其他节点中，当选取字段类型时，就可以看到前置的脚本节点output节点对应字段。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1686219166770-6aa02a23-6860-4753-a0f2-67246415a59f.png)
## 注意事项[​](#nOg7N)
新的脚本节点，代替了原groovy节点，脚本具有更广泛的开发者群体。脚本节点仅支持ES5语法，不支持ES6及以上的语法。暂不支持批量更新节点的处理。请勿进行大内存场景的数据处理，超过10M(目前暂定10M，后续宜搭会根据实际情况调整)会触发内存超限错。误。CPU占用超过5S会触发自动保护机制(例如写个死循环)会报错。不支持xhr、fetch网络请求，window、console、print等顶级对象和函数。支持在代码块里定义function。请不要在function之外添加return语句。
