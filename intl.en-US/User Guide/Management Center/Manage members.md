# Manage members {#concept_bc1_sbd_bhb .concept}

The super administrator can manage the members in the system and control their access permissions. On the Members Management page, you can view each member's username and display name and the time when each member is added to the Dataphin system. Only the super administrator can add and delete members. All users are allowed to trigger account system synchronization when they need to refresh account information.

## View and add members {#section_pkz_ccd_bhb .section}

1.  Log on to the Dataphin console as a super administrator.
2.  Choose **Management Center** \> **Members Management**. On the page that appears, you can view member information including username, display name, and the time each member is added to the system, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136281/156134648840434_en-US.png)

    **Note:** The super administrator account is your enterprise's Alibaba Cloud account. The display name of the Alibaba Cloud account is set by using the Dataphin console. We recommend that you use your Alibaba Cloud account name as the display name. This ensures that the display name is unique and your account is secure. On the member list page, by clicking the upward arrow or downward arrow next to Username, you can sort the members in ascending or descending alphabetical order by account name. By clicking the upward arrow or downward arrow next to Added At, you can sort the members in ascending or descending order of the time when each member is added.

3.  Click **Add Members**, select a username, and click **OK**, as shown in the following figure.

    **Note:** To authorize Dataphin to retrieve the list of RAM users under your Alibaba Cloud account, you need to log on to your Alibaba Cloud account and configure a valid AccessKey in the Dataphin console. Then, you can use your Alibaba Cloud account to search for RAM users in the Dataphin console and add these RAM users as members of the Dataphin system. For more information, see [Configure an AccessKey](../../../../intl.en-US/Preparations/Configure an AccessKey.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136281/156134648840449_en-US.png)


## Delete members {#section_bt2_2cd_bhb .section}

Select the members you want to delete and click **Delete** \> **OK**. By deleting a member on this page, the corresponding RAM user will not be deleted from the RAM system. To stop the RAM user from using Dataphin, you need to delete the user in the RAM console so that the user cannot log on to Dataphin.

## Synchronize account systems {#section_yqp_2cd_bhb .section}

If user information is updated in RAM, click **Account System Synchronization** to synchronize the user information displayed in Dataphin with RAM. To synchronize account information, your Alibaba Cloud account needs to configure a valid AccessKey in the Dataphin console.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136281/156134648840450_en-US.png)

