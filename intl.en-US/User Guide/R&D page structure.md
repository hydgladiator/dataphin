# R&D page structure {#concept_whq_wfd_bhb .concept}

This topic describes the method to go to the R&D page, the structure of the R&D page, the functions provided by each section, and how to use each button.

## Go to the R&D page {#section_byh_f1k_dhb .section}

On the Dataphin homepage, click **R&D**. Alternatively, you can access the R&D page from the quick access area located in the middle of the homepage, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136286/156135553541057_en-US.png)

## Introduction to the R&D page structure {#section_xtb_zfd_bhb .section}

The R&D page consists of four modules: Develop, Publish, Scheduling, and Permissions.

|Module|Description|
|------|-----------|
|Develop|This module includes the following three parts: -   Standards and Modeling tab: allows you to create metrics and data models.
-   Data Processing tab: allows you to create sync tasks, code tasks, functions, and resource files.
-   Ad Hoc Query tab: allows you to perform data queries and verification before publishing a task.

**Note:** The ad hoc query function is only available in the development environment.


 |
|Publish|The Publish module is only available in the development environment. -   You can view the tasks submitted from the development environment and publish them to the production environment to start data production.
-   You can view the publishing history.

 |
|Scheduling|This module consists of the following two parts: -   Scheduling center: allows you to view and manage recurring tasks and instances, one-time tasks and instances, logical table tasks and instances, and retroactive data generation instances.
-   Monitoring and alerting: allows you to set alert rules and view the alerts for the tasks in the production environment. The monitoring and alerting function is only available in the production environment.

 |
|Permissions|To ensure the secure and controllable use of data resources, permissions to use data tables are controlled. To use a table, you need to request field level permissions and receive approval.|

## Functions and usage guidelines {#section_sr2_j1k_dhb .section}

-   **R&D page** 

    After entering the R&D page, you can see the operation guide for the entire R&D process \(for more information, see [Figure 1](#fig_iga_21h_tg7)\). You can click the plus sign icon ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136286/156135553541131_en-US.png) under each module in the guide diagram to create the corresponding item.

    ![](images/41141_en-US.png "Operation guide")

-   **Sections of the R&D page** 

    ![](images/41153_en-US.png "Sections")

    |No.|Description|
    |---|-----------|
    |1|Identifies the environment type. By clicking this button, you can switch between the development environment and production environment. Prod represents the production environment, while Dev represents the development environment. **Note:** If you open project A in the production environment and then switch to the development environment, the counterpart of project A in the development environment \(project A\_dev\) will open.

 |
    |2|Displays the name of the current project and the environment type, which is identified by either Prod or Dev. By clicking the drop-down arrow on the right of the project name, the list of projects in the current environment appears. You can switch to another project by clicking a project in the list. **Note:** If you open a project in the development environment and then switch to the counterpart project in the production environment, the environment type displayed in section 1 is also changed to the production environment, and vice versa.

 |
    |3|A create button. You can click this button to create data standardization items, logical tables, and code tasks.|
    |4|A refresh button and a create button. You can click these two buttons to refresh the list below and create an item or task.|
    |5|A search box. You can enter a keyword to search for an item or task that is already created.|
    |6|Displays the items or tasks that have already been created.|
    |7|A navigation submenu that shows the following types of data standardization items: dimension, business process, atomic metric, business filter, and derived metric. You can click this submenu to display the list of each type of item. In each list, you can perform operations such as view, create, and unpublish.|
    |8|A navigation submenu that shows three logical table types: logical fact table, logical dimension table, and logical aggregate table. You can click this submenu to display the list for each type of logical table. In each list, you can perform operations such as view, create, delete, and unpublish. **Note:** You cannot manually create logical dimension tables. After a dimension is created, the system creates a logical dimension table by default.

 |
    |9|You can click this button to view the list of data standardization items that have already been created.|
    |10|The four modules related to R&D. You can click each module name to open the corresponding module page.|
    |11|A global search box. You can search for physical tables, logical tables, data standardization items, functions, and resources. You can select filter conditions to find your target item.|
    |12|**Recent Items** button. By clicking this button, a list of recently opened items appear. You can click an item to open the item editing page.|
    |13|**View Attributes**. By clicking this button, a list of recently opened items appear. You can click an item to display its attributes and the actions that can be performed on this item, such as modifying this item and referencing this item to create other items.|

-   **Buttons on the R&D page** 

    ![](images/41180_en-US.png "Buttons")

    |No.|Description|
    |---|-----------|
    |1|By moving the pointer over an item or a task, this button appears. You can click this button to copy the name of the item or the task.|
    |2|By moving the pointer over an item or task, this button appears. You can click this button to show more actions, including change, unpublish, and delete.|
    |3|The buttons from left to right will trigger specific actions, such as steal lock \(or lock\), save, submit, and locate.     -   Steal lock \(or lock\): Items and tasks are locked by their creator by default. When other users have permission to modify the items and tasks, they need to steal the lock before performing modifications.
    -   Save: You can click this button to save the item or task information on the current page.
    -   Submit: You can click this button to submit an item or a task. After submission, you can publish the item or task on the [Publish](intl.en-US/User Guide/Manage publishing/Publish.md#) page.
    -   Locate: You can click Positioning to locate an item or a task in the left-side list.
 |
    |4|By clicking this button, a list appears to show the opened tabs. You can click tab names to switch to different tabs. In the list, you can also quickly close the opened tabs.|
    |5|You can click this button to display the operation guide page \(for more information, see [Figure 1](#fig_iga_21h_tg7)\).|


