# Standards and modeling: Modeling engine {#concept_odx_hwn_fhb .concept}

Based on the built-in rules of the modeling engine, Dataphin verifies the logical tables during logical table creation, submission, and logical tables task scheduling, and then converts these logical tables into physical tables. Therefore, you can query these physical tables. Modeling engine is used to ensure the model quality and control of the R&D process. Standard, reliable, stable, and efficient models rely on the intelligent modeling engine service.

## Query logical tables using SQL statements {#section_lcz_g24_fhb .section}

Dataphin supports the query of a logical table based on the snowflake schema. The snowflake schema can query data based on \[logical model. dimension-associated field. dimension-associated field.**...**.attribute\] \(such as order.buyer.membership type.type\). This can improve the coding efficiency of the SQL queries.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149950/156134651941707_en-US.png)

-   **Query logical fact tables or logical dimension tables** 
    -   SQL syntax:

        ``` {#codeblock_dxu_siw_qdh}
        SELECT Column,
                LTable.Column,   // Logical table name.field name
                LTable.Role(relation - dimension).….Dimension_Column,   //Logical table name.role name (dimension-associated field name).dimension attribute name
        FROM    LD.LTable   //Business unit name.logical table name 
        WHERE   …
        ```

        ``` {#codeblock_l17_4jp_xzv}
        SELECT Column,
                LTable_Alias.Column,
                LTable_Alias.Role(relation - dimension).….Dimension_Column
        FROM    LD.LTable    Alias
        WHERE   …
        ```

    -   SQL format:

        ``` {#codeblock_3in_lm1_g59}
        SELECT a. dim_industry.in_name,
                a.dim_industry.IN_ID,
                name,
                ceo_name,
                company_id
        FROM   LD_demo.dim_company.dim_industry.in_name  a
        WHERE   ds = '${bizdate}'
        LIMIT  100;
        ```

-   **Query logical aggregate tables** 
    -   SQL syntax:

        ``` {#codeblock_qjl_dur_mhb}
        SELECT Column,
                LTable.Column,
                LTable.Dimension(granularity).….Dimension_Column,
        FROM    LD.LTable
        WHERE   …
        ```

        ``` {#codeblock_x5h_817_rde}
        SELECT Column,
                Alias.Column,
                Alias.Dimension (granularity).….Dimension_Column
        FROM    LD.LTable Alias
        WHERE   …
        ```

    -   SQL format:

        ``` {#codeblock_d17_uv9_044}
        SELECT customer_id,
                c.dim_customer.address_line1,
                c.dim_customer.dim_tax_rate.tx_name,
                crt_trd_comm_amt_30d_trd_valid,
                acct_cnt_td_actv_account,
                watch_sec_cnt_td_actv_watches,
                avg_crt_trd_comm_7d,
                crt_trd_acct_cnt_7d,
                crt_trd_cnt_1d,
                avg_crt_trd_comm_1d,
                crt_trd_comm_amt_1d_trd_valid,
                crt_trd_acct_cnt_1d,
                watch_sec_cnt_td_inac_watches,
                watch_sec_cnt_td,
                acct_cnt_td,
                crt_trd_cnt_7d
        FROM  LD_DEMO.DWS_CUSTOMER c
        WHERE ds='${bizdate}'
        LIMIT 100;
        ```


**Note:** 

-   If two dimension-associated fields referenced by dimension roles in a logical dimension table have the same name, you need to set different display names. This is to prevent conflicts with field names in an SQL statement.
-   Only logical dimension tables of parent dimensions can be queried. If a dimension is a child dimension, you can only use the child dimension based on the logical dimension tables of the parent dimension, or dimension-associated fields.
-   Fields contained in the logical dimension table of a child dimension are displayed in the list of logical dimension table fields of the parent dimension.
-   A dimension that composes the statistic granularity of a logical aggregate table can be referenced in a similar way to associate a dimension to a logical aggregate table. You can obtain the \[dimension \_ primary key\] data by running the SELECT \* command. To prevent slow query of a full table, we recommend that you obtain the primary key by using the SELECT logical table name.dimension table name.primary key statement and obtain the attribute information by using the SELECT logical table name.dimension table name.attribute statement.

## Verify the repetition of the computing logic {#section_fdj_g24_fhb .section}

One of the core benefits of Dataphin is the unique definition, which requires that the name and computing logic are unique. When you submit a standard definition or logical tables, Dataphin will verify the name, display name, and computing logic of the object. You can only submit them when the definition or objects are unique. If duplicate computing logic exists, the system displays a message to help you avoid creating objects with the same name but different meanings or vice versa.

When you submit and publish objects, the system parses the requests based on the abstract syntax tree \(AST\) and verifies the repetition of computing logic \(or expressions\). The objects include time periods, dimensions, logical dimension table fields, logical fact tables, logical fact table fields, atomic metrics, business filters, and custom metrics of logical aggregate tables. If duplicate computing logic exists, the system displays a message to indicate that the object computing logic is repeated.

## Refresh model versions in a dynamic way {#section_xhp_o8r_ups .section}

Dynamic refresh can improve the efficiency of submitting and converting logical tables. It can help increase the flexibility of modifying logical tables, and reduce the computing engine resource consumption for physical table changes, historical data changes, and migration. During SQL task scheduling, the system automatically identifies and routes to the corresponding physical tables based on the latest logical table conversion to obtain the required data.

To view the version information of a logical table, you can select **Versions** on the top of the logical table tab.

