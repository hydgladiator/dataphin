# Create dimensions {#concept_twk_xz1_fhb .concept}

This topic describes what dimensions are, how to go to the Dimensions page and create a dimension, and the four types of dimensions.

## Overview {#section_otp_gpv_fhb .section}

A dimension is a statistical object. It is an entity that actually exists. It is not created because of the occurrence of any event. By creating a dimension, you can standardize your business entities \(or master data\) during architectural design to ensure their uniqueness.

To enter the Dimensions page, choose **R&D** \> **Develop** \> **Standards and Modeling** \> **Dimensions**, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149551/156134670041571_en-US.png)

## Create a dimension {#section_plp_rzb_fhb .section}

1.  You can open the dimension creation page by using the following four methods:
    -   Click the plus sign icon on the right of the project name. Choose **Data Standardization** \> **Dimensions**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149551/156134670041513_en-US.png)

    -   In the upper-right corner of the left-side navigation pane, click the **Create File** icon, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149551/156134670141884_en-US.png)

    -   Click the plus sign icon under the Dimensions module in the guide diagram, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149551/156134670141885_en-US.png)

    -   In the lower part of the left-side navigation pane, click **Dimensions Object List**. On the **Dimensions** tab, click **Create Dimension**, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149551/156134670141516_en-US.png)

2.  Open the dimension creation page, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149551/156134670141518_en-US.png)

3.  Configure the basic dimension settings and dimension logic information.
    -   Basic information: Enter the required information as prompted.
    -   Logic information: The logic information is used to describe and define the scope of the dimension to ensure that the dimension is accurate and unique when you add dimension attributes later. The required configurations vary by dimension type.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149551/156134670141522_en-US.png)

        -   **Common dimension:** Enter the primary key information as prompted. Note that to create a dimension by adding additional attributes to an existing dimension, you must specify the existing dimension as the parent dimension. Select Yes for Parent Dimension, and then enter a parent dimension name. After the created dimension is published, it is automatically associated with the parent dimension.
        -   **Common dimension \(hierarchy\):** Dataphin supports the creation of hierarchical dimensions. For example, in terms of the **category** dimension, your business analysis may be performed based on a category hierarchy. The hierarchy consists of several levels: **level 1 category**, **level 2 category**, and **leaf category**. A stable hierarchical relationship exists between dimension levels. The businesses' database uses a table to record the parent-child category relationship. You can define the level information and logic information based on the parent-child category relationship table to create all levels of a dimension. This ensures the stability of hierarchical relationships, that is, you cannot delete a specific level. You can only update the number of levels and hierarchical relationships based on the configuration template for common dimensions \(hierarchy\). After a common dimension \(hierarchy\) is published, the system automatically generates a set of logical dimension tables with hierarchical associations. For more information about logical dimension tables, see [Overview](intl.en-US/User Guide/Data modeling and development/Logical tables: Logical dimension tables/Overview.md#).
        -   **Enumeration dimension:** Dataphin supports the definition of enumeration dimension. Apart from existing business objects, the perspectives of analysis may also include enumerated values. For example, data is analyzed by gender, age group, and education level. You can define enumerated objects by specifying **code,value** pairs.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149551/156134670241541_en-US.png)

        -   **Virtual dimension:** This dimension allows you to perform standardized business modeling. Modeling is performed regardless of whether your dimension objects are not business entities and whose data scope is not fixed. For example, the **visitor** dimension does not have the corresponding business entity, and no fixed and unique source tables exist to help define a stable data scope for the visitor dimension. Dataphin defines such a dimension as a virtual dimension. You can define a primary key that has no specific computing logic to identify virtual dimension objects.

