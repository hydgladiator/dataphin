# Configure central tables {#concept_185588 .concept}

This topic describes how to configure a logical dimension table and view the table computing logic.

1.  [Go to the logical table editing page](intl.en-US/User Guide/Data modeling and development/Logical tables: Logical dimension tables/Configure logical models and tables.md#section_ysx_sb3_fhb), and select **Central Table Settings** tab in the page to open the central table configuration page.
2.  On the central table configuration page, you can modify attributes, modify model relationships, add attributes, add associated dimensions, and define public computing logic.

    **Define public computing logic**: SQL segments that can be used in multiple logical tables can be defined as a **public computing logic**. This ensures that the same data processing logic is reused in an easy and convenient way to achieve the effect of temporary or intermediate tables.

3.  Click the ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/159794/156134673144653_en-US.png) icon next to the logical dimension table name, you can view the table computing logic and compare the current code with the published code of the logical dimension table.

**Note:** 

-   The system automatically generates the corresponding variables for the business unit and project that are in the production environment. For example, if you have a business unit named LD\_Trade, the system automatically generates the business unit variable $\{LD\_Trade\}. This variable is replaced by LD\_Trade\_dev by default during execution in the development environment, and LD\_Trade by default during execution in the production environment. You can also set a fixed value for the business unit name or project name during execution to improve the flexibility of code execution in different environments.
-   When modifying a logical table, we recommend that you select a table in the production environment \(if a production environment exists\) as the source table. We recommend that you either use the variables of projects or business units or the table of the production environment for the namespace prefix of the table name in the code. This ensures that data in the development environment is not referenced during publishing the logical table to the production environment, which guarantees the data accuracy.

