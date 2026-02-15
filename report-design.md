---
title: 报表设计介绍
url: https://docs.aliwork.com/docs/yida_support/_5/tsmk65
source: docs.aliwork.com
---

# 报表设计介绍

未升级到新版信息架构的组织，请 [**点此查看**](https://www.yuque.com/yida/support/uvu5ql)** **使用手册
## 1. 简介[​](#uGjsl)
### 1.1 功能介绍[​](#fx2RS)
将已提交的表单数据、本地文件数据或第三方系统数据进行图表展示![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1635230928058-54de5988-1187-43da-b2bb-9e8753b75ef1.png)
### 1.2 使用场景[​](#QlgIy)
需要将员工提交的数据做一个汇总进行查看，就可以设置一个报表页面，然后使用报表设计器里面的组件进行数据分析、汇总、查询等
## 2. 报表创建方式[​](#JsPYH)
创建报表有2个路径：（1）进入宜搭后，点击「我的应用」，创建应用进入后，在页面管理中部可选择需要创建的页面，选择「新建报表」![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1635230995951-d4c2e23c-4bff-4902-a52e-a1ea6d89fbdf.png)
（2）在应用首页左上角，蓝色+号 >> 新建报表![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1635231120757-72d23c42-e738-490e-af78-c3c15ed7bdc8.png)
## 3. 报表配置[​](#ogycD)
按照上述步骤创建好报表后跳转到报表设计页面，在顶部组件库拉取所需的** **[**报表组件**](https://www.yuque.com/yida/support/wq6oap)![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1632471238351-834081e5-a47b-4970-be3c-0b120335692d.png)
选择好组件后，点击画布中间已选择的组件，右边会弹出配置数据集![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1635231220731-31ba61ac-3a59-4d5d-894a-ce344103845d.png)
选择数据集，可选择创建的表单，也可选择** **[**视图表**](https://www.yuque.com/yida/support/oim554)、[**数据准备**](https://www.yuque.com/yida/support/dkm8ph)、[**跨应用**](https://www.yuque.com/yida/support/btrtnt)![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1635231323690-22352bb2-6813-471a-a479-1031e94be11e.png)
## 4.常见问题[​](#h6PLF)
##### Q：基础表格如何实现跳转到数据详情？[​](#UALId)
您可以前往[链接跳转](ox8nu4/vg422d)中了解如何配置表格链接跳转，可以自定义实现目标地址跳转，如查看数据详情等。可以通过宜搭-一问一答了解：[https://cloud.video.taobao.com/play/u/null/p/1/e/6/t/1/394576387188.mp4?SBizCode=xiaoer](https://cloud.video.taobao.com/play/u/null/p/1/e/6/t/1/394576387188.mp4?SBizCode=xiaoer)
##### Q：基础表格如何实现列相同字段合并（合并单元格）？[​](#NHMOQ)
通过报表-表格组件【合并单元格】的能力，可以快速实现列相同字段的合并展示，**当相同的字段顺序较为混乱时，请先对需要合并的列字段排序**，后开启【合并单元格】的能力。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1672759868228-797f7fdf-7612-481e-8b7f-61214cce04ed.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1672759929777-24ee9e3a-44d6-4c10-8451-2ce1e172ddd4.png)
##### Q：选择数据集时，主子表无法同时选择？[​](#gqCgf)
默认情况下无法同时选择，需要通过视图表（或数据准备）进行关联。宜搭报表中主表与子表单关联可以设置关联条件用 「主表的实例ID = 子表单数据的父实例ID」进行关联。
##### Q：为什么系统提示我触发“宜搭资源保护”[​](#mb1Bg)
为保障宜搭整体性能稳定，宜搭系统新增监测复杂数据查询的计算资源消耗。例如使用报表公式VAL和CASEWHEN，就容易产生复杂数据查询的SQL，进而可能触发宜搭资源保护措施。
