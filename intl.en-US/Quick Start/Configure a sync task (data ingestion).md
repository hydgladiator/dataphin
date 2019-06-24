# Configure a sync task \(data ingestion\) {#task_371710 .task}

This topic describes how to create, configure, and submit a sync task.

Data ingestion is achieved through data synchronization. Data synchronization is the process of importing data of a table in the source database to the target database. For example, importing data of table A in a MySQL database to table B in a PostgreSQL database.

1.  Log on to Dataphin.
2.  On the Dataphin homepage, click **R&D** to go to the R&D page.
3.  Choose **Develop** \> **Data Processing** \> **Sync Tasks**. Click the **Create File** icon, as shown in the following figure.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301853/156136876548016_en-US.png)


4.  In the Create File dialog box, enter the sync task **Name**, **Schedule Type**, **Description**, and **Select Directory**, then click **OK**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301853/156136876648017_en-US.png)

 

    **Note:** **Schedule Type**, you can select **Recurring Node** or **One-Time Node**. Details are as follows:

    -   **Recurring Node**: refers to a task that runs on a regular basis.
    -   **One-Time Node**: refers to a task that has no dependency and is manually triggered.
5.  In the sync task list in the left-side navigation pane, locate the created sync task and click it to open the sync task configuration page.
6.  Configure the sync task. Specify the source table, target table, and fields to be synchronized. For more information, see [Configure a sync task](../../../../intl.en-US/User Guide/Data ingestion/Sync tasks/Create sync tasks.md#section_gqr_41j_bhb).![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301853/156136876648018_en-US.png)


7.  After configuring the sync task, click **Submit** in the upper-right corner to complete the configuration and submit the sync task.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/301853/156136876648019_en-US.png)



