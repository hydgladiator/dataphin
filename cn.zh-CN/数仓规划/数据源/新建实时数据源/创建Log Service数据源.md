---
keyword: 创建Log Service数据源
---

# 创建Log Service数据源

创建Log Service数据源用于实现Dataphin能够读取Log Service的业务数据。在引入Log Service的业务数据至Dataphin中进行数据开发的场景中，您需要先创建Log Service数据源。本文为您介绍如何创建Log Service类型的数据源。

Log Service即阿里云日志服务，如果您使用的是阿里云日志服务，在对接Dataphin进行数据开发时，您需要先完成Log Service数据源的创建。更多Log Service信息，请参见[什么是日志服务](/cn.zh-CN/产品简介/什么是日志服务.md)。

Dataphin支持通过VPC网络和公网连接Log Service。Dataphin连接Log Service时，可以选择Log Service在VPC网络或公网环境下对应的Endpoint，Log Service的Endpoint请参见[服务入口](/cn.zh-CN/开发指南/API参考/服务入口.md)。通常，VPC网络较公网稳定，建议您选择VPC网络连通Dataphin和Log Service。

## 使用限制

-   仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   当业务数据源（Log Service）使用VPC网络时，则仅支持创建与Dataphin实例在同一地域Log Service数据源。

## 操作步骤

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**消息队列**区域，选择**Log Service**。

    如果您最近使用过Log Service，也可以在**最近使用**区域选择Log Service。同时，您也可以在快搜索框中，输入Log Service的关键词，快速筛选。

    ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1472658261/p302694.png)

4.  在**新建Log Service数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1472658261/p302695.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![gfagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1472658261/p302696.png)

        **说明：** 通常，生产数据源和开发数据源配置参数值不同，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**LogHub Endpoint**|Log Service的Endpoint，建议配置阿里云VPC网络下的Endpoint。如何获取Endpoint，请参见[服务入口](/cn.zh-CN/开发指南/API参考/服务入口.md)。**说明：** 仅支持配置与Dataphin实例在同一地域的Log Service Endpoint。 |
        |**Project**|Log Service项目名称。在[Log Service控制台](https://sls.console.aliyun.com/lognext/profile)页面，查看Project名称。|
        |**Access ID**、**Access Key**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成Log Service数据源的创建。


完成Log Service数据源的创建后，即可将Log Service的业务数据引入至Dataphin。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

