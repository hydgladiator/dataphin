---
keyword: 创建MaxCompute数据源
---

# 创建MaxCompute数据源

创建MaxCompute数据源用于实现Dataphin能够读取MaxCompute的业务数据，及能够向MaxCompute写入数据。在引入MaxCompute的业务数据至Dataphin和将Dataphin的数据写入至MaxCompute的场景中，您需要先创建MaxCompute数据源。本文为您介绍如何创建MaxCompute类型的数据源。

## 使用限制

-   Dataphin仅支持超级管理员和项目管理员角色创建数据源。

    如何添加并授予项目管理员角色的项目成员，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   使用阿里云VPC网络连通MaxCompute和Dataphin时，仅支持选择与Dataphin实例在同一地域下的Endpoint。

    MaxCompute的Endpoint地址，请参见[Endpoint](/cn.zh-CN/准备工作/Endpoint.md)。


## 操作步骤

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
        |数据源名称|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |数据源描述|对MaxCompute数据源的简单描述。|
        |数据源配置|基于业务数据源是否区分生产数据源和开发数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。生产数据源和开发数据源需要配置的参数相同。

        ![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0344897261/p300715.png)

        **说明：** 通常，生产数据源和开发数据源配置的连接参数不同，但Dataphin也支持配置成相同的连接参数。

        |参数|描述|
        |--|--|
        |Endpoint|MaxCompute的Endpoint，建议填写阿里云VPC网络下的Endpoint。如何获取Endpoint，请参见[Endpoint](/cn.zh-CN/准备工作/Endpoint.md)。**说明：** 如果填写阿里云VPC网络下的Endpoint，则仅支持填写与Dataphin实例在同一地域下的Endpoint。 |
        |Project Name|此处为MaxCompute项目名称，非工作空间名称。您可以登录[MaxCompute控制台](https://workbench.data.aliyun.com/#/MCEngines)，左上角切换地域后，即可在项目管理页签查看到具体的MaxCompute项目名称。 |
        |Access ID、Access Key|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成MaxCompute数据源的创建。


完成MaxCompute数据源的创建后，即可将MaxCompute的业务数据引入至Dataphin，或将Dataphin的数据写入至MaxCompute数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

