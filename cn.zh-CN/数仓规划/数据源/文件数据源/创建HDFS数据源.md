---
keyword: 创建HDFS数据源
---

# 创建HDFS数据源

创建HDFS数据源用于实现Dataphin能够读取HDFS的业务数据，及能够向HDFS写入数据。在引入HDFS的业务数据至Dataphin和将Dataphin的数据写入至HDFS的场景中，您需要先创建HDFS数据源。本文为您介绍如何创建HDFS类型的数据源。

HDFS集群由NameNode和DataNode构成master-worker（主从）模式：

-   NameNode用于构建命名空间，管理文件的元数据等。
-   DataNode用于存储数据，及处理数据块的读写。

![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/6601658261/p302328.png)

如果您使用的是HDFS，在对接Dataphin进行数据开发或将Dataphin的数据写入至HDFS的场景中，您需要先完成HDFS数据源的创建。更多HDFS信息，请参见[HDFS官方介绍](http://hadoop.apache.org/docs/r1.2.1/hdfs_design.html)。

Dataphin支持通过公网连接HDFS。为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin公网环境下的IP地址段添加到数据源的白名单中。

## 使用限制

-   Dataphin仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   目前，HDFS数据源不支持通过VPC网络连通Dataphin实例。

## 步骤一：添加Dataphin IP地址至HDFS访问白名单

您需要将公网环境下的Dataphin IP地址添加至至HDFS访问白名单中。

|地域|IP地址|
|--|----|
|华东2（上海）|47.102.151.182|
|华南1（深圳）|119.23.173.65|
|华北2（北京）|123.56.104.202|
|华东1（杭州）|47.96.75.100|

## 步骤二：创建HDFS数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**文件**区域，选择**HDFS**。

    如果您最近使用过HDFS，也可以在**最近使用**区域选择HDFS。同时，您也可以在快搜索框中，输入HDFS的关键词，快速筛选。

    ![faa](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/6601658261/p302325.png)

4.  在**新建HDFS数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/6601658261/p302326.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![fagA](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/6601658261/p302327.png)

        **说明：** 通常，生产数据源和开发数据源需要配置不同的参数值，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**NameNode**|NameNode为HDFS集群中NameNode节点的HostName或者IP和端口。配置样例：`host=192.168.1.169,webUiPort=,ipcPort=8020`。其中，`webUiPort`和`IPCport`在CDH5环境下默认是50070和8020，您可根据实际情况填写对应的端口。 |
        |**配置文件**|用于上传Hadoop的配置文件，例如hdfs-site.xml、core-site.xml，配置文件可在Hadoop集群导出。|
        |**Access ID**、**Access Key**|当前账号的AccessKey ID和AccessKey Secret。如何获取，请参见[获取AccessKey]()。|
        |**Kerberos**|Kerberos是一种基于对称密钥技术的身份认证协议。如果Hadoop集群有Kerberos认证，则需要开启Kerberos认证，并上传用户的Krb5认证文件或配置KDC Server地址、Keytab File和Principal：

        -   **Krb5文件**：上传Krb5文件进行Kerberos认证。
        -   **KDC Server**：KDC服务器地址，辅助完成Kerberos认证。
        -   **Keytab File**：上传keytab文件，您可以在HDFS Server上获取keytab文件。
        -   **Principal**：填写HDFS Keytab File文件对应的Kerberos认证用户名。
**说明：** 支持配置多个KDC Server服务地址，使用英文逗号（,）分割。 |

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成HDFS数据源的创建。


完成HDFS数据源的创建后，即可将HDFS的业务数据引入至Dataphin，或将Dataphin的数据写入至HDFS数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

