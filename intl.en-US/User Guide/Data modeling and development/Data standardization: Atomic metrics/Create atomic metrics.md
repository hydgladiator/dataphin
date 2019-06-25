# Create atomic metrics {#concept_tdr_vkp_fhb .concept}

An atomic metric is an abstraction of statistical criteria and specific algorithms. To eliminate definition and development inconsistency, Dataphin introduces the concept of "Design to Code". When a metric is defined, the statistical criteria \(computing logic\) is also defined. Re-engineering of ETL process is not required, which increases the development efficiency and ensures the consistency of statistical results.

Based on the complexity of computing logic, Dataphin categorized atomic metrics into two types:

-   Native atomic metric, such as the payment amount.
-   Composite metric, which is constructed based on the combination of atomic metrics. For example, the customer unit price is calculated based on the payment amount divided by the number of buyers.

To create an atomic metric, follow these steps:

1.  Choose **R&D** \> **Develop** \> **Standards and Modeling** \> **Atomic Metrics** to open the corresponding page.
2.  You can open the atomic metric creation dialog box by using four methods. The methods are similar to those for creating a dimension. For more information, see [Create dimensions](intl.en-US/User Guide/Data modeling and development/Data standardization: Dimensions/Create dimensions.md#).
3.  On the atomic metric creation page, select a data domain and a source table as prompted. To ensure standardization of specifications and processing during data modeling, the source table only supports two table types: logical dimension table and logical fact table.

    **Note:** After the source table is selected, the page displays the list of existing atomic metrics that are defined based on the source table.

4.  On the creation page, click **Create Atomic Metric**, enter the required information as prompted, and then click **Submit**.
5.  After the atomic metric is submitted, you can publish the atomic metric. For more information, see [Publish](intl.en-US/User Guide/Manage publishing/Publish.md#).

