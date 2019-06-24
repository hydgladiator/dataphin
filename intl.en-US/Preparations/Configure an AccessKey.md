# Configure an AccessKey {#concept_xlf_tg5_zgb .concept}

This topic describes the functions of AccessKeys and how to configure an AccessKey.

## Functions of AccessKeys {#section_htr_fq2_2hb .section}

You need to log on to the Alibaba Cloud official website by using your Alibaba Cloud account and configure a valid AccessKey. We recommend that you configure an AccessKey for your Alibaba Cloud account. Go to the Dataphin console and authorize the AccessKey to Dataphin. The AccessKey allows Dataphin to perform the following operations:

-   Dataphin can obtain the RAM user list. This allows you to use your Alibaba Cloud account to search for and add RAM users as members in the Dataphin console. Your Alibaba Cloud account is the only super administrator in Dataphin.
-   Dataphin can obtain the latest user account information saved in the RAM system, such as usernames and display names. If the super administrator finds changes in RAM user information, the super administrator can synchronize the account system of Dataphin with RAM. This synchronization is to ensure consistency of account information between the two systems.
-   When the monitoring and alerting service is available in Dataphin, Dataphin can obtain the latest contact information of the configured alert contacts. Then Dataphin can support alert notifications. An alert notification indicates that alert information is sent to alert contacts through the specified notification channels. In the beta phase, Dataphin cannot obtain the latest contact information, and alert notification is not supported.

## Configure an AccessKey {#section_h45_ns2_2hb .section}

1.  Log on to the Alibaba Cloud official website by using your Alibaba Cloud account. Go to the **management console**.
2.  Move the pointer over your profile picture and select **accesskeys**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/156136806544297_en-US.png)

3.  In the dialog box that appears, click **Continue to manage AccessKey** to create an AccessKey for your Alibaba Cloud account.

    **Note:** If you click **Get Started with Sub User's AccessKey**, you will be redirected to a page where you can create AccessKeys for RAM user accounts.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/156136806541322_en-US.png)

4.  Click **Create AccessKey**. In the dialog box that appears, enter your verification code. Then, an AccessKey is created.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135653/156136806541323_en-US.png)

5.  Log on to Dataphin console by using your Alibaba Cloud account. In the upper-right corner of the Dataphin workspace, click **Configure AccessKey** to configure or update the AccessKey authorized to Dataphin.

    **Note:** 

    -   After Dataphin is activated, the system displays the **Configure AccessKey** dialog box when you log on to your Alibaba Cloud account for the first time. You must first configure an AccessKey before continuing.
    -   In the Configure AccessKey dialog box, you need to enter the AccessKey ID and AccessKey Secret that form the AccessKey you created in the preceding steps.
6.  Click **Verify**. If the system displays a message indicating that the verification is passed, click **OK**.
7.  If you want to update the AccessKey, click **Change**. In the dialog box that appears, enter the new AccessKey ID and AccessKey Secret, and click **Verify**. If the system displays a message indicating that the verification is passed, click **OK**. If no update is required, you can close the dialog box without updating the AccessKey.

