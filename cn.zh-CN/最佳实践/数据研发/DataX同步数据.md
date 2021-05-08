---
keyword: DataX同步数据
---

# DataX同步数据

DataX是异构数据源离线同步的工具，支持多种异构数据源之间高效的数据同步。Dataphin系统内嵌了DataX组件，支持通过构建Shell任务调用DataX，实现数据同步。本教程以RDS MySQL数据库为例，为您介绍基于Dataphin如何调用DataX同步数据。

-   已开通RDS MySQL实例，且RDS MySQL实例的网络类型为专有网络。如何开通RDS MySQL实例，请参见[创建RDS MySQL实例](/cn.zh-CN/RDS MySQL 数据库/快速入门/创建RDS MySQL实例.md)。
-   已创建RDS MySQL实例的数据库和账号，创建过程中需要您记录数据库名称、用户名和密码。如何创建数据库和账号，请参见[创建数据库和账号](/cn.zh-CN/RDS MySQL 数据库/快速入门/创建数据库和账号.md)。

Dataphin系统内嵌了DataX组件，在Dataphin中创建和运行DataX任务（Shell任务）即可将DataX调用起来，以实现数据同步。

DataX支持同步数据的数据源包括MySQL、Oracle、SQL Server、PostgreSQL、HDFS、Hive、HBase等。DataX的更多信息，请参见[DataX](https://github.com/alibaba/DataX?spm=a2c4g.11186623.2.22.6ee76324XCkyEG)。

## 使用限制

Shell任务不支持通过内网地址访问RDS MySQL实例。

## 操作流程

|功能|描述|
|--|--|
|[步骤一：连通RDS MySQL实例与Dataphin间的网络](#section_fl8_1p1_o24)|在您开始同步数据前，首先需要连通RDS MySQL实例和Dataphin间的网络。|
|[步骤二：创建数据同步的源表和目标表](#section_7o6_vhv_l4v)|登录至RDS MySQL实例，创建本教程中用于数据同步的源表和目标表。|
|[步骤三：下载并配置DataX任务的代码模板](#section_xd9_9cs_0ux)|下载并配置DataX任务的代码模板后，保存为**datax.json**。|
|[步骤四：上传datax.json文件至Dataphin](#section_omb_41d_zth)|上传DataX任务代码文件至Dataphin平台后，DataX任务即可调用。|
|[步骤五：创建DataX任务](#section_x8g_2ct_8ef)|在开发环境创建并运行同步数据的DataX任务。|
|[步骤六：运行生产环境中的DataX任务](#section_aoa_rco_skn)|在生产环境运行DataX任务，保障生产环境业务数据的正常产出。|

## 步骤一：连通RDS MySQL实例与Dataphin间的网络

1.  申请RDS MySQL实例的外网地址。如何申请外网地址，请参见[申请或释放外网地址](/cn.zh-CN/RDS MySQL 数据库/数据库连接/申请或释放外网地址.md)。

2.  在[数据库连接](https://rdsnext.console.aliyun.com/rdsList/basic)页面，获取RDS MySQL实例的外网地址和端口。

    ![faga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5508909161/p267366.png)

3.  添加RDS MySQL实例的外网地址和端口至Dataphin项目空间的沙箱白名单。如何添加沙箱白名单，请参见[添加沙箱白名单](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

4.  添加`0.0.0.0/0`至RDS MySQL实例的白名单。如何添加白名单，请参见[设置IP白名单](/cn.zh-CN/RDS MySQL 数据库/快速入门/设置白名单/设置IP白名单.md)。

    **说明：** 完成数据同步后，请立即删除`0.0.0.0/0`。


## 步骤二：创建数据同步的源表和目标表

使用命令行方式连接RDS MySQL实例，请参见[方法三：使用命令行方式连接实例](/cn.zh-CN/RDS MySQL 数据库/快速入门/连接MySQL实例.md)。创建同步数据的源数据表和目标数据表：

1.  创建源数据表的代码示例如下。

    ```
    create table datax_test1( area varchar(255),province varchar(255) );
    insert into datax_test1 values('华北','山东省'),('华南','河南省');
    ```

2.  创建目标数据表的代码示例如下。

    ```
    create table datax_test2( area varchar(255),province varchar(255) );
    ```


## 步骤三：下载并配置DataX任务的代码模板

1.  下载DataX任务的[代码模板](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/170609/cn_zh/1607656169263/datax)。

2.  配置代码模板中的如下参数后，保存为**datax.json**至本地。

    |参数|描述|
    |--|--|
    |\{username\}|配置为已创建RDS MySQL实例的用户名，即登录数据库的用户名。|
    |\{password\}|登录数据库的密码。本教程中配置为前提条件已创建RDS MySQL实例的密码，即登录数据库的密码。|
    |\{\{Public Endpoint\}:\}|链接地址。本教程配置为已获取的RDS MySQL实例的外网地址。|
    |\{DatabaseName\}|数据库名称。本教程配置为前提条件中已创建的RDS MySQL实例的数据库名称。|
    |\{table\_name1\}|源数据表的表名。本教程配置为datax\_test1。|
    |\{table\_name2\}|目标数据表的表名。本教程配置为datax\_test2。|
    |\{columnname1\}|数据同步的字段。本教程配置为area。|
    |\{columnname2\}|数据同步的字段。本教程配置为province。|

    代码模板的代码如下。

    ```
    {
        "job": {
            "content": [
                {
                    "reader": {
                        "name": "mysqlreader",
                        "parameter": {
                            "column": [
                                "{columnname1}",
                                "{columnname2}"
                            ],
                            "connection": [
                                {
                                    "jdbcUrl":
    ["jdbc:mysql://{Public Endpoint}:3306/{DatabaseName}"],
                                    "table": ["{table_name1}"]
                                }
                            ],
                            "password": "{password}",        
                            "username": "{username}"
                        }
                    },
                    "writer": {
                        "name": "mysqlwriter",
                        "parameter": {
                            "column": [
                            "{columnname1}",
                            "{columnname2}"
                            ],
                            "connection": [
                                {
                                    "jdbcUrl":
    "jdbc:mysql://{Public Endpoint}:3306/{DatabaseName}",
                                    "table": ["{table_name2}"]
                                }
                            ],
                            "password": "{password}",        
                            "username": "{username}"
                        }
                    }
                }
            ],
            "setting": {
                "speed": {
                    "channel": "1"
                }
            }
        }
    }
    ```


## 步骤四：上传**datax.json**文件至Dataphin

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  在Dataphin首页，单击**研发**。

4.  在数据**开发**页面，单击**数据处理**。

5.  在**数据处理**页面的左侧导航栏，单击![资源管理](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2987549951/p96911.png)**资源管理**图标。

6.  在**资源管理**页面，单击**资源管理**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72394.png)图标。

7.  在**新建资源**对话框中，配置参数后，单击**提交**。

    ![gagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9383767061/p184797.png)

    |参数|描述|
    |--|--|
    |**类型**|本教程中需要上传的文件格式为JSON，则类型选择**others**。

系统支持选择的类型包括**file**、**jar**、**python**和**others**，适用场景说明如下：

    -   上传的文件格式为XLS、DOC、TXT、CSV，则类型选择为**file**。
    -   上传的文件格式为JAR，则类型选择为**jar**。
    -   上传的文件格式为PY，则类型选择为**python**。
    -   上传的文件格式非XLS、DOC、TXT、CSV、JAR、PY，则类型选择为**others**。 |
    |**名称**|本教程中的名称为**datax.json**。本教程名称的命名规则如下：

    -   名称必须以.json结尾。
    -   字母、数字、下划线（\_）或半角句号（.）组合组成。
    -   不能以数字开头。 |
    |**描述**|填写资源的描述，例如DataX test。|
    |**上传文件**|选择[步骤三：下载并配置DataX任务的代码模板](#section_xd9_9cs_0ux)中保存至本地的**datax.json**文件。|
    |**计算类型**|本教程中上传的资源（**datax.json**）用于DataX代码任务中引用，因此选择**无归属引擎**。计算类型用于定义资源文件是否需要上传至计算引擎的存储层。Dataphin系统支持的计算类型包括**MaxCompute**、**Flink**和**无归属引擎**，适用场景说明如下：

    -   自定义MaxCompute类型的函数时，**计算类型**选择为**MaxCompute**。
    -   自定义Flink类型的函数时，**计算类型**选择为**Flink**。
    -   代码任务引用的资源文件，**计算类型**选择为**无归属引擎**。 |
    |**选择目录**|默认为**资源管理**。|

8.  在**提交备注**对话框，填写备注信息后，单击**确定并提交**。

9.  发布资源文件至生产环境。

    1.  在**数据开发**页面，单击顶部菜单栏的**发布**。

    2.  在**待发布对象列表**页面，单击**数据处理**页签。

    3.  在**数据处理**页签，单击**datax.json**资源的**操作**列下的![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2066898161/p264574.png)图标。

        ![faga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7495339161/p267669.png)

    4.  在**发布**对话框，填写发布名称或备注信息后，单击**确定**，即可将资源文件发布至生产环境。

    5.  单击左侧导航栏的**发布记录列表**。在**发布记录列表**页面，查看资源文件的发布状态为**发布成功**即可。

        ![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7495339161/p267671.png)


## 步骤五：创建DataX任务

1.  请参见[步骤四：上传datax.json文件至Dataphin](#section_omb_41d_zth)，进入数据**开发**页面。

2.  在数据**开发**页面，单击左侧区域的**数据处理**。

3.  在**数据处理**页面，单击左侧导航栏![agaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8980863061/p176215.png)**计算任务**图标。

4.  在**计算任务**页面，单击**计算任务**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72394.png)图标，选择**通用脚本** \> **SHELL**。

5.  在**新建文件**对话框，配置参数后，单击**确定**。

    ![gagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7495339161/p267672.png)

    |参数|描述|
    |--|--|
    |**名称**|本教程中的名称为**DataX**。|
    |**调度类型**|本教程中选择任务的调度类型为**手动节点**。调度类型用于定义任务发布至生产环境的调度方式。Datpahin系统支持的调度类型包括**周期性节点**和**手动节点**，适用场景说明如下：

    -   任务需要参与系统的周期性调度，且需要依赖上游节点，则**调度类型**选择为**周期性节点**。
    -   任务不需要参与系统的周期性调度，且需要依赖上游节点，则**调度类型**选择为**手动节点**。该类型的任务在生产环境的运行需要您手动触发。 |
    |**描述**|填写对任务的简单描述，例如测试DataX。|
    |**选择目录**|默认为**计算任务**。|

6.  在代码编写页面，编写并运行DataX任务的代码。

    代码如下。

    ```
    @resource_reference{"datax.json"}
    python $DATAX_HOME/bin/datax.py datax.json #Dataphin系统已内置DataX的安装目录为DATAX_HOME/bin/datax.py。
    ```

    其中，resource\_reference\{\}用于调用已上传的**datax.json**资源文件。

7.  单击页面右上角的**执行**，即可运行DataX任务。

    运行结果显示的读写失败总数为0时，表示DataX任务同步数据成功。

    ![gaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7495339161/p267726.png)

8.  发布DataX任务至生产环境。

    1.  在**计算任务**页面，单击顶部菜单栏的**发布**。

    2.  在**待发布对象列表**页面，单击**数据处理**页签。

    3.  在**数据处理**页签，单击**DataX**任务的**操作**列下的![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2066898161/p264574.png)图标。

        ![gsahs](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7495339161/p267729.png)

    4.  在**发布**对话框，填写发布名称或备注信息后，单击**确定**，即可将DataX任务发布至生产环境。

    5.  单击左侧导航栏的**发布记录列表**。在**发布记录列表**页面，查看DataX任务的发布状态为**发布成功**即可。

        ![fagagh](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7495339161/p267730.png)


## 步骤六：运行生产环境中的DataX任务

1.  请参见[步骤四：上传datax.json文件至Dataphin](#section_omb_41d_zth)，进入数据**开发**页面。

2.  在数据**开发**页面，单击顶部菜单栏的**运维**。

3.  在**运维**中心，单击项目名称后的![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8495339161/p267741.png)图标，切换至生产环境（![rqgqag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8495339161/p267746.png)）。

4.  在**运维**中心，运行DataX任务。

    1.  单击左侧导航栏的![dGFg](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p265816.png)图标。

    2.  在**手动任务运维列表**页面，单击**DataX**任务。

    3.  在**DataX**任务的详情页面，单击页面左上角的**运行**。

        ![gaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8495339161/p267749.png)

    4.  在**运行**对话框，保持默认参数，单击**确定**。

5.  查看DataX任务运行生成的实例运行日志。

    1.  单击左侧导航栏的![gagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4066898161/p265824.png)图标。

    2.  在**手动实例运维列表**页面，单击**DataX**任务。

    3.  在**DataX**任务的详情页面，单击页面上方的**查看运行日志**。

        ![faga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8495339161/p267747.png)

    4.  在**运行日志**页面，查看**读写失败总数**。

        运行日志显示的读写失败总数为0时，表示DataX任务在生产环境同步数据成功，即可保障生产环境业务数据正常产出。

        ![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8495339161/p267744.png)


