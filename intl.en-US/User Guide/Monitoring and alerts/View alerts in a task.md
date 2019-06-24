# View alerts in a task {#concept_y1n_jpk_bhb .concept}

When a task of monitoring configuration triggers an alert rule, the system pushes an alert to the recipients through the specified notification method. At the same time, an alert is recorded on the **Alerts in Task** page. On this page, you can view all the recorded alerts.

## Search for and view alerts {#section_kgd_44y_bhb .section}

1.  Choose **R&D** \> **Scheduling** \> **Monitoring** \> **Alerts in Task** to open the corresponding page, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136668/156134720140775_en-US.png)

2.  At the top of the right-side workspace, you can enter keywords in the search box to search for alerts. You can also expand the filter settings under the search box to filter results. You can filter the search results by selecting the alert cause, notification method, notification status, and other options.

    **Note:** In the **Sending Status** column, the **Sent** status indicates that an alert message has been sent but no response is returned, and the **Success** status indicates that an alert message has been sent to the recipient.

3.  The following area displays the task name and ID, monitoring type, alert cause, notification method, notification status, recipient, and alert time. By default, alert records are displayed in descending order \(from latest to earliest\) according to the alert time.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136668/156134720140776_en-US.png)

    **Note:** If you have not configured a recipient or the recipient information is incorrect, the notification status of the alert is **Failed**. To check the details, you can move the pointer over the information icon next to the notification status.


## View alert details {#section_e4b_p4y_bhb .section}

In the list of alerts, click **Alert Details** under the **Actions** column to view the alert details of the task.

## Note {#section_ym0_co1_8n9 .section}

The message limits under different notification methods are as follows:

-   SMS: A maximum of 100 messages per tenant per day.
-   Emails: A maximum of 2,000 messages per tenant per day.
-   Voice messages: A maximum of 100 voice messages per tenant per day. In this case, one voice message indicates one minute.

**Note:** Currently, both configuring contact information and delivering alert notifications are not supported in the beta phase.

