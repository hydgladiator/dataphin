---
keyword: 创建MaxCompute数据源
---

# 创建MaxCompute数据源

创建MaxCompute数据源用于实现Dataphin能够读取MaxCompute的业务数据，及能够向MaxCompute写入数据。在引入MaxCompute的业务数据至Dataphin和将Dataphin的数据写入至MaxCompute的场景中，您需要先创建MaxCompute数据源。本文为您介绍如何创建MaxCompute类型的数据源。

MaxCompute即阿里云大数据计算服务，如果您使用的是阿里云大数据计算服务MaxCompute，在对接Dataphin进行数据开发或将Dataphin的数据导出至MaxCompute场景中，您需要先完成MaxCompute数据源的创建。更多MaxCompute信息，请参见[什么是MaxCompute](/cn.zh-CN/产品简介/什么是MaxCompute.md)。

Dataphin支持通过公网和VPC网络连接MaxCompute。Dataphin连接MaxCompute时，可以选择MaxCompute在VPC网络或公网环境下对应的Endpoint，MaxCompute的Endpoint请参见[Endpoint](/cn.zh-CN/准备工作/Endpoint.md)。通常，VPC网络较公网稳定，建议您选择VPC网络连通Dataphin和MaxCompute。

为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin不同网络环境下的IP地址段添加到数据源的白名单中，更多对接配置详情请参见[设置IP白名单](/cn.zh-CN/安全管理/安全管理详解/设置IP白名单.md)。

## 使用限制

-   Dataphin仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   当您使用VPC网络连接Dataphin实例与MaxCompute项目时，仅支持连接与Dataphin实例在同一地域的MaxCompute项目。

## 步骤一：添加Dataphin IP地址至MaxCompute白名单

基于您选择连通Dataphin与MaxCompute的网络类型，添加对应网络类型下的Dataphin IP地址至MaxCompute白名单中。如何添加白名单，请参见[设置IP白名单](/cn.zh-CN/安全管理/安全管理详解/设置IP白名单.md)。

-   使用公网连通Dataphin与MaxCompute时，需要添加公网下Dataphin IP地址至MaxCompute白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）|47.102.151.182|
    |华南1（深圳）|119.23.173.65|
    |华北2（北京）|123.56.104.202|
    |华东1（杭州）|47.96.75.100|

-   使用VPC网络连通Dataphin与MaxCompute时，需要添加VPC网络下Dataphin IP地址至MaxCompute白名单中。

    |地域|IP地址|
    |--|----|
    |华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）|**100.104.0.0/16****说明：** **100.104.0.0/16**是华东2（上海）、华南1（深圳）、华北2（北京）和华东1（杭州）地域的通用IP白名单。推荐使用该白名单。 |
    |华东2（上海）|100.104.228.128/26、100.104.115.192/26|
    |华南1（深圳）|100.104.48.128/26|
    |华北2（北京）|100.104.238.64/26|
    |华东1（杭州）|100.104.45.0/26|


## 步骤二：创建MaxCompute数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**大数据存储**区域，选择**MaxCompute**。

    如果您最近使用过MaxCompute，也可以在**最近使用**区域选择MaxCompute。同时，您也可以在快搜索框中，输入MaxCompute的关键词，快速筛选。

    ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0344897261/p300875.png)

4.  在**新建MaxCompute数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0344897261/p300710.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0344897261/p300715.png)

        **说明：** 通常，生产数据源和开发数据源需要配置不同的参数值，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**Endpoint**|MaxCompute的Endpoint，建议填写阿里云VPC网络下的Endpoint。如何获取Endpoint，请参见[Endpoint](/cn.zh-CN/准备工作/Endpoint.md)。**说明：** 当您使用VPC网络连接Dataphin与MaxCompute时，此处需要配置为Dataphin实例所在地域下MaxCompute的Endpoint。 |
        |**Project Name**|此处为MaxCompute项目名称，非DataWorks工作空间名称。您可以登录[MaxCompute控制台](https://workbench.data.aliyun.com/#/MCEngines)，左上角切换地域后，即可在项目管理页签查看到具体的MaxCompute项目名称。

![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8401639261/p307404.png) |
        |**Access ID**、**Access Key**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成MaxCompute数据源的创建。


完成MaxCompute数据源的创建后，即可将MaxCompute的业务数据引入至Dataphin，或将Dataphin的数据写入至MaxCompute数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

