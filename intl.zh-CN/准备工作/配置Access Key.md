# 配置Access Key {#concept_xlf_tg5_zgb .concept}

本文为您介绍Access Key的功能，以及如何将主账号Access Key授权给Dataphin。

## Access Key功能介绍 {#section_htr_fq2_2hb .section}

主账号需要在阿里云官网创建有效的AccessKey（建议创建主账号的AccessKey），并登录Dataphin管理控制台，将创建的AccessKey授权给Dataphin以实现如下功能：

-   获取子账号名单，便于主账号（Dataphin中唯一的超级管理员角色）搜索并添加子账号为Dataphin成员。
-   获取用户账号信息（ID、昵称），使用户信息与RAM账号信息保持一致。
-   Dataphin的监控报警功能生效时，可获取账号最新联系方式，使报警通知功能生效启用（即通过用户设定的通知渠道给对应用户发送报警信息）。

    **说明：** 公测期间不支持获取联系方式，所以暂不支持报警消息推送。


## 配置Access Key {#section_h45_ns2_2hb .section}

1.  使用主账号登录阿里云官网，单击页面右上方的用户图像，选择**accesskeys**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/156136461444297_zh-CN.png)

2.  在弹出的**安全提示**框中，选择**继续使用AccessKey**，为主账号创建AccessKey。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/156136461441322_zh-CN.png)

    **说明：** 如果选择**开始使用子用户AccessKey**会跳转至创建子账号页面，您可以为子账号创建AccessKey。

3.  单击**创建AccessKey**，填写校验码后，即可创建成功。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/156136461441323_zh-CN.png)

4.  主账号登录Dataphin管理控制台，单击**Access Key配置**，配置或更新授权给Dataphin的Access key。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/156136461441319_zh-CN.png)

    **说明：** 

    -   开通Dataphin之后，主账号首次登录管理控制台，会弹出**Access Key配置**窗口，强制主账号配置Access Key。
    -   这里填写的Access Key ID和Access Key secret，即是上述步骤中创建的主账号Access Key。
5.  Access Key填写完成后，单击**校验**。返回校验成功后，单击**确定**。
6.  如果需要更新Access Key，单击**修改**，输入新的**Access Key ID**和**Access Key Secret**，单击**校验**。返回校验成功后，单击**确定**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/156136461544301_zh-CN.png)


