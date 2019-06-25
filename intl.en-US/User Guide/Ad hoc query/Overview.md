# Overview {#concept_i4h_mjb_fhb .concept}

Ad hoc query provides the data query function. If your computing engine is Hadoop, Hive SQL is supported in an ad hoc query. If your computing engine is MaxCompute, MaxCompute SQL is supported in an ad hoc query. The system can automatically identify the SQL syntax based on the configured computing engine.

Dataphin uses the business unit as the namespace for the unique logical table models, and the following two features are added to the syntax for logical tables:

-   When referencing logical tables in SQL statements, use the format of business unit. logical table in SQL statements.
-   Supports the query logic in the format of \[business unit. logical table. dimension-associated field.**...**.dimension-associated field.dimension field\] in SQL statements. If the query logic is set as a condition of a SELECT or WHERE clause, you only need to enter the \[logical table.dimension-associated field.**...**.dimension-associated field.dimension field\], which can be used to search for fields associated with dimensions.

**Note:** The system-generated flag field **Is\_XX** of a child dimension is not supported as the condition of a SELECT statement, and the primary key field of a virtual dimension is also not supported. A virtual dimension is only used for statistical granularity construction.

