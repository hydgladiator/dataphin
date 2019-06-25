# Add task monitoring configuration {#concept_g4c_hpk_bhb .concept}

Task monitoring is configured to monitor the running status of tasks that are published to the production environment. This helps you know the tasks status in real time. To manage task monitoring and alerts, you need to switch to the production environment in the R&D workbench.

1.  Choose **R&D** \> **Scheduling** \> **Monitoring** \> **Task Monitoring Configuration** to open the configuration page of task monitoring.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136665/156134690440767_en-US.png)
2.  Click **Add Task Monitoring** in the upper-right corner, and a dialog box appears, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136665/156134690440771_en-US.png)

3.  Set configuration items for task monitoring.
    -   Select task: You can select one or more tasks in the drop-down list for monitoring.
    -   Alert cause: You can select the following four options: Error, Complete, Incomplete until a certain time point, and Timeout with specifying a value of specific minutes.
    -   Recipient: You can set a task owner as an alert recipient, or you can select up to three recipients from the drop-down list as custom recipients.
    -   Notification method: Currently, only emails and SMS are supported.
4.  After completing the preceding settings, click **OK**.

    **Note:** Currently, both configuring contact information and delivering alert notifications are not supported in the beta phase.


