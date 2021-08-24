---
keyword: [输入组件, Hologres]
---

# 配置Hologres输入组件

Hologres输入组件用于读取Hologres数据源的数据。同步Hologres数据源的数据至其他数据源的场景中，您需要先配置Hologres输入组件读取的数据源，再配置数据同步的目标数据源。本文为您介绍如何配置Hologres输入组件。

-   已创建Hologres数据源并已申请Hologres数据源的同步读权限：
    -   如何创建数据源，请参见[创建Hologres数据源]()。
    -   如何申请数据源同步读权限，请参见[管理数据源权限](/cn.zh-CN/资产中心/权限管理/我的权限/管理数据源权限.md)。
-   已为Hologres数据源创建数据表。具体操作，请参见[表](/cn.zh-CN/连接开发工具/HoloWeb/连接管理/表.md)。

## 操作步骤

1.  请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)，进入离线单条管道脚本的开发页面。

2.  在离线单条管道脚本的开发页面，单击页面右上角的**组件库**。

3.  单击**输入**前的![dgd](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3593819951/p80354.png)图标。

4.  拖动**Hologres**组件至左侧的管道画布中。

5.  鼠标悬停至**Hologres**组件框内右键单击，选择**属性配置**。

6.  在**Hologres输入配置**对话框，配置参数。

    ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2079851261/p276514.png)

    |参数|说明|
    |--|--|
    |步骤名称|即Hologres输入组件的名称。Dataphin自动生成步骤名称，您也可以根据业务场景修改。命名规则如下：    -   只能包含汉字、字母、下划线（\_）、数字。
    -   不能超过64个字符。 |
    |数据源|选择Hologres类型的数据源。如果您还没有Hologres类型的数据源，单击![dfag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2193819951/p80969.png)图标，创建数据源。具体操作，请参见[t1995468.md\#]()。 |
    |表|选择Hologres数据源中的数据表。如果Hologres数据源中还没有数据表，则需要提前创建数据表。具体操作，请参见[表](/cn.zh-CN/连接开发工具/HoloWeb/连接管理/表.md)。 |
    |输入过滤|配置Hologres输入组件读取数据时需要过滤掉的数据。例如，`ID>112`。|
    |输出字段|输出字段区域展示Hologres读取到数据表的字段。同时，您也可以通过以下方式，删除已读取的字段：

    -   单击**操作**列下的![sgaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2193819951/p80971.png)图标，删除字段。
    -   单击**字段管理**，在**字段管理**页面，选择某个字段后，单击![sfsga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1293819951/p80985.png)图标，将**已选的输入字段**移入到**未选的输入字段**。

![gshsh](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/2079851261/p276507.png) |

7.  单击**确认**，完成Hologres输入组件的配置。


完成输入组件的配置后，即可配置数据同步的目标数据源。具体操作，请参见[配置离线单条管道](/cn.zh-CN/数据引入/数据集成/离线单条管道/配置离线单条管道.md)。

