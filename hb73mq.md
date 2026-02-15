---
title: 饼图
url: https://docs.aliwork.com/docs/yida_support/_5/aii2tp/wq6oap/nm74ys/hb73mq
source: docs.aliwork.com
---

# 饼图

| **能力** | **免费版** | **轻享版** | **专业版** | **专属版** |
|---|---|---|---|---|
| 饼图 | 支持 | 支持 | 支持 | 支持 |
## 1. 简介[​](#hYrV4)
### 1.1 功能简介[​](#pkGeA)
如果需要查看每个部门的数据占比情况，就可以使用到饼图这个组件来呈现了。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1625923875411-aca9fa4d-e2c5-4b60-aae5-e66003f1d847.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1625923881256-3c794a1e-5428-43af-bd63-d8e71ffbd57a.png)
亮点：可以自行控制组件的大小和随意移动组件位置（靠左、居中、靠右）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1626427000355-313868f5-ad73-4a41-bf51-6f5053188657.png)
### 1.2 使用场景[​](#txdnD)
例如，使用角度展示数据占比大小，如下图所示![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1625923875411-aca9fa4d-e2c5-4b60-aae5-e66003f1d847.png)
### 1.3 基本要求[​](#zFmwy)
饼图的基本要求如下：**分类字段****数值字段****趋势值字段****总值字段****总趋势值字段****总值下钻图标**最多1个字段最多1个字段可多选字段，最多30个字段最多1个字段可多选字段，最多30个字段最多1个字段
## 2. 操作步骤[​](#v4cGH)
### 2.1 选择组件，配置数据集[​](#hfDUV)
创建报表，添加饼图组件，选择一个数据集，如图：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1640572059706-2d278280-2d84-4850-b7ba-a26c05863ff8.png)
选择数据集
### 2.2 选择图表展示字段[​](#ympaU)
将右边的字段拖动放到【分类】、【数值】、【趋势值】、【总值】、【总趋势值】、【总值下钻图标】上基础字段分类：展示饼图的分类字段数值：按分类统计数据并展示占比高级字段**趋势值**：当饼图图例类型为【指标卡】时显示，一般用于提示各分类的变化趋势**总值**：在开启【环形图】时显示，一般用于显示各分类值的总和**总趋势值**：在开启【环形图】时显示，一般用于提示各分类值总和的变化趋势条件过滤：支持
**可以直接选择数据集下的字段，也可以通过公式生成，如何使用公式请查看 **[**报表公式**](https://www.yuque.com/yida/support/yrofmw)![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1640572128256-b8e34556-8943-4d94-accc-71ecb7d0f884.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1625925823959-d6830d14-a2ff-4190-9cb4-e4c1a6892bdd.png)
配置后的案例![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1625925806560-23424cad-b932-449d-9254-e527b45ce7db.png)
配置后的案例
### 2.3 样式设置[​](#FYhUo)
分为五小类，有样式配置、标签、图例、提示信息、百分比小数位数，如图：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1640572359721-c07f54d3-4b55-40c7-a35c-8753a8933817.png)
#### 2.3.1 样式配置[​](#ePues)
支持调整饼图的颜色、尺寸基础饼图变环形图调整环形图的内半径
注：当 [**分组颜色**](https://yuque.antfin.com/youshu/doc/loqg2n/edit#pAmxH)** **未配置，在样式 中调整颜色才生效自定义颜色支持写英文或 16 进制颜色值：#5894FF，多值用英文逗号隔开******内指标即为图中红色圈起来的，如图：**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1635235612557-d4d2402a-3768-49ba-b172-cf0e3622d4b2.png)
设置后的效果图
#### 2.3.2 标签[​](#GyNrX)
支持开启与关闭，开启后支持连接线位置与显示、标签大小与显示的内容、颜色（默认是黑色）等；**注：位置选择蜘蛛图时无颜色设置，只有设置为外部或内部才可以设置字体颜色**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1626427761341-1c1c8ee1-190e-4fa4-9a9c-8ca71a782c1c.png)
设置标签
#### 2.3.3 图例[​](#k1v5r)
支持开启与关闭，开启后支持调整位置与是否分页（默认是开启）图例类型：图例项与指标卡指标卡：布局为垂直时，支持调整两栏比例![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1626428011416-d9683c3b-111b-43cf-aceb-e50d76ee49d5.png)
图例项![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1626428054726-fc77ed7e-ae88-4bcd-9f4d-dbc3e3268f03.png)
指标卡
#### 2.3.4 提示信息[​](#HSaAZ)
支持开启与关闭，开启的效果：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1626428154707-ba43ef72-7ae5-4271-bbd3-093657682b11.png)
设置提示信息
#### 2.3.5 百分比小数位数[​](#QBlNz)
设置百分比时，保留小数点后几位，如图：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1626428198009-4ec7bf06-480f-4bf6-b735-b95011b03ef3.png)
设置小数位数
## 3. 更多信息[​](#JCsg6)
此处为语雀内容卡片，点击链接查看：[https://www.yuque.com/go/doc/49490921](../../../ox8nu4/qpdzl5)
