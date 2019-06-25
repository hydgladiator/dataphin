# Logical table task instances {#concept_wng_3hw_chb .concept}

This topic describes the features of the Logical Table Instances page.

## Basic information {#section_zfs_mjj_dhb .section}

1.  [Enter the Scheduling page](intl.en-US/User Guide/Scheduling center/Overview.md#section_dcr_kpw_chb), and click **Logical Table Task Instances** to go to the corresponding page, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139468/156134689841032_en-US.png)

2.  On the Logical Table Task Instances page, the layout is as follows:
    -   In the left-side navigation pane, you can search for and display logical table instances and node instances of logical table conversion tasks.
        -   In the top of the left-side navigation pane, you can enter a logical table name, conversion task node name, or node ID in the search box to search for the corresponding instances. When you search for a logical table instance, a node ID is an exact match keyword, whereas a node name and logical table name are approximate match keywords. By default, the business data timestamp for filtering logical table task instances is yesterday. You can also select **2 Days Ago**, **All** or **a specific date** to filter the search results.
        -   The search results are displayed in two layers. The first layer displays logical tables, and the second layer displays the nodes of the logical tables. By default, the node type \(displayed as an icon\), node ID, and node name are displayed. All logical tables are listed in alphabetical order.
        -   Move the pointer over a logical table node instance, and the **View Fields** icon is displayed. Click the icon to expand the details, you can view the fields contained in the node, as shown in the following figure.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139468/156134689941039_en-US.png)

    -   In the right-side workspace, you can see all node instances of the logical table and their status, such as running, succeeded, and failed. In the lower-left corner of the workspace, a thumbnail of the node instance is displayed.
        -   In the upper-left corner, the name of the current logical table is displayed, you can click the double arrow icon next to it to view the corresponding instances or tasks.
        -   In the upper-right corner, you can click **Refresh** to view the latest relationships between nodes. In the search box, you can also enter a node name or field name to locate the node in the directed acyclic graph \(DAG\).
        -   A toolbar is displayed at the bottom of the right-side workspace, you can use it to zoom in or zoom out of the entire DAG or display the DAG in full-screen mode.
        -   You can also drag the DAG to adjust its location. Click a node in the DAG, the detailed information of the node is displayed in the lower-right corner.

## Right-click menus {#section_cg2_kmj_dhb .section}

Right-click a logical table instance in the DAG, all supported operations are displayed, as shown in the following figure. With permissions, you can perform operations such as view operational logs, view node scripts, rerun and resume scheduling, view recurring tasks, and view instances.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139468/156134689941041_en-US.png)

