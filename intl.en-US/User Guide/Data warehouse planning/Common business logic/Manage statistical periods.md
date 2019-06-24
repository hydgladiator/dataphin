# Manage statistical periods {#concept_gyr_pss_2hb .concept}

This topic describes how to create, modify, or delete statistical periods.

Common business logic is used to define global concepts to ensure the consistent definition and use of these concepts throughout the Dataphin system. Currently, you can only define statistical periods as common business logic. For example, you can define seven days before today, 30 days before today, calendar week, or calendar year as a statistical period.

## Create statistical periods {#section_l97_wgs_95v .section}

**Note:** 

-   After you set the computation configuration on the **Management Center** \> **Computing Engine Configuration** page, the Dataphin system automatically initializes the built-in statistical periods.
-   You can only create statistical periods after you have completed configuration of the computing engine on the **Computing Engine Configuration** page. For more information, see [Set the computation configuration](intl.en-US/User Guide/Management Center/Set the computation configuration.md#).
-   Project administrators and the super administrator can define the frequently referenced statistical periods on the Statistical Periods tab.

1.  Log on to the Dataphin.
2.  In the top navigation bar of the Dataphin homepage, choose **Planning**. Alternatively, you can go to the Planning page from the **Intelligent Data Warehouse Planning** quick access area.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/148397/156134886841387_en-US.png)

3.  In the left-side navigation pane, choose **Common Business Logic**. Click **Create Statistical Period** on the right side of the page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149032/156134886841421_en-US.png)

    **Note:** In Common Business Logic page, you can view a list of statistical periods that can be used in all projects. The list displays information including the statistical period display name, alias, description, expression, creation details, and update information.

4.  In the dialog box that appears, enter the required information, including a statistical period display name, alias, description, expressions, and parameters, then click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149032/156134886841422_en-US.png)

    **Note:** 

    -   In **Expression Parameter Description**, the functions provided are only used to configure statistical periods. You cannot use the functions to write SQL code for big data computation.
    -   When specifying the **Start Time** and the **End Time**, you need to comply with the rules in **Expression Parameter Description**.
    -   You cannot create the same statistical period multiple times. If you create a statistical period that already exists and click **OK**, the system displays an error message: The statistical period already exists.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149032/156134886841424_en-US.png)

5.  When all checks based on verification rules \(naming rules and time definition rules\) are passed, click **OK** to complete the creation. A message is displayed, indicating that the creation is successful, and you can find the created statistical period in the list.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149032/156134886841425_en-US.png)

6.  You can reference this statistical period when creating a derived metric on the **R&D** \> **Develop** \> **Standards and Modeling** \> **Derived Metrics** page. For more information, see [Create derived metrics](intl.en-US/User Guide/Data modeling and development/Data standardization: Derived metrics/Create derived metrics.md#).

## Modify and delete statistical periods {#section_jxs_a6y_ai1 .section}

-   The user who creates a statistical period and the super administrator can modify and delete the statistical period.
-   A project administrator cannot modify or delete the statistical periods created by other administrators. Users who are not an administrator can only view statistical periods.
-   A statistical period that a derived metric references can only be modified but cannot be deleted. For example, if the statistical period of a published derived metric is 150 days before today, the statistical period can only be modified but cannot be deleted. If no dependency is specified, the statistical period can be deleted.

