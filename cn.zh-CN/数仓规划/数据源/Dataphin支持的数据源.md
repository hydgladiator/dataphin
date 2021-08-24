---
keyword: Dataphin支持的数据源
---

# Dataphin支持的数据源

在使用Dataphin前，您需要选择符合业务场景需求的数据库或数据仓库作为数据源，用于读取原始数据和写入数据建设过程中的数据。Dataphin集成了丰富的数据引擎，支持对接如MaxCompute、Hive等数据仓库，也支持对接企业传统数据库，如MySQL、Oracle等。

Dataphin支持对接的数据源包括大数据存储型数据源、文件数据源、消息队列数据源、关系型数据源和NoSQL数据源，各模块支持对接的数据源类型说明如下。如果您需要在Dataphin中连接某数据源，则需要先在数仓规划中的数据源模块创建该数据源。

## 大数据存储型数据源

|数据源类型|数据集成|实时研发|数据治理|数据服务|数据安全|创建数据源的操作指导|
|-----|----|----|----|----|----|----------|
|MaxCompute|支持|支持|支持|不支持|支持|[创建MaxCompute数据源](/cn.zh-CN/数仓规划/数据源/大数据存储数据源/创建MaxCompute数据源.md)|
|Hive|支持|不支持|支持|不支持|支持|[创建Hive数据源](/cn.zh-CN/数仓规划/数据源/大数据存储数据源/创建Hive数据源.md)|
|SAP HANA|支持|不支持|不支持|不支持|不支持|[创建SAP HANA数据源](/cn.zh-CN/数仓规划/数据源/大数据存储数据源/创建SAP HANA数据源.md)|
|DataHub|不支持|支持|不支持|不支持|不支持|[创建DataHub数据源](/cn.zh-CN/数仓规划/数据源/大数据存储数据源/创建DataHub数据源.md)|
|Hologres|支持|支持|不支持|不支持|不支持|[创建Hologres数据源]()|

## 文件数据源

|数据源类型|数据集成|实时研发|数据治理|数据服务|数据安全|创建数据源的操作指导|
|-----|----|----|----|----|----|----------|
|HDFS|支持|不支持|不支持|不支持|不支持|[创建HDFS数据源](/cn.zh-CN/数仓规划/数据源/文件数据源/创建HDFS数据源.md)|
|FTP|支持|不支持|不支持|不支持|不支持|[创建FTP数据源](/cn.zh-CN/数仓规划/数据源/文件数据源/创建FTP数据源.md)|
|OSS|支持|不支持|不支持|不支持|不支持|[创建OSS数据源](/cn.zh-CN/数仓规划/数据源/文件数据源/创建OSS数据源.md)|

## 消息队列数据源

|数据源类型|数据集成|实时研发|数据治理|数据服务|数据安全|创建数据源的操作指导|
|-----|----|----|----|----|----|----------|
|Log Service|支持|支持|不支持|不支持|不支持|[创建Log Service数据源](/cn.zh-CN/数仓规划/数据源/消息队列数据源/创建Log Service数据源.md)|
|Kafka|不支持|支持|不支持|不支持|不支持|[创建Kafka数据源](/cn.zh-CN/数仓规划/数据源/消息队列数据源/创建Kafka数据源.md)|
|RocketMQ|不支持|支持|不支持|不支持|不支持|[创建RocketMQ数据源](/cn.zh-CN/数仓规划/数据源/消息队列数据源/创建RocketMQ数据源.md)|

## 关系型数据源

|数据源类型|数据集成|实时研发|数据治理|数据服务|数据安全|创建数据源的操作指导|
|-----|----|----|----|----|----|----------|
|PolarDB|支持|不支持|不支持|不支持|不支持|[创建PolarDB数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建PolarDB数据源.md)|
|PolarDB-X（原DRDS）|支持|支持|不支持|不支持|不支持|[创建PolarDB-X数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建PolarDB-X数据源.md)|
|MySQL|支持|不支持|不支持|支持|不支持|[创建MySQL数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建MySQL数据源.md)|
|Microsoft SQL Server|支持|不支持|不支持|支持|不支持|[创建Microsoft SQL Server数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建Microsoft SQL Server数据源.md)|
|PostgreSQL|支持|不支持|不支持|支持|不支持|[创建PostgreSQL数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建PostgreSQL数据源.md)|
|Oracle|支持|不支持|不支持|支持|不支持|[创建Oracle数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建Oracle数据源.md)|
|AnalyticDB for MySQL 2.0|支持|不支持|不支持|支持|不支持|[创建AnalyticDB for MySQL数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建AnalyticDB for MySQL数据源.md)|
|AnalyticDB for MySQL 3.0|支持|支持|不支持|支持|不支持|[新建AnalyticDB for MySQL 3.0数据源]()|
|AnalyticDB for PostgreSQL|支持|不支持|支持|支持|支持|[创建AnalyticDB for PostgreSQL数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建AnalyticDB for PostgreSQL数据源.md)|
|OceanBase|支持|不支持|不支持|不支持|不支持|[创建OceanBase数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建OceanBase数据源.md)|
|Vertica|支持|不支持|不支持|不支持|不支持|[创建Vertica数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建Vertica数据源.md)|
|IBM DB2|支持|不支持|不支持|不支持|不支持|[创建IBM DB2数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建IBM DB2数据源.md)|
|Teradata|支持|不支持|不支持|不支持|不支持|[创建Teradata数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建Teradata数据源.md)|
|Impala|不支持|不支持|不支持|支持|不支持|[创建Impala数据源](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建Impala数据源.md)|

## NoSQL数据源

|数据源类型|数据集成|实时研发|数据治理|数据服务|数据安全|创建数据源的操作指导|
|-----|----|----|----|----|----|----------|
|HBase|支持|不支持|不支持|支持|不支持|[创建HBase数据源]()|
|Elasticsearch|支持|不支持|不支持|支持|不支持|[创建Elasticsearch数据源]()|
|MongoDB|支持|不支持|不支持|支持|不支持|[创建MongoDB数据源]()|
|Tablestore|不支持|支持|不支持|不支持|不支持|[创建Tablestore数据源]()|
|Aliyun HBase|不支持|支持|不支持|不支持|不支持|[创建Aliyun HBase数据源]()|

