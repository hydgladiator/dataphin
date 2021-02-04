---
keyword: MaxCompute计算源
---

# 新建MaxCompute计算源

MaxCompute计算源用于绑定Dataphin项目空间和MaxCompute项目，为Dataphin项目提供处理离线计算任务的计算源。如果Dataphin系统的计算引擎设置为MaxCompute，则只有项目空间添加了MaxCompute计算源，才支持规范建模、即席查询、MAXC任务、通用脚本等功能。本文为您介绍如何新建MaxCompute计算源。

已设置Dataphin计算引擎为MaxCompute，请参见[计算设置](/cn.zh-CN/全局管理/管理中心/计算设置.md)。

系统支持超级管理员和项目管理员角色的账号新建计算源。更多信息，请参见[数仓规划权限列表](/cn.zh-CN/权限管理/数仓规划权限列表.md)。

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  在数仓**规划**页面，单击左侧导航栏的**计算源**。

3.  在**计算源**页面，单击页面右上方的**新增计算源**。

4.  在**新建计算源**对话框，配置参数。

    ![test](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6697723061/p174916.png)

    |参数|描述|
    |--|--|
    |**计算源类型**|选择为**MaxCompute**。|
    |**计算源名称**|计算源名称由汉字、数字、字母、下划线（\_）或短划线（-）组合组成。|
    |**计算源描述**|填写计算源的简单描述。|
    |**Endpoint**|默认为计算引擎的Endpoint，不支持修改。|
    |**Project Name**|填写在DataWorks中创建的MaxCompute项目名称。请参见[工作空间列表]()，获取MaxCompute项目的**Project Name**。 |
    |**Access ID**、**Access Key**|填写可以访问MaxCompute项目的账号的AccessKey ID和AccessKey Secret。在[用户信息管理](https://usercenter.console.aliyun.com/)页面，获取账号的AccessKey ID和AccessKey Secret。**说明：**

    -   为了保证Dataphin项目空间与MaxCompute项目正常连接，建议填写MaxCompute项目管理员的AccessKey。
    -   为了保证元数据正常采集，请尽量不修改MaxCompute项目的AccessKey。 |

5.  单击**测试连接**，测试连接的计算源。

6.  测试成功后，单击**提交**。

    完成创建MaxCompute计算源后，即可为项目绑定MaxCompute计算源，请参见[新建项目](/cn.zh-CN/数仓规划/项目管理/新建项目.md)。


