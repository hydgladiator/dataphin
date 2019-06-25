# Edit and run ad hoc query tasks {#concept_zby_svb_fhb .concept}

This topic describes how to edit and run ad hoc query tasks. To edit and run an ad hoc query task, follow these steps:

1.  Choose **R&D** \> **Develop** \> **Ad Hoc Query** to go to the Ad Hoc Query tab page.
2.  In the left-side navigation pane, select an ad hoc query task, and the Code Editor window appears. In the upper-right corner of the code editor, click **Steal Lock** to edit the SQL statements. Note that if the tasks are created by other users, you must steal the lock before editing these tasks.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149654/156134654241593_en-US.png)

    **Note:** When searching for a logical table, you need to include the business unit name prefix in the logical table name. When searching for a physical table, you need to include the name of the table's associated project in the physical table name. If you want to query data of the development environment, add **\_ Dev** followed by the project name or business name of the production environment. The system automatically generates the corresponding variables for both the business unit and project in the production environment. For example, if you have a business unit named LD\_Trade, the system automatically generates the business unit variable $\{LD\_Trade\}. This variable is replaced by LD\_Trade\_dev by default during code execution in the development environment, and LD\_Trade by default during code execution in the production environment. You can also assign a specific value to the variable when you run the code, to improve the flexibility of code execution in different environments.

3.  After the SQL code is edited, you can beautify, precompile, save, and run SQL statements by clicking the corresponding buttons in the upper-right corner.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149654/156134654241595_en-US.png)


