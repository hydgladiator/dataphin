# Create sync tasks {#concept_ehb_lmd_bhb .concept}

This topic describes how to create and configure a sync task.

## Task creation process {#section_y3t_hz3_bhb .section}

A sync task imports data in a source table into the target table. The process of creating a sync task is as follows:

1.  [Create synchronization target tables](intl.en-US/User Guide/Data ingestion/Create synchronization target tables.md#).
2.  Create a sync task.
3.  Configure the information about the source table and target table for the sync task.

    **Note:** When configuring the target table information, you need to use the target table created in **step 1**. By default, a 0.5-core CPU and 1 GB of memory are allocated to process the sync task. Expanding resources is not supported.

4.  Save or submit the task.
    -   A one-time task can be directly saved or submitted.
    -   A recurring task can be saved or submitted only after you have configured the scheduling information.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135642840491_en-US.png)

## Create a sync task {#section_hcw_lz3_bhb .section}

1.  Choose **R&D** \> **Develop** \> **Data Processing** \> **Sync Tasks**. In the left-side navigation pane, click **Create File**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135642840498_en-US.png)

2.  In the Create File dialog box that appears, specify the task name, schedule type, and other information, and click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135642840500_en-US.png)

    **Note:** **Schedule Type**, you can select **Recurring Node** or **One-Time Node**. Details are as follows:

    -   **Recurring Node**: refers to a task that runs on a regular basis.
    -   **One-Time Node**: refers to a task that has no dependency and is manually triggered.

## Configure a sync task {#section_gqr_41j_bhb .section}

**Configuration process**

The following figure shows the process of configuring a sync task.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135642940588_en-US.png)

Both the source table and the target table can be from multiple types of data sources. The data sources are classified into the following categories:

-   Relational databases: MySQL, Vertica, Oracle, SQL Server, PostgreSQL, DRDS, and AnalyticDB
-   Alibaba Cloud's big data warehouse storage: MaxCompute
-   Open-source big data warehouse storage: Hive
-   Unstructured data storage: FTP, HDFS, and Elasticsearch
-   NoSQL data storage: HBase and MongoDB

    **Note:** When HBase is used as the source or target data storage, HBase 1.1.x and HBase 0.94.x are supported.


Shards of tables in MySQL, PostgreSQL, Oracle, SQL Server, and Vertica data storage can be used as the synchronization source.

**Procedure**

1.  Click the sync task you created and select the source data storage.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135642940549_en-US.png)

2.  Select a table in this data source. If the data source is a MySQL, PostgreSQL, SQL Server, or Oracle database, select the **Single Table** or **Multiple Tables** mode.
    -   **Single Table mode** 

        You can search for tables by table name in single-table mode. Prefix matching is supported. Select a specific source table from the matched tables in the drop-down list, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135642940551_en-US.png)

    -   **Multiple Tables mode** 
        1.  In Multiple Tables mode, multiple data tables with the same structure can be returned based on the preset rules. For example, enter all\_sales\_mysql\_data\_copy\[1-5\], as shown in the following figure.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135642940560_en-US.png)

        2.  After you enter the information, click **Confirm Match Details** on the right. Two data tables, **all\_sales\_mysql\_data\_copy1** and **all\_sales\_mysql\_data\_copy2** are returned. The system will check whether these three tables match the metadata of the source database, as shown in the following figure.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135643040561_en-US.png)

        3.  If a table is not found in the source database, the name of the table is highlighted, the **OK** button is dimmed, and field metadata information will not be loaded. If all tables are found in the source database, the **OK** button is available. After you click OK, field metadata is loaded based on the first table that is matched, as shown in the following figure.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135643040562_en-US.png)

3.  When you select a table, the fields in the table are displayed. You can delete the displayed fields. To add a field that you have deleted, click **Create Field**, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135643040563_en-US.png)

4.  Enter a partitioning field, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135643040564_en-US.png)

    **Note:** 

    -   For a partitioned table, a partitioning field is mandatory. The partitioning field format supports wildcards used in shell commands in Linux. The **asterisk \(\*\)** matches one or more occurrences of any character, including no character. The **question mark \(?\)** matches a single occurrence of any character. For example, a partitioned table is configured as month=201701,ds=20170101,/\*query\*/ month\>=201701and the partitioning field is configured as ds=$\{bizdate\}.
    -   If the data source is a MySQL, SQL Server, or PostgreSQL database, tables from these sources have no partitions. You can configure a filter condition rather than specify a partitioning field. The filter condition you enter is a WHERE clause excluding the WHERE keyword. For example, if you want to import the tables with an ID greater than 2 and a name of Dataphin, you need to set the filter condition to id\>2 and name="Dataphin".
5.  Configure the target table.
    1.  Select a data source, table, conflict resolution policy \(Append Data or Overwrite Data\), and partitioning fields. Select the fields to be synchronized.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135643140567_en-US.png)

    2.  Adjust field matching. If the field names on both sides are the same, they will be matched by default. If the field names on both sides are different, you need to adjust them manually. Delete the fields that are not matched. Move the pointer over the blank area of the field list. From the displayed field list, select a field that can match the field on the other side, as shown in the following figure.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135643140581_en-US.png)

6.  Configure the synchronization limits. To adjust the number of concurrent tasks and errors allowed, you can configure the parameters in the **Sync Limits** section. In most cases, you do not need to configure the synchronization limits. You can retain the default values, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135643140584_en-US.png)

    -   Speed Limit: specifies the data transfer rate during synchronization. The default value is 1 MB/s. The system will try to reach this transfer rate, but the system will not exceed this rate. The configured rate affects resource scheduling. The higher the rate, the more resources are used to execute a task.
    -   Concurrent Tasks: specifies the number of concurrent data extraction tasks.
    -   Error Threshold: specifies how many errors are allowed in the synchronization process before the sync task is stopped. The default value is 0, indicating that no errors are allowed.
7.  [Configure task scheduling](intl.en-US/User Guide/Data ingestion/Sync tasks/Configure task scheduling.md#).
8.  Save and submit the task, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136299/156135643140587_en-US.png)


