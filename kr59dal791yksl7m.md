---
title: 数据库表结构字典
url: https://docs.aliwork.com/docs/yida_support/_15/tymkt6/kr59dal791yksl7m
source: docs.aliwork.com
---

# 数据库表结构字典

V1.0 更新时间 2024.11
在配置专属存储的专属数据库时，宜搭平台会在您配置数据库中添加一些必要的数据表，用于存储您在使用宜搭过程中所产生的数据。这些数据表的结构并不是一成不变的，表结构会随着业务发展和技术迭代而变化，可能会新增字段或表。通常情况下为了不影响您的业务正常运行，原有字段一般会保持不变，但是宜搭平台仍然建议您在使用该数据时，不要对该数据产生强依赖关系。
## 数据表清单[​](#T4dOk)
### **odin_open_application_data**[​](#odin_open_application_data)
**表名称**： odin_open_application_data**描述**：表单实例（表单与报表共用）数据表。**字符集**：UTF8
| **列名** | **类型** | **长度** | **精度** | **标度** | **是否为空** | **缺省值** | **描述** |
|---|---|---|---|---|---|---|---|
| **id** | varchar | 128 |  |  | Y |  | 唯一id，历史数据可能为空，唯一性还是看pid |
| **gmt_create** | timestamp |  |  |  | N |  | 创建时间 |
| **gmt_modified** | timestamp |  |  |  | N |  | 修改时间 |
| **creator** | varchar | 64 |  |  | Y |  | 创建人 |
| **modifier** | varchar | 64 |  |  | Y |  | 修改人 |
| **is_deleted** | bpchar | 1 |  |  | N | n | 是否删除 |
| **corp_id** | varchar | 128 |  |  | Y |  | 实例插入的组织id |
| **namespace_code** | varchar | 128 |  |  | N |  | 应用appType |
| **table_name** | varchar | 128 |  |  | N |  | 表单模型id |
| **pid** | varchar | 64 |  |  | N |  | 实例id |
| **parent_pid** | varchar | 64 |  |  | Y |  | 用于比如子表关联，子表的数据通过这个关联主表的pid |
| **json_data** | jsonb |  |  |  | Y |  | 具体组件数据，json |
| **data_version** | int8 |  |  |  | N | 0 | 数据变动版本 |
| **data_order** | int8 |  |  |  | N | 0 | 数据展示顺序，一般用于子表 |
| **索引名** | 类型 | 包含字段 |
| **odin_open_application_data_gmt_modified_idx1** | Normal | gmt_modified |
| **odin_open_application_data_namespace_code_creator_idx1** | Normal | namespace_code,creator |
| **odin_open_application_data_namespace_code_table_name_gmt_c_idx1** | Normal | namespace_code,table_name,gmt_create |
| **odin_open_application_data_namespace_code_table_name_paren_idx1** | Normal | namespace_code,table_name,parent_pid,is_deleted |
| **odin_open_application_data_namespace_code_table_name_pid_idx1** | Unique | namespace_code,table_name,pid |
| **odin_open_application_data_pid_idx1** | Normal | pid |
### tianshu_form_data_operation_log[​](#tianshu_form_data_operation_log)
**表名称**：tianshu_form_data_operation_log**描述**：表单数据操作记录表。**字符集**：utf8mb4**列名****类型****长度****精度****标度****是否为空****缺省值****描述****id**bigint(20) unsigned200N依赖tianshu_form_data_operation_log_id_seq生成主键**gmt_create**datetimeN创建时间**gmt_modified**datetimeN修改时间**creator**varchar(64)64N创建人**modifier**varchar(64)64N修改人**is_deleted**char(1)1N是否逻辑删除**system_type**varchar(64)64N系统类型**app_type**varchar(64)64N应用key**form_inst_id**varchar(128)128N表单实例数据Id**operation_type**varchar(64)64N操作类型**operation_field**varchar(64)64N操作字段**pre_value**mediumtext16777215Y原内容**value**mediumtext16777215Y修改后内容**shard_key**varchar(130)130N分库分表键**pre_code**mediumtext16777215Y原控件值对应的code**code**mediumtext16777215Y控件对应的code**operation_id**varchar(64)64Y操作唯一ID**parent_operation_field**varchar(64)64NROOT父级操作字段**parent_operation_id**varchar(64)64NROOT父级操作id**trigger_src**varchar(4000)4000Y触发源描述**trigger_type**varchar(4)4Y触发源类型**索引名**类型包含字段**idx_app_type**Normalapp_type**idx_inst_id_parent_operation_field_gmt_modified**Normalform_inst_id,parent_operation_field,gmt_modified**idx_inst_id_parent_operation_field_parent_operation_id**Normalform_inst_id,parent_operation_field,parent_operation_id**idx_operation_id**Normaloperation_id**idx_operation_id_is_deleted**Normaloperation_id,is_deleted**idx_opertaion_field_gmt_modified**Normaloperation_field,gmt_modified**idx_parentoperationid_parentoperationfield**Normalparent_operation_id,parent_operation_field**PRIMARY**Primaryid**uk_inst_id_id**Uniqueform_inst_id,id
### **tianshu_proc_inst_carbon**[​](#tianshu_proc_inst_carbon)
表名称：tianshu_proc_inst_carbon描述：流程实例抄送人表字符集：utf8mb4**列名****类型****长度****精度****标度****是否为空****缺省值****描述****id**bigint(20)190N依赖proc_inst_carbon_id_seq生成 主键**gmt_create**datetimeN创建时间**gmt_modified**datetimeN修改时间**shard_key**varchar(130)130N分表字段**system_type**varchar(64)64N系统分类**app_type**varchar(64)64N应用类型**form_uuid**varchar(128)128N表单UUID**is_deleted**char(1)1N删除标记**form_inst_id**varchar(128)128N实例ID**form_inst_title**varchar(1024)1024N实例标题**carbon**varchar(64)64N抄送人**activity_id**varchar(128)128N抄送节点ID**process_code**varchar(128)128N流程编码**inst_status**varchar(32)32N实例状态**is_printed**char(1)1Y是否已打印**inst_originator**varchar(64)64Y实例发起人**索引名**类型包含字段**idx_carbon**Normalcarbon**idx_carbon_app**Normalcarbon,shard_key,is_deleted**idx_form_inst_id**Normalform_inst_id**idx_form_uuid_carbon**Normalform_uuid40,carbon20,is_deleted**idx_inst_originator**Normalinst_originator**idx_shard_key**Normalshard_key**PRIMARY**Primaryid
### tianshu_data_form_version[​](#tianshu_data_form_version)
**表名称**：tianshu_data_form_version**描述**：实例数据的表单版本关联表**字符集**：utf8mb4**列名****类型****长度****精度****标度****是否为空****缺省值****描述****id**bigint(20) unsigned200N依赖data_form_version_id_seq生成 主键**gmt_create**datetimeN创建时间**gmt_modified**datetimeN修改时间**creator**varchar(64)64N创建人**modifier**varchar(64)64N修改人**form_uuid**varchar(128)128N表单id**model_uuid**varchar(128)128N模型id**inst_id**varchar(128)128N实例id**version**bigint(20)190N表单版本**system_type**varchar(64)64N系统版本**app_type**varchar(64)64N应用ID**shard_key**varchar(130)130N分库分表键**索引名**类型包含字段**idx_form_uuid**Normalform_uuid**idx_inst_id**Normalinst_id**idx_model_uuid**Normalmodel_uuid**idx_shard_key**Normalshard_key**PRIMARY**Primaryid
### **tianshu_form_data_stash**[​](#tianshu_form_data_stash)
表名称：tianshu_form_data_stash描述：表单缓存表字符集：utf8mb4**列名****类型****长度****精度****标度****是否为空****缺省值****描述****id**bigint(20) unsigned200N依赖form_data_stash_id_seq生成主键**gmt_create**datetimeN创建时间**gmt_modified**datetimeN修改时间**shard_key**varchar(130)130N分库分表键**is_deleted**char(1)1N是否删除标记**system_type**varchar(64)64N系统标识**app_type**varchar(64)64N应用标识**form_uuid**varchar(64)64N表单UUID**inst_value**mediumtext16777215Y表单内容**creator**varchar(64)64N创建人**modifier**varchar(64)64N修改人**索引名**类型包含字段**idx_form_creator**Normalshard_key90,form_uuid,creator**PRIMARY**Primaryid
### **tianshu_form_remark**[​](#tianshu_form_remark)
表名称：tianshu_form_remark描述：评论功能字符集：utf8mb4**列名****类型****长度****精度****标度****是否为空****缺省值****描述****id**bigint(20) unsigned200N依赖form_remark_id_seq生成主键**gmt_create**datetimeN创建时间**gmt_modified**datetimeN修改时间**creator**varchar(64)64N创建者**modifier**varchar(64)64N修改者**form_inst_id**varchar(128)128N实例ID**reply_id**bigint(20) unsigned200Y关联ID**content**text65535N内容**files**varchar(3000)3000Y附件**reply_user_id**varchar(64)64Y回复的人员ID**at_user_id**varchar(640)640Y被AT的人员ID**is_deleted**char(1)1Nn删除标识**system_type**varchar(64)64N系统类型**app_type**varchar(64)64N应用类型**shard_key**varchar(130)130N分库分表键**images**text65535Y图片**索引名**类型包含字段**idx_form_inst_id**Normalform_inst_id**PRIMARY**Primaryid
### **alibpms_app_cm_operator_record**[​](#alibpms_app_cm_operator_record)
**表名称**：alibpms_app_cm_operator_record**描述**：流程实例审批记录表**字符集**：utf8mb4**说明：**不包含正在进行中的审批任务。**列名****类型****长度****精度****标度****是否为空****缺省值****描述****id**bigint(20)190N依赖pro_operator_record_id_seq生成主键id**operator**varchar(64)64Y实际操作人id**operate_time**datetime(3)Y操作时间**action**varchar(256)256Y操作动作描述**remark**text65535Y操作备注**process_instance_id**varchar(64)64Y流程实例ID**activity_setting_id**varchar(64)64Y节点定义ID**task_id**varchar(64)64Y任务ID**step**varchar(256)256Y操作步骤**visible**varchar(128)128Y是否可见（true可见，false不可见）**app_key**varchar(128)128Y应用key**activity_id**varchar(64)64Y节点ID**original_operator**varchar(64)64Y原始操作人**agent_operator**varchar(64)64Y代理操作人**operate_type**varchar(32)32Y操作类型**group_id**bigint(20)190N1接入方隔离**from_mobile**char(1)1Nn标记是否来自移动审批**files**longtext4294967295Y标记文件字段**user_job**varchar(70)70Y用户职位标记**is_deleted**char(1)1Nn删除标记**gmt_modified**datetimeY修改时间**modifier**varchar(64)64Y修改人**step_en**varchar(256)256Y英文的操作步骤**notice**text65535Y审批职责中英文**reason**text65535Y审批缘由中英文**digital_sign**varchar(512)512Y电子手签图片**target_users**text65535Y目标人员，多人逗号隔开**索引名**类型包含字段**idx_activity_id**Normalapp_key,activity_id**idx_process_instance_id**Normalapp_key,process_instance_id,operate_time**idx_task_id**Normalapp_key,task_id**operator**Normalapp_key,operator**original_operator**Normalapp_key,original_operator**PRIMARY**Primaryid
## 其他部分表[​](#b6eb8a89)
tianshu_instance_relation：表单实例关系表 --- 宜搭专属老存储使用，已经废弃yida_entity_instance：表单实例数据表 --- 宜搭专属老存储使用，已经废弃，目前很多用户还在依赖，会通过odin_open_application_data表异步同步，建议还是以odin_open_application_data表为准超时添加索引demo如下，里面内容替换下，还是以odin_open_application_data为准：```
`CREATE INDEX CONCURRENTLY idx_model_filed_textField_xxxxx ON odin_open_application_data (
namespace_code,
table_name,
is_deleted,
parent_pid,
(json_data ->> 'textField_xxxxx')
) WHERE namespace_code = 'APP_xxxx' and table_name = 'xxxx';
`
```
或者产品化界面（优先使用手动建索引，不懂的话，就产品上建，产品上建的索引个别情况可能不是最佳效率, 有需要也可以联系研发）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1748402700206-ec8b3812-20ed-45f3-80ae-1edc884d3204.png)
如果是物理列场景的话，比如下面的phy_textfield_lmsj0bkf字段的查询：```
`select count(*) from yida_app_data_form_xxxxx a WHERE ( a.is_deleted = 'n' AND ( a.phy_textfield_lmsj0bkf = 'xxx')) AND ( a.namespace_code = 'xxxx' AND  a.table_name = 'xxx' AND  a.parent_pid IS NULL)
针对phy_textfield_lmsj0bkf建btree索引
CREATE INDEX CONCURRENTLY idx_model_phy_textfield_lmsj0bkf ON yida_app_data_form_xxxxx (
namespace_code,
table_name,
is_deleted,
parent_pid,
phy_textfield_lmsj0bkf
)
`
```
tianshu_form_data：表单数据表 --- 宜搭专属老存储使用，已经废弃ecds_xxxx：宜搭系统内部表 --- 这类都是系统运行内部表，勿操作，换库也不要自己建，会自动生成yida_app_data_xxx：物理列表 --- 表结构同odin_open_application_data，只是json字段打平；一个表单一张表，子表也是独立表.具体如下： ![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1748402700129-c62188eb-fc24-4991-aa5e-dc0dd88d28ac.png)
这个对应的表名是上面表单页面编码对应的下划线小写： yida_app_data_form_obd66r71q2asxubwc9p3g8yneplv2jcv43d6m3 因为考虑到数据库表名长度限制的问题，所以这边针对子表的表名 本来是yida_app_data_form_obd66r71q2asxubwc9p3g8yneplv2jcv43d6m3_tableFieldXxx 如果达到64个字节才会用md5 hash最终计算方式结果类似下面：```
`String physicalTableName = tableName.substring(0, 63 - tableNameHashPostfix.length()) + tableNameHashPostfix;
`
```
tableName是yida_app_data_form_obd66r71q2asxubwc9p3g8yneplv2jcv43d6m3_tableFieldXxx ， tableNameHashPostfix是 "_" + tableNameMd5（tableNameMd5是md5加密后的结果 8af1899537e0ac902f784162207c0e54）![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1748402700284-0fb40a17-73b1-487e-92e5-5544b7e2f76d.png)
