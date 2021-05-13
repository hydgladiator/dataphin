---
keyword: MaxCompute数据源
---

# 新建MaxCompute数据源

本文为您介绍如何新建MaxCompute类型的数据源。

-   已获取MaxCompute的**Endpoint**。
-   已获取MaxCompute的**Project Name**。
-   在[用户信息管理](https://usercenter.console.aliyun.com/)页面，获取鉴权的**Access ID**和**AccessKey Secret**。

新建数据源的权限限制，详情请参见[数仓规划权限列表](/cn.zh-CN/权限管理/数仓规划权限列表.md)。

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  进入数仓**规划**页面。

    -   在Dataphin首页，单击顶部菜单栏的**规划**。
    -   在Dataphin首页，单击顶部菜单栏下方的**智能数仓规划**。
4.  在数仓**规划**页面，单击左侧导航栏的**数据源**。

5.  在**数据源**页面，单击右上方的**新建数据源**。

6.  在**新建数据源**对话框中，填写数据源信息。

    ![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2353036061/p93925.png)

    |参数|描述|
    |--|--|
    |**数据源类型**|选择数据源类型为**MAX\_COMPUTE**。|
    |**数据源名称**|填写数据源名称。数据源名称由汉字、数字、字母、下划线（\_）或短划线（-）组合组成。**说明：** **数据源名称**不能超过64个字符。 |
    |**数据源描述**|填写对数据源的简单描述。|
    |**数据源配置**|配置数据源：     -   如果开发模式是Basic模式，则选择**生产数据源**。
    -   如果开发模式是Dev-Prod模式，则可以通过以下方式配置数据源：
        -   单击**生产+开发数据源**，配置生产环境和开发环境的数据源。
        -   单击**生产数据源**，配置生产数据源。完成生产数据源的创建后，单击**开发数据源**，配置开发环境的数据源。

![fagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6278209951/p93912.png)

**说明：** 系统支持配置**生产数据源**和**开发数据源**为相同的数据源，也可以配置为不同的数据源。 |
    |**生产数据源**或**生产+开发数据源**|**Endpoint**|填写`http://service.cn.maxcompute.aliyun.com/api`。|
    |**Project Name**|填写DataWorks创建的MaxCompute（ODPS）项目名称。|
    |**Access ID**|访问密钥中的AccessKey ID，您可以通过[用户信息管理](https://usercenter.console.aliyun.com/)页面获取。|
    |**Access Key**|访问密钥中的AccessKey Secret，您可以通过[用户信息管理](https://usercenter.console.aliyun.com/)页面获取。|

7.  单击**测试连接**。

8.  测试成功后，单击**确定**，完成MaxCompute数据源的创建。


