# Configure logical models and tables {#concept_t5b_4b3_fhb .concept}

One logical dimension table corresponds to one dimension. A logical dimension table stores dimension attributes that describe facts. After a dimension is published, the system automatically creates a logical dimension table. You can view the model information, add attributes, add dimension association, add child dimensions, and configure logical table conversion.The core objective of configuring logical dimension tables is to configure the relevant attribute information for the logical dimension tables.

**Note:** 

-   Logical dimension tables extract the relative persistence dimension attributes without requiring redundant information of fields that are not associated with dimensions.
-   You do not need to define the same attribute fields that are in the published parent dimension for the child dimension.

## Go to the logical table editing page {#section_ysx_sb3_fhb .section}

1.  As shown in the following figure, in the left-side navigation pane, move the pointer over the navigation submenus and choose **Logical Tables** \> **Logical Dimension Tables**. Click a logical table to open the logical table editing page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149732/156594391441615_en-US.png)

2.  The logical table editing page consists of the following areas:
    -   On the top of the right-side workspace, you can view table information and configure scheduling information.
    -   In the upper-right corner of the right-side workspace, you can save, submit, and perform other operations.
    -   In the middle of the right-side workspace, you can view model information such as logical table details, associated dimensions, and associated child dimensions.

## Model information {#section_m44_5d3_fhb .section}

The model information includes the table name, field list, and relationships with other logical tables. As shown in the following figure, you can quickly add attributes, associated dimensions, and child dimensions. You can also select the **Central Table Settings** tab to modify the relevant content. You can perform the following steps:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149732/156594391441617_en-US.png)

1.  Add attributes

    Click **Add Attribute** to open the Create Attribute dialog box. You can add attributes by selecting the **Import Fields** or **Customize Fields** mode. If you select the **Import Fields** mode, the computing logic is automatically created. You can modify the computing logic as required.

    If you want to add a field that requires a complex computing logic to the logical table, select the Customize Fields mode to add the field through a custom SQL statement. Use **as k** to identify the association key and set other fields as the attributes by default. For more information about the sample code, click **Example**. To ensure that the submission is successful, you can click **Code Check** to check whether the SQL syntax is correct.

2.  Create dimension association \(build star schema or snowflake schema\)

    Click **Create Dimension Association**, select the associated dimension and attribute fields, and then edit the dimension role information to complete the dimension association.

3.  Add child dimensions

    Click **Add Child Dimension** to create a dimension. The system automatically binds the parent dimension and child dimensions during this process. After the dimension creation is submitted and published, the child dimension is added to the model.


## Table information {#section_6m0_w59_okd .section}

On the logical table editing page, select the **Table Information** tab. In the window that appears on the right side of the page, table details are displayed.

