---
keyword: Aliyun\_Hbase数据源
---

# 新建Aliyun\_Hbase数据源

本文为您介绍如何新建Aliyun\_Hbase类型的数据源。

-   已获取业务数据源内置Apache ZooKeeper的Quorum的连接地址。
-   已获取业务数据源的EndPoint地址。
-   已获取业务数据源的**用户名**和**密码**。

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  进入数仓**规划**页面。

    -   在Dataphin首页，单击顶部菜单栏的**规划**。
    -   在Dataphin首页，单击顶部菜单栏下方的**智能数仓规划**。
4.  在数仓**规划**页面，单击左侧导航栏的**数据源**。

5.  在**数据源**页面，单击右上方的**新建数据源**。

6.  在**新建数据源**对话框中，填写数据源信息。

    ![faga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8971530161/p211974.png)

    |参数|描述|
    |--|--|
    |**数据源类型**|选择**ALIYUN\_HBASE**。|
    |**数据源名称**|填写数据源名称。|
    |**数据源描述**|填写对数据源简单的描述。|
    |**数据源配置**|选择新建数据源所属的项目：     -   如果您的开发模式是Basic模式，则新建数据源时选择**生产数据源**。
    -   如果您的开发模式是Dev-Prod模式，则可以通过两种方式新建数据源：
        -   单击**生产数据源**，完成生产数据源的配置后，单击**开发数据源**添加开发环境的数据源。

![fagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6278209951/p93912.png)

        -   单击**生产+开发数据源**，完成生产环境和开发环境的数据源创建。 |
    |**服务类型**|可选择**STANDARD**和**ENHANCED**：     -   如果**服务类型**选择**STANDARD**，还需要配置**版本**和**zkQuorum**。
    -   如果**服务类型**选择**ENHANCED**，还需配置**endPoint**、**用户名**、**密码**。 |

7.  数据源信息填写完成后，单击**测试连接**。

8.  测试成功后，单击**确定**，完成Aliyun\_Hbase数据源的创建。


