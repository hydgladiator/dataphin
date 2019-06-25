# Develop a dimension table {#concept_qs1_4k5_zgb .concept}

This topic describes how to define a dimension and how to develop a logical dimension table.

## Define a dimension {#section_rrr_2tz_zgb .section}

1.  Log on to Dataphin.
2.  On the Dataphin homepage, click **R&D** to go to the R&D page.
3.  Choose **Develop** \> **Standards and Modeling** \> **Dimensions**. Click the **Create File** icon.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135660/156134593140265_en-US.png)

4.  In the **Create Dimension** page, enter **Basic Dimension information** and **Dimension Logic**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135660/156134593140271_en-US.png)

    **Note:** 

    -   You can write SQL statements to define the **Primary Key Computing Logic** for a dimension.
        1.  View the example of SQL writing by clicking **Example** behind the **Primary Key Computing Logic**.
        2.  After the SQL statement is compiled, click **Code Check** behind the **Primary Key Computing Logic** to check whether the SQL statements you have compiled comply with the specifications.
    -   For more information about dimension definition, see [Create dimensions](../../../../intl.en-US/User Guide/Data modeling and development/Data standardization: Dimensions/Create dimensions.md#).
5.  After entering the dimension information, click **Save** and **Submit** icon.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135660/156134593140273_en-US.png)

6.  After a dimension is defined, a logical dimension table is generated. The generated logical dimension table name is the same as the dimension name you defined. You can choose **R&D** \> **Develop** \> **Standards and Modeling** \> **Logical Dimension Tables**, then search for the generated logical dimension table.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135660/156134593249819_en-US.png)


## Develop a logical dimension table {#section_e4z_h5z_zgb .section}

1.  On the Dataphin homepage, click **R&D** to go to the R&D page.
2.  Choose **Develop** \> **Standards and Modeling** \> **Logical Dimension Tables**. Locate the logical dimension table generated through the preceding steps. Click it to open the table configuration page. Then you can **Create Dimension Association**, **Add Attribute** and **Add Child Dimension** as needed, as shown in the following figure.

    **Note:** For more information about logical dimension tables, see [Overview](../../../../intl.en-US/User Guide/Data modeling and development/Logical tables: Logical dimension tables/Overview.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135660/156134593240279_en-US.png)

3.  Click **Add Attribute**. In the dialog box that appears, select a source table and fields, and then click**Save and Verify**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135660/156134593240280_en-US.png)

4.  After the logical dimension table is configured, click the **Save** and **Submit** icons in the upper-right corner.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/135660/156134593240281_en-US.png)


