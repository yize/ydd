---
title: 顺序执行
url: https://docs.aliwork.com/docs/yida_support/_3/yovph5uaoyxb6f02/gd8wqzg0reppv4fk
source: docs.aliwork.com
---

# 顺序执行

宜搭专属版支持设置集成&自动化流顺序执行，开启顺序执行后，同一个集成自动化流的多个实例，将顺序执行，适用于数据有前后依赖关系的场景。例如库存的获取及更新。原集成自动化流的运行方式默认为**并行**，多条数据触发同一个集成自动化流，将会同步执行。执行速度较快，适合运行实例间互不影响的流程。开启顺序执行后，多条数据将逐条执行，速度较慢，适合运行实例间有先后依赖的流程。**说明：**开启顺序执行后，集成自动化流的多个实例将逐条执行，执行速度可能会比较慢，请按需谨慎开启。
![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/png/1733998023611-d9e4446c-0c53-467a-a84d-721fd91041ed.png)
