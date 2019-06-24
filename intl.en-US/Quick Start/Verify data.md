# Verify data {#task_388590 .task}

This topic describes how to use an ad hoc query to verify that your expected data is generated.

After completing the retroactive data generation task, you can perform data verification by using the ad hoc query.

The ad hoc query module provides you with the data query function. If your computing engine is MaxCompute, MaxCompute SQL is supported in an ad hoc query. If your computing engine is Hadoop, Hive SQL is supported in an ad hoc query. The system can automatically identify the SQL syntax based on the configured computing engine.

1.  Log on to Dataphin.
2.  In the top navigation bar of the Dataphin homepage, click **R&D** to go to the R&D page.
3.  Choose **Develop** \> **Ad Hoc Query**, click the **Create File** icon.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/315007/156135835648130_en-US.png)


4.  In the **Create File** dialog box, enter the **Name**, **Description**, and **Select Directory**, then click **OK**.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/315007/156135835748131_en-US.png)


5.  Click the ad hoc query file created in the preceding step to go to Code Editor page.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/315007/156135835748127_en-US.png)


6.  Write an SQL query statement, and then click **Save**, and **Run** in the upper-right corner. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/315007/156135835748128_en-US.png)

    **Note:** When writing SQL statements, you need to note that the table format is project name.table name, such as LD\_dataphin\_public\_test\_dev.dim\_qaz.

7.  View the result returned by the ad hoc query on the **Result** tab in the lower part of the code editor.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/315007/156135835748129_en-US.png)



