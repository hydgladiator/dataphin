---
keyword: 创建Kafka数据源
---

# 创建Kafka数据源

创建Kafka数据源用于实现Dataphin能够读取Kafka的业务数据，及能够向Kafka写入数据。在引入Kafka的业务数据至Dataphin和将Dataphin的数据写入至Kafka的场景中，您需要先创建Kafka数据源。本文为您介绍如何创建Kafka数据源。

Kafka是一种消息队列，用于处理实时数据。Dataphin支持对接Kafka09、Kafka010、Kafka011。如果您使用的是Kafka，在对接Dataphin进行数据开发或将Dataphin的数据导出至Kafka，您需要先完成Kafka数据源的创建。Kafka不同版本的功能介绍，请参见官方文档：

-   [Kafka09](https://kafka.apache.org/090/documentation.html?spm=a2c4g.11186623.2.13.98fc7ceblM1zIF#newconsumerconfigs)
-   [Kafka010](https://kafka.apache.org/0100/documentation.html?spm=a2c4g.11186623.2.14.98fc7ceblM1zIF#newconsumerconfigs)
-   [Kafka011](https://kafka.apache.org/0110/documentation.html?spm=a2c4g.11186623.2.15.98fc7ceblM1zIF#consumerconfigs)

Dataphin支持通过公网连接Kafka。为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin公网环境下的IP地址段添加到数据源的白名单中。

## 使用限制

Dataphin仅支持超级管理员和项目管理员角色创建数据源。

如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

## 步骤一：添加Dataphin IP地址至Kafka白名单

您需要将公网环境下的Dataphin IP地址添加至至Kafka访问白名单中。

|地域|IP地址|
|--|----|
|华东2（上海）|47.102.151.182|
|华南1（深圳）|119.23.173.65|
|华北2（北京）|123.56.104.202|
|华东1（杭州）|47.96.75.100|

## 步骤二：创建Kafka数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**消息队列**区域，选择**Kafka**。

    如果您最近使用过Kafka，也可以在**最近使用**区域选择Kafka。同时，您也可以在快搜索框中，输入Kafka的关键词，快速筛选。

    ![fagfag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8966658261/p302699.png)

4.  在**新建Kafka数据源**对话框中，配置连接数据源参数后，单击**确定**。

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

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。生产数据源和开发数据源需要配置的参数相同。

        ![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3439349261/p302701.png)

        **说明：** 通常，生产数据源和开发数据源配置的连接参数不同，但Dataphin也支持配置成相同的连接参数。

        |参数|描述|
        |--|--|
        |Kafka集群地址|配置格式`{ip/domain name}:{port}`，如果需要配置多个节点的地址使用英文逗号（,）隔开。配置样例`192.0.2.0:9092,192.0.2.1:9092,192.0.2.2:9092`。

Dataphin支持对接Kafka09、Kafka010、Kafka011，如何配置不同版本的Kafka集群地址，请参见官方文档：

        -   [Kafka09](https://kafka.apache.org/090/documentation.html?spm=a2c4g.11186623.2.13.98fc7ceblM1zIF#newconsumerconfigs)
        -   [Kafka010](https://kafka.apache.org/0100/documentation.html?spm=a2c4g.11186623.2.14.98fc7ceblM1zIF#newconsumerconfigs)
        -   [Kafka011](https://kafka.apache.org/0110/documentation.html?spm=a2c4g.11186623.2.15.98fc7ceblM1zIF#consumerconfigs) |

        **说明：** 创建Kafka数据源时不支持测试数据源是否可以和Dataphin进行正常的连通，因此需要您确保连接信息的正确性。

5.  单击**确定**，完成Kafka数据源的创建。


完成Kafka数据源的创建后，即可基于Kafka的业务数据开发流批一体任务。具体操作，请参见[创建Flink SQL任务](/cn.zh-CN/数据开发/数据处理/新建FLINK任务/新建Flink_SQL任务.md)、[步骤一：创建并调试Flink Template SQL计算任务](/cn.zh-CN/数据开发/数据处理/新建FLINK任务/新建Flink_Template_SQL计算任务.md)、[创建Flink DataStream计算任务](/cn.zh-CN/数据开发/数据处理/新建FLINK任务/新建Flink_DataStream计算任务.md)。

