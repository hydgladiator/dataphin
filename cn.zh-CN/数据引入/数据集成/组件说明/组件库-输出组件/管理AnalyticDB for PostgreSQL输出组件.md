---
keyword: [输出组件, AnalyticDB for PostgreSQL]
---

# 管理AnalyticDB for PostgreSQL输出组件

AnalyticDB for PostgreSQL输出组件用于向AnalyticDB for PostgreSQL数据源写入数据。同步其他数据源的数据至AnalyticDB for PostgreSQL数据源的场景中，完成源数据的信息配置后，需要配置AnalyticDB for PostgreSQL输出组件的目标数据源。本文为您介绍如何配置AnalyticDB for PostgreSQL输出组件。

-   获取待同步写的AnalyticDB for PostgreSQL相关信息：
    -   如何创建数据源，请参见[t1882929.md\#](/cn.zh-CN/数仓规划/数据源/关系型数据源/创建AnalyticDB for PostgreSQL数据源.md)。
    -   如何申请数据源同步写权限，请参见[管理数据源权限]()。
-   已为AnalyticDB for PostgreSQL数据源创建数据表。具体操作，请参见[数据表管理](/cn.zh-CN/数据管理/数据表管理.md)。

## 配置属性

1.  进入离线单条管道脚本的开发页面，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

2.  在离线单条管道脚本的开发页面，单击页面右上角的**组件库**。

3.  单击**输出**前的![dgd](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3593819951/p80354.png)图标。

4.  将**AnalyticDB for PostgreSQL**组件拖到左侧的管道画布中。

5.  将鼠标放置在**AnalyticDB for PostgreSQL**组件框内右键单击，选择**属性配置**。

6.  在**AnalyticDB for PostgreSQL输出配置**对话框，配置参数。

    ![test](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3882004261/p284491.png)

    |参数|说明|
    |--|--|
    |步骤名称|即AnalyticDB for PostgreSQL输出组件的名称。Dataphin自动生成步骤名称，您也可以根据业务场景修改。命名规则如下：    -   只能包含汉字、字母、下划线（\_）、数字。
    -   不能超过64个字符。 |
    |数据源|在数据源下拉列表中，展示所有AnalyticDB for PostgreSQL类型的数据源，包括您已拥有同步写权限的数据源和没有同步写权限的数据源。对于没有同步写权限的数据源，您可以数据源后的**申请**，申请数据源的同步写权限。具体操作，请参见[管理数据源权限]()。

![test](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3882004261/p284600.png)

如果您还没有AnalyticDB for PostgreSQL类型的数据源，单击![dfag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2193819951/p80969.png)图标，创建数据源。具体操作，请参见[新建Hologres数据源]()。 |
    |表|选择AnalyticDB for PostgreSQL数据源中的数据表为数据同步的目标表。如果AnalyticDB for PostgreSQL数据源中还没有数据表，您也可以执行如下步骤，简单快速的生成目标表：

    1.  单击**一键生成目标表**。
    2.  在代码输入框中，输入建表语句。代码示例如下所示。

        ```
CREATE TABLE IF NOT EXISTS datax_test
(order_id bigint comment '订单号',
`area` string comment '区域',
province string comment '省份',
city   string comment '城市',
product_type string comment '类型',
order_name string comment '客户名称',
report_date datetime comment '日期',
order_amt double comment '销售额')
PARTITIONED BY (  `ds` STRING);
        ```

    3.  单击**新建**，完成目标表的。

新建成功后的目标表默认为输出数据的目标表。 |
    |解析方案|解析方案用于自定义数据写入至AnalyticDB for PostgreSQL数据源前和数据写入至AnalyticDB for PostgreSQL数据源后的一些特殊处理。**解析方案**包括**填写准备语句**和**填写完成语句**：

    -   **填写准备语句**：导入前执行的SQL脚本。

例如，数据同步至AnalyticDB for PostgreSQL数据源前自定义数据清洗的规则。

    -   **填写完成语句**：导入后执行的SQL脚本。

例如，数据写入目标表A后，重命名目标表A为B。

**说明：** 如果**填写准备语句**中 |
    |输入字段|展示从源表中读取的字段。|
    |输出字段|展示目标表的字段。|
    |快速映射|映射关系用于将源表的输入字段和目标表的输出字段映射起来。映射关系包括同名映射和同行映射。适用场景说明如下：    -   同名映射：对字段名称相同的字段进行映射。

如下图所示，选择同名映射后，输入**id**字段对应的数据映射到输出字段的**id**中。

![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7079022261/p278674.png)

    -   同行映射：源表和目标表的字段名称不一致，但字段对应行的数据需要映射。只映射同行的字段。

例如，**endpoint\_type**字段对应的数据映射至**id**字段中。

![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7079022261/p278672.png) |

7.  单击**确认**，完成AnalyticDB for PostgreSQL输出组件的配置。

    完成输出组件的配置后，即可配置离线单条管道的调度参数。具体操作，请参见[配置离线单条管道]()。


