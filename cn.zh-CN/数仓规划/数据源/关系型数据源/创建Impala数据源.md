# 创建Impala数据源

创建TImpala数据源用于实现Dataphin能够将数据写入至Impala中。在将Dataphin的数据写入至Impala的场景中，您需要先创建Impala数据源。本文为您介绍如何创建Impala类型的数据源。

Impala是用于处理存储在Hadoop集群中大量数据的SQL查询引擎。如果您使用的是Impala，在导出Dataphin数据至Impala，您需要先完成Impala数据源的创建。更多Impala信息，请参见[Impala官网](http://impala.apache.org/)。

Dataphin支持通过公网连接Impala。为避免因数据源白名单限制导致数据对接访问失败，您需将Dataphin在公网环境下的IP地址段添加到数据源的白名单中。

## 使用限制

-   仅支持超级管理员和项目管理员角色创建数据源。

    如何添加项目成员并授予项目管理员角色，请参见[添加项目成员](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

-   仅支持创建1.x、2.x、3.x版本的Impala数据源。

## 步骤一：添加Dataphin IP地址至数据库白名单

添加公网环境下的Dataphin IP地址至数据源白名单中。

|地域|IP地址|
|--|----|
|华东2（上海）|47.102.151.182|
|华南1（深圳）|119.23.173.65|
|华北2（北京）|123.56.104.202|
|华东1（杭州）|47.96.75.100|

## 步骤二：创建Impala数据源

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  按照下图指引，进入**新建数据源**页面。

    ![gaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0323766261/p296046.png)

3.  在**新建数据源**对话框的**关系型数据库**区域，选择**Impala**。

    如果您最近使用过Impala，也可以在**最近使用**区域选择Impala。同时，您也可以在快搜索框中，输入Impala的关键词，快速筛选。

    ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/6075089261/p305230.png)

4.  在**新建Impala数据源**对话框中，配置连接数据源参数后，单击**确定**。

    1.  配置数据源的基本信息。

        ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/6075089261/p305232.png)

        |参数|描述|
        |--|--|
        |**数据源名称**|命名规则如下：        -   只能包含字母、数字或下划线（\_）。
        -   长度不能超过64字符。 |
        |**版本**|仅支持选择1.x、2.x、3.x版本。|
        |**数据源描述**|对数据源的简单描述。|
        |**数据源配置**|选择需要配置的数据源：        -   如果业务数据源区分生产数据源和开发数据源，则选择**生产+开发数据源**。
        -   如果业务数据源不区分生产数据源和开发数据源，则选择**生产数据源**。 |

    2.  配置数据源与Dataphin的连接参数。

        当上述步骤中选择了**生产+开发数据源**，则配置页面如下图所示。如果上述步骤中您选择了**生产数据源**，则仅展示生产数据源的配置页面。

        ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5075089261/p305280.png)

        **说明：** 通常，生产数据源和开发数据源配置的参数值不同，但Dataphin也支持配置成相同的参数值。

        |参数|描述|
        |--|--|
        |**JDBC URL**|链接地址的格式为`jdbc:impala//{服务器地址}:{端口}/{实例名称}`。例如，`jdbc:impala//10.0.0.1:5433/dataphin`。|
        |**Kerberos**|Kerberos是一种基于对称密钥技术的身份认证协议：        -   Hadoop集群有Kerberos认证，则需要开启**Kerberos**。
        -   Hadoop集群没有Kerberos认证，则无需开启**Kerberos**。 |
        |**Krb5文件**/**KDC Server**、**Keytab File**、**Principal**|开启**Kerberos**后，需要配置参数如下：        -   **Krb5文件**/**KDC Server**：需要上传包含Kerberos认证域名的Krb5文件、配置KDC服务器地址，辅助完成Kerberos认证。

**说明：** 支持配置多个KDC Server服务地址，使用英文逗号（,）分割。

        -   **Keytab File**：上传登录Krb5文件域名或KDC服务器地址的账号和密码的文件。
        -   **Principal**：配置Keytab File文件对应的Kerberos认证用户名。 |
        |**用户名**、**密码**|如果您没有开启**Kerberos**，则需要配置访问Impala实例的用户名和密码。|

    3.  配置数据源元数据库参数。

        ![gaaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/6075089261/p305283.png)

        |参数|描述|
        |--|--|
        |**数据库类型**|根据集群中使用的元数据库类型，选择数据库类型。Dataphin支持选择MySQL和PostgreSQL。|
        |**JDBC URL**|填写对应元数据库的链接地址：        -   MySQL：格式为`jdbc:mysql://{链接地址}[,failoverhost...]{端口}/{数据库名称} [?propertyName1][=propertyValue1][&propertyName2][=propertyValue2]...`。
        -   PostgreSQL：格式为`jdbc:postgresql://{链接地址}:{端口}/{数据库名称}`。 |
        |**用户名**、**密码**|填写登录元数据库的用户名和密码。|

5.  单击**测试连接**，测试数据源是否可以和Dataphin进行正常的连通。

    如果连接测试失败，您可以根据网络连通常见问题进行排查。详细内容，请参见[网络连通的常见问题]()。

6.  测试成功后，单击**确定**，完成Vertica数据源的创建。


完成Impala数据源的创建后，即可将Impala的业务数据引入至Dataphin或将Dataphin的数据写入至Impala。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

