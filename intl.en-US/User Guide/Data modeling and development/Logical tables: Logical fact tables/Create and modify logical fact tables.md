# Create and modify logical fact tables {#concept_s3t_ccp_fhb .concept}

Logical fact tables that model a specific business process enrich the detailed information of transactions in the business process. Logical fact tables are used to extract detailed data of common transactions from business data.

**Note:** Logical fact tables extract descriptive information about transactions without the need to contain attribute information of dimensions related to the transactions. Attribute information of the dimensions are contained in logical dimension tables.

## Create a logical fact table {#section_3wa_efw_xvl .section}

1.  Choose **R&D** \> **Develop** \> **Standards and Modeling** \> **Logical Fact Tables**.
2.  You can open the dialog box for logical fact table creation by using the following four methods:
    -   Click the plus sign icon on the right of the project name. Choose **Logical Tables** \> **Logical Fact Tables**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/150112/156134675041910_en-US.png)

    -   In the upper-right corner of the left-side navigation pane, click the **Create File** icon, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/150112/156134675141911_en-US.png)

    -   Click the plus sign icon under the **Logical Fact Table** module in the guide diagram, as shown in the following figure. For more information about the guide diagram, see [Functions and usage guidelines](intl.en-US/User Guide/R&D page structure.md#section_sr2_j1k_dhb).

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/150112/156134675141917_en-US.png)

    -   In the lower part of the left-side navigation pane, click **Business Processes Object List**. On the Business Processes tab, locate the business process to model. Click **Create Logical Table** in the **Actions** column on the right of the business process.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/150112/156134675141918_en-US.png)

3.  Open the dialog box for logical fact table creation:
4.  Specify the basic information of the logical fact table as prompted.

    The basic information of a logical fact table is as follows:

    -   Business unit and project: You do not need to specify them. The system sets them by default.
    -   Business process and data domain: You must specify them.
    -   Fact table type: You must select a type. You can select **Transaction Fact Table** or **Periodic Snapshot Fact Table**.
        -   Transaction fact table: tracks and measures events in businesses, that is, business processes. For example, you can design a transaction fact table to store data used for tracking order payment events that occur in order transactions.
        -   Periodic snapshot fact table: captures the state of a measure over a specified time interval. For example, a periodic snapshot fact table can be used to track account balances and commodity inventory.
    -   Name, display name, and description:
        -   The name format is fct \_ business process \_ \[custom component\] \_ di or df. The custom component is optional.
        -   Suffix di or df: If you are creating a **transaction fact table**, the suffix is di, which indicates daily incremental data. If you are creating a **periodic snapshot fact table**, the suffix is df, which indicates daily full data.
    -   Main source table: specifies the main source table of the logical fact table. The main source table can be either a physical table or a logical table.
5.  Define the primary key of the logical fact table.
    -   If you do not set a primary key, the logical fact table does not have a primary key. In this case, you can enter a condition to filter data in the main source table. You need to enter a filter condition excluding the WHERE keyword. The filter condition is optional.
    -   If you set a primary key, the logical fact table has a primary key. In this case, you must enter primary key information and primary key computing logic.

        **Note:** 

        -   If a logical fact table has a primary key \(such as order ID\), the fields to be added later must be associated with the primary key. Specifically, in the computing logic of those fields, you need to configure the associated primary key as the keyword k, for example order\_id as k. The keyword k allows the system to identify the associated key.
        -   If a logical fact table does not have a primary key \(for example, a browsing history table\), and if a union or a join exists in the SQL computing logic of the fields to be added, ensure that the main source table is referenced in the computing logic. The records produced by the computing logic must be within the range of records in the main source table of the logic fact table.
6.  After you have performed the preceding steps, the initial status page of the logical fact table is displayed.

    There are three main sections on the page:

    -   The upper-left section includes the Table Information, Logical Table Conversion Task Settings, and Central Table Settings tabs.
        -   Configure the logical table conversion task: You can refer to the configuration for a logical dimension table. For more information, see [Manage logical table conversion task settings](intl.en-US/User Guide/Data modeling and development/Logical tables: Logical dimension tables/Manage logical table conversion task settings.md#).
        -   Configure the central table: You can refer to the configuration for a logical dimension table. For more information, see [Configure central tables](intl.en-US/User Guide/Data modeling and development/Logical tables: Logical dimension tables/Configure central tables.md#).
    -   In the middle of the Central Table section, you can create dimension associations, measures, and fact attributes.
    -   In the upper-left corner of the Central Table section, you can search for fields, show and hide fields, and view table details and the modeled business process.
7.  Configure the scheduling policy.

    The required operations are the same as those performed to configure the scheduling policy for a logical dimension table. For more information, see [Scheduling Configuration](intl.en-US/User Guide/Data modeling and development/Logical tables: Logical dimension tables/Scheduling Configuration.md#).

8.  Submit the logical fact table.

    In the upper-right corner of your designed model, click **Submit**.

    **Note:** 

    -   The function of the **Steal Lock** button are the same as the Steal Lock button on other pages.
    -   On the logical fact table edit page, you can filter fields by the status of computing logic, and define the public computing logic. You can also view the table computing logic, and configure the logical table conversion task and scheduling policy. The operations on this page are the same as those on the edit page for each logical dimension table.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/150112/156134675141942_en-US.png)

9.  Publish the logical fact table. After the logical fact table is published, the system automatically generates a logical table conversion task and periodically schedules the task.

    **Note:** To publish a logical table, you must first have the permissions of a project production account instead of a personal development account. You also need to have the permission to query the tables referenced in the computing logic of the logical table.


## Modify a logical fact table {#section_stp_nsh_rey .section}

The required operations are similar to creating a logical fact table.

