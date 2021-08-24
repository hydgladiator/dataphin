---
keyword: 创建RocketMQ数据源
---

# 创建RocketMQ数据源

创建RocketMQ数据源用于实现Dataphin能够读取RocketMQ的业务数据。在引入RocketMQ的业务数据至Dataphin中进行数据开发的场景中，您需要先创建RocketMQ数据源。本文为您介绍如何创建RocketMQ数据源。

RocketMQ即阿里云消息队列RocketMQ版，如果您使用的是阿里云消息队列RocketMQ版，在对接Dataphin进行数据开发时，您需要先完成RocketMQ数据源的创建。更多阿里云消息队列RocketMQ版信息，请参见[什么是消息队列RocketMQ版？]()。

Dataphin支持通过公网或VPC网络连接RocketMQ。Dataphin连接RocketMQ时，可以选择RocketMQ在VPC网络或公网环境下对应的Endpoint。通常，VPC网络较公网稳定，建议您选择VPC网络连通Dataphin和RocketMQ。

## 使用限制

-   仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   当您使用VPC网络连接Dataphin与RocketMQ时，仅支持连接与Dataphin实例在同一地域的RocketMQ。

## 操作步骤

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**消息队列**区域，选择**RocketMQ**。

    如果您最近使用过RocketMQ，也可以在**最近使用**区域选择RocketMQ。同时，您也可以在快搜索框中，输入RocketMQ的关键词，快速筛选。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2310858261/p302801.png)

4.  在**新建RocketMQ数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9966658261/p302700.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2310858261/p302856.png)

        **说明：** 通常，生产数据源和开发数据源需要配置成不同的参数值，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**Endpoint**|RocketMQ实例的Endpoint。您可以在[消息队列RocketMQ版控制台](https://ons.console.aliyun.com)的**实例详情**页面，查看Endpoint。![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2310858261/p302882.png)

建议您选择TCP协议客户端接入点下内网访问对应的Endpoint。**说明：** 当RocketMQ实例与Dataphin实例在同一地域时，才可以使用内网访问对应的Endpoint。 |
        |**Instance ID**|RocketMQ实例的ID。您可以在[消息队列RocketMQ版控制台](https://ons.console.aliyun.com)的**实例详情**页面，查看实例ID。![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2310858261/p302871.png) |
        |**Access ID**、**Access Key**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|

        **说明：** 创建RocketMQ数据源时不支持测试数据源是否可以和Dataphin进行正常的连通，因此需要您确保连接信息的正确性。

5.  单击**确定**，完成RocketMQ数据源的创建。


完成RocketMQ数据源的创建后，即可基于RocketMQ的业务数据开发流批一体任务。具体操作，请参见[创建Flink SQL任务](/cn.zh-CN/数据开发/数据处理/新建FLINK任务/新建Flink_SQL任务.md)、[步骤一：创建并调试Flink Template SQL计算任务](/cn.zh-CN/数据开发/数据处理/新建FLINK任务/新建Flink_Template_SQL计算任务.md)、[创建Flink DataStream计算任务](/cn.zh-CN/数据开发/数据处理/新建FLINK任务/新建Flink_DataStream计算任务.md)。

