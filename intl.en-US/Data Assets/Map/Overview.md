# Overview

This topic describes a brief introduction to data assets and three modes of asset overview.

## Data assets overview

After data acquisition, integration, processing, and other development works are complete, you can manage the data on the Data Assets page in a systematic way.

Based on the standards and methodology of data asset management, Dataphin can check and assess the data assets, including:

-   Extracts and analyzes metadata automatically, and constructs data assets visually, allowing managers to understand the value of data assets.
-   Data production provides an end-to-end inventory check and analysis of computing, storage, security, and applications. This helps you to discover problems, propose and implement governance optimization solutions, reducing costs and improving efficiency at the data layer. You can access the Data Assets page to view the results of data modeling and development, as well as the data table details.

## Global mode

The Global mode displays business units that have a large data size and their respective total data sizes as planets in a visual view.

1.  Log on to Dataphin.
2.  In the top navigation bar of the Dataphin homepage, choose **Data Assets** to go to the data assets page.
3.  Choose **Overview** \> **Global** to go to the data asset page of the global mode. The lower-right corner displays the names, data sizes, and percentages of the top five business units ranked by data size. The total number of tasks, tables, and projects are also displayed.

    ![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/en-US/3737719851/p40660.png)

    **Note:** The data asset overview only contains the metadata of the production environment and the application data that has been processed.

4.  Move the pointer over any planet to display the used computing resources, storage size, the number of projects, and the number of tables, as shown in the following figure.

    ![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/en-US/3737719851/p40661.png)


## Flow mode

The Flow mode shows the data import, integration, and output process in a visual view, revealing the capabilities of the Data Mid-End.

1.  Log on to Dataphin.
2.  In the top navigation bar of the Dataphin homepage, choose **Data Assets** to go to the data assets page.
3.  Choose **Overview** \> **Flow** to open the data asset page of the flow mode. This page shows the data ingest progress, the number of total tables, and data applications such as data query and other applications in a visual view, as shown in the following figure.

    ![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/en-US/4737719851/p40663.png)

4.  Move the pointer over the **Data Ingestion Progress** area, and the number of source databases is displayed, as shown in the following figure.

    ![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/en-US/4737719851/p40664.png)

5.  Move the pointer over the **Total Tables** area, you can view the following data from the perspective of data standardization: the number of dimensions, business processes, business filters, atomic metrics, and derived metrics. You also can view the following data from the perspective of data models: the number of dimension-based models, fact-based models, and theme-based models, as shown in the following figure.

    ![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/en-US/4737719851/p40665.png)


## Structure mode

In Structure mode, components in different shapes represent business entities, whereas lines of different styles represent business relations between the entities. This mode shows a clear view of the data structure in a single business unit.

1.  Log on to Dataphin.
2.  In the top navigation bar of the Dataphin homepage, choose **Data Assets** to go to the data assets page.
3.  Choose **Overview** \> **Structure** to open the data asset page of the structure mode. You can switch business units to view their corresponding dimension maps and dimensions associated with the business.

    As shown in the following figure, you can select another business unit in the upper-right corner to display all the dimensions, business processes, and their relationships under this business unit. You can drag the progress bar above to rotate and display other dimensions and business processes of the business unit.

    ![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/en-US/5737719851/p40667.png)

4.  Select a specific dimension, such as "customer\_2", the corresponding dimension entities and business processes of this dimension are highlighted. Select a specific business process, and the associated dimensions are highlighted. You can also search for a dimension or business process in the search box in the upper-left corner, as shown in the following figure.

    ![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/en-US/5737719851/p40668.png)


