# Concepts {#concept_tnb_wrt_zgb .concept}

This topic describes basic concepts such as business unit, common business logic, project management, database engine, dimension, and dimension. Other concepts include business process, logical dimension table, logical fact table, atomic metric, business filter, and derived metric.

## Business unit {#section_pck_5qx_k2b .section}

A business unit is used to define the name and business space of a data warehouse. A relatively independent business system in an enterprise can be referred to as a business unit. If your business involves retail and entertainment, and business systems are relatively isolated from each other, you need to create two business units: retail and entertainment. If your business only involves retail, and the systems in the business are less isolated, you only need to build one business unit: retail.

## Common business logic {#section_fmd_wqx_k2b .section}

Common business logic is global concepts or parameters required for an enterprise to produce data. By defining common business logic, you can ensure that the definitions of global concepts are consistent throughout the whole system and can be universally referenced. An example of common business logic is statistical period.

## Project management {#section_e1w_xqx_k2b .section}

A project is a physical space division that allows users to isolate developers and the resources that they use.

## Database engine {#section_kb2_zqx_k2b .section}

You can register your physical databases to Dataphin. Physical databases serve as the underlying data sources for projects and also the source for data synchronization.

## Dimension {#section_og1_cqx_k2b .section}

A dimension is a statistical object. It is an entity that actually exists. By creating a dimension, you can standardize your business entities \(or master data\) during architectural design to ensure their uniqueness.

## Business process {#section_tv1_hqx_k2b .section}

A business process is a collection of all events in a business activity. By creating a business process, you can standardize a type of transaction event in business to ensure its uniqueness.

## Logical dimension table {#section_zw1_jqx_k2b .section}

One logical dimension table corresponds to one dimension. A logical dimension table stores dimension attributes that describe facts. Logical dimension tables are used to design and process detailed data of common objects, so that detailed data of the objects can be extracted from business data.

## Logical fact table {#section_ukr_kqx_k2b .section}

A logical fact table models a business process and stores attributes and measures about the business process. Logical fact tables are used to design and process detailed data of common transactions, so that detailed data of the transactions can be extracted from business data.

## Atomic metric and business filter {#section_p5b_4qx_k2b .section}

An atomic metric and business filter are the computing logic and attributive limitation commonly used in business. An atomic metric and business filter are expressions formulated based on fields in a logical table. These are reusable common data elements extracted to calculate aggregated data.

## Derived metrics {#section_d5w_4qx_k2b .section}

A derived metric is a commonly used statistical metric. It is used to aggregate the data of an object group in a specific range during a time period.

Therefore, a derived metric is defined by the time period \(statistical period\), statistical object \(statistic granularity\), range \(business filter\), and calculation method \(atomic metric\). For example, calendar week, member, order paid with coupons, and amount of money paid refer to statistical period, statistic granularity, business filter, and atomic metric, respectively.

