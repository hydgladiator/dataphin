---
keyword: MaxCompute数据源
---

# 新建MaxCompute数据源

新建MaxCompute数据源用于连通MaxCompute数据源与Dataphin实例。如果业务数据来源于MaxCompute数据源，则在您开始基于Dataphin开发数据前，需要新建MaxCompute数据源。本文为您介绍如何新建MaxCompute数据源。

系统支持超级管理员和项目管理员角色的账号新建数据源。更多信息，请参见[数仓规划权限列表](/cn.zh-CN/权限管理/数仓规划权限列表.md)。

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  在数仓**规划**页面，单击左侧导航栏的**数据源**。

3.  在**数据源**页面，单击右上方的**新建数据源**。

4.  在**新建数据源**对话框的**大数据存储**区域，选择**MaxCompute**。

    ![gaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1129918061/p201855.png)

    如果您最近使用过MaxCompute，也可以在**最近使用**区域选择MaxCompute。同时，您也可以在快搜索框中，输入MaxCompute的关键词，快速筛选。

5.  在**新建数据源**对话框中，填写数据源信息。

    ![gagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1129918061/p201863.png)

    |参数|描述|
    |--|--|
    |**数据源名称**|填写数据源名称。数据源名称由汉字、数字、字母、下划线（\_）或短划线（-）组合组成。**说明：** **数据源名称**不能超过64个字符。 |
    |**数据源描述**|填写对数据源的简单描述。|
    |**数据源配置**|配置数据源：     -   如果开发模式是Basic模式，则选择**生产数据源**。
    -   如果开发模式是Dev-Prod模式，则可以通过以下方式配置数据源：
        -   单击**生产+开发数据源**，配置生产环境和开发环境的数据源。
        -   单击**生产数据源**，配置生产数据源。完成生产数据源的创建后，单击**开发数据源**，配置开发环境的数据源。

![fagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6278209951/p93912.png)

**说明：** 系统支持配置**生产数据源**和**开发数据源**为相同的数据源，也可以配置为不同的数据源。 |
    |**生产数据源**或**生产+开发数据源**|**Endpoint**|默认为计算引擎的Endpoint，不支持修改。|
    |**Project Name**|填写在DataWorks中创建的MaxCompute项目名称。请参见[工作空间列表]()，获取MaxCompute项目的**Project Name**。 |
    |**Access ID**、**Access Key**|填写可以访问MaxCompute项目的账号的AccessKey ID和AccessKey Secret。在[用户信息管理](https://usercenter.console.aliyun.com/)页面，获取账号的AccessKey ID和AccessKey Secret。**说明：**

    -   为了保证Dataphin项目空间与MaxCompute项目正常连接，建议填写MaxCompute项目管理员的AccessKey。
    -   为了保证元数据正常采集，请尽量不修改MaxCompute项目的AccessKey。 |

6.  单击**测试连接**。

7.  测试成功后，单击**确定**，完成MaxCompute数据源的创建。

    完成MaxCompute数据源的创建后，即可使用MaxCompute的业务数据开发数据。


