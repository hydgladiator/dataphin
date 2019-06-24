# Modify business filters {#concept_icp_hh4_fhb .concept}

This topic describes how to modify a business filter.

1.  Choose **R&D** \> **Develop** \> **Standards and Modeling** \> **Business Filters** to open the corresponding page.
2.  In the left-side navigation pane, select the business filter to be modified. In the page that appears on the right side, click **Change** to open the Change Business Filter dialog box.
3.  In the dialog box that appears, modify the business filter as required, and then click **Submit**. Similar to atomic metrics, after the statistical criteria defined by the business filter is changed, all derived metrics that are defined based on the business filter are affected. Therefore, we recommend that you use caution when changing a business filter.
4.  View the same-source business filter. Select a business filter and click **View Same Source** on the page that appears. You can view the business filters that are defined based on the same source logical table as this business filter.

    To create a new business filter based on the source logical table of the selected business filter, you can select the source logical table or click **View Same Source** to open the corresponding page.


**Note:** 

-   Source logical tables of business filters:

    A business filter is a data element defined to build derived metrics that are required for statistical analysis. Therefore, the business filters can only be created based on two types of detailed data tables: logical dimension table and logical fact table.

-   Relationship between business filters and derived metrics:
    -   After the computing logic of a business filter is updated, the derived metrics that are associated with the business filter are also updated.
    -   If a business filter is deleted or the name is changed, you need to check whether it is used to define a derived metric. If yes, you cannot delete or change the business filter.

