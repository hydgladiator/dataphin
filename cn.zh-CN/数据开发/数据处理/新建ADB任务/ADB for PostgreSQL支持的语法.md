---
keyword: ADB for PostgreSQL支持的语法
---

# ADB for PostgreSQL支持的语法

本文为您介绍Dataphin的计算引擎为AnalyticDB for PostgreSQL时，系统支持的SQL命令及语法。

-   [CREATE DATABASE](#section_lrt_lcn_aj6)
-   [CREATE INDEX](#section_8kj_oaf_tbv)
-   [CREATE ROLE](#section_ojb_vst_7ce)
-   [CREATE SEQUENCE](#section_49n_51q_knb)
-   [CREATE USER](#section_r3g_o78_msx)
-   [CREATE VIEW](#section_5hz_rdk_g50)
-   [CREATE SCHEMA](#section_dm3_loq_t4b)
-   [CREATE TABLE](#section_avh_ocl_jk3)
-   [CREATE TABLE AS](#section_mvu_zpn_msh)
-   [SELECT](#section_e50_ufg_pxm)
-   [ALTER DATABASE](#section_5f6_e0c_z9c)
-   [ALTER EXTERNAL TABLE](#section_3ii_yx3_cw1)
-   [ALTER INDEX](#section_umk_z25_rm5)
-   [ALTER SCHEMA](#section_atn_3vl_aey)
-   [ALTER TABLE](#section_oun_k8m_zer)
-   [DROP DATABASE](#section_7pz_9hh_jfc)
-   [DROP INDEX](#section_do4_ej0_74t)
-   [DROP SCHEMA](#section_jbu_0jj_15a)
-   [DROP ROLE](#section_gro_2yd_imh)
-   [DROP SEQUENCE](#section_11g_npu_9hp)
-   [DROP USER](#section_z7j_fma_pub)
-   [DROP VIEW](#section_v0a_ap9_qfs)
-   [DROP TABLE](#section_ttl_abq_jc7)
-   [BEGIN](#section_ueu_6yh_0dm)
-   [CHECKPOINT](#section_ag6_inx_5hg)
-   [CLOSE](#section_8gn_mrz_m6p)
-   [CLUSTER](#section_t36_css_xi8)
-   [COMMENT](#section_h4v_zpx_cps)
-   [COMMIT](#section_gcc_drg_uye)
-   [DEALLOCATE](#section_hvr_xr4_lps)
-   [DECLARE](#section_xjk_9ve_w8o)
-   [DELETE](#section_s6p_u4v_9oj)
-   [END](#section_x92_taw_zu0)
-   [EXPLAIN](#section_hqu_wal_5qi)
-   [FETCH](#section_c4b_6gs_1mh)
-   [LOAD](#section_azx_9pt_93b)
-   [LOCK](#section_kv6_3g1_ydl)
-   [MOVE](#section_m17_f2p_w3c)
-   [PREPARE](#section_h2h_bw8_648)
-   [REASSIGN OWNED](#section_z7u_4ob_gkz)
-   [REINDEX](#section_phh_417_j78)
-   [RELEASE SAVEPOINT](#section_po2_sla_yje)
-   [RESET](#section_p7z_gqw_ky8)
-   [ROLLBACK](#section_5o2_tqs_wkv)
-   [ROLLBACK TO SAVEPOINT](#section_djo_212_mic)
-   [SAVEPOINT](#section_h31_sgf_k36)
-   [SELECT INTO](#section_tnu_5vv_ejl)
-   [SET](#section_mgx_8wr_33j)
-   [SET ROLE](#section_fw2_uji_pc6)
-   [SET SESSION AUTHORIZATION](#section_kl9_tfp_6nq)
-   [SET TRANSACTION](#section_ppj_dky_dn5)
-   [SHOW](#section_ssq_9nl_exq)
-   [START TRANSACTION](#section_ofd_idx_rue)
-   [TRUNCATE](#section_4hx_2e4_hbt)
-   [UPDATE](#section_9l5_veo_y8b)
-   [VACUUM](#section_zc2_xhm_jt9)
-   [VALUES](#section_4ll_8ml_gxy)

## CREATE DATABASE

创建数据库。

```
CREATE DATABASE name [ [WITH] [OWNER [=] dbowner]
                     [TEMPLATE [=] template]
                     [ENCODING [=] encoding]
                     [CONNECTION LIMIT [=] connlimit ] ]
```

## CREATE INDEX

定义索引。

```
CREATE [UNIQUE] INDEX name ON table
       [USING btree|bitmap|gist]
       ( {column | (expression)} [opclass] [, ...] )
       [ WITH ( FILLFACTOR = value ) ]
       [TABLESPACE tablespace]
       [WHERE predicate]
```

更多信息请参见[CREATE INDEX](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CREATE_INDEX.html)。

## CREATE ROLE

定义数据库角色（用户或组）。

```
CREATE ROLE name [[WITH] option [ ... ]]
```

更多信息请参见[CREATE ROLE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CREATE_ROLE.html)。

## CREATE SEQUENCE

定义序列生成器。

```
CREATE [TEMPORARY | TEMP] SEQUENCE name
       [INCREMENT [BY] value] 
       [MINVALUE minvalue | NO MINVALUE] 
       [MAXVALUE maxvalue | NO MAXVALUE] 
       [START [ WITH ] start] 
       [CACHE cache] 
       [[NO] CYCLE] 
       [OWNED BY { table.column | NONE }]
```

更多信息请参见[CREATE SEQUENCE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CREATE_SEQUENCE.html)。

## CREATE USER

定义默认具有LOGIN权限的数据库角色。

```
CREATE USER name [ [WITH] option [ ... ] ]
```

更多信息请参见[CREATE USER](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CREATE_USER.html)。

## CREATE VIEW

定义视图。

```
CREATE [OR REPLACE] [TEMP | TEMPORARY] VIEW name
       [ ( column_name [, ...] ) ]
       AS query
```

更多信息请参见[CREATE VIEW](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CREATE_VIEW.html)。

## CREATE SCHEMA

定义SCHEMA。

```
CREATE SCHEMA schema_name [AUTHORIZATION username] 
   [schema_element [ ... ]]

CREATE SCHEMA AUTHORIZATION rolename [schema_element [ ... ]]
```

更多信息请参见[CREATE SCHEMA](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CREATE_SCHEMA.html)。

## CREATE TABLE

定义表。

```
CREATE [[GLOBAL | LOCAL] {TEMPORARY | TEMP}] TABLE table_name ( 
[ { column_name data_type [ DEFAULT default_expr ] 
   [column_constraint [ ... ]
[ ENCODING ( storage_directive [,...] ) ]
] 
   | table_constraint
   | LIKE other_table [{INCLUDING | EXCLUDING} 
                      {DEFAULTS | CONSTRAINTS}] ...}
   [, ... ] ]
   )
   [ INHERITS ( parent_table [, ... ] ) ]
   [ WITH ( storage_parameter=value [, ... ] )
   [ ON COMMIT {PRESERVE ROWS | DELETE ROWS | DROP} ]
   [ DISTRIBUTED BY (column, [ ... ] ) | DISTRIBUTED RANDOMLY ]
   [ PARTITION BY partition_type (column)
       [ SUBPARTITION BY partition_type (column) ] 
          [ SUBPARTITION TEMPLATE ( template_spec ) ]
       [...]
    ( partition_spec ) 
        | [ SUBPARTITION BY partition_type (column) ]
          [...]
    ( partition_spec
      [ ( subpartition_spec
           [(...)] 
         ) ] 
    )
```

更多信息请参见[CREATE TABLE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CREATE_TABLE.html)。

## CREATE TABLE AS

从查询的结果中定义新的表。

```
CREATE [ [GLOBAL | LOCAL] {TEMPORARY | TEMP} ] TABLE table_name
   [(column_name [, ...] )]
   [ WITH ( storage_parameter=value [, ... ] ) ]
   [ON COMMIT {PRESERVE ROWS | DELETE ROWS | DROP}]
   [TABLESPACE tablespace]
   AS query
   [DISTRIBUTED BY (column, [ ... ] ) | DISTRIBUTED RANDOMLY]
```

更多信息请参见[CREATE TABLE AS](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CREATE_TABLE_AS.html)。

## SELECT

从表或视图中检索行。

```
[ WITH with_query [, ...] ]
SELECT [ALL | DISTINCT [ON (expression [, ...])]]
  * | expression [[AS] output_name] [, ...]
  [FROM from_item [, ...]]
  [WHERE condition]
  [GROUP BY grouping_element [, ...]]
  [HAVING condition [, ...]]
  [WINDOW window_name AS (window_specification)]
  [{UNION | INTERSECT | EXCEPT} [ALL] select]
  [ORDER BY expression [ASC | DESC | USING operator] [NULLS {FIRST | LAST}] [, ...]]
  [LIMIT {count | ALL}]
  [OFFSET start]
  [FOR {UPDATE | SHARE} [OF table_name [, ...]] [NOWAIT] [...]]
```

更多信息请参见[SELECT](http://docs.greenplum.org/6-4/ref_guide/sql_commands/SELECT.html)。

## ALTER DATABASE

修改数据库属性。

```
ALTER DATABASE name [ WITH CONNECTION LIMIT connlimit ]
ALTER DATABASE name SET parameter { TO | = } { value | DEFAULT }
ALTER DATABASE name RESET parameter
ALTER DATABASE name RENAME TO newname
ALTER DATABASE name OWNER TO new_owner
```

更多信息请参见[ALTER DATABASE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/ALTER_DATABASE.html)。

## ALTER EXTERNAL TABLE

改变外部表的定义。

```
ALTER EXTERNAL TABLE name RENAME [COLUMN] column TO new_column
ALTER EXTERNAL TABLE name RENAME TO new_name
ALTER EXTERNAL TABLE name SET SCHEMA new_schema
ALTER EXTERNAL TABLE name action [, ... ]
```

更多信息请参见[ALTER EXTERNAL TABLE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/ALTER_EXTERNAL_TABLE.html)。

## ALTER INDEX

改变索引的定义。

```
ALTER INDEX name RENAME TO new_name
ALTER INDEX name SET TABLESPACE tablespace_name
ALTER INDEX name SET ( FILLFACTOR = value )
ALTER INDEX name RESET ( FILLFACTOR )
```

更多信息请参见[ALTER INDEX](http://docs.greenplum.org/6-4/ref_guide/sql_commands/ALTER_INDEX.html)。

## ALTER SCHEMA

改变模式的定义。

```
ALTER SCHEMA name RENAME TO newname

ALTER SCHEMA name OWNER TO newowner
```

更多信息请参见[ALTER SCHEMA](http://docs.greenplum.org/6-4/ref_guide/sql_commands/ALTER_SCHEMA.html)。

## ALTER TABLE

改变的表的定义。

```
ALTER TABLE [ONLY] name RENAME [COLUMN] column TO new_column

ALTER TABLE name RENAME TO new_name

ALTER TABLE name SET SCHEMA new_schema

ALTER TABLE [ONLY] name SET 
     DISTRIBUTED BY (column, [ ... ] ) 
   | DISTRIBUTED RANDOMLY 
   | WITH (REORGANIZE=true|false)

ALTER TABLE [ONLY] name action [, ... ]

ALTER TABLE name
   [ ALTER PARTITION { partition_name | FOR (RANK(number)) 
   | FOR (value) } partition_action [...] ] 
   partition_action
```

更多信息请参见[ALTER TABLE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/ALTER_TABLE.html)。

## DROP DATABASE

删除数据库。

```
DROP DATABASE [IF EXISTS] name
```

更多信息请参见[DROP DATABASE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DROP_DATABASE.html)。

## DROP INDEX

删除索引。

```
DROP INDEX [IF EXISTS] name [, ...] [CASCADE | RESTRICT]
```

更多信息请参见[DROP INDEX](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DROP_INDEX.html)。

## DROP SCHEMA

删除SCHEMA。

```
DROP SCHEMA [IF EXISTS] name [, ...] [CASCADE | RESTRICT]
```

更多信息请参见[DROP SCHEMA](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DROP_SCHEMA.html)。

## DROP ROLE

删除数据库角色。

```
DROP ROLE [IF EXISTS] name [, ...]
```

更多信息请参见[DROP ROLE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DROP_ROLE.html)。

## DROP SEQUENCE

删除序列。

```
DROP SEQUENCE [IF EXISTS] name [, ...] [CASCADE | RESTRICT]
```

更多信息请参见[DROP SEQUENCE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DROP_SEQUENCE.html)。

## DROP USER

删除数据库用户。

```
DROP USER [IF EXISTS] name [, ...]
```

更多信息请参见[DROP USER](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DROP_USER.html)。

## DROP VIEW

删除视图。

```
DROP VIEW [IF EXISTS] name [, ...] [CASCADE | RESTRICT]
```

更多信息请参见[DROP VIEW](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DROP_VIEW.html)。

## DROP TABLE

删除表。

```
DROP TABLE [IF EXISTS] name [, ...] [CASCADE | RESTRICT]
```

更多信息请参见[DROP TABLE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DROP_TABLE.html)。

## BEGIN

启动事务块。

```
BEGIN [WORK | TRANSACTION] [transaction_mode]
      [READ ONLY | READ WRITE]
```

更多信息请参见[BEGIN](http://docs.greenplum.org/6-4/ref_guide/sql_commands/BEGIN.html) 。

## CHECKPOINT

强制事务记录检查点。

```
CHECKPOINT
```

更多信息请参见[CHECKPOINT](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CHECKPOINT.html)。

## CLOSE

关闭游标。

```
CLOSE cursor_name
```

更多信息请参见[CLOSE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CLOSE.html) 。

## CLUSTER

根据索引对磁盘上的堆存储表，重新排序。

```
CLUSTER indexname ON tablename

CLUSTER tablename

CLUSTER
```

更多信息请参见[CLUSTER](http://docs.greenplum.org/6-4/ref_guide/sql_commands/CLUSTER.html)。

## COMMENT

定义或修改对象的注释。

```
COMMENT ON
{ TABLE object_name |
  COLUMN table_name.column_name |
  AGGREGATE agg_name (agg_type [, ...]) |
  CAST (sourcetype AS targettype) |
  CONSTRAINT constraint_name ON table_name |
  CONVERSION object_name |
  DATABASE object_name |
  DOMAIN object_name |
  FILESPACE object_name |
  FUNCTION func_name ([[argmode] [argname] argtype [, ...]]) |
  INDEX object_name |
  LARGE OBJECT large_object_oid |
  OPERATOR op (leftoperand_type, rightoperand_type) |
  OPERATOR CLASS object_name USING index_method |
  [PROCEDURAL] LANGUAGE object_name |
  RESOURCE QUEUE object_name |
  ROLE object_name |
  RULE rule_name ON table_name |
  SCHEMA object_name |
  SEQUENCE object_name |
  TABLESPACE object_name |
  TRIGGER trigger_name ON table_name |
  TYPE object_name |
  VIEW object_name } 
IS 'text'
```

更多信息请参见[COMMENT](http://docs.greenplum.org/6-4/ref_guide/sql_commands/COMMENT.html)。

## COMMIT

提交当前事务。

```
COMMIT [WORK | TRANSACTION]
```

更多信息请参见[COMMIT](http://docs.greenplum.org/6-4/ref_guide/sql_commands/COMMIT.html)。

## DEALLOCATE

取消分配预编译的语句。

```
DEALLOCATE [PREPARE] name
```

更多信息请参见[DEALLOCATE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DEALLOCATE.html)。

## DECLARE

定义游标。

```
DECLARE name [BINARY] [INSENSITIVE] [NO SCROLL] CURSOR 
     [{WITH | WITHOUT} HOLD] 
     FOR query [FOR READ ONLY]
```

更多信息请参见[DECLARE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DECLARE.html)。

## DELETE

从表中删除行。

```
DELETE FROM [ONLY] table [[AS] alias]
      [USING usinglist]
      [WHERE condition | WHERE CURRENT OF cursor_name ]
```

更多信息请参见[DELETE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/DELETE.html)。

## END

结束当前事务。

```
END [WORK | TRANSACTION]
```

更多信息请参见[END](http://docs.greenplum.org/6-4/ref_guide/sql_commands/END.html)。

## EXPLAIN

展示语句的查询计划。

```
EXPLAIN [ANALYZE] [VERBOSE] statement
```

更多信息请参见[EXPLAIN](http://docs.greenplum.org/6-4/ref_guide/sql_commands/EXPLAIN.html)。

## FETCH

通过游标获取查询结果的行。

```
FETCH [ forward_direction { FROM | IN } ] cursorname
```

更多信息请参见[FETCH](http://docs.greenplum.org/6-4/ref_guide/sql_commands/FETCH.html) 。

## LOAD

加载或重新加载共享库文件。

```
LOAD 'filename'
```

更多信息请参见 [LOAD](http://docs.greenplum.org/6-4/ref_guide/sql_commands/LOAD.html)。

## LOCK

锁住一张表。

```
LOCK [TABLE] name [, ...] [IN lockmode MODE] [NOWAIT]
```

更多信息请参见[LOCK](http://docs.greenplum.org/6-4/ref_guide/sql_commands/LOCK.html)。

## MOVE

放置游标。

```
MOVE [ forward_direction {FROM | IN} ] cursorname
```

更多信息请参见[MOVE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/MOVE.html)。

## PREPARE

准备一个执行的语句。

```
PREPARE name [ (datatype [, ...] ) ] AS statement
```

更多信息请参见[PREPARE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/PREPARE.html)。

## REASSIGN OWNED

修改数据库角色。

```
REASSIGN OWNED BY old_role [, ...] TO new_role
```

更多信息请参见[REASSIGN OWNED](http://docs.greenplum.org/6-4/ref_guide/sql_commands/REASSIGN_OWNED.html)。

## REINDEX

重新构建索引。

```
REINDEX {INDEX | TABLE | DATABASE | SYSTEM} name
```

更多信息请参见[REINDEX](http://docs.greenplum.org/6-4/ref_guide/sql_commands/REINDEX.html)。

## RELEASE SAVEPOINT

销毁定义过的SAVEPOINT。

```
RELEASE [SAVEPOINT] savepoint_name
```

更多信息请参见[RELEASE SAVEPOINT](http://docs.greenplum.org/6-4/ref_guide/sql_commands/RELEASE_SAVEPOINT.html)。

## RESET

恢复系统配置参数的值为默认值。

```
RESET configuration_parameter

RESET ALL
```

更多信息请参见[RESET](http://docs.greenplum.org/6-4/ref_guide/sql_commands/RESET.html)。

## ROLLBACK

中止当前事务。

```
ROLLBACK [WORK | TRANSACTION]
```

更多信息请参见[ROLLBACK](http://docs.greenplum.org/6-4/ref_guide/sql_commands/ROLLBACK.html)。

## ROLLBACK TO SAVEPOINT

将当前事务回滚到某个SAVEPOINT。

```
ROLLBACK [WORK | TRANSACTION] TO [SAVEPOINT] savepoint_name
```

更多信息请参见[ROLLBACK TO SAVEPOINT](http://docs.greenplum.org/6-4/ref_guide/sql_commands/ROLLBACK_TO_SAVEPOINT.html)。

## SAVEPOINT

在当前事务定义一个新的SAVEPOINT。

```
SAVEPOINT savepoint_name
```

更多信息请参见[SAVEPOINT](http://docs.greenplum.org/6-4/ref_guide/sql_commands/SAVEPOINT.html)。

## SELECT INTO

从查询结果中定义一个新的表。

```
[ WITH with_query [, ...] ]
SELECT [ALL | DISTINCT [ON ( expression [, ...] )]]
    * | expression [AS output_name] [, ...]
    INTO [TEMPORARY | TEMP] [TABLE] new_table
    [FROM from_item [, ...]]
    [WHERE condition]
    [GROUP BY expression [, ...]]
    [HAVING condition [, ...]]
    [{UNION | INTERSECT | EXCEPT} [ALL] select]
    [ORDER BY expression [ASC | DESC | USING operator] [NULLS {FIRST | LAST}] [, ...]]
    [LIMIT {count | ALL}]
    [OFFSET start]
    [FOR {UPDATE | SHARE} [OF table_name [, ...]] [NOWAIT] 
    [...]]
```

更多信息请参见[SELECT INTO](http://docs.greenplum.org/6-4/ref_guide/sql_commands/SELECT_INTO.html)。

## SET

改变数据库配置参数的值。

```
SET [SESSION | LOCAL] configuration_parameter {TO | =} value | 
    'value' | DEFAULT}

SET [SESSION | LOCAL] TIME ZONE {timezone | LOCAL | DEFAULT}
```

更多信息请参见[SET](http://docs.greenplum.org/6-4/ref_guide/sql_commands/SET.html)。

## SET ROLE

设置当前会话当前角色的标识符。

```
SET [SESSION | LOCAL] ROLE rolename

SET [SESSION | LOCAL] ROLE NONE

RESET ROLE
```

更多信息请参见[SET ROLE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/SET_ROLE.html)。

## SET SESSION AUTHORIZATION

设置会话角色标识符和当前会话当前角色的标识符。

```
SET [SESSION | LOCAL] SESSION AUTHORIZATION rolename

SET [SESSION | LOCAL] SESSION AUTHORIZATION DEFAULT

RESET SESSION AUTHORIZATION
```

更多信息请参见[SET SESSION AUTHORIZATION](http://docs.greenplum.org/6-4/ref_guide/sql_commands/SET_SESSION_AUTHORIZATION.html)。

## SET TRANSACTION

设置当前事务的特征。

```
SET TRANSACTION [transaction_mode] [READ ONLY | READ WRITE]

SET SESSION CHARACTERISTICS AS TRANSACTION transaction_mode 
     [READ ONLY | READ WRITE]
```

更多信息请参见[SET TRANSACTION](http://docs.greenplum.org/6-4/ref_guide/sql_commands/SET_TRANSACTION.html)。

## SHOW

显示当前系统配置参数的值。

```
SHOW configuration_parameter

SHOW ALL
```

更多信息请参见[SHOW](http://docs.greenplum.org/6-4/ref_guide/sql_commands/SHOW.html)。

## START TRANSACTION

开始事务块。

```
START TRANSACTION [SERIALIZABLE | READ COMMITTED | READ UNCOMMITTED]
                  [READ WRITE | READ ONLY]
```

更多信息请参见[START TRANSACTION](http://docs.greenplum.org/6-4/ref_guide/sql_commands/START_TRANSACTION.html)。

## TRUNCATE

清空表的所有行。

```
TRUNCATE [TABLE] name [, ...] [CASCADE | RESTRICT]
```

更多信息请参见[TRUNCATE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/TRUNCATE.html)。

## UPDATE

更新表的行。

```
UPDATE [ONLY] table [[AS] alias]
   SET {column = {expression | DEFAULT} |
   (column [, ...]) = ({expression | DEFAULT} [, ...])} [, ...]
   [FROM fromlist]
   [WHERE condition | WHERE CURRENT OF cursor_name ]
```

更多信息请参见[UPDATE](http://docs.greenplum.org/6-4/ref_guide/sql_commands/UPDATE.html)。

## VACUUM

垃圾收集和选择性分析数据库。

```
VACUUM [FULL] [FREEZE] [VERBOSE] [table]

VACUUM [FULL] [FREEZE] [VERBOSE] ANALYZE
              [table [(column [, ...] )]]
```

更多信息请参见[VACUUM](http://docs.greenplum.org/6-4/ref_guide/sql_commands/VACUUM.html)。

## VALUES

计算一组行。

```
VALUES ( expression [, ...] ) [, ...]
   [ORDER BY sort_expression [ASC | DESC | USING operator] [, ...]]
   [LIMIT {count | ALL}] [OFFSET start]
```

更多信息请参见[VALUES](http://docs.greenplum.org/6-4/ref_guide/sql_commands/VALUES.html)。

