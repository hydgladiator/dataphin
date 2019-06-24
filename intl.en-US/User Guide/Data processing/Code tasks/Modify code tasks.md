# Modify code tasks {#concept_ekk_rz1_fhb .concept}

This topic describes how to modify code tasks.

1.  Choose **R&D** \> **Develop** \> **Data Processing** \> **Code Tasks** to open the corresponding page.
2.  For a code task that is created by other users, you must click **Steal Lock** before modifying the code task, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149548/156134707141510_en-US.png)

3.  You can write code, configure scheduling parameters, and view the node version. In the upper-right corner, you can steal the lock, execute code, precompile SQL statements, save files, and submit tasks. Quick reference of resources or functions is supported.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149548/156134707141511_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149548/156134707241512_en-US.png)

4.  To configure the task scheduling policy, click **Scheduling Configuration**. When the schedule mode of a code task is dry-run, the schedule does not run any scripts but marks the task status as successful.

    -   The upstream dependency is required. If no upstream dependency exists, you can enter the default virtual node \(virtual\_root\_node\_xxx\) of the tenant as the upstream dependency. The current node is required. Enter a name and click OK to add an output task node for the current node.
    -   You can set the priority of a scheduled task at the task granularity. The higher the priority, the earlier the task is submitted and run in the distributed cluster. Currently, task scheduling supports the following five levels of priority: highest priority, high priority, medium priority, low priority, and lowest priority.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149548/156134707241515_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149548/156134707241517_en-US.png)

    **Note:** 

    -   The output name must be normalized to **project name. table name** because the output name must be unique in the whole system. However, the production environment and development environment are isolate, and they verify the output names in their own environment. If the output name does not have the project name prefix, the identification of the node dependencies may be unclear, and the upstream nodes may fail to be parsed. Either of them will cause scheduling failure.
    -   All nodes have at least one upstream node. If no upstream node exists, you can set a virtual task node as the upstream node. By default, the system generates a virtual task node as the global root node, which is virtual\_root\_node.
    -   Currently, the scheduling upstream node only supports searching by node name and node ID. We recommend that you keep the node name of each upstream node consistent with the output name, and configure an output name for each node. This helps to avoid task scheduling errors from occurring. The ID of a code task node or a sync task node in the production environment is the same as that in the development environment.

