# 创建Hive数据源

创建Hive数据源用于实现Dataphin能够读取Hive的业务数据，及能够向Hive写入数据。在引入Hive的业务数据至Dataphin和将Dataphin的数据写入至Hive的场景中，您需要先创建Hive数据源。本文为您介绍如何创建Hive类型的数据源。

Hive是基于Hadoop的一个数据仓库工具，可以将结构化的数据文件映射为一张数据库表，并提供SQL查询功能。Hive用于转化HQL或SQL语句为MapReduce、Tez等程序。

![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8134248261/p301336.png)

-   Hive处理的数据存储在HDFS中。
-   Hive分析数据底层的实现是MapReduce、Tez等。
-   Hive的执行程序运行在Yarn上。

如果您使用的是Hive，在对接Dataphin进行数据开发或将Dataphin的数据写入至Hive的场景中，您需要先完成Hive数据源的创建。更多Hive信息，请参见[Hive官网](https://hive.apache.org/)。

Dataphin支持通过公网连接Hive。为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin公网环境下的IP地址段添加到数据源的白名单中。

## 使用限制

Dataphin仅支持超级管理员和项目管理员角色创建数据源。如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

## 步骤一：添加Dataphin IP地址至数据库白名单

您需要将公网环境下的Dataphin IP地址添加至数据库白名单中。

|地域|IP地址|
|--|----|
|华东2（上海）|47.102.151.182|
|华南1（深圳）|119.23.173.65|
|华北2（北京）|123.56.104.202|
|华东1（杭州）|47.96.75.100|

## 步骤二：创建Hive数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  在Dataphin首页，单击顶部菜单栏的**规划**。

3.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

4.  在**新建数据源**对话框的**大数据存储**区域，选择**Hive**。

    如果您最近使用过Hive，也可以在**最近使用**区域选择Hive。同时，您也可以在快搜索框中，输入Hive的关键词，快速筛选。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0026708261/p300871.png)

5.  在**新建Hive数据源**对话框中，配置数据源的基本信息。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0026708261/p300886.png)

    |参数|描述|
    |--|--|
    |**数据源名称**|命名规则如下：    -   只能包含字母、数字或下划线（\_）。
    -   长度不能超过64字符。 |
    |**数据源描述**|对数据源的简单描述。|
    |**数据源配置**|选择需要配置的数据源：    -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
    -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

6.  配置数据源与Dataphin的连接参数。

    当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

    ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0026708261/p300948.png)

    **说明：** 通常，生产数据源和开发数据源需要配置不同的参数值，但Dataphin也支持配置成相同的参数值。

    1.  配置**集群配置**区域的参数。

        ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0026708261/p301021.png)

        |参数|描述|
        |--|--|
        |**NameNode**|NameNode为HDFS集群中NameNode节点的HostnNme或者IP和端口。配置样例：`host=192.168.1.169,webUiPort=,ipcPort=8020`。其中，`webUiPort`和`IPCport`在CDH5环境下默认是50070和8020，您可根据实际情况填写对应的端口。 |
        |**配置文件**|用于上传Hadoop的配置文件，例如hdfs-site.xml、core-site.xml，配置文件可在Hadoop集群导出。|
        |**Kerberos**|Kerberos是一种基于对称密钥技术的身份认证协议，可以为其他服务提供身份认证功能，且支持SSO（即客户端身份认证后，可以访问多个服务，例如HBase和HDFS）。如果Hadoop集群有Kerberos认证，则需要上传Krb5认证文件或配置KDC Server地址：

        -   Krb5认证文件：需要上传Krb5文件进行Kerberos认证。
        -   KDC Server地址：KDC服务器地址，辅助完成Kerberos认证。
**说明：** 支持配置多个KDC Server服务地址，使用英文逗号（,）分割。 |

    2.  如果集群配置中开启了Kerberos，则需要配置**HDFS配置**区域的参数。

        ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0026708261/p301022.png)

        |参数|描述|
        |--|--|
        |**HDFS Keytab File**|上传keytab文件，您可以在HDFS集群中的NameNode节点使用ipa-getkeytab命令获取keytab文件。|
        |**HDFS Principal**|填写HDFS Keytab File文件对应的Kerberos认证用户名。|

    3.  配置**Hive配置**区域的参数。

        -   如果集群配置中开启了Kerberos，则配置如下参数。

            ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7296708261/p301340.png)

            |参数|描述|
            |--|--|
            |**JDBC URL**|支持配置以下两种链接地址：            -   Hive Server的链接地址，格式为`jdbc:hive://{链接地址}:{端口}/{数据库名称}`。

如果开启了Kerberos，则链接地址格式为`hiveUrl=jdbc:hive2://XXX.com:10001/default;principal=hive/XXX@XX.COM`。

            -   ZooKeeper的链接地址，格式为`jdbc:hive2://zk01:2181,zk02:2181,zk03:2181/;serviceDiscoveryMode=zooKeeper;zooKeeperNamespace=hiveserver2`。

如果开启了Kerberos，则链接地址格式为`jdbc:hive2://zk01:2181,zk02:2181,zk03:2181/;serviceDiscoveryMode=zooKeeper;zooKeeperNamespace=hiveserver2;principal=hive/XXX@XX.COM`。 |
            |**Hive Keytab File**|上传keytab文件，您可以在Hive Server上获取keytab文件。|
            |**Hive Principal**|填写Hive Keytab File文件对应的Kerberos认证用户名。|

        -   如果集群配置中关闭了Kerberos，则配置如下参数。

            ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7296708261/p301339.png)

            |参数|描述|
            |--|--|
            |**JDBC URL**|支持配置以下三种链接地址：            -   Hive Server的链接地址，格式为`jdbc:hive://{链接地址}:{端口}/{数据库名称}`。
            -   ZooKeeper的链接地址。例如`jdbc:hive2://zk01:2181,zk02:2181,zk03:2181/;serviceDiscoveryMode=zooKeeper;zooKeeperNamespace=hiveserver2`。
            -   开启Kerberos的链接地址，格式为`jdbc:hive2://{链接地址}:{端口}/{数据库名称};principal=hive/_HOST@xx.com`。 |
            |**用户名**、**密码**|填写登录Hive Server的用户名和密码。|

    4.  配置**元数据库配置**区域的参数后，单击**确定**。

        ![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7296708261/p301024.png)

        |参数|描述|
        |--|--|
        |**数据库类型**|根据集群中使用的元数据库类型，选择数据库类型。支持选择MySQL和PostgreSQL。|
        |**JDBC URL**|填写对应元数据库的链接地址：        -   MySQL：格式为`jdbc:mysql://{链接地址}[,failoverhost...]{端口}/{数据库名称} [?propertyName1][=propertyValue1][&propertyName2][=propertyValue2]...`。
        -   PostgreSQL：格式为`jdbc:postgresql://{链接地址}:{端口}/{数据库名称}`。 |
        |**用户名**、**密码**|登录元数据库的用户名和密码。|

7.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

8.  测试成功后，单击**确定**，完成Hive数据源的创建。


完成Hive数据源的创建后，即可将Hive的业务数据引入至Dataphin，或将Dataphin的数据写入至Hive数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

