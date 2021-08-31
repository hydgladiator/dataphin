# 同步RAM用户账号至Dataphin

在添加其他人员共同使用Dataphin前，您需要将其他人员使用的RAM用户账号同步至Dataphin中。本文为您介绍阿里云账号如何通过配置AccessKey同步RAM用户账号至Dataphin中。

在开始执行操作前，请确认您已具备以下条件：

-   完成阿里云账号及其访问密钥AccessKey的创建。具体操作，请参见[准备阿里云账号](/cn.zh-CN/准备工作/准备账号/准备阿里云账号.md)。
-   完成阿里云账号下RAM用户的创建。具体操作，请参见[t1845130.md\#](/cn.zh-CN/准备工作/准备账号/创建RAM用户.md)。

1.  使用阿里云账号登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台首页，单击**Access Key配置**。

    ![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3517755261/p292024.png)

3.  在**AccessKey配置**对话框，单击**修改**后，按照操作提示配置需要同步至Dataphin的RAM用户账号所属的阿里云账号信息，包括**主账号名称**、**AccessKey ID**和**AccessKey Secret**。

    您可以在[AccessKey](https://ram.console.aliyun.com/manage/ak)页面，获取**AccessKey ID**和**AccessKey Secret**；在[账号中心](https://account.console.aliyun.com/v2/#/basic-info/index)页面，查看阿里云账号名称。

4.  单击**校验**。

5.  返回校验成功后，单击**确定**。

    完成配置AccessKey后，您可以在下图的**添加成员**对话框的**成员名**下拉列表中查看RAM用户账号。

    ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8910600361/p313021.png)


同步阿里云账号下的RAM用户至Dataphin后，需要先添加RAM用户为Dataphin成员，再将该RAM用户添加至Dataphin的项目空间进行研发数据。如何添加RAM用户为Dataphin成员，请参见[添加成员](/cn.zh-CN/全局管理/管理中心/成员管理.md)。

