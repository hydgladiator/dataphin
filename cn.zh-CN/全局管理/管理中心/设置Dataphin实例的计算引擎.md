---
keyword: 计算设置
---

# 设置Dataphin实例的计算引擎

在您开始创建用于研发数据的项目空间前，需要先设置Dataphin实例的计算引擎。设置Dataphin实例的计算引擎后，系统支持为项目空间添加离线计算引擎（MaxCompute或AnalyticDB for PostgreSQL）和实时计算引擎（Flink）。本文为您介绍如何设置Dataphin实例的计算引擎。

-   如果您购买的Dataphin实例是基础研发版，则需要添加AnalyticDB for PostgreSQL类型的离线计算引擎。

    请您提前创建AnalyticDB for PostgreSQL实例，创建过程中需要您记录实例的名称。创建AnalyticDB for PostgreSQL实例，请参见[创建AnalyticDB for PostgreSQL实例](/cn.zh-CN/快速入门/创建实例.md)。

-   如果您购买的Dataphin实例是智能研发版，则需要添加MaxCompute类型的离线计算引擎。

    请您提前开通MaxCompute，开通MaxCompute过程中，需要您记录MaxCompute项目所在地域。开通MaxCompute，请参见[开通MaxCompute](/cn.zh-CN/准备工作/开通MaxCompute.md)。


## 注意事项

-   系统默认支持实时计算引擎（Flink）。
-   当前，一个Dataphin实例仅支持添加一种离线计算引擎：
    -   基础研发版支持的离线计算引擎为AnalyticDB for PostgreSQL。
    -   智能研发版支持的离线计算引擎为MaxCompute。
-   成功设置Dataphin实例的计算引擎并开始数据建设后，系统不支持修改计算引擎。

## 设置智能研发版实例的计算引擎

1.  使用阿里云账号登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  在Dataphin产品首页，单击顶部菜单栏的**管理中心**。

4.  在**管理中心**页面，单击左侧导航栏的**计算设置**。

5.  在**计算设置**页面的**MaxCompute**区域，根据Dataphin实例所在的地域，配置**Endpoint**。

    不同地域的**Endpoint**，详情参见下表。

    |区域|Endpoint|
    |--|--------|
    |华东2（上海）|`http://service.cn-shanghai.maxcompute.aliyun-inc.com/api`|
    |华北2（北京）|`http://service.cn-beijing.maxcompute.aliyun-inc.com/api`|
    |华南1（深圳）|`http://service.cn-shenzhen.maxcompute.aliyun-inc.com/api`|
    |华东1（杭州）|`http://service.cn-hangzhou.maxcompute.aliyun-inc.com/api`|

6.  单击**校验**。

7.  校验成功后，单击**确认并开始数据建设**，即可开始数据建设。

    完成Dataphin实例计算引擎的设置后，即可开始创建用于研发数据的项目空间，详情请参见[新建项目](/cn.zh-CN/数仓规划/项目管理/新建项目.md)。


## 设置基础研发版实例的计算引擎

1.  请参见[设置智能研发版实例的计算引擎](#section_3oa_p8q_nwq)，进入**计算设置**页面。

2.  在**计算设置**页面的**离线计算引擎**区域，选择计算引擎为**AnalyticDB for PostgreSQL**。

3.  在**JDBC URL**输入框中，输入jdbc:postgresql://实例ID.gpdb.rds.aliyuncs.com:端口/实例名称。

    其中：

    -   实例ID：AnalyticDB for PostgreSQL实例的ID。
    -   端口：AnalyticDB for PostgreSQL实例的端口。
    -   实例名称：AnalyticDB for PostgreSQL实例的名称。
    在AnalyticDB for PostgreSQL实例详情页面，获取实例ID和端口，请参见[进入AnalyticDB for PostgreSQL实例详情页](/cn.zh-CN/快速入门/客户端连接.md)。

4.  单击**校验**。

5.  校验成功后，单击**确认并开始数据建设**，即可开始数据建设。

    完成Dataphin实例计算引擎的设置后，即可开始创建用于研发数据的项目空间，详情请参见[新建项目](/cn.zh-CN/数仓规划/项目管理/新建项目.md)。


