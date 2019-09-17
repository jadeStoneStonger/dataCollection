# dataCollection
数据源(mysql binlog)(或者是业务日志)->日志解析器(解析binlog用canal，其他自定义)->mq(kafka)->数据库（es/redis）->前端展示(Kibana)

目前先做binlog+canal+kafka+es+kibana这一套流程

## 前期准备
- mysql 开启bin-log日志
- cannal基础知识：安装canal服务端，写canal客户端代码
- kafka基础知识：会用api即可
- elasticsearch基础知识：会用api即可
- kibana基础知识：会用即可

## 项目意义
- 整合各个开源软件的过程，过一遍数据采集的流程，方便大家面试吹逼
- 可以用于解决mysql mq 发送一致性问题，避免硬编码；
- 可以进行日志分析（预警等）
- 可以进行数据异构（mysql支持查询的维度有限，可以将数据抽取到es中）

## 架构演进历史
数据抽取的演进：
1.  硬编码
2.  aop
3.  bin-log分析
