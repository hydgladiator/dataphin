---
keyword: [实时计算, Flink引擎, 计算资源]
---

# 新建Flink计算源

Flink计算源用于承载Dataphin项目下基于Flink的计算资源（以CU为单位，含资源队列），只有绑定了Flink计算源的项目，才支持基于Flink引擎研发计算任务。本文将为您介绍如何新建Flink计算源。

-   获取Flink计算源的**Project Name**，详情请参见[Flink项目](https://help.aliyun.com/document_detail/62458.html)。
-   在[用户信息管理](https://usercenter.console.aliyun.com/)页面，获取您访问阿里云官网的**Access ID**和**Access Key**。

1.  请参见[入口介绍](/cn.zh-CN/数仓规划/概述.md)，进入数仓规划页面。

2.  在数仓**规划**页面，单击左侧导航栏的**计算源**。

3.  在**计算源**页面，单击**新增计算源**。

4.  在**新建计算源**对话框，配置参数。

    ![tst](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7697723061/p175008.png)

    |参数|描述|
    |--|--|
    |**计算类型**|选择为**FLINK**。|
    |**计算源名称**|填写计算源的名称。|
    |**计算源描述**|填写计算源的描述。|
    |**Project Name**|填写项目的英文名称。|
    |**Access ID**|填写鉴权的Access ID。|
    |**Access Key**|填写鉴权Access Key。|

    **说明：**

    -   新建实时计算源时，仅允许添加同一个RAM主账号下的Real-time Compute项目。
    -   新建实时计算源时，请尽量填写Real-time Compute项目管理员的Access Key，以保证连接无误。
    -   新建实时计算源时，请尽量不修改Real-time Compute项目的Access Key，保证元数据正常采集。
    -   计算源创建完成后，计算源类型不支持更改。
5.  单击**测试连接**，测试连接的计算源。

6.  单击**提交**，完成Flink计算源的创建。

    完成创建Flink计算源后，即可为项目绑定Flink计算源，详情请参见[创建Basic项目空间](/cn.zh-CN/数仓规划/创建项目空间/创建Basic项目空间.md)或[创建Prod和Dev项目空间](/cn.zh-CN/数仓规划/创建项目空间/创建Prod和Dev项目空间.md)。


