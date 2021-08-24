---
keyword: 创建Aliyun HBase数据源
---

# 创建Aliyun HBase数据源

创建Aliyun HBase数据源用于实现Dataphin能够读取Aliyun HBase的业务数据。在开发流批一体任务的场景中，如果业务数据来源于Aliyun HBase，则在您开始研发数据前需要先完成Aliyun HBase数据源的创建。本文为您介绍如何创建Aliyun HBase数据源。

Aliyun HBase即阿里云的云数据库HBase。如果您使用的是云数据库HBase，在对接Dataphin进行数据开发时，您需要先完成Aliyun HBase数据源的创建。更多云数据库HBase信息，请参见[产品概述]()。

Dataphin支持对接标准版Aliyun HBase和增强版Aliyun HBase，且均支持通过VPC网络和公网连接。通常，VPC网络较公网稳定，建议您选择VPC网络连通Dataphin和Aliyun HBase。

为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin不同网络环境下的IP地址段添加到数据源的白名单中。

## 使用限制

-   仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   当业务数据源（Aliyun HBase）使用VPC网络时，则仅支持创建与Dataphin实例在同一地域Aliyun HBase数据源。

## 步骤一：添加Dataphin IP地址至数据库白名单

基于业务数据源所在的网络环境，添加对应环境下的Dataphin IP地址至数据库白名单中。如何添加白名单，请参见[增强版Aliyun HBase设置白名单]()、[标准版Aliyun HBase设置白名单]()。

-   公网的数据源需要添加公网下Dataphin IP地址至数据库白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）|47.102.151.182|
    |华南1（深圳）|119.23.173.65|
    |华北2（北京）|123.56.104.202|
    |华东1（杭州）|47.96.75.100|

-   VPC网络的数据源需要添加VPC网络下的Dataphin IP地址至数据库白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）|**100.104.0.0/16****说明：** **100.104.0.0/16**是华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）地域的通用IP白名单。推荐使用该白名单。 |
    |华东2（上海）|100.104.228.128/26、100.104.115.192/26|
    |华南1（深圳）|100.104.48.128/26|
    |华北2（北京）|100.104.238.64/26|
    |华东1（杭州）|100.104.45.0/26|


## 步骤二：创建Aliyun HBase数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**NoSQL**区域，选择**Aliyun HBase**。

    如果您最近使用过Aliyun HBase，也可以在**最近使用**区域选择Aliyun HBase。同时，您也可以在快搜索框中，输入Aliyun HBase的关键词，快速筛选。

    ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5974539261/p306985.png)

4.  在**新建Aliyun HBase数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5974539261/p306986.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        -   如果您的阿里云HBase实例的服务类型为标准型，则选择为**标准型**。

            ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5974539261/p307255.png)

            |参数|描述|
            |--|--|
            |**服务类型**|选择为**标准型**。|
            |**版本**|选择阿里云HBase实例对应的主版本号。您可以在[阿里云Hbase控制台](https://hbase.console.aliyun.com/hbase)的数据库连接页面，查看主版本号。![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5974539261/p307287.png) |
            |**zkQuorum**|配置阿里云HBase实例的链接地址，推荐您使用专有云网络的链接地址。您可以在[阿里云Hbase控制台](https://hbase.console.aliyun.com/hbase)的数据库连接页面，查看链接地址。![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5974539261/p307288.png) |

        -   如果您的阿里云HBase实例的服务类型为增强型，则选择为**增强型**。

            ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5974539261/p307259.png)

            |参数|描述|
            |--|--|
            |**服务类型**|选择为**增强型**。|
            |**Endpoint**|选择阿里云HBase实例对应CQL访问地址。您可以在[阿里云Hbase控制台](https://hbase.console.aliyun.com/hbase)的数据库连接页面，查看CQL访问地址。![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5974539261/p307303.png) |
            |**用户名****密码**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|

        **说明：** 通常，生产数据源和开发数据源需要配置成不同的参数值，但Dataphin也支持配置成相同的参数值。

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成Aliyun HBase数据源的创建。


完成Aliyun HBase数据源的创建后，即可开始开发流批一体任务。具体操作，请参见[创建Flink SQL任务](/cn.zh-CN/数据开发/数据处理/新建FLINK任务/新建Flink_SQL任务.md)、[创建Flink DataStream计算任务](/cn.zh-CN/数据开发/数据处理/新建FLINK任务/新建Flink_DataStream计算任务.md)或[步骤一：创建并调试Flink Template SQL计算任务](/cn.zh-CN/数据开发/数据处理/新建FLINK任务/新建Flink_Template_SQL计算任务.md)。

