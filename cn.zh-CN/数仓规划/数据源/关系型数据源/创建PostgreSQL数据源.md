---
keyword: PostgreSQL数据源
---

# 创建PostgreSQL数据源

创建PostgreSQL数据源用于实现Dataphin能够读取PostgreSQL的业务数据，及能够向PostgreSQL写入数据。在引入PostgreSQL的业务数据至Dataphin和将Dataphin的数据写入至PostgreSQL的场景中，您需要先创建PostgreSQL数据源。本文为您介绍如何创建PostgreSQL类型的数据源。

## PostgreSQL数据源类型介绍

Dataphin支持添加的PostgreSQL数据源类型包括公网数据库、阿里云数据库和ECS（VPC）自建数据源。不同类型数据源的网络连通，所需的配置细节不一致，如下图所示。

![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1014309261/p300445.png)

|数据源类型|数据源类型和网络连通说明|网络连通操作指导|
|-----|------------|--------|
|阿里云数据库|即阿里云RDS PostgreSQL。创建数据源过程中，需要根据业务情况选择访问方式（公网IP和VPC网络）后，再配置网络连通参数。|1.  [步骤一：添加Dataphin IP地址至数据库白名单](#section_vpv_j0i_bn6)
2.  [步骤二：创建PostgreSQL数据源](#section_tk5_u1q_2ky) |
|公网数据库|即具备公网访问能力的数据库，访问方式默认为公网IP。直接添加Dataphin IP地址至数据库白名单中即可。|
|ECS（VPC）自建数据源|即在阿里云ECS上自建的数据且访问方式为VPC网络。直接配置网络连通参数即可。|

为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin不同网络环境下的IP地址段添加到数据源的白名单中。

## 使用限制

-   仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   仅支持创建与Dataphin实例在同一地域的ECS（VPC）自建数据源和阿里云数据库（VPC网络）类型的数据源。

## 步骤一：添加Dataphin IP地址至数据库白名单

基于业务数据源所在的网络环境，添加对应环境下的Dataphin IP地址至数据库白名单中。以阿里云RDS PostgreSQL为例为您介绍如何添加白名单，详情请参见[设置白名单](/cn.zh-CN/RDS PostgreSQL 数据库/数据安全/加密/IP白名单与安全组/设置白名单.md)。

-   公网数据库、阿里云数据库且访问方式为公网访问，则需要添加公网下Dataphin IP地址至数据库白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）|47.102.151.182|
    |华南1（深圳）|119.23.173.65|
    |华北2（北京）|123.56.104.202|
    |华东1（杭州）|47.96.75.100|

-   ECS（VPC）自建数据源、阿里云数据库且访问方式为VPC网络，则需要添加VPC网络下Dataphin IP地址至数据库白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）|**100.104.0.0/16****说明：** **100.104.0.0/16**是华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）地域的通用IP白名单。推荐使用该白名单。 |
    |华东2（上海）|100.104.228.128/26、100.104.115.192/26|
    |华南1（深圳）|100.104.48.128/26|
    |华北2（北京）|100.104.238.64/26|
    |华东1（杭州）|100.104.45.0/26|


## 步骤二：创建PostgreSQL数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**关系型数据库**区域，选择**PostgreSQL**。

    如果您最近使用过PostgreSQL，也可以在**最近使用**区域选择PostgreSQL。同时，您也可以在快搜索框中，输入PostgreSQL的关键词，快速筛选。

    ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1014309261/p304110.png)

4.  在**新建PostgreSQL数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1014309261/p304112.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1014309261/p304113.png)

        **说明：** 通常，生产数据源和开发数据源配置的参数值不同，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**JDBC URL**|链接地址的格式为`jdbc:postgresql://{链接地址}:{端口}/{数据库名称}`。以阿里云 RDS PostgreSQL数据库为例，您可以在数据库连接页面、数据库管理页面获取链接地址、端口和数据库名称。

![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1014309261/p304114.png) |
        |**Schema**|**Schema**即PostgreSQL实例的数据库名称。在PostgreSQL实例的数据管理页面获取数据库名称，如下图所示。![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2014309261/p304116.png) |
        |**用户名**和**密码**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|
        |**类型**|Dataphin支持选择以下几种数据源类型：        -   **公网数据库**：如果您的数据源具备公网访问能力，则可以选择**公网数据库**。
        -   **阿里云数据库**：如果您的数据源是阿里云数据库RDS，请选择库**阿里云数据**。阿里云数据库支持通过**公网IP**或**VPC网络**连接Dataphin。

**说明：** 如果您的数据源是阿里云数据库RDS且支持公网访问，则您可以选择公网数据库，也可以选择阿里云数据库（公网IP）。

        -   **ECS（VPC）自建数据源**：如果您的数据源是在阿里云ECS上自建的数据库，且使用的网络环境为VPC，请选择**ECS（VPC）自建数据源**。 |
        |**区域**、**VPC ID**、**RDS ID**/**ECS ID**|当**类型**选择为**ECS（VPC）自建数据源**和**阿里云数据库**（VPC网络），还需配置**区域**、**VPC ID**、**RDS ID**/**ECS ID**这些网络参数，其中：        -   **阿里云数据库**（VPC网络）：配置如下参数。
            -   **区域**：仅支持选择当前Dataphin实例所在的地域。

**说明：** 仅支持添加与Dataphin实例在同一地域的PostgreSQL数据源至Dataphin。

            -   **VPC ID**：填写阿里云RDS PostgreSQL实例的VPC ID。
            -   **RDS ID**：填写阿里云RDS PostgreSQL实例的ID。
        -   **ECS（VPC）自建数据源**：配置如下参数。
            -   **区域**：仅支持选择当前Dataphin实例所在的地域。

**说明：** 仅支持添加与Dataphin实例在同一地域的PostgreSQL数据源至Dataphin。

            -   **VPC ID**：填写云服务器ECS实例的VPC ID。
            -   **ECS ID**：填写云服务器ECS实例的ID。
您可以在PostgreSQL实例的控制台页面、ECS实例的控制台页面查看VPC ID、RDS ID、ECS ID，如下图所示。

![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2014309261/p304115.png) |

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成PostgreSQL数据源的创建。


完成PostgreSQL数据源的创建后，即可将PostgreSQL的业务数据引入至Dataphin，或将Dataphin的数据写入至PostgreSQL数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

