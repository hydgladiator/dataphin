# Permissions {#concept_zvz_zpk_bhb .concept}

All data resources are created in a project. To ensure secure and controllable use of data, you must apply for permissions to use data tables based on field level. After approval, you can use the fields in a table.

## Apply for permissions {#section_wym_m1s_bhb .section}

1.  On the [Data asset map](intl.en-US/User Guide/Data assets/Map/Data asset map.md#) page, developers can find the required data table and view detailed metadata of this table. However, if you want to query data in the table, you must apply for permissions. To apply for permissions, click **Apply for Permissions** to open the page to request permissions, select required fields, enter a reason for the permission, and then click Submit.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136677/156134737840742_en-US.png)

2.  Dataphin can display information about the source data table during a permission request process. The information includes table types, business units, and metadata of the fields in the table. Dataphin allows you to apply for access permissions following the least permission principle. You can apply for the field-level permissions, and select different validity periods for the permissions. The validity period can be 30 days, 90 days, 180 days, 1 year, or a custom period. You can also describe the business scenario and purpose in the reason field for the permission request so that the reviewer can decide whether to grant the permission. All permissions granted to the project production account are permanent permissions.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136677/156134737840743_en-US.png)

    **Note:** When applying for permissions, you can select either of the following account types:

    -   Personal development account: This account is used by developers to log on to the system for development operations, such as data standardization and data modeling scenarios.
    -   Project production account: This account is managed by a super administrator or a project administrator. It is used to execute recurring tasks with periodic scheduling configuration. This avoids task execution failure because of an invalid personal development account.
3.  After the request is submitted, a message is displayed as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136677/156134737840744_en-US.png)


## Manage permission requests {#section_eff_k1s_bhb .section}

 **For applicants** 

1.  To view the permission requests and current approval status, choose **Permissions** \> **Submitted Requests**. For permission requests that are under review, you can click **Details** to check the request details, or click **Cancel** to cancel the request.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136677/156134737840745_en-US.png)

2.  For permission requests that are approved, you can check approved permissions by selecting **My Permissions** in the left-side navigation pane. The list shows the permissions at the data table level. Under the Actions column, you can click **Details** to view the permissions of specific fields.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136677/156134737940748_en-US.png)


 **For reviewers** 

1.  After a permission request is submitted, the system assigns the request to a project administrator to which the data table belongs at random. The administrator can review the request by choosing **Permissions** \> **My Approvals** and decide whether to approve or reject the request.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136677/156134737940751_en-US.png)

2.  If you decide to approve the request, click **Approve**, and enter approval comments in the dialog box that appears, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136677/156134737940754_en-US.png)

3.  If you decide to reject the request, click **Reject**, and enter rejection comments in the dialog box that appears, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136677/156134737940755_en-US.png)


