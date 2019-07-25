# Billing {#concept_nbp_1tx_dhb .concept}

This topic describes the current billing standard of Dataphin.

Before purchasing Dataphin, you need to know the following:

-   Dataphin is currently in the beta phase, the number of customers who can purchase Dataphin is limited. We recommend that you contact Alibaba Cloud customer sales team and provide the data construction requirements and background information of your enterprise. Then, you can determine whether Dataphin's functions and version meet specific your requirements. If Dataphin meets your requirements, communicate with the sales team to obtain the purchase permission.
-   Alibaba Cloud carefully considers each request for a Dataphin refund. We recommend that you carefully read the terms and conditions before purchasing the service. If a refund is approved after the purchase, your service usage fees will be deducted from your refund.

Dataphin is in the beta phase. Currently, only the Intelligence Edition is available in Shanghai, China. The services provided and billing standards are as follows:

-   The price is 50 thousand CNY/month. You must purchase at least a three-month plan. The subscription expiration date cannot be later than the beta end date. The beta end date is temporarily set to September 30, 2019.
-   The number of users is unlimited. A maximum of 200 data processing units are supported. Each tenant is allocated 40c160g of scheduling resources.

    **Note:** 

    -   In the beta phase, details about scheduling resource consumption are described as follows:
        -   Each tenant is allocated 40c160g of scheduling resources. Synchronization may be adversely affected when a large number of concurrent sync tasks exist or the amount of data to be synchronized is too large.
        -   40c160g indicates that you can use ECS resources with 40 CPU cores and 16 GB of memory. For more information about ECS, see [What is ECS?](../../../../intl.en-US/Product Introduction/What is ECS?.md#).
        -   No additional fees are charged for resources used to run sync tasks and other scheduling resources.
    -   Definition of processing unit:

        -   One sync task node or one code task node is calculated as one processing unit.
        -   Every 10 fields in each logical table model is calculated as one processing unit. If there are fewer than 10 fields, the fields are also calculated as one processing unit during billing. The method for calculating the number of processing units billed is to divide the number of fields in each logical table model by 10 and round the result up to the nearest integer. For logical dimension table models and logical fact table models, only the number of fields in the central tables are included in calculating the number of processing units billed. For logical aggregate tables, the number of derived metrics is included in the calculation. In the beta phase, one logical table is calculated as one data processing unit.
        The total number of data processing units to be billed is calculated by adding the results of the preceding calculations.

-   Currently, the monitoring and alerting system does not support pushing alert notifications.

