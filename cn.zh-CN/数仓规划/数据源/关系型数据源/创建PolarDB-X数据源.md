---
keyword: 创建PolarDB-X数据源
---

# 创建PolarDB-X数据源

创建PolarDB-X数据源用于实现Dataphin能够读取PolarDB-X的业务数据，及能够向PolarDB-X写入数据。在引入PolarDB-X的业务数据至Dataphin和将Dataphin的数据写入至PolarDB-X的场景中，需要先创建PolarDB-X数据源。本文为您介绍如何创建PolarDB-X数据源。

PolarDB-X（原DRDS升级版）是由阿里巴巴自主研发的云原生分布式数据库。如果您使用的是PolarDB-X，在对接Dataphin进行数据开发时，您需要先完成PolarDB-X数据源的创建。更多PolarDB-X信息，请参见[产品概述]()。

Dataphin支持通过VPC网络和公网连接PolarDB-X。不同类型的网络连通方式下，所需的配置细节不一致，如下图所示。

![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7845809261/p304022.png)

为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin不同网络环境下的IP地址段添加到数据源的白名单中。

## 使用限制

-   仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   当业务数据源（PolarDB-X）使用VPC网络时，则仅支持创建与Dataphin实例在同一地域PolarDB-X数据源。

## 步骤一：添加Dataphin IP地址至数据库白名单

基于业务数据源所在的网络环境，添加对应环境下的Dataphin IP地址至数据库白名单中。以阿里云数据库为例为您介绍如何添加白名单，请参见[设置白名单]()。

-   访问方式为公网访问，则需要添加公网下Dataphin IP地址至数据库白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）|47.102.151.182|
    |华南1（深圳）|119.23.173.65|
    |华北2（北京）|123.56.104.202|
    |华东1（杭州）|47.96.75.100|

-   访问方式为VPC网络，则需要添加VPC网络下Dataphin IP地址至数据库白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）|**100.104.0.0/16****说明：** **100.104.0.0/16**是华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）地域的通用IP白名单。推荐使用该白名单。 |
    |华东2（上海）|100.104.228.128/26、100.104.115.192/26|
    |华南1（深圳）|100.104.48.128/26|
    |华北2（北京）|100.104.238.64/26|
    |华东1（杭州）|100.104.45.0/26|


## 步骤二：创建PolarDB-X数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**关系型数据库**区域，选择**PolarDB-X（原DRDS）**。

    如果您最近使用过PolarDB-X，也可以在**最近使用**区域选择PolarDB-X。同时，您也可以在快搜索框中，输入PolarDB-X的关键词，快速筛选。

    ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3336098261/p304038.png)

4.  在**新建PolarDB-X（原DRDS）数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3336098261/p304035.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/4336098261/p304040.png)

        **说明：** 通常，生产数据源和开发数据源需要配置的参数值不同，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**JDBC URL**|链接地址的格式为`jdbc:mysql://{链接地址}:{端口}/{数据库名称}`。您可以在[PolarDB-X控制台](https://polardb-x.console.aliyun.com)实例对应数据库的详情页面，查看链接地址、端口和数据库名称。下图示例为VPC网络下的链接信息。

![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/4336098261/p304109.png) |
        |**用户名**、**密码**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|
        |**访问方式**|选择对应的访问方式：        -   PolarDB-X数据源所在网络环境为VPC网络，则访问方式选择为**VPC网络**。
        -   PolarDB-X数据源所在网络环境为公网，则访问方式选择为**公网IP**。 |
        |**区域**、**VPC ID**、**DRDS ID**|当**访问方式**选择为**VPC网路**，则需要配置如下参数：        -   **区域**：仅支持选择当前Dataphin实例所在的地域。

**说明：** 仅支持添加与Dataphin实例在同一地域的PolarDB-X数据源至Dataphin。

        -   **VPC ID**：填写PolarDB-X实例的VPC ID。
        -   **DRDS ID**：填写PolarDB-X实例的ID。
在[PolarDB-X控制台](https://polardb-x.console.aliyun.com)的实例详情页面，查看实例ID和VPC ID。![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/4336098261/p304106.png) |

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成PolarDB-X数据源的创建。


完成PolarDB-X数据源的创建后，即可将PolarDB-X的业务数据引入至Dataphin，或将Dataphin的数据写入至PolarDB-X数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

