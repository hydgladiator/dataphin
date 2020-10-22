---
keyword: [Dataphin数据源, 开发Dataphin数据源]
---

# 开发Dataphin数据源

数据服务平台支持将逻辑表和物理表配置为供应用调用的Dataphin数据源。本文为您介绍如何新建Dataphin数据源。

Dataphin数据源支持根据应用的业务场景进行二次开发，为您提供了安全稳定、低成本、易上手的数据开放共享服务。

1.  使用业务应用用户或超级管理员角色的账号，登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  进入**Dataphin数据源**页面。

    1.  在Dataphin首页，单击**服务**，进入数据**服务**页面。

    2.  在顶部菜单栏，单击**平台管理**。

    3.  在左侧导航栏，单击**Dataphin数据源**。

4.  在**Dataphin数据源**页面，单击页面右上角的**新建数据源**。

5.  根据**新建Dataphin数据源**页面提示，配置参数。

    ![faga](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6911987951/p85631.png)

    |区域|参数|描述|
    |--|--|--|
    |数据源基本信息|数据源名称|填写数据源的名称。|
    |数据源描述|填写对数据源简单的描述。|
    |逻辑表选择|未选逻辑表|展示您具有权限的逻辑表。您可以选择表后单击![fafa](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6911987951/p85842.png)图标，同步到已选逻辑表区域。|
    |已选逻辑表|展示已选择的逻辑表。您可以选择表后单击![faga](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6911987951/p85845.png)图标，同步到未选逻辑表区域。|
    |物理表选择|未选物理表|展示您具有权限的物理表。您可以选择表后单击![fafa](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6911987951/p85842.png)图标，同步到已选择物理表区域。|
    |已选物理表|展示已选择的物理表。您可以选择表后单击![faga](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6911987951/p85845.png)图标，同步到未选物理表区域。|
    |计算空间选择|请选择数据运算所在项目空间|选择数据运算所在的Dataphin项目空间。|

6.  完成参数配置后，单击**确定**，完成Dataphin数据源的创建。Dataphin数据源新建成功的同时，也将该数据源发布到Dataphin数据源列表中，供应用调用。

    您也可以对已有的数据源执行如下操作。

    |操作|描述|
    |--|--|
    |编辑|单击**操作**列下的![faga](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6911987951/p85510.png)图标，编辑数据源。|
    |删除|单击**操作**列下的![gaga](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6911987951/p85543.png)图标，删除数据源。|


