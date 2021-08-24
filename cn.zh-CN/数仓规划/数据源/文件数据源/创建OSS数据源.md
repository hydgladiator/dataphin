---
keyword: 创建OSS数据源
---

# 创建OSS数据源

创建OSS数据源用于实现Dataphin能够读取OSS的业务数据，及能够向OSS写入数据。在引入OSS的业务数据至Dataphin和将Dataphin的数据写入至OSS的场景中，您需要先创建OSS数据源。本文为您介绍如何创建OSS类型的数据源。

OSS即阿里云对象存储OSS。如果您使用的是阿里云对象存储OSS，在对接Dataphin进行数据开发或将Dataphin的数据写入至OSS时，您需要先完成OSS数据源的创建。更多OSS信息，请参见[什么是对象存储OSS](/cn.zh-CN/产品简介/什么是对象存储OSS.md)。

Dataphin支持通过VPC网络和公网连接OSS。Dataphin连接OSS时，可以选择OSS在VPC网络或公网环境下对应的Endpoint，OSS的Endpoint请参见[访问域名和数据中心](/cn.zh-CN/开发指南/访问域名（Endpoint）/访问域名和数据中心.md)。通常，VPC网络较公网稳定，建议您选择VPC网络连通Dataphin和OSS。

## 使用限制

Dataphin仅支持超级管理员和项目管理员角色创建数据源。

如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

## 操作步骤

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**文件**区域，选择**OSS**。

    如果您最近使用过OSS，也可以在**最近使用**区域选择OSS。同时，您也可以在快搜索框中，输入OSS的关键词，快速筛选。

    ![cagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8027658261/p302691.png)

4.  在**新建OSS数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8027658261/p302692.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。生产数据源和开发数据源需要配置的参数相同。

        ![fafa](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7945089261/p302693.png)

        **说明：** 通常，生产数据源和开发数据源配置的连接参数不同，但Dataphin也支持配置成相同的连接参数。

        |参数|描述|
        |--|--|
        |**Endpoint**|OSS所在地域对应的Endpoint，格式为`http://{oss-Region}.aliyuncs.com`，其中Region为Bucket所在地域。例如，华东1（杭州）的Endpoint填写为`https://oss-cn-hangzhou.aliyuncs.com` OSS服务的Endpoint和区域有关。访问不同的区域时，需要填写不同的域名。 |
        |**Bucket**|OSS所在地域对应的Bucket信息。用于存储对象的容器。在[Bucket 列表](https://oss.console.aliyun.com/bucket)页面，获取OSS所在地域对应的Bucket。您可以创建一个或多个存储空间，每个存储空间可添加一个或多个文件。您可以在数据同步任务中查找此处输入的存储空间中相应的文件，没有添加的存储空间，则不能查找其中的文件。 |
        |**Access ID**、**Access Key**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成OSS数据源的创建。


完成OSS数据源的创建后，即可将OSS的业务数据引入至Dataphin，或将Dataphin的数据写入至OSS数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

