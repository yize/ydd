---
title: 从AI表格/钉钉OA审批表单创建表单
url: https://docs.aliwork.com/docs/yida_support/_11/xm7x0w/yvp9hw/asly1w503ereg286
source: docs.aliwork.com
---

# 从AI表格/钉钉OA审批表单创建表单

## 版本说明[​](#rU1Xf)
| **能力/版本** | **宜搭免费版** | **宜搭轻享版** | **宜搭专业版** | **宜搭专属版** |
|---|---|---|---|---|
| 组织数量限制 | 1个 | 3个 | 5个 | 10个 |
| 单次拉取数据量 | 1000条 | 2000条 | 5000条 | 1万条 |
| 手动同步次数 | 1次/天/个 | 5次/天/个 | 20次/天/个 | 100次/天/个 |
| 定时同步频率 | ❌ | 每天一次 | 每小时一次 | 每5分钟一次 |
| 同步触发逻辑 | ❌ | ✅支持触发集成自动化、校验、业务规则等 | ✅支持触发集成自动化、校验、业务规则等 | ✅支持触发集成自动化、校验、业务规则等 |
个数增购包：500元/个/年，仅付费版可增购，免费版需升级。
## 1. 简介[​](#B9mAn)
### 1.1 功能简介[​](#vS8DJ)
同步AI表格/OA审批表单数据，完成AI表格/OA审批到宜搭的数据打通，方便用户在宜搭侧直接引用AI表格/OA审批的数据。
### 1.2 使用场景[​](#aqssl)
**活动组织者**可以使用AI表格/OA审批来管理活动的各个环节，如参会人员注册、日程安排、物资准备等。参与者可以通过表单提交反馈和需求。**安全管理人员**可以使用AI表格同步表单来记录安全检查结果、事故报告、整改措施等。这有助于预防事故发生，保障员工的安全和健康。
## 2. 操作步骤[​](#nAxlM)
两种类型操作步骤基本一致
### 2.1 新建页面-选择钉钉AI表格/OA审批表单[​](#ePkhC)
登录[**宜搭工作台**](https://www.aliwork.com/workPlatform)。选择目标应用，进入应用的页面管理页。单击左上角![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1740551983685-a926aca7-fbdf-4205-a7fc-6ce38271537e.png)
号，选择从钉钉数据同步到表单-**钉钉AI表格**。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752203989598-57b2caa2-03fb-48c9-84ce-cb4ba420f599.png)
### 2.2 选择需要同步的AI表格/OA审批表单[​](#h47Zm)
AI表格OA审批表单![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752204056608-8982e2cc-6d3d-45ae-ab2f-b7e40c52ca6c.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752205490966-be57587b-6ada-4b1f-aec2-925e937e94ca.png)
**AI表格可选范围：**1.企业知识库内，当前用户有可管理权限的AI表格。2.我的文档内，当前用户创建的AI表格。
**OA审批表单可选范围：**目前当权限申请通过后，可获取组织中所有OA审批表单。请谨慎授权。
### 2.3 设置同步字段[​](#LuGCE)
**图例****配置项****基本说明**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752204667629-31412c6e-a88a-4304-ba89-414b54c3cce5.png)
**同步表单**默认同步到新的普通表单。选择同步到已有表单，可下拉选择该应用内已经存在的表单。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752204681693-2544e21d-4b52-4536-bd2e-0beb79b1d3bf.png)
**设置同步字段**可手动点击【添加同步字段】，勾选即添加。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/gif/1752204591392-50053dba-e733-4662-ba69-ac205dc1797d.gif)
可点击AI进行匹配![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1740554319189-09a6f30b-bfcc-4633-bb9a-2e0299c239ac.png)
。
### 2.4 设置同步规则[​](#yHB5D)
**图例****配置项****基本说明**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752204740966-55481e57-6087-4248-99af-2648ca1d9eff.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752205023356-28631ecb-bad9-43c8-8844-84239f27ede0.png)
**数据同步方式**数据同步时要设置去重主键。一般建议用唯一id或多个字段作为联合主键来识别重复数据。有3种同步方式：仅新增：即只同步当前表单主键不存在的数据。仅更新：即只同步当前表单主键存在的数据。新增或更新：即 如果主键在当前表单存在就更新数据，如果主键不存在就新增数据。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752204786160-00a102f1-6def-4ba9-9088-0351b0efcd9d.png)
**定时同步规则**配置项：同步时间：默认是当前时间，可手动修改重复规则每5分钟同步一次**仅专属版支持该权益**每小时同步一次**仅专业版及以上支持该权益**每天同步一次**轻享版及以上**每个工作日同步一次**轻享版及以上**每周（周五）同步一次**轻享版及以上**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752205151811-540acc3c-51f4-4ba0-9843-989b82eed21a.png)
结束时间：什么时候停止同步有2种配置方式运行次数：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1740554955665-2b2e79af-547b-4899-98ff-0fd85a9dabbe.png)
指定时间：可选择日期和时间。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1740554972951-98254847-a24b-4d3a-a123-cb87a8917de5.png)
**同步数据范围和排序**目前每次同步，普通表单最多1w条数据，流程表单最多300条数据。当数据量过大时，可以通过【过滤条件+排序】来更新指定数据。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752205380431-77f37665-9ec4-4706-87bb-84a6336ec183.png)
注：此处的「普通表单」、「流程表单」是指宜搭的页面类型。AI表格表单和OA审批表单在宜搭里初次创建的时候，都是「普通表单」。「流程表单」是针对后续用户手动将普通表单「一键转为流程表单」这种情况。**其他**可选择数据同步时，是否触发校验规则、业务规则、集成自动化流、消息通知和第三方服务回调。上述配置项配置完毕后，可点击【保存并同步】进行首次数据同步。【特别说明】当历史数据超过1万条，希望初始化的时候都同步到宜搭表单中，目前有2种解决方案：方案1：「同步规则」-「同步数据范围和排序」，配置「条件过滤」，分多次手动更新同步。方案2：创建表单后，将剩下的数据，通过「批量导入」的方式，一次性导入到对应的表单里。
### 2.4 数据查看[​](#zsTDQ)
创建完成后，即可看到应用里新生成了一个「普通表单」，同时应用里也会同步生成一个同名同类型的数据集。创建完成后首次数据同步，或需要一些时间，如果发现数据和源头不一致，可等待几分钟。可以通过点击「数据集同步」来查看同步日志。操作方式参考下图：![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/gif/1752215286944-8f8d32a7-8f6f-40cb-8b8e-52c18bf4055c.gif)
创建完成后，如果需要修改同步规则，或者手动更新数据，可在表单的拉下操作栏中找到对应操作入口，如下图。![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1752217486206-25278ca2-8600-4749-847f-b0f455f0d7d9.png)
**同步数据按钮说明：****免费版：**仅支持每天点击同步一次。**付费版：**非无限点击，详细可查看第一节版本说明。
## 3. 格式支持说明[​](#tAHQ7)
**AI表格数据同步格式支持说明****字段类型****字段名称****AI表格数据类型****是否支持同步****同步后数据类型****注意事项****常用组件**文本文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597205446-0b5b3adb-831c-48b3-84c1-1209bfccce28.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596623101-29ac9d74-5b31-4b9e-b1b3-8d1dfb150e7d.png)
多选数组![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597195917-0ef679f0-98e8-4924-a149-6d02e20a5ca3.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596056633-9b972ffb-878b-4218-a996-1495142df769.png)
同步数据类型需选择文本类型，否则无法读取数据。同步后显示的选项ID群组数组![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597311782-bb3c1dc9-1444-476f-be49-8554ebcc168c.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596403575-648dec66-a005-4b8e-add0-31e2b8e30735.png)
同步后显示的群组ID日期日期![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597244981-4fc856a1-088c-44a5-96be-2588ed760fd9.png)
支持日期复选框布尔![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597180834-be4f1046-0fd5-41e4-b8f0-0bdc905be38c.png)
支持文本链接链接![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597228662-617bf22a-c4f0-44b9-8838-cdc6914d9510.png)
支持文本公式公式![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597333275-a6f06e26-e801-4237-b26e-9368495f8e29.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596654120-4f48b21a-9dc8-4be6-bf64-9b28d95d969f.png)
数据类型需选择文本类型，否则无法读取数据。地理位置地图定位![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597365929-cc297841-819d-4b0b-941a-d1794507fb7d.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596458888-89fc1675-6786-47ee-bb08-967024f40d16.png)
数据类型需选择文本类型，否则无法读取数据。电话电话，带验证![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597556553-b4423090-e070-42f4-857a-09d5be573363.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596470294-026d6f6a-d335-4394-96ae-181ced32fb7c.png)
数据类型需选择文本类型，否则无法读取数据。评分评分组件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597863488-92c74236-d8d0-4990-a307-0a0e82ba0a7d.png)
支持数值![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598174352-1bc4f711-246b-41a3-9937-c698fe7a22cf.png)
邮箱文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597905753-9fc4e698-e206-4c28-a933-dea28b9199d8.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598184728-efe84afd-db8f-4b54-8466-2130c2caab12.png)
手写签名图片![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597922811-e0572a5d-ce8b-4205-9140-6c6573706bdf.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598197512-30ba9d18-0ff2-45dc-9826-4326fcff51b8.png)
单选文本支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596086810-f2926bf8-1cbe-4f15-919c-423c44cf850a.png)
同步后显示的选项ID人员成员![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597153984-4f8499cf-f298-413b-9acc-5dceba1262ff.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596032956-86faff18-98ef-4043-8f64-f968ccd55786.png)
同步数据类型需选择文本类型，否则无法读取数据。同步后显示的人员ID
部门部门![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597165466-4982d15c-72fc-4ffb-a299-acae151eedb4.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743595818634-06ba2959-fd9a-416b-b9d4-2bf1acb68163.png)
同步数据类型需选择文本类型，否则无法读取数据。同步后显示的部门ID
数字数字支持数值附件 附件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597471638-0a0dea0c-cace-4c12-936a-f064e81af015.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596520195-ff2f152d-a6ff-4317-a452-d88723ccaeb5.png)
数据类型需选择文本类型，否则无法读取数据。进度进度条![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597444402-7d21a959-8038-4564-a051-42cfaea7ea7d.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596505117-8dde53b0-6566-4ae9-b943-a16124f9c654.png)
数据类型需选择文本类型，否则无法读取数据。查找引用搜索框![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597832312-87dcd0dc-fbef-45e0-870d-0f9c7e1b0901.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598271075-1b817c4c-5661-4bd9-8acd-f154d522380f.png)
条码文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597845499-b746f383-6062-4d1e-9d56-ea348eaaf632.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598254310-488d13a0-5280-43cd-b834-6f19db4454f7.png)
地址级联框![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597422346-d8da0f25-e1c8-49c6-bfab-27ab4f302884.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743596555278-b106385f-18f9-4956-9ab3-54e30ca11a72.png)
数据类型需选择文本类型，否则无法读取数据。货币数字![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597892191-1773f9e7-cb84-45fa-af77-db40bd3630a6.png)
支持数值![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598242315-85c4f1b2-d2ad-411e-8e7e-e5b32ea1dda5.png)
身份证身份证支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598224884-253e0805-15cf-48c6-95e6-30af1fd7b5ea.png)
**高级组件**自动编号数字![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597593006-88975c75-f16a-4e14-9c50-246e04a222c4.png)
❌不支持数值、文本都不支持![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597741306-4c8714f7-f2d6-4f9b-b39b-5d202ce7f615.png)
单向关联关联组件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597981653-2a98a966-b024-46e2-af55-c5ee8adc3943.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743599040473-77e5587f-e0f3-4561-8f25-9b80e10eff9d.png)
关联引用关联组件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598007138-06adc9d5-0418-4626-b4d2-995785104849.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743599087215-c86ece97-2e33-424e-8b3a-6eb5b9846469.png)
更新人成员❌不支持文本
最后更新时间日期❌不支持文本
富文本富文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598096145-c043eb05-819d-4ccd-829b-88d092d322d9.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598626668-9d54357b-b625-4cdd-a2a9-aa538d4e7ba3.png)
流程流程组件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597961804-10a2c872-9915-461b-9abb-709882819597.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598612492-88a96d2c-b1d0-4531-bf63-e83195181905.png)
数据类型需选择文本类型，否则无法读取数据。展示流程ID双向关联文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743597996348-2dac2e85-ecf8-4b38-bd6d-fdc3f120eee9.png)
支持文本![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743599053435-01c61843-f509-433d-b276-b8ad72a9f572.png)
创建人成员❌不支持文本数据类型需选择文本类型，否则无法读取数据。创建时间日期❌不支持文本数据类型需选择文本类型，否则无法读取数据。按钮按钮组件![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598132137-03a7cd8c-711a-4fd9-88e8-4626a1f4ca04.png)
❌不支持单行文本/多行文本均不支持![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1743598532121-f5fe3941-d814-4a7a-a25e-0acc300d1621.png)
**OA审批表单数据同步格式支持说明：****OA审批表单组件类型****是否支持同步****宜搭表单组件类型****同步后数据类型**单行文本支持单行文本文本多行文本支持多行文本文本数值支持数值数值日期支持日期日期其他组件支持必须选「单行文本」或「多行文本」文本宜搭为了更好的优化宜搭使用手册内容和质量，占用您3-5分钟时间，辛苦填写一下文档反馈问卷。文档反馈问卷是匿名提交，同时问卷信息仅用于宜搭文档体验反馈收集，感谢您对宜搭的支持！[**点此填写调研问卷**](https://www.aliwork.com/o/cesqwekd?ddtab=true)
**----获取宜搭最新信息，欢迎关注我们----**![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/jpeg/1632807780139-91cbcd43-8c42-44f3-9b2d-0d8b799ab7ea.jpeg)
