---
keyword: 创建PolarDB数据源
---

# 创建PolarDB数据源

创建PolarDB数据源用于实现Dataphin能够读取PolarDB的业务数据，及能够向PolarDB写入数据。在引入PolarDB的业务数据至Dataphin和将Dataphin的数据写入至PolarDB的场景中，需要先创建PolarDB数据源。本文为您介绍如何创建PolarDB数据源。

PolarDB是阿里云自主研发新一代关系型数据库，兼容MySQL、PostgreSQL语法的云托管数据库产品。如果您使用的是PolarDB，在对接Dataphin进行数据开发时，您需要先完成PolarDB数据源的创建。更多PolarDB信息，请参见[什么是PolarDB](/cn.zh-CN/产品简介/什么是PolarDB.md)。

Dataphin仅支持对接MySQL和PostgreSQL作为引擎的PolarDB数据库，支持通过VPC网络和公网连接PolarDB数据库。PolarDB支持以下三种类型的MySQL和PostgreSQL数据库作为引擎：公网数据库、阿里云数据库和ECS（VPC）自建数据库。数据库类型不同，所需的配置细节不同，如下图所示。

![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1014309261/p300445.png)

|数据源类型|数据源类型和网络连通说明|网络连通操作指导|
|-----|------------|--------|
|阿里云数据库|即阿里云PolarDB MySQL或PolarDB PostgreSQL。创建数据源过程中，需要根据业务情况选择访问方式（公网IP和VPC网络）后，再配置网络连通参数。|1.  [步骤一：添加Dataphin IP地址至数据库白名单](#section_6em_u52_1dp)
2.  [步骤二：创建PolarDB数据源](#section_cjo_dpc_8w6) |
|公网数据库|即具备公网访问能力的数据库，访问方式默认为公网IP。直接添加Dataphin IP地址至数据库白名单中即可。|
|ECS（VPC）自建数据源|即在阿里云ECS上自建的数据库且访问方式为VPC网络。直接配置网络连通参数即可。|

为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin不同网络环境下的IP地址段添加到数据源的白名单中。

## 使用限制

-   仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   当业务数据源（PolarDB）使用VPC网络时，则仅支持创建与Dataphin实例在同一地域PolarDB数据源。

## 步骤一：添加Dataphin IP地址至数据库白名单

基于PolarDB数据源引擎（MySQL或PostgreSQL）所在的网络环境，添加对应环境下的Dataphin IP地址至数据库白名单中。以阿里云数据库为例为您介绍如何添加白名单，请参见[设置白名单](/cn.zh-CN/用户指南/数据安全和加密/设置集群白名单/设置白名单.md)。

-   公网数据库、阿里云数据库且访问方式为公网访问，则需要添加公网下Dataphin IP地址至数据库白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）|47.102.151.182|
    |华南1（深圳）|119.23.173.65|
    |华北2（北京）|123.56.104.202|
    |华东1（杭州）|47.96.75.100|

-   ECS（VPC）自建数据源、阿里云数据库且访问方式为VPC网络，则需要添加VPC网络下Dataphin IP地址至数据库白名单中。ECS（VPC）自建数据源如何添加白名单请参见[添加安全组规则](/cn.zh-CN/安全/安全组/添加安全组规则.md)。

    |地域|IP地址|
    |--|----|
    |华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）|**100.104.0.0/16****说明：** **100.104.0.0/16**是华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）地域的通用IP白名单。推荐使用该白名单。 |
    |华东2（上海）|100.104.228.128/26、100.104.115.192/26|
    |华南1（深圳）|100.104.48.128/26|
    |华北2（北京）|100.104.238.64/26|
    |华东1（杭州）|100.104.45.0/26|


## 步骤二：创建PolarDB数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**关系型数据库**区域，选择**PolarDB**。

    如果您最近使用过PolarDB，也可以在**最近使用**区域选择PolarDB。同时，您也可以在快搜索框中，输入PolarDB的关键词，快速筛选。

    ![fahgah](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/4704578261/p303758.png)

4.  在**新建PolarDB数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5704578261/p303759.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对PolarDB数据源的简单描述。|
        |**数据库类型**|基于PolarDB底层的引擎类型，选择对应的数据库类型：        -   如果PolarDB底层的引擎为MySQL，则选择**MySQL**。
        -   如果PolarDB底层的引擎为PostgreSQL，则选择**PostgreSQL**。 |
        |**数据源配置**|基于业务数据源是否区分生产数据源和开发数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5380488261/p303803.png)

        **说明：** 通常，生产数据源和开发数据源需要配置不同的参数值，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**JDBC URL**|链接地址的格式为`jdbc:{数据库类型}://{链接地址}:{端口}/{数据库名称}`。其中：        -   数据库类型：
            -   上述步骤中数据库类型选择为MySQL，则配置为`mysql`。
            -   上述步骤中数据库类型选择为PostgreSQL，则配置为`postgresql`。
        -   以数据库类型为MySQL为例，为您介绍如何获取链接地址、端口和数据库名称：
            -   在[数据库连接](https://rdsnext.console.aliyun.com/rdsList/basic)页面，获取MySQL实例的链接地址、端口。

![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9105467261/p267366.png)

            -   在[数据库管理](https://rdsnext.console.aliyun.com/detail/rm-uf6rsk4w04ark6mk4/dataManage/databaseList?region=cn-shanghai&DedicatedHostGroupId=)页面，获取MySQL实例的数据库名称。

![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9105467261/p296222.png) |
        |**Schema**|当上述步骤中数据库类型选择为**PostgreSQL**，需要配置**Schema**。**Schema**即PostgreSQL实例的数据库名称。在PostgreSQL实例的数据管理页面获取数据库名称，如下图所示。![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5380488261/p303826.png)

**说明：** 当上述步骤中-\`库类型选择为**MySQL**，则配置页面没有**Schema**配置项。 |
        |**用户名**、**密码**|登录PolarDB数据源引擎MySQL或PostgreSQL的用户名和密码。|
        |**类型**|PolarDB数据源的引擎MySQL、PostgreSQL均支持选择以下几种类型：        -   **公网数据库**：如果您的数据源具备公网访问能力，则可以选择**公网数据库**。
        -   **阿里云数据库**：如果您的数据源是阿里云数据库RDS，请选择库**阿里云数据**。阿里云数据库支持通过**公网IP**或**VPC网络**连接Dataphin。

**说明：** 如果您的数据源是阿里云数据库且支持公网访问，则您可以选择公网数据库，也可以选择阿里云数据库（公网IP）。

        -   **ECS（VPC）自建数据源**：如果您的数据源是在阿里云ECS上自建的数据库，且使用的网络环境为VPC，请选择**ECS（VPC）自建数据源**。 |
        |**区域**、**VPC ID**、**PolarDB ID**/**ECS ID**|当**类型**选择为**ECS（VPC）自建数据源**和**阿里云数据库**（VPC网络），还需配置**区域**、**VPC ID**、**PolarDB ID**/**ECS ID**这些网络参数，其中：        -   **阿里云数据库**（VPC网络）：配置如下参数。
            -   **区域**：仅支持选择当前Dataphin实例所在的地域。

**说明：** 仅支持添加与Dataphin实例在同一地域的PolarDB数据源至Dataphin。

            -   **VPC ID**：填写PolarDB实例的VPC ID。
            -   **PolarDB ID**：填写PolarDB实例的ID。
        -   **ECS（VPC）自建数据源**：配置如下参数。
            -   **区域**：仅支持选择当前Dataphin实例所在的地域。

**说明：** 仅支持添加与Dataphin实例在同一地域的MySQL数据源至Dataphin。

            -   **VPC ID**：填写云服务器ECS实例的VPC ID。
            -   **ECS ID**：填写云服务器ECS实例的ID。
您可以在[PolarDB控制台](https://polardb.console.aliyun.com)的实例基本信息页面、[ECS实例控制台](https://ecs.console.aliyun.com)的实例详情页面查看VPC ID、PolarDB ID、ECS ID，如下图所示。

![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5380488261/p303950.png) |

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成PolarDB数据源的创建。


完成PolarDB数据源的创建后，即可将PolarDB的业务数据引入至Dataphin，或将Dataphin的数据写入至PolarDB数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

