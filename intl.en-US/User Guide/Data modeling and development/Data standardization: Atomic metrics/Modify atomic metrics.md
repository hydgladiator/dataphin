# Modify atomic metrics {#concept_slb_xkp_fhb .concept}

This article describes how to modify atomic metrics.

1.  Choose **R&D** \> **Develop** \> **Standards and Modeling** \> **Atomic Metrics** to open the corresponding page.
2.  In the left-side navigation pane, select the atomic metric to be modified. In the page that appears on the right side, click **Change** to open the Change Atomic Metric dialog box.
3.  Modify the atomic metric information as needed, and then click **Submit**.

    **Note:** After the statistical criteria defined by the atomic metric is changed, all derived metrics that are defined based on the atomic metric are affected. Therefore, we recommend that you use caution when changing an atomic metric.

4.  View the same-source atomic metrics. Select an atomic metric and click **View Same Source** on the page that appears. You can view the atomic metrics that are defined based on the same source logical table as this atomic metric.

    To create a new atomic metric based on the source logical table of the selected atomic metric, you can select the source logical table or click **View Same Source** to open the corresponding page.


**Note:** Source logic tables of atomic metrics:

-   An atomic metric is a data element defined to build derived metrics that are required for statistical analysis. Therefore, the atomic metric can only be created based on two types of detailed data tables: logical dimension table and logical fact table.
-   Composite metrics do not have source tables. A composite metric is created based on the source tables of atomic metrics.

**Note:** Relationship between atomic metrics and derived metrics:

-   After the computing logic of an atomic metric is updated, the derived metrics defined based on the atomic metric are also updated.
-   If an atomic metric is deleted or the name is changed, you need to check whether it is used to define a derived metric. If yes, you cannot delete or change the atomic metric.
-   Changing the data type of an atomic metric affects the derived metrics that are defined based on the atomic metric.

