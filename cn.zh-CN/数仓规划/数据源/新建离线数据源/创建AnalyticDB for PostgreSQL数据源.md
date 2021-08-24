---
keyword: 创建AnalyticDB for PostgreSQL数据源
---

# 创建AnalyticDB for PostgreSQL数据源

创建AnalyticDB for PostgreSQL数据源用于实现Dataphin能够读取AnalyticDB for PostgreSQL的业务数据。在引入AnalyticDB for PostgreSQL的业务数据至Dataphin和将Dataphin的数据写入至AnalyticDB for PostgreSQL的场景中，您需要先创建AnalyticDB for PostgreSQL数据源。本文为您介绍如何创建AnalyticDB for PostgreSQL类型的数据源。

AnalyticDB for PostgreSQL即阿里云的云原生数仓AnalyticDB PostgreSQL，如果您使用的是云原生数仓AnalyticDB PostgreSQL，在对接Dataphin进行数据开发时，您需要先完成AnalyticDB for PostgreSQL数据源的创建。更多云原生数仓AnalyticDB PostgreSQL信息，请参见[产品概述](/cn.zh-CN/产品简介/产品概述.md)。

Dataphin支持通过公网IP和VPC网络连接AnalyticDB for PostgreSQL。不同网络类型的连通方式，所需的配置细节不一致，如下图所示。

![fFgf](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2906309261/p304832.png)

为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin不同网络环境下的IP地址段添加到数据源的白名单中，更多对接配置详情可参见[设置白名单](/cn.zh-CN/快速入门/设置白名单.md)。

## 使用限制

-   仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   当业务数据源使用VPC网络时，则仅支持创建与Dataphin实例在同一地域AnalyticDB for PostgreSQL数据源。

## 步骤一：添加Dataphin IP地址至数据库白名单

基于业务数据源所在的网络环境，添加对应环境下的Dataphin IP地址至数据库白名单中。如何设置白名单请参见[设置白名单](/cn.zh-CN/快速入门/设置白名单.md)。

-   访问方式为公网IP时，则需要添加公网下Dataphin IP地址至数据库白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）|47.102.151.182|
    |华南1（深圳）|119.23.173.65|
    |华北2（北京）|123.56.104.202|
    |华东1（杭州）|47.96.75.100|

-   访问方式为VPC网络时，则需要添加VPC网络下Dataphin IP地址至数据库白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）|**100.104.0.0/16****说明：** **100.104.0.0/16**是华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）地域的通用IP白名单。推荐使用该白名单。 |
    |华东2（上海）|100.104.228.128/26、100.104.115.192/26|
    |华南1（深圳）|100.104.48.128/26|
    |华北2（北京）|100.104.238.64/26|
    |华东1（杭州）|100.104.45.0/26|


## 步骤二：创建AnalyticDB for PostgreSQL数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**关系型数据库**区域，选择**AnalyticDB for PostgreSQL**。

    如果您最近使用过AnalyticDB for PostgreSQL，也可以在**最近使用**区域选择AnalyticDB for PostgreSQL。同时，您也可以在快搜索框中，输入AnalyticDB for PostgreSQL的关键词，快速筛选。

    ![fag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2906309261/p304833.png)

4.  在**新建AnalyticDB for PostgreSQL数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3906309261/p304834.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![fag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3906309261/p304848.png)

        **说明：** 通常，生产数据源和开发数据源配置的参数值不同，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**JDBC URL**|链接地址的格式为`jdbc:postgresql//{链接地址}:{端口}/{实例名称}`。在数据库连接页面查看链接地址和端口。

![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3906309261/p304845.png)

在云数据仓库AnalyticDB PostgreSQL实例列表页面，查看实例名称。

![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3906309261/p304847.png) |
        |**用户名**、**密码**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|
        |**访问方式**|选择对应的访问方式：        -   数据源所在网络环境为公网，则访问方式选择为**公网IP**。
        -   数据源所在网络环境为阿里云VPC网络，则访问方式选择为**VPC网络**。 |
        |**区域**、**VPC ID**、**集群ID**|当**访问方式**选择为**VPC网路**，则需要配置如下参数：        -   **区域**：仅支持选择当前Dataphin实例所在的地域。

**说明：** 仅支持添加与Dataphin实例在同一地域的AnalyticDB for PostgreSQL数据源至Dataphin。

        -   **VPC ID**：填写AnalyticDB for PostgreSQL实例的VPC ID。
        -   **集群 ID**：填写AnalyticDB for PostgreSQL集群ID。
在云数据仓库AnalyticDB PostgreSQL实例列表页面，查看实例ID和VPC ID。![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3906309261/p304843.png) |

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成AnalyticDB for PostgreSQL数据源的创建。


完成AnalyticDB for PostgreSQL数据源的创建后，即可将AnalyticDB for PostgreSQL的业务数据引入至Dataphin或将Dataphin的数据写入至AnalyticDB for PostgreSQL。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

