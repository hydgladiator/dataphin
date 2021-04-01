---
keyword: DML
---

# DML操作

MaxCompute中的DML语句包括插入、更新和删除数据操作。本文为您介绍Dataphin支持的MaxCompute的DML操作语句。

|功能|是否支持|
|--|----|
|[插入或覆写数据（INSERT INTO \| INSERT OVERWRITE）](/cn.zh-CN/开发/SQL及函数/DML操作/插入或覆写数据（INSERT INTO | INSERT OVERWRITE）.md)|-   支持`insert {into|overwrite} table <table_name> [partition (<pt_spec>)] <select_statement> from <from_statement>;`
-   不支持指定列插入数据：`insert into table <table_name> [partition (<pt_spec>)] (<col_name> ,<col_name> ...) <select_statement> from <from_statement>;`
-   不支持插入数据排序：`insert {into|overwrite} table <table_name> [partition (<pt_spec>)] [(<col_name> [,<col_name> ...)] <select_statement> from <from_statement> [zorder by <zcol_name> [, <zcol_name> ...]];` |
|[插入或覆写动态分区数据（DYNAMIC PARTITION）](/cn.zh-CN/开发/SQL及函数/DML操作/插入或覆写动态分区数据（DYNAMIC PARTITION）.md)|是|
|[多路输出（MULTI INSERT）](/cn.zh-CN/开发/SQL及函数/DML操作/多路输出（MULTI INSERT）.md)|是|
|[VALUES](/cn.zh-CN/开发/SQL及函数/DML操作/VALUES.md)|-   支持`insert … values`
-   不支持`values table` |
|[LOAD](/cn.zh-CN/开发/SQL及函数/SQL增强操作/LOAD.md)|否|

