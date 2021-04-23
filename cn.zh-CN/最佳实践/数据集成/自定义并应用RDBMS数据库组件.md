---
keyword: 自定义并应用RDBMS数据库组件
---

# 自定义并应用RDBMS数据库组件

为了满足不同业务场景数据集成的诉求，Dataphin支持用户自定义当前系统不支持的RDBMS数据库（关系型数据库）类型的组件。您只需要准备关系型数据库的驱动，即可自定义RDBMS数据库类型的组件。本教程以MySQL为例，为您介绍如何自定义RDBMS数据库类型的组件。

-   已开通RDS MySQL实例，且网络类型为专有网络（VPC）。如何开通RDS MySQL实例，请参见[创建RDS MySQL实例](/cn.zh-CN/RDS MySQL 数据库/快速入门/创建RDS MySQL实例.md)。
-   已创建RDS MySQL实例的数据库和账号，创建过程中需要您记录数据库名称、用户名和密码。如何创建数据库和账号，请参见[创建数据库和账号](/cn.zh-CN/RDS MySQL 数据库/快速入门/创建数据库和账号.md)。

RDBMS数据库即关系型数据库，包括MySQL、Oracle、SQL Server、PostgreSQL、Vertica、DRDS、DB2、OceanBase、PolarDB、SAP HANA和TeraData。本教程以MySQL为例，带您体验自定义及应用RDBMS数据库类型的组件。

## 操作流程

自定义并应用MySQL数据库组件的流程，如下图所示。

![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2066898161/p265938.png)

|步骤|描述|
|--|--|
|[步骤一：下载自定义MySQL数据库组件的驱动](#section_o6r_tey_soe)|获取自定义MySQL数据库组件驱动。|
|[步骤二：配置网络和创建数据表](#section_1sc_acd_hl5)|在您开始自定义并应用RDBMS数据库组件前，需要配置RDS MySQL实例和Dataphin间的网络，及创建同步数据的源表和目标表。|
|[步骤三：创建自定义组件](#section_cau_eug_2kr)|自定义组件的类型为**test\_rdbms\_mysql**。完成定义后，即可在组件库的开发模块下查询到自定义的组件。|
|[步骤四：创建数据源实例](#section_ca2_5zq_wnw)|基于自定义的组件类型（**test\_rdbms\_mysql**），创建**TEST\_RDBMS\_MYSQL**类型的数据源实例。完成创建数据源实例后，即可将RDS MySQL实例的业务数据引入至Dataphin实例。|
|[步骤五：创建离线管道任务](#section_ee6_xy6_9ld)|基于自定义的组件类型（**test\_rdbms\_mysql**）和数据源实例（**test\_rdbms\_mysql**），创建离线管道任务。完成离线管道任务的创建后，即可运行离线管道任务，以实现数据的集成（同步数据）。|
|[步骤六：生产环境中运行离线管道任务](#section_idc_cq7_3pq)|在生产环境运行离线管道任务，保障生产环境业务数据的正常产出。|

## 步骤一：下载自定义MySQL数据库组件的驱动

请下载MySQL数据库的[驱动](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/206129/cn_zh/1618542516387/mysql-connector-java-5.1.47.jar)。

## 步骤二：配置网络和创建数据表

-   连通RDS MySQL实例与Dataphin实例间的网络。
    -   添加RDS MySQL实例的外网地址和端口至Dataphin项目空间的沙箱白名单：
        1.  获取RDS MySQL实例的外网地址、端口。

            进入[数据库连接](https://rdsnext.console.aliyun.com/rdsList/basic)页面，获取RDS MySQL实例的外网地址和端口。

            ![faga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5508909161/p267366.png)

        2.  添加RDS MySQL实例的外网地址和端口至Dataphin项目空间的沙箱白名单。如何添加沙箱白名单，请参见[添加沙箱白名单](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。
    -   添加Dataphin的IP至RDS MySQL实例的白名单。如何添加Dataphin的IP至RDS MySQL实例的白名单，请参见[设置IP白名单](/cn.zh-CN/RDS MySQL 数据库/快速入门/设置白名单/设置IP白名单.md)。

        |地域|IP白名单|
        |--|-----|
        |华东2（上海）|100.104.228.128/26、100.104.115.192/26|
        |华南1（深圳）|100.104.48.128/26|
        |华北2（北京）|100.104.238.64/26|
        |华东2（上海）、华南1（深圳）、华北2（北京）|100.104.0.0/16|

-   创建同步数据的源数据表和目标数据表。

    使用命令行方式连接MySQL实例，连接后创建同步数据的源数据表和目标数据表。如何连接MySQL实例，请参见[方法三：使用命令行方式连接实例](/cn.zh-CN/RDS MySQL 数据库/快速入门/连接MySQL实例.md)。

    -   创建源数据表的代码示例如下。

        ```
        create table xin_test_scr2
        (
        id string,
        name string
        );
        insert into xin_test_scr2 values('1001','huayu1'),('1002','huayuyu2'),('1003','huayuyu3'),('1004','huayuyu4'),('1005','huayuyu5'),('1006','huayuyu6'),('1007','huayuyu7'),('1008','huayuyu8'),('1009','huayuyu9'),('1010','huayuyu10'),('1011','huayuyu11'),('1012','huayuyu12'),('1013','huayuyu13'),('1014','huayuyu14'),('1015','huayuyu15'),('1016','huayuyu16'),('1017','huayuyu17'),('1018','huayuyu18'),('1019','huayuyu19'),('1021','huayuyu21'),('10022','huayuyu22'),('1023','huayuyu23');
        ```

    -   创建目标数据表的代码示例如下。

        ```
        create table xin_test_det_1
        (    
        id string,    
        name string
        );
        ```


## 步骤三：创建自定义组件

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  进入**自定义组件**页面。

    1.  在Dataphin首页，单击**研发**。

    2.  在数据**开发**页面，单击项目名称后的![test](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3497549951/p110384.png)图标，选择数据开发的项目空间（**Dev**项目）。

        如果您当前访问的是**Dev**项目，且项目空间为您的数据开发空间，则不需要选择项目空间。

    3.  在数据**开发**页面，将鼠标悬停在顶部菜单栏的**开发**上，单击**集成**。

    4.  在数据**集成**页面，单击左侧导航栏的![gagaG](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9228073061/p176621.png)图标。

4.  在**自定义组件**页面，单击![gagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2066898161/p264477.png)图标。

5.  在**新建自定义组件**页面，配置参数。

    ![fagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2066898161/p264485.png)

    |区域|参数|描述|
    |--|--|--|
    |基本信息|类型|选择**类型**为**RDBMS数据库**。|
    |名称|填写**名称**为**test\_rdbms\_mysql**。**说明：** 因为名称定义了自定义组件的类型，所以系统不支持创建相同名称的自定义组件。 |
    |描述|填写对自定义组件的简单描述。例如，自定义组件测试。|
    |选择目录|自定义组件的默认目录为**自定义组件**。|
    |资源信息|驱动名称|填写**驱动名称**为**com.mysql.jdbc.Driver**。|
    |文件上传|上传已下载的驱动文件（**mysql-connector-java-5.1.47**）。|

6.  单击**提交**。

7.  在**提交备注**对话框中，填写备注信息。

8.  单击**确定并提交**，完成自定义组件的提交。

9.  发布自定义组件至生产环境。

    1.  在**数据集成**页面，单击顶部菜单栏的**发布**。

    2.  在**待发布对象列表**页面的**管道脚本**页签，

    3.  选择**管道脚本**页签，选中**test\_rdbms\_mysql**后单击**操作**列下的![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2066898161/p264574.png)图标。

        ![fagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2066898161/p264567.png)

    4.  在**发布**对话框，填写发布名称或备注信息后，单击**确定**，即可将自定义组件发布至生产环境。

    5.  单击左侧导航栏的**发布记录列表**。在**发布记录列表**页面，查看自定义组件的发布状态为**发布成功**即可。

        ![dagga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3066898161/p265400.png)


## 步骤四：创建数据源实例

1.  在**数据集成**页面，鼠标选停至![afgagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3066898161/p264656.png)图标后，单击**规划**。

2.  在数仓**规划**页面，单击左侧导航栏的**数据源**。

3.  在**数据源**页面，单击页面右上角的**新建数据源**。

4.  在**新建数据源**对话框，选择**TEST\_RDBMS\_MYSQL**类型的数据源。

5.  在**新建TEST\_RDBMS\_MYSQL数据源**对话框，配置参数。

    ![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3066898161/p264665.png)

    |参数|描述|
    |--|--|
    |**数据源名称**|填写**数据源名称**为**test\_rdbms\_mysql**。|
    |**数据源描述**|填写数据源的简单描述。|
    |**数据源配置**|配置数据源：     -   如果开发模式是Basic模式，则选择**生产数据源**。
    -   如果开发模式是Dev-Prod模式，则可以通过以下方式配置数据源：
        -   单击**生产+开发数据源**，配置生产环境和开发环境的数据源。
        -   单击**生产数据源**，配置生产数据源。完成生产数据源的创建后，单击**开发数据源**，配置开发环境的数据源。

![fagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6278209951/p93912.png)

**说明：** 系统支持配置**生产数据源**和**开发数据源**为相同的数据源，也可以配置为不同的数据源。 |
    |**生产数据源**或**生产+开发数据源**|**链接地址**|填写数据源的链接地址。链接地址的格式为`jdbc:mysql://{Public Endpoint}:3306/{DatabaseName}`：

    -   \{Public Endpoint\}：外网地址。
    -   \{DatabaseName\}：数据库名称。 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|

    **说明：** 自定义类型数据源不支持连接测试，请您务必保证数据源连接信息的准确性。

6.  单击**确定**。


## 步骤五：创建离线管道任务

1.  在**数据源**页面，鼠标选停至![afgagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3066898161/p264656.png)图标后，单击**研发**。

2.  在数据**开发**页面，鼠标选停至**开发**，单击**集成**。

3.  创建管道开发脚本。

    1.  在数据**集成**的**离线管道**页面，鼠标悬停至![gagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3066898161/p264982.png)图标后，单击**离线单条管道**。

    2.  在**创建管道开发脚本**对话框，配置参数。

        ![fGag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3066898161/p264986.png)

        |参数|描述|
        |--|--|
        |管道名称|**管道名称**填写为**test**。|
        |调度类型|**调度类型**选择为**手动节点**。|
        |描述|填写简单的描述。例如，**测试自定义组件**。|
        |选择目录|默认为**离线管道**。|

    3.  单击**确定**。

4.  开发离线管道任务。

    1.  在**test**离线管道页面，单击页面右上角的![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3066898161/p265010.png)图标后，单击**开放**前的![dgd](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3593819951/p80354.png)图标。

    2.  拖动组件**test\_rdbms\_mysql\_输入**和**test\_rdbms\_mysql\_输出**至左侧的管道画布中。

        ![faga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2066898161/p266063.png)

    3.  鼠标选停至**test\_rdbms\_mysql\_输入**组件框内右键单击后，单击**属性配置**。

    4.  在**test\_rdbms\_mysql\_输入输入配置**对话框，配置输入参数。

        ![gagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3066898161/p265295.png)

        |参数|描述|
        |--|--|
        |步骤名称|本教程中保持默认。您也可以修改名称。步骤名称命名规则如下：

        -   只能包括字母、数字和短划线（-）。
        -   长度为64字符以内。 |
        |数据源|选择**test\_rdbms\_mysql**。|
        |表|填写来源表为**xin\_test\_src2**。|
        |输入过滤|本教程中无需配置。输入过滤即填写输入字段的过滤信息，例如`ds=${bizdate}`。**输入过滤**适用于以下两种场景：

        -   固定的某一部分数据。
        -   参数过滤。 |
        |输出字段|输出字段即需要同步数据的字段。本教程中添加源表**xin\_test\_scr2**中的**id**和**name**字段为输入组件的输出字段：        1.  在**输出字段**区域，单击**新建输出字段**。
        2.  填写**输出字段**为**id**，**类型**选择为**String**。
        3.  单击**新建输出字段**。
        4.  填写**输出字段**为**name**，**类型**选择为**String**。 |

    5.  单击**确认**。

    6.  单击输入组件中的①后拖动并指向输出组件中的②处，形成有向连线。

        ![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3066898161/p263210.png)

    7.  鼠标选停至**test\_rdbms\_mysql\_输出**组件框内右键单击后，单击**属性配置**。

    8.  在**test\_rdbms\_mysql\_输出输出配置**对话框，配置输出参数。

        ![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p265362.png)

        |参数|描述|
        |--|--|
        |步骤名称|本教程中保持默认。您也可以修改名称。步骤名称命名规则如下：

        -   只能包括字母、数字和短划线（-）。
        -   长度为64字符以内。 |
        |数据源|选择**test\_rdbms\_mysql**。|
        |表|填写目标表为**xin\_test\_dst\_1**。|
        |解析方案|本教程中无需选择。解析方案为非必填项。选择数据输出前和输出完成的一些特殊处理方式。**解析方案**包括**填写准备语句**和**填写完成语句**：

        -   **填写准备语句**：导入前执行的SQL脚本。
        -   **填写完成语句**：导入后执行的SQL脚本。 |
        |输入字段|默认展示输入组件中配置的输出字段。|
        |输出字段|输出字段即需要同步数据的字段。本教程中添加源表**xin\_test\_scr2**中的**id**和**name**字段为输出组件的输出字段：        1.  在**输出字段**区域，单击**新建输出字段**。
        2.  填写**输出字段**为**id**，**类型**选择为**String**。
        3.  单击**新建输出字段**。
        4.  填写**输出字段**为**name**，**类型**选择为**String**。 |
        |映射关系|单击**快速映射**后，选择**同名映射**。映射关系指的是输入组件的输出字段和输出组件的输出字段间的映射关系。映射关系包含同名映射和同行映射：

        -   同名映射：映射字段名称相同的字段。
        -   同行映射：映射同行的字段。同行映射后，输入字段为最终的输出字段。 |

    9.  单击**确认**。

5.  单击离线管道**test**页面上方的**执行**，执行离线管道任务，查看任务是否正常执行。

    执行后的结果如下，读取和写入的数据均为23，表示任务运行正常。

    ![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p265372.png)

6.  单击页面右上方的![dggd](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6783819951/p80823.png)图标，提交管道脚本。

7.  在**提交备注**对话框，填写备注信息。

8.  单击**确定并提交**。

9.  发布离线管道任务至生产环境。

    1.  在**数据集成**页面，单击顶部菜单栏的**发布**。

    2.  在**待发布对象列表**页面的**管道脚本**页签，

    3.  选择**管道脚本**页签，选中**test**后单击**操作**列下的![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2066898161/p264574.png)图标。

        ![gagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p265435.png)

    4.  在**发布**对话框，填写发布名称或备注信息后，单击**确定**，即可将离线管道任务发布至生产环境。

    5.  单击左侧导航栏的**发布记录列表**。在**发布记录列表**页面，查看离线管道任务的发布状态为**发布成功**即可。

        ![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3957419161/p265441.png)


## 步骤六：生产环境中运行离线管道任务

1.  在数据**集成**页面，单击顶部菜单栏的**运维**。

2.  在运维中心，运行离线管道任务。

    1.  单击左侧导航栏的![dGFg](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p265816.png)图标。

    2.  在**手动任务运维列表**页面，单击离线管道任务**test**。

        ![gaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p263271.png)

    3.  在离线管道任务**test**的详情页面，单击页面左上角的**运行**。

    4.  在**运行**对话框，保持默认参数，单击**确定**。

3.  查看离线管道任务运行生成的实例运行日志。

    1.  单击左侧导航栏的![gagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p265824.png)图标。

    2.  在**手动实例运维列表**页面，单击离线管道实例**test**。

        ![gagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p263284.png)

    3.  在离线管道实例**test**的详情页面，单击页面上方的**查看运行日志**。

    4.  在**运行日志**页面，查看**读出记录总数**和**写出记录总数**。

        生产环境管道实例运行日志中的读取记录总数、写入记录总数，与开发环境管道任务运行结果的读取总数、写入总数保持一致（均为23）。这样离线管道任务在生产环境可以正常运行，即可保障生产环境业务数据正常产出。

        ![dgaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p263286.png)


