# Unpublish or delete dimensions {#concept_qzb_nyv_fhb .concept}

This topic describes how to unpublish and delete a dimension.

Unpublishing and deleting a dimension mainly changes the current status of the dimension.

1.  Choose **R&D** \> **Develop** \> **Standards and Modeling** \> **Dimensions**.
2.  You can unpublish or delete a dimension by using the following three methods.
    -   In the dimension list in the left-side navigation pane, move the pointer over the dimension you want to unpublish or delete. Click the More ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149433/156134671141498_en-US.png) icon and select Unpublish or Delete.
    -   In the dimension list in the left-side navigation pane, click the dimension you want to unpublish or delete. The View Attributes tab appears in the right-side navigation pane to show the dimension attributes. On the View Attributes tab, click the More ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149421/156134671141484_en-US.png) icon and select Unpublish or Delete.
    -   On the Dimensions Object List page, locate the dimension you want to unpublish or delete. Click the More ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149421/156134671141484_en-US.png) icon in the Actions column on the right of the dimension.
3.  Select **Unpublish** or **Delete**. You must submit and publish the operations if you want the operations to take effect in the production environment. For more information about how to publish the operations, see [Publish](intl.en-US/User Guide/Manage publishing/Publish.md#).

    **Note:** 

    -   When a dimension is unpublished, the corresponding logical dimension table is deleted from the production environment to ensure that the corresponding logical dimension table is unavailable in the production environment.
    -   Before you unpublish or delete a dimension, you need to ensure that its corresponding logical dimension table is not referenced. You must check that the dimension is not associated with any other logical dimension tables and has no child dimensions.

