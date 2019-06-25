# Create code tasks {#concept_jrr_hq1_fhb .concept}

Code tasks consist of various data development tasks. The type of code tasks supported varies by computing engine configuration. The MaxCompute computing engine supports the following types of code tasks: MaxCompute SQL, MaxCompute MapReduce, MaxCompute Spark, Shell, and Python. If the configured MaxCompute computing engine supports Spark, Spark tasks can be run as expected. For more information, see [Limits](../../../../intl.en-US/Product Introduction/Limits.md#).

**Note:** You need to set the IP whitelist for each project on the project management page. The security of the project is guaranteed by limiting access resources of the corresponding IP addresses when running a task or scheduling a task.

## Create a code task {#section_iw3_2x1_fhb .section}

1.  Choose **R&D** \> **Develop** \> **Data Processing** \> **Code Tasks** to open the corresponding page.
2.  In the left-side navigation pane, click the plus sign icon in the upper-right corner to create a folder and code task. After you click the plus sign and select a code task type, a dialog box appears. In the dialog box that appears, you can move the code task or folder to another directory.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149468/156134680541508_en-US.png)

    Note:

    -   The Python version is 2.7. The built-in library can be obtained by running the following command: pip list. You can set the memory size up to 8 GB for Shell and Python tasks.
    -   By default, a 0.5-core CPU and 1 GB of memory are allocated to process each Shell or Python task.
    -   To set a resource size and referenced resource \(such as the DataX script\) for a Shell task or a Python task, you can add the content similar to the following before the original code:

        ``` {#codeblock_pz6_3p4_ngu}
        @required_resource{required_memory=2Gb;required_cpus=1.0} @resource_reference{"myDataXJob.json"}
        python $DATAX_HOME/bin/datax.py --jvm '-Xms2g -Xmx2g' myDataXJob.json                    
        ```

        Note: Use -- jvm '-Xms2g -Xmx2g' to specify the actual JVM memory size when DataX is running. We recommend that you set the JVM memory size to the same value of memory size specified in `required_memory` of required\_resource to make full use of the requested resources.

    -   To ensure that a Spark task runs as expected, add the following content before the original code:

        ``` {#codeblock_7hx_fhb_w7l}
        --conf
        spark.hadoop.odps.task.major.version=cupid_v2
        --conf
        spark.hadoop.odps.end.point=http://service.cn.maxcompute.aliyun.com/api
        --conf
        spark.hadoop.odps.runtime.end.point=http://service.cn.maxcompute.aliyun-inc.com/api
        --deploy-mode cluster                    
        ```

    -   When searching for a logical table, you need to include the business unit name prefix in the logical table name. When searching for a physical table, you need to include the name of the table's associated project in the physical table name. If you want to query the development environment data, add **\_ dev** followed by the project name or business name of the production environment. The system automatically generates the corresponding variables for both the business unit and project in production environment. For example, if you have a business unit named LD\_Trade, the system automatically generates the business unit variable $\{LD\_Trade\}. This variable is replaced by LD\_Trade\_dev by default during code execution in the development environment, and LD\_Trade by default during code execution in the production environment. You can also assign a specific value to the variable when you run the code, to improve the flexibility of code execution in different environments.
3.  In the code task creation dialog box, enter a task name, scheduling type, description, and other information. Then, click **OK** to complete task creation.

    **Note:** 

    -   The task name must be unique in the system.
    -   There are two schedule types: recurring node schedule and one-time node schedule. Recurring nodes are run on a specified schedule, and one-time nodes are triggered by clicking Run in the code editor.
    -   In dual-environment mode, when the data processing objects in the development environment are published to the production environment, the production environment does not save folder information. To avoid publishing failures because of duplicate object names in the production environment, ensure that the object does not have the same name in the project corresponding to the production environment.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149468/156134680541509_en-US.png)


