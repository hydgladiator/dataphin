---
keyword: 创建DataHub数据源
---

# 创建DataHub数据源

创建DataHub数据源用于实现Dataphin能够读取DataHub的业务数据。在引入DataHub的业务数据至Dataphin中进行数据开发的场景中，您需要先创建DataHub数据源。本文为您介绍如何创建DataHub类型的数据源。

DataHub即阿里云流式数据服务DataHub，如果您使用的是阿里云流式数据服务DataHub，在对接Dataphin进行数据开发时，您需要先完成DataHub数据源的创建。更多DataHub信息，请参见[产品概述]()。

Dataphin支持通过VPC网络和公网连接DataHub。Dataphin连接DataHub时，可以选择DataHub在VPC网络、经典网络、公网环境下对应的Endpoint，DataHub的Endpoint请参见[域名列表]()。通常，VPC网络较公网和经典网络稳定，建议您使用VPC网络连通Dataphin和DataHub。

## 使用限制

-   Dataphin仅支持超级管理员和项目管理员角色创建数据源。

    如何添加成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   当您使用VPC网络连接Dataphin与DataHub时，仅支持连接与Dataphin在同一地域的DataHub。

## 操作步骤

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**大数据存储**区域，选择**DataHub**。

    如果您最近使用过DataHub，也可以在**最近使用**区域选择DataHub。同时，您也可以在快搜索框中，输入DataHub的关键词，快速筛选。

    ![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0448668261/p302319.png)

4.  在**新建DataHub数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![fafa](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0448668261/p302320.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/6960089261/p302321.png)

        **说明：** 通常，生产数据源和开发数据源需要配置不同的参数值，但Dataphin也支持配置成相同参数值。

        |参数|描述|
        |--|--|
        |**Endpoint**|DataHub的Endpoint，建议填写阿里云VPC网络下的Endpoint。如何获取Endpoint，请参见[域名列表]()。**说明：** 如果填写阿里云VPC网络下的Endpoint，则仅支持填写与Dataphin实例在同一地域下的Endpoint。 |
        |**Project Name**|DataHub项目名称。在[DataHub控制台](https://dhsnext.console.aliyun.com/?spm=a2c4g.11186623.2.4.4964a8cbrD6uwi)页面，查看Project Name。|
        |**Access ID**、**Access Key**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成DataHub数据源的创建。


完成DataHub数据源的创建后，即可将DataHub的业务数据引入至Dataphin，或将Dataphin的数据写入至DataHub数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

