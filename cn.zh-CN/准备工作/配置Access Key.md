# 配置Access Key {#concept_xlf_tg5_zgb .concept}

本文为您介绍Access Key的功能，以及如何配置Access Key。

## Access Key功能介绍 {#section_htr_fq2_2hb .section}

主账号需要在阿里云官网配置有效的AccessKey（建议是主账号的AccessKey），并登录Dataphin管理控制台，将AccessKey授权给Dataphin以实现如下功能：

-   获取子账号名单，便于主账号（Dataphin中唯一的超级管理员角色）搜索并添加子账号为Dataphin成员。
-   获取用户账号信息（ID、昵称），保持用户信息与RAM账号信息一致。
-   Dataphin的监控报警功能生效时，可获取账号最新联系方式，报警通知功能可以生效启用（即通过用户设定的通知渠道给对应用户发送报警信息）。公测期不支持获取联系方式，暂不支持报警消息推送。

## 配置Access Key {#section_h45_ns2_2hb .section}

1.  主账号登录[阿里云官网](https://www.aliyun.com/)后，单击右上方**控制台**，进入阿里云管理控制台页面。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/155599017441320_zh-CN.png)

2.  鼠标悬停于右上角的用户图像，选择**accesskeys**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/155599017444297_zh-CN.png)

3.  在弹出的安全提示框中，单击**继续使用AccessKey**，为主账号创建AccessKey。

    **说明：** 单击**开始使用子用户AccessKey**会跳转到创建子账号页面，可以为子账号创建AccessKey。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/155599017441322_zh-CN.png)

4.  单击**创建AccessKey**，填写校验码后，即可创建成功。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/155599017441323_zh-CN.png)

5.  主账号登录Dataphin的[管理控制台](../../../../cn.zh-CN/.md#)，单击右上方的**Access Key配置**按钮，配置或更新授权给Dataphin的Access key，如下图所示。

    **说明：** 

    -   开通Dataphin之后，主账号首次登录管理控制台，会弹出**Access Key配置**窗口，强制主账号配置Access Key。
    -   这里填写的Access Key ID和Access Key secret，就是刚刚上述步骤中创建的Access Key。
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/155599017541319_zh-CN.png)

6.  填好之后，单击**校验**，返回校验成功，然后单击**确定**即可。
7.  如需更新Access Key，单击**修改**，输入新的Access Key ID和Access Key secret，单击**校验**，返回校验成功，然后单击**确定**即可。如无需更新，可以关闭弹窗，不做更新。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/155599017544301_zh-CN.png)


