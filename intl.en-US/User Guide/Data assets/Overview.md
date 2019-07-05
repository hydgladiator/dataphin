# Overview {#concept_xn4_qpk_bhb .concept}

This topic describes a brief introduction to data assets and three modes of asset overview.

## Data assets overview {#section_1ih_z7j_g89 .section}

After data acquisition, integration, processing, and other development works are complete, you can manage the data on the Data Assets page in a systematic way.

Based on the standards and methodology of data asset management, Dataphin can check and assess the data assets, including:

-   Extracts and analyzes metadata automatically, and constructs data assets visually, allowing managers to understand the value of data assets.
-   Data production provides an end-to-end inventory check and analysis of computing, storage, security, and applications. This helps you to discover problems, propose and implement governance optimization solutions, reducing costs and improving efficiency at the data layer. You can access the Data Assets page to view the results of data modeling and development, as well as the data table details.

## Global mode {#section_s3z_25o_v7o .section}

The Global mode displays business units that have a large data size and their respective total data sizes as planets in a visual view.

1.  Log on to Dataphin.
2.  In the top navigation bar of the Dataphin homepage, choose **Data Assets** to go to the data assets page.
3.  Choose **Overview** \> **Global** to go to the data asset page of the global mode. The lower-right corner displays the names, data sizes, and percentages of the top five business units ranked by data size. The total number of tasks, tables, and projects are also displayed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136672/156231452840660_en-US.png)

    **Note:** The data asset overview only contains the metadata of the production environment and the application data that has been processed.

4.  Move the pointer over any planet to display the used computing resources, storage size, the number of projects, and the number of tables, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136672/156231452840661_en-US.png)


## Flow mode {#section_p2n_xyd_95d .section}

The Flow mode shows the data import, integration, and output process in a visual view, revealing the capabilities of the Data Mid-End.

1.  Log on to Dataphin.
2.  In the top navigation bar of the Dataphin homepage, choose **Data Assets** to go to the data assets page.
3.  Choose **Overview** \> **Flow** to open the data asset page of the flow mode. This page shows the data ingest progress, the number of total tables, and data applications such as data query and other applications in a visual view, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136673/156231452840663_en-US.png)

4.  Move the pointer over the **Data Ingestion Progress** area, and the number of source databases is displayed, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136673/156231452940664_en-US.png)

5.  Move the pointer over the **Total Tables** area, you can view the following data from the perspective of data standardization: the number of dimensions, business processes, business filters, atomic metrics, and derived metrics. You also can view the following data from the perspective of data models: the number of dimension-based models, fact-based models, and theme-based models, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136673/156231452940665_en-US.png)


## Structure mode {#section_xwm_tb3_agk .section}

In Structure mode, components in different shapes represent business entities, whereas lines of different styles represent business relations between the entities. This mode shows a clear view of the data structure in a single business unit.

1.  Log on to Dataphin.
2.  In the top navigation bar of the Dataphin homepage, choose **Data Assets** to go to the data assets page.
3.  Choose **Overview** \> **Structure** to open the data asset page of the structure mode. You can switch business units to view their corresponding dimension maps and dimensions associated with the business.

    As shown in the following figure, you can select another business unit in the upper-right corner to display all the dimensions, business processes, and their relationships under this business unit. You can drag the progress bar above to rotate and display other dimensions and business processes of the business unit.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136674/156231453040667_en-US.png)

4.  Select a specific dimension, such as "customer\_2", the corresponding dimension entities and business processes of this dimension are highlighted. Select a specific business process, and the associated dimensions are highlighted. You can also search for a dimension or business process in the search box in the upper-left corner, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136674/156231453040668_en-US.png)


