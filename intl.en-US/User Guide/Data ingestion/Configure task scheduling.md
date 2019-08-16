# Configure task scheduling {#concept_wjk_mmd_bhb .concept}

Scheduling configuration is a common feature for code tasks and sync tasks. Scheduling configuration is required for all tasks involved in scheduling.

1.  Open the Scheduling Configuration page, as shown in the following figure. A code task is used as an example in the figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593585940589_en-US.png)

2.  Configure parameters. Click **Parameters and Descriptions**. The system displays instructions for configuring parameters, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586040590_en-US.png)

3.  Configure parameters in the Scheduling Configuration section, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586040591_en-US.png)

    **Schedule mode** 

    -   Normal: The task is executed based on the configured recurrence pattern.
    -   Dry-run: The task is executed based on the configured recurrence pattern. However, once this task is scheduled to run, a success message is returned without executing the task.
    -   Pause Scheduling: The scheduling of the task is paused. The execution of the task is based on the configured recurrence pattern. However, once this task is scheduled to run, the system does not execute the task but directly displays a message saying that task execution failed. You can select this check box when you do not need to run the task at present but will run it later.
    **Recurrence**

    You can set Recurrence to Day, Week, Month, Hour, or Minute.

    -   Daily recurrence: Every day, a task node runs at the specified execution time after the execution of its upstream task nodes succeeds. That is, this task node is executed only after all of its upstream task nodes have run successfully and when the specified execution time arrives. The default execution time is 00:00:00, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586040595_en-US.png)

    -   Weekly recurrence: specifies the day or days of each week when the task recurs. During the days not specified, dry-run is executed, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586040599_en-US.png)

    -   Monthly recurrence: specifies the day or days of each month when the task recurs. During the days not specified, dry-run is executed, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586040600_en-US.png)

    -   Hourly recurrence: specifies a repeat interval of hours, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586140601_en-US.png)

    -   Minutely recurrence: specifies a repeat interval of minutes, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586140602_en-US.png)

    **Depend on Previous Instance**

    If **Depend on Previous Instance** is selected, the current task node is set to run after the previous instance of another node or the current node runs successfully.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586140603_en-US.png)

4.  Configure the dependencies, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586140604_en-US.png)

    1.  Configure the upstream dependencies. Specify the task nodes on which the current task node depends. The specified nodes must exist.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586140605_en-US.png)

        -   For a SQL code task node, click **Start Parsing** to automatically use the source tables referenced in the SQL script as the upstream dependencies of the current node.
        -   Alternatively, click **Create Upstream Dependency**, search for your desired node by node output name, and click **OK** to add an upstream dependency.
        **Note:** 

        -   The node output name is globally unique and different nodes must have different output names. The output name of an SQL code task node is generally the source table name.
        -   Each tenant \(enterprise\) will have a root node during initialization. The root node is a virtual node whose name starts with `virtual`.
    2.  Specify the output name of the current node. Click **Add**, enter a node output name, and click **OK**, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586140606_en-US.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136301/156593586240608_en-US.png)

        **Note:** 

        -   In [step a](#4a), you search for the upstream node by node output name. The node output name is the output information of the node.
        -   You can set multiple output names for the current task node. These output names can be specified to represent the current task node when this node is set to be the upstream node of other nodes. Use a consistent naming convention. This makes it easier for other users to find the upstream node when creating a node.

