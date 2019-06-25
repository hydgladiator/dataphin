# Modify business unit parameters {#task_610732 .task}

This topic describes how to modify business unit parameters.

1.  Log on to Dataphin as a super administrator. 

    **Note:** Only the super administrator can modify the business unit parameters.

2.  In the top navigation bar of the Dataphin homepage, choose **Planning**. Alternatively, you can go to the planning page from the **Intelligent Data Warehouse Planning** quick access area.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/148397/156134660841387_en-US.png)


3.  In the left-side navigation pane, choose **Business Units**. Click a business unit, you can view its **Business Unit Parameters** on the right side of the business unit, as shown in figure below. 

    **Note:** **Business Unit Parameters** is a common and unified parameter information in the business unit, including the default format and value assignment of parameters. The details are as follows:

    -   Time partition: You need to set a display name and default value for the time-based partitioning field. The time-based partitioning field you have configured here is set as the default time-based partitioning field of logical tables.
    -   Business date: You need to set a default value for the bizdate data timestamp parameter that is used during task scheduling.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/492611/156134660849121_en-US.png)

4.  Modify the business unit parameters. 
    -   Click **Change** on the right of Time partition. In the dialog box that appears, modify the display name, name, data type, default value, or description, then click **OK**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/492611/156134660849126_en-US.png)

        **Note:** When logical tables exist in the business unit, you cannot modify the **Name** and **Data Type** of the time partition.

    -   Click **Change** on the right of Business data. In the dialog box that appears, modify the **Parameter value**, then click **OK**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/492611/156134660849128_en-US.png)


