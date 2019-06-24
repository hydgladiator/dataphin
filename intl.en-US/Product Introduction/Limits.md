# Limits {#concept_av1_vrt_zgb .concept}

This topic describes the limits on using Dataphin.

To ensure stable running of Dataphin, observe the following limits or recommendations.

|Operation|Limit/Recommendation|
|---------|--------------------|
|Management Center: manage members| -   A super administrator is a role that is automatically generated through system initialization after you purchase Dataphin. Your Alibaba Cloud account is assigned to the super administrator role by default. A Dataphin system has only one super administrator. The super administrator has all permissions on the system.
-   In the Alibaba Cloud RAM account system, to update the user list and user information, perform the following steps:
    1.  Log on to the [Dataphin console](../../../../intl.en-US/User Guide/Navigate the console/Dataphin console.md#) as the super administrator. Configure a valid AccessKey to authorize Dataphin to retrieve the RAM user list from the RAM system.
    2.  Trigger an account system synchronization to obtain the list of RAM users under the Alibaba Cloud account. Then, add RAM users as members of Dataphin.

 |
|Management Center: set the computing engine configuration| -   The super administrator can only update the global configuration for computing engines when no computing engines have been added to the system.
-   If your computing engine type is MaxCompute, we recommend that you set the endpoint to http://service.cn.maxcompute.aliyun-inc.com/api. If you need to use the data distilling service, we recommend that you contact MaxCompute Customer Support Service. This is to confirm that the region of your data center supports the endpoint of Spark. The data distilling service is not available in the beta version.

 |
|Computing engine type: select a computing engine type|You need to purchase MaxCompute resources before adding computing engines. The Dataphin system uses the resources to support data construction. -   Select a computing engine type and configure the cluster where your computing engine is located. For example, you need to set the endpoint of the cluster. MaxCompute is the only type of computing engine that is currently available. The system uses MaxCompute to support data construction. Select the computing engine type and configure the computing engine settings based on your computing engine cluster.
-   If you want to run Spark tasks on MaxCompute for computing, contact the MaxCompute Product Team to check whether the Spark service is activated in the region where your MaxCompute computing engine is deployed. If the Spark service is not active, your Spark tasks will not run.
-   We recommend that you only use Dataphin to build and manage data to avoid metadata and permission errors.

 |
|Data source management: add data sources| -   We recommend that you set an AccessKey with administrative privileges for data source management. You can configure an AccessKey for your Alibaba Cloud account or grant full MaxCompute permissions to the AccessKey of a RAM user account.
-   We do not recommend that you configure one physical database as two data sources. Two data sources cannot have the same configuration.

 |
|Project management: configure project names| -   When the data source type is MaxCompute, the project name must be the same as your MaxCompute project name.
-   The project name must not start with `LD_` or `ld_`. If project names start with LD\_ or ld\_, project names conflict with business unit names. In this case, errors may occur during table query because the system will not know whether you want to query a logical table or physical table. In Dataphin, when querying a logical table, you must prefix the table name with the corresponding business unit name. When querying a physical table, you must prefix the table name with the corresponding project name.

 |
|Project management: configure computing engines| -   If a physical database has been configured as a data source, we do not recommend that you add, delete, or modify data in the database from non-Dataphin consoles.
-   We do not recommend that you use computing engines from different clusters.

 |
|R&D Workbench: process data| -   Computing engines cannot read data from different clusters.
-   Dataphin cannot obtain the metadata of tables or update information about tables that are not created in Dataphin.

 |
|R&D Workbench: standard modeling| -   We recommend that you use caution when naming data standardization items and logical tables and set their names in lowercase for easier reading. Make sure that their names are valid and easy to read because the names cannot be changed when they have downstream dependencies.
-   Use abbreviations whenever possible to avoid data production errors because the field name length exceeds the limit imposed by the database.

 |
|R&D Workbench: ad hoc query|When querying a logical table, prefix the table name with the corresponding business unit name. When querying a physical table, prefix the table name with the corresponding project name. If you want to query the development environment data, append **\_ dev** to the business unit name or project name for the production environment. The system automatically generates the corresponding variables for both the business unit and project in the production environment. For example, if you have a business unit named LD\_Trade, the system automatically generates the business unit variable $\{LD\_Trade\}. This variable is replaced by LD\_Trade\_dev by default when it is run in the development environment, and replaced by LD\_Trade by default in the production environment. You can assign a specific value for the variable when writing SQL code. This is designed to help improve the flexibility of SQL code when it is run in different environments.

 |

