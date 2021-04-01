---
keyword: DQL操作
---

# DQL操作

MaxCompute中的DQL语句包括SELECT、JOIN、WHERE子句等。本文为您介绍Dataphin支持的MaxCompute的DQL操作语句。

|功能|是否支持|
|--|----|
|[命令格式](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/SELECT语法.md)|是|
|[列表达式（select\_expr）](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/SELECT语法.md)|-   支持`*`
-   支持`distinct`
-   不支持正则表达式 |
|[WHERE子句（where\_condition）](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/SELECT语法.md)|Dataphin 2.9.2及之后版本支持UDF分区裁剪|
|当SQL语句设置了group by属性，即`set odps.sql.groupby.position.alias=true;`，group by中的整型常量会被当做select的列序号处理，详情请参见[GROUP BY分组查询（col\_list）](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/SELECT语法.md)|是|
|[基础子查询](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/子查询（SUBQUERY）.md)|-   支持`select <select_expr> from (<select_statement>) <sq_alias_name>;`
-   不支持`select (<select_statement>) from <table_name>;` |
|[IN SUBQUERY](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/子查询（SUBQUERY）.md)|是|
|[NOT EXISTS SUBQUERY](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/子查询（SUBQUERY）.md)|是|
|[SCALAR SUBQUERY](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/子查询（SUBQUERY）.md)|是|
|[交集、并集和补集](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/交集、并集和补集.md)|-   支持`intersect`
-   不支持`intersect all`
-   不支持`intersect distinct` |
|[并集](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/交集、并集和补集.mdsection_jh0_60d_t18)|-   支持`union all`
-   支持`union [distinct]` |
|[补集](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/交集、并集和补集.mdsection_4dy_wcz_jx1)|-   支持`except`
-   支持`minus`
-   不支持`except distinct`
-   不支持`minus distinct`
-   不支持`except all`
-   不支持`minus distinct` |
|[JOIN](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/JOIN.md)|是|
|[SEMI JOIN（半连接）](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/SEMI JOIN（半连接）.md)|是|
|[MAPJOIN HINT](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/MAPJOIN HINT.md)|是|
|[Lateral View（行转列）](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/Lateral View（行转列）.md)|是|
|[GROUPING SETS](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/GROUPING SETS.md)|是|
|[COMMON TABLE EXPRESSION（CTE）](/cn.zh-CN/开发/SQL及函数/SQL增强操作/COMMON TABLE EXPRESSION（CTE）.md)|是|
|[CLONE TABLE](/cn.zh-CN/开发/SQL及函数/SQL增强操作/CLONE TABLE.md)|否|
|[SELECT TRANSFORM](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/SELECT TRANSFORM.md)|否|
|[EXPLAIN](/cn.zh-CN/开发/SQL及函数/SQL增强操作/EXPLAIN.md)|否|
|[执行语序](/cn.zh-CN/开发/SQL及函数/DQL操作（SELECT）/SELECT语序.md)|否|

