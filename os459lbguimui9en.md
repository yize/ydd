---
title: 2025年12月 私有化版更新
url: https://docs.aliwork.com/docs/yida_support/_16/os459lbguimui9en
source: docs.aliwork.com
---

# 2025年12月 私有化版更新

## 功能更新：支持达梦数据库（国产信创）[​](#iXhyR)
数据库支持版本：[https://eco.dameng.com/download/](https://eco.dameng.com/download/)![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1766544117094-38ac3089-aae2-4fe0-af67-05117a4e3dc7.png)
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1766540480382-567b4a22-457a-4498-af5c-c11f9f743370.png)
### 系统配置推荐：[​](#WLIze)
建议最低配置及以上
| CPU | 内存 | 存储 | 实例数 |
|---|---|---|---|
| 32核 | 64G | 1TB SSD | 1 |
### 数据库配置文件：[​](#EtBHf)
DM.INI 文件配置并重启```
`COMPATIBLE_MODE  = 7
JSON_MODE  = 1
`
```
## 私有化版体验优化[​](#dvcku)
**部门组件兼容性改善**：解决了Excel导入时包含部门组件的公式计算报错的问题，并增强了根据部门名称查找部门ID的能力。**自动化流程稳定性提高**：修复了集成自动化发起审批流程失败的问题，确保业务流程自动化更加可靠。**数据管理界面优化**：解决了数据管理页转交成员组件显示(null)的问题，以及消息通知页面新建消息列表不展示的问题。**子表导入用户字段支持工号匹配**：加强了子表导入用户字段时对工号匹配的支持，提高了数据录入的准确性。**流水号生成规则明确化**：修复了自动生成流水号开关开启后不会生成流水号的错误，确保流水号生成机制清晰可控。**连接器及人员组件查询优化**：解决了连接器创建账号错误，并移除了人员组件查询中的虚拟AI助理，提高了查询结果的真实性和实用性。
## [​](#ehJNV)
