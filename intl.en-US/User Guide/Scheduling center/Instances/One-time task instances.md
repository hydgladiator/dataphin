# One-time task instances {#concept_k2j_2hw_chb .concept}

This topic describes the features of the One-time Task Instances page.

## Basic information {#section_zx3_4xc_dhb .section}

1.  [Enter the Scheduling page](intl.en-US/User Guide/Scheduling center/Overview.md#section_dcr_kpw_chb), and click **One-time Task Instances** to go to the corresponding page, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134687940989_en-US.png)

2.  On the One-time Task Instances page, all one-time task instances are displayed by default in descending order of running time.
    -   In the left-side navigation pane, you can search for and display one-time task instances. In the search box of the left-side navigation pane, you can enter a node name or ID to search, and select **My Task Instances** and **Running Today** to filter the instances owned by the current user and the one-time task instances created on the current day. All one-time task instances that meet the search criteria are displayed in the descending order by running time. Each row displays the task type \(displayed as an icon\), node ID, node name, start time, end time, and elapsed time of running the task instance.
    -   Select a one-time task instance, the code and details of the one-time task instance are displayed in the right-side workspace. You can click the buttons in the workspace to manage the one-time task instances. The details of the one-time task instance are displayed at the top of the right-side workspace, including the status, ID, name, elapsed time, task type, priority, and owner of the current instance. A one-time instance supports the following operations: rerun the task instance, terminate the task instance, view operational log, view operations log, and edit task nodes.

## Rerun {#section_xqw_pxc_dhb .section}

As shown in the following figure, in the right-side workspace, click **Rerun**. In the dialog box that appears, click **OK** to rerun the current one-time task instance.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134687940993_en-US.png)

**Note:** The instance can only be rerun when the current one-time instance execution is completed \(such as in the success, failure, or not running status\). Otherwise, the **Rerun** button is unavailable.

## Terminate the running instance {#section_s1y_kvh_dhb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134687940995_en-US.png)

1.  As shown in the preceding figure, if the current one-time task instance is not completed \(such as in the initial status, waiting for resources, or running status\), you can see the **Terminate** button in the right-side workspace.
2.  Click **Terminate**, and a dialog box appears, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134688040997_en-US.png)

3.  Click **OK** to terminate the running instance. After the one-time task instance is terminated, its status is set to Failed.

## View run log {#section_mg1_hvh_dhb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134688040998_en-US.png)

As shown in the preceding figure, click **View Run Log**. On the Operational Log page that appears, you can view the detailed information of the running process, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134688041001_en-US.png)

## View operations log {#section_nyb_c13_dhb .section}

1.  As shown in the following figure, click **View Operations Log**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134688041002_en-US.png)

2.  In the Operations Log page that appears, you can view the operation history, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134688041004_en-US.png)

3.  Click **Details** of an operations log, you can view the detailed information of the operation, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134688141006_en-US.png)


## Edit nodes {#section_ibn_g13_dhb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139465/156134688141007_en-US.png)

-   In the right-side workspace, click **Edit development node** to go to the editing page of the corresponding node in the development environment.
-   Click **Edit production node** to go to the editing page of the corresponding node in the production environment.

