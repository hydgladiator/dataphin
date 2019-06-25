# Recurring task instances {#concept_rxd_xj5_chb .concept}

This topic describes the features of the Recurring Task Instances page.

## Basic information {#section_b35_djc_dhb .section}

1.  [Enter the Scheduling page](intl.en-US/User Guide/Scheduling center/Overview.md#section_dcr_kpw_chb), and click **Recurring Task Instances** to go to the corresponding page, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139460/156134687040945_en-US.png)

2.  On the Recurring Task Instances page, all task instances are displayed by default in descending order of task ID.
    -   In the left-side navigation pane, you can search for and display recurring task instances.
    -   In the right-side workspace, you can see the DAG, with the selected instance being the central node and both upstream and downstream instance nodes at the first level. In the upper-right corner of the right-side workspace, you can click **Refresh** to view the latest relationships between the instance nodes. In the search box, you can also enter an instance node ID or name to locate the instance node in the DAG. At the bottom of the right-side workspace, you can use the toolbar to zoom in or out of the entire DAG, display the DAG in full-screen mode, and set the layers of DAG to be displayed by default. You can also drag the instance to adjust the location of the DAG. After you select a node, the detailed information of the node is displayed in the lower-right corner of the DAG.

## Search and filter recurring task instances {#section_a3s_gtc_dhb .section}

-   **Standard search and filter** 

    In the search box at the top of the left-side navigation pane, you can enter a node name or ID to search for instances. You can also select **My Task Instances**, **Task Instances with Errors**, and **Incomplete Task Instances** to filter the instances owned by the current user, instances with errors, and incomplete instances. When you search for a recurring task instance, an instance node ID is an exact match keyword, while an instance node name is an approximate match keyword. By default, the date-based timestamp of business data for search is **Yesterday**. You can also select **2 Days Ago**, **All**, or click a date to select the corresponding date to filter the search results. The task instances are grouped by instance types and displayed on the **Code & Sync Task Instances** page and **Logical Table Conversion Task Instances** tab pages. The instances are sorted in descending order of instance node ID.

-   **Advanced search and filter** 

    Click the funnel icon on the left side of the search box, an advanced search box appears, as shown in the following figure. You can filter search results based on instance owners and instance statuses.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139460/156134687140948_en-US.png)


## Right-click menus {#section_tqn_4vc_dhb .section}

As shown in the following figure, right-click a recurring task instance in the DAG to display all the supported operations. Depending on your permissions, parts of the following operations are displayed: show parent nodes and child nodes, view operational log, view node script, edit nodes, view operations log, terminate instance running, rerun and resume scheduling, rerun downstream node instances, set the instance to succeeded and resume scheduling, remove upstream dependency, force rerun, pause the instance running, and other operations.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139460/156134687140950_en-US.png)

