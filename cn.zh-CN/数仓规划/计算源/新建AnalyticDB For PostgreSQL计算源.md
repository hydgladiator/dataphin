---
keyword: AnalyticDB For PostgreSQL计算源
---

# 新建AnalyticDB For PostgreSQL计算源

AnalyticDB For PostgreSQL计算源用于绑定Dataphin项目和AnalyticDB For PostgreSQL项目，为Dataphin项目提供处理离线计算任务的计算源。如果Dataphin系统的计算引擎设置为AnalyticDB For PostgreSQL，则只有添加了AnalyticDB For PostgreSQL计算源的项目，支持ADB任务、即席查询、通用脚本等功能。本文为您介绍如何新建AnalyticDB For PostgreSQL计算源。

-   Dataphin的计算引擎设置为AnalyticDB For PostgreSQL，详情请参见[设置Dataphin实例的计算引擎](/cn.zh-CN/全局管理/管理中心/设置Dataphin实例的计算引擎.md)。
-   已获取AnalyticDB For PostgreSQL计算引擎数据库对应的Schema、用户名和密码，详情请参见。

如果Dataphin系统的计算引擎设置为AnalyticDB For PostgreSQL，则项目绑定不同计算源类型对应的功能说明如下。

|项目绑定计算源类型|支持的功能|
|---------|-----|
|项目仅绑定了Flink类型的计算源|Flink任务|
|项目绑定了AnalyticDB For PostgreSQL和Flink类型的计算源|即席查询、ADB任务、通用脚本|

新建AnalyticDB For PostgreSQL计算源的权限限制，详情请参见[数仓规划权限列表](/cn.zh-CN/权限管理/数仓规划权限列表.md)。

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  在数仓**规划**页面，单击左侧导航栏的**计算源**。

3.  在**计算源**页面，单击**新增计算源**。

4.  在**新建计算源**对话框，配置参数。

    |参数|描述|
    |--|--|
    |**计算类型**|选择为**AnalyticDB For PostgreSQL**。|
    |**计算源名称**|计算源名称由汉字、数字、字母、下划线（\_）或短划线（-）组合组成。|
    |**计算源描述**|填写计算源的简单描述。|
    |**JDBC URL**|默认为计算引擎的JDBC URL，不支持修改。|
    |**Schema**|填写计算引擎数据库对应的Schema连接信息。|
    |**用户名**|填写AnalyticDB For PostgreSQL计算引擎数据库的登录用户名。|
    |**密码**|填写AnalyticDB For PostgreSQL计算引擎数据库的登录密码。|

5.  单击**测试连接**，测试连接的计算源。

6.  测试成功后，单击**提交**。

    完成创建AnalyticDB For PostgreSQL计算源后，即可为项目绑定AnalyticDB For PostgreSQL计算源，详情请参见[t149036.md\#](/cn.zh-CN/数仓规划/创建项目空间/创建Basic项目空间.md)或[管理项目空间的权限和计算源](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。


