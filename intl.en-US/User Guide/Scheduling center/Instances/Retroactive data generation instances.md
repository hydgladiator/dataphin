# Retroactive data generation instances {#concept_djz_2hw_chb .concept}

This topic describes the features of the Retroactive Data Generation Instances page.

## Basic information {#section_c4g_3f3_dhb .section}

1.  [Enter the Scheduling page](intl.en-US/User Guide/Scheduling center/Overview.md#section_dcr_kpw_chb), and click **Retroactive Data Generation Instances** to go to the corresponding page, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139466/156134716841014_en-US.png)

2.  On the Retroactive Data Generation Instances page, the retroactive data generation instances that are run today are displayed by default, and listed in descending order of execution time.
    -   In the left-side navigation pane, you can search for and display retroactive data generation instances.
    -   In the right-side workspace, you can see the DAG, with the selected instance being the central node, and both upstream and downstream instance nodes at the first level. In the upper-right corner, you can click **Refresh** to view the relationships between the most recent instance nodes. In the search box, you can also enter a node ID or name to locate the instance node in the DAG. A toolbar is displayed at the bottom of the right-side workspace, you can use it to zoom in or zoom out of the entire DAG, set the default layers, or display the DAG in full-screen mode. You can also drag the instance to adjust the location of the DAG. In the lower-right corner of the DAG, the details of the selected instance are displayed.

## Search and filter retroactive data generation instances {#section_arr_zf3_dhb .section}

-   **Standard search and filter** 

    In the left-side navigation pane, you can enter the node name, node ID, or retroactive data generation instance name in the search box to search for instances. You can also select **My Task Instances** and **Created By Me** to quickly filter your retroactive data generation instances. By default, the running date of the retroactive data generation instances is today. You can modify the filtering conditions of the running date and date-based timestamp of business data to view the corresponding retroactive data generation instances. The instances are sorted in descending order of generation time. Note that the display of the search results between the retroactive data generation instances and recurring task instances are different. The retroactive data generation instances are displayed in three levels: the first level is the retroactive data generation task level, the second level is the date-based timestamp of business data level, and the third level is the retroactive data generation instance level.

-   **Advanced search and filter** 

    Click the funnel icon on the left side of the search box, an advanced search box appears, as shown in the following figure. You can filter search results based on instance owners and the instance status.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/139466/156134716841016_en-US.png)


## Right-click menus {#section_lwr_3f3_dhb .section}

The right-click menus of the retroactive data generation instances are similar to the right-click menus of recurring instances. For more information, see [Recurring task instances](intl.en-US/User Guide/Scheduling center/Instances/Recurring task instances.md#).

