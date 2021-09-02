---
keyword: 计算设置
---

# 设置Dataphin实例的计算引擎

在开始使用Dataphin前，您需要完成Dataphin实例计算引擎的设置，即配置Dataphin实例的计算集群地址。在后续数据研发过程中，计算引擎用于采集、连接及管理元数据。本文为您介绍如何设置Dataphin实例的计算引擎。

当前，Dataphin计算引擎包括MaxCompute和Flink，默认支持Flink且已内置了Flink的计算集群地址。因此，在设置Dataphin实例计算引擎的过程中，您只需要配置MaxCompute的集群地址。

## 前提条件

在开始执行操作前，请确认您已开通Dataphin。如何开通Dataphin请参见[开通Dataphin](/cn.zh-CN/准备工作/开通Dataphin.md)。

## 操作步骤

1.  使用阿里云账号登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  在Dataphin产品首页，单击顶部菜单栏的**管理中心**。

4.  在**管理中心**页面，单击左侧导航栏的**计算设置**。

    ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7750550361/p314233.png)

5.  在**计算设置**页面的**MaxCompute**区域，根据Dataphin实例所在的地域，配置对应地域MaxCompute的**Endpoint**。

    MaxCompute不同地域的**Endpoint**，请参见下表。

    |地域|Endpoint|
    |--|--------|
    |华东2（上海）|`http://service.cn-shanghai.maxcompute.aliyun-inc.com/api`|
    |华北2（北京）|`http://service.cn-beijing.maxcompute.aliyun-inc.com/api`|
    |华南1（深圳）|`http://service.cn-shenzhen.maxcompute.aliyun-inc.com/api`|
    |华东1（杭州）|`http://service.cn-hangzhou.maxcompute.aliyun-inc.com/api`|

6.  单击**校验**。Dataphin会自动校验您所配置的Endpoint所属的地域是否和当前Dataphin实例在同一个地域。

7.  校验成功后，单击**确认并开始数据建设**，即可开始数据建设。


完成设置Dataphin实例的计算引擎后，您就可以准备后续数据研发过程中用于读取和写入数据的数据源、用于提供计算资源的计算源。具体操作，[准备数据源和计算源](/cn.zh-CN/准备工作/准备数据源和计算源.md)。

