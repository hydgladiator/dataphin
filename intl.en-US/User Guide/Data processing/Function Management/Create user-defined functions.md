# Create user-defined functions {#concept_x3f_bhb_fhb .concept}

Function management refers to managing SQL functions used in code development. These functions includes those supported by the computing engine source by default, built-in functions provided by the system, and user-defined functions. Built-in functions are only for viewing and cannot be edited. Depending on the computing type, the system automatically provides built-in Hive functions for the Hadoop computing engine or built-in MaxCompute functions for the MaxCompute computing engine. The namespace of Hadoop Hive UDFs is global, and the namespace of MaxCompute UDFs is project.

To create a user-defined function, follow these steps:

1.  Choose **R&D** \> **Develop** \> **Data Processing** \> **Function Management** to open the Function Management page.
2.  Create a function. You can open the function creation page by clicking one of the three icons in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149561/156134682741534_en-US.png)

3.  Click one of the icons to open the function creation dialog box. In the dialog box that appears, enter the required information. The name must be unique, and each parameter must comply with the specifications of the computing engine. The resource file referenced by a function must be created before you create a function. For more information, see [Create resources](intl.en-US/User Guide/Data processing/Resource Management/Create resources.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149561/156134682741535_en-US.png)

4.  Click **Submit**. Then, you can go to the **Ad Hoc Query** tab page to test whether the function is as expected. For more information about ad hoc queries, see [Overview](intl.en-US/User Guide/Ad hoc query/Overview.md#).

