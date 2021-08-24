---
keyword: 创建Vertica数据源
---

# 创建Vertica数据源

创建Vertica数据源用于实现Dataphin能够读取Vertica的业务数据。在引入Vertica的业务数据至Dataphin和将Dataphin的数据写入至Vertica的场景中，您需要先创建Vertica数据源。本文为您介绍如何创建Vertica类型的数据源。

Vertica是一款基于列存储架构的数据库。如果您使用的是Vertica，在对接Dataphin进行数据开发时，您需要先完成Vertica数据源的创建。更多Vertica信息，请参见[Vertica官网](https://www.vertica.com/)。

Dataphin支持通过公网连接Vertica。为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin在公网环境下的IP地址段添加到数据源的白名单中。

## 使用限制

仅支持超级管理员和项目管理员角色创建数据源。

如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

## 步骤一：添加Dataphin IP地址至数据库白名单

添加公网环境下的Dataphin IP地址至数据源白名单中。

|地域|IP地址|
|--|----|
|华东2（上海）|47.102.151.182|
|华南1（深圳）|119.23.173.65|
|华北2（北京）|123.56.104.202|
|华东1（杭州）|47.96.75.100|

## 步骤二：配置创建Vertica数据源的参数

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**关系型数据库**区域，选择**Vertica**。

    如果您最近使用过Vertica，也可以在**最近使用**区域选择Vertica。同时，您也可以在快搜索框中，输入Vertica的关键词，快速筛选。

    ![rfagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9274809261/p304893.png)

4.  在**新建Vertica数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![cagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9274809261/p304898.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![fagah](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9274809261/p304912.png)

        **说明：** 通常，生产数据源和开发数据源配置的参数值不同，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**JDBC URL**|链接地址的格式为`jdbc:vertica//{服务器地址}:{端口}/{实例名称}`。例如，`jdbc:vertica//10.0.0.1:5433/dataphin`。|
        |**Schema**|Vertica实例对应的数据库名称，例如`public`。|
        |**用户名**、**密码**|访问Vertica实例的用户名和密码。|

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成Vertica数据源的创建。


完成Vertica数据源的创建后，即可将Vertica的业务数据引入至Dataphin或将Dataphin的数据写入至Vertica。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

