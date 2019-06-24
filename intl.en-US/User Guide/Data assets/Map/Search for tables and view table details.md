# Search for tables and view table details {#concept_kzv_ffr_bhb .concept}

This topic describes how to search for tables and view table details on the Asset Map page.

## Search for tables and view results {#section_p2w_4lq_bhb .section}

You can view the search results either by searching at the top of the Map page or by selecting a dimension under the Business Units section. The filtering conditions aggregated based on the search results are displayed in the left-side navigation pane, and the associated data tables are displayed in the right-side workspace, as shown in the following figure. The filtering conditions have the following three types: business properties, data properties, and development properties.

-   Business properties include business units, data domains, dimensions, and business processes.
-   Data properties include logical table types, such as the logical dimension table, logical fact table, and logical aggregate table.
-   Development properties include the table type and project that a table belongs to.

Select one filtering option to filter data assets and update the search results. By default, each filtering property only displays one row of filtering options, you can click the drop-down arrow to view more filtering options. To check details of a data asset, you can select the data asset in the search results and go to the details page.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136675/156134731740703_en-US.png)

## View physical tables {#section_c5w_jlr_bhb .section}

1.  View the details of a physical table.

    The table details page varies depending on the table types. On the Search Results page, select a physical table and go to the details page, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136675/156134731840711_en-US.png)

    The table type, table name, table display name, primary key, and table operations are displayed. The table operations include the following four types: apply for permissions, bookmark, export, and view SELECT statement.

    -   Table type: The table type can be one of the following four types: logical dimension table, logical fact table, logical aggregate table, and physical table. The following section uses a physical table as an example to describe how to view physical table information.
    -   Table name: The format is **business unit name.table name**. A maximum of 70 characters in length is allowed to be displayed for the name, and the excess part that exceeds 70 characters is displayed with an ellipsis.
    -   Table display name: If a table does not have a display name, this field will be displayed as blank. For example, the physical table does not have a display name and is displayed as blank.
    -   Apply for permission: After you click Apply for Permission, you will go to the Permission Request page. The current table information \(such as table type, business unit, and fields\) is automatically displayed in the permission request.
    -   View SELECT statement: After you click View SELECT Statement, the script editor is displayed, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136675/156134731840712_en-US.png)

    -   Bookmark: This operation includes the following two status:
        -   Hollow bookmark icon ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136675/156134731840713_en-US.png) indicates that the table has not been bookmarked. If you click this icon, the system displays a message indicating that the table is bookmarked.
        -   Solid bookmark icon ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136675/156134731840714_en-US.png) indicates that the table has been bookmarked, you can click this icon to remove the table from your bookmarks.
    -   Export: You can click Export to export the fields to an Excel file, which contains the field name, primary key, field type, description, and popularity of the fields.
2.  View the partition information of physical tables.

    Select the **Partition Overview** tab to view the partition information of the physical table, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136675/156134731840715_en-US.png)

3.  Select the **Data Preview** tab to view the data content, including the metric name and five data records, as shown in the following figure. If you are not authorized to execute the SELECT statements to select data from the data table, the data content is displayed as "\*\*\*" by default.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136675/156134731840716_en-US.png)

4.  Select the **Tasks** tab to view the task history of generating data tables or partitions recently. The following figure shows the task ID, execution time, start time, end time, and other information.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136675/156134731940717_en-US.png)

5.  Select the **Data Lineage** tab to view the dependencies between data tables, as shown in the following figure. Click the upstream and downstream nodes to display more information about upstream dependencies and downstream dependencies.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136675/156134731940719_en-US.png)


## View logical tables {#section_irm_klr_bhb .section}

**Note:** The following section uses a logical fact table as an example to describe how to view logical table information.

1.  View logical table information.
    -   **Logical table details** 

        The details page of logical tables is different from the details page of physical tables. By default, the details page of logical tables displays the following information: data table name, display name, icon of the table type, primary table, primary key, and filtering conditions. In the right-side pane, the following information is displayed: basic information \(such as owner, creation time, and description\), access information \(such as the number of bookmarks and visits\), physical information \(such as storage volume\), and update information \(such as DDL update time, data update time, and last access time\).

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136764/156134731940726_en-US.png)

    -   **Partition overview** 

        In a logical table, the information of field granularity is displayed. Locate a field and click **Partition Details** under **Actions** column to view the details, including partitions, number of records, creation time, and the update time of the field.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136764/156134731940728_en-US.png)

    -   **Data exploration** 

        Locate a field and click **Data Exploration** under the **Actions** column to view the fields by numerical type, the fields by numerical interval, and data preview.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136764/156134732040729_en-US.png)

2.  Select **Partition Overview** to view the distribution of all partition fields in the logical table. Filtering by fields and partitions is supported.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136764/156134732040730_en-US.png)

3.  Select **Tasks** to view the information of logical table tasks that are scheduled, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136764/156134732040732_en-US.png)


