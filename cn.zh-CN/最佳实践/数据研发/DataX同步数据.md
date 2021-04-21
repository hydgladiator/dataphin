# DataX同步数据

DataX是异构数据源离线同步的工具，支持多种异构数据源之间高效的数据同步。Dataphin系统内嵌了DataX组件，支持通过构建Shell任务调用DataX，实现数据同步。本教程以MySQL数据库为例，为您介绍基于Dataphin如何调用DataX同步数据。

开通RDS MySQL，详情请参见[RDS实例购买指南](/cn.zh-CN/快速入门/RDS实例购买指南.md)。创建RDS MySQL实例过程中，需要您记录数据库名称、用户名和密码。

DataX支持同步数据的数据源包括 MySQL、Oracle、SQL Server、PostgreSQL、HDFS、Hive、HBase等。有关DataX更多信息，请参见[DataX](https://github.com/alibaba/DataX?spm=a2c4g.11186623.2.22.6ee76324XCkyEG)。

## 准备工作

在您开始同步数据前，需要登录至RDS MySQL实例，创建同步数据的源表和目标表、获取实例的外网地址。同时，为了实现RDS MySQL实例和Dataphin之间的网络互通，需要将RDS MySQL实例的外网地址加入项目空间的沙箱白名单中，Dataphin的IP加入至 RDS MySQL实例的白名单中。

-   使用DMS工具连接实例，详情请参见[方法一：使用DMS工具连接实例（推荐）](/cn.zh-CN/RDS MySQL 数据库/快速入门/连接MySQL实例.md)，获取RDS MySQL的外网地址。

    ![test](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7043857061/p185011.png)

-   使用命令行方式连接实例，详情请参见[方法三：使用命令行方式连接实例](/cn.zh-CN/RDS MySQL 数据库/快速入门/连接MySQL实例.md)。创建同步数据的源数据表和目标数据表。

    创建源数据表的代码示例如下。

    ```
    create table 'datax_test1'( 'area' varchar(255),'province' varchar(255) );
    insert into datax_test1 values('华北','山东省'),('华南','河南省');
    ```

    创建目标数据表的代码示例如下。

    ```
    create table 'datax_test2'( 'area' varchar(255),'province' varchar(255) );
    ```

-   添加访问地址外网地址和端口3306至项目空间的沙箱白名单，详情请参见[添加沙箱白名单](/cn.zh-CN/数仓规划/管理项目空间的权限和计算源.md)。

    RDS ID为RDS MySQL的实例ID。

-   添加Dataphin的IP至RDS MySQL的白名单，详情请参见[设置IP白名单](/cn.zh-CN/RDS MySQL 数据库/快速入门/设置白名单/设置IP白名单.md)。
    -   如果数据源使用了VPC网络，则Dataphin的IP白名单见下表。

        |地域|IP白名单|
        |--|-----|
        |华东2（上海）|100.104.228.128/26、100.104.115.192/26|
        |华南1（深圳）|100.104.48.128/26|
        |华北2（北京）|100.104.238.64/26|
        |所有地域|100.104.0.0/16|

    -   如果数据源公网数据库或数据源使用了公网IP，则Dataphin的IP白名单见下表。

        |地域|IP白名单|
        |--|-----|
        |华东2（上海）|47.102.151.182|
        |华南1（深圳）|119.23.173.65|
        |华北2（北京）|123.56.104.202|

-   请您下载DataX任务代码的配置模板（[JSON文件](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/170609/cn_zh/1607656169263/datax)）。

## 步骤一：编辑JSON文件

编辑已下载的JSON文件，配置模板的代码。

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

其中，

-   \{username\}：登录数据库的用户名
-   \{password\}：登录数据库的密码
-   \{\{Public Endpoint\}:\}：外网地址
-   \{DatabaseName\}：数据库名称
-   \{table\_name1\}：源数据表的表名
-   \{table\_name2\}：目标数据表的表名
-   \{columnname1\}、\{columnname2\}：字段名

以上参数需要替换为准备工作中已创建数据库的对应信息，同时根据业务情况可以增删同步的字段，保存修改后的JSON文件至本地。

## 步骤二：上传JSON文件

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  进入**资源管理**页面。

    1.  在Dataphin首页，单击**研发**。

    2.  在数据**开发**页面，单击**数据处理**。

    3.  在左侧导航栏，单击![资源管理](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2987549951/p96911.png)**资源管理**图标。

4.  在**资源管理**页面，单击**资源管理**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72394.png)图标。

5.  在**新建资源**对话框中，配置参数。

    ![gagaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9383767061/p184797.png)

    |参数|描述|
    |--|--|
    |**类型**|选择**others**。|
    |**名称**|填写资源名称，例如datax.json。**说明：** 名称必须以.json结尾。 |
    |**描述**|填写资源的描述，例如DataX test。|
    |**上传文件**|选择本地的datax.json文件。|
    |**计算类型**|选择**无归属引擎**。**说明：** DataX的资源存储至Dataphin系统，因此仅支持选择**无归属引擎**。 |
    |**选择目录**|默认为**资源管理**。|

6.  单击**提交**，完成资源的提交。

7.  在**提交备注**对话框，填写备注信息。

8.  单击**确定并提交**。


## 步骤三：创建DataX任务

1.  在**数据处理**页签，单击左侧导航栏![agaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8980863061/p176215.png)**计算任务**图标。

2.  在**计算任务**页面，单击**计算任务**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72394.png)图标，选择**通用脚本** \> **SHELL**。

3.  在**新建文件**对话框，配置参数。

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9097549951/p72228.png)

    |参数|描述|
    |--|--|
    |**名称**|填写计算任务的名称为DataX。|
    |**调度类型**|选择任务的调度类型为**周期性节点**。|
    |**描述**|填写对任务的简单描述。|
    |**选择目录**|选择DataX任务所在的目录。|

4.  单击**确定**。


## 步骤四：编写并运行DataX任务代码

1.  在代码编写页面，编写运行DataX任务的代码。

    代码如下。运行代码节点的默认资源大小为256 MB。

    ```
    @resource_reference{"datax.json"}
    python $DATAX_HOME/bin/datax.py datax.json
    ```

    如果DataX任务的资源大于256 MB，建议使用如下代码，自定义所需资源大小。

    ```
    @required_resource{required_memory=2GB;required_cpus=1.0}
    @resource_reference{"datax.json"}
    python $DATAX_HOME/bin/datax.py --jvm '-Xms2g -Xmx2g' datax.json
    ```

    其中，

    -   required\_resource\{\}，自定义所需的资源大小。
    -   系统已内置DataX\_Home为DataX的安装目录（DATAX\_HOME/bin/datax.py），DataX入口在DataX安装的bin文件下。
    -   --jvm '-Xms2g -Xmx2g'定义DataX实际运行时的虚拟机内存，建议内存大小与required\_resource\{\}中的required\_memory保持一致。
2.  单击页面右上角的**执行**，即可运行DataX任务代码。

    运行结果显示的读写失败总数为0时，表示DataX同步数据成功。

    ![geg](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1106726061/p184810.png)


## （可选）调度运维

如果您需要定期同步数据，则需要配置DataX同步任务的调度参数并发布至生产环境，参与生产环境的调度。

1.  在代码编写页面，单击页面上方的**调度配置**，配置调度参数，详情请参见[t159807.md\#](/cn.zh-CN/数据开发/规范建模/逻辑表-维度逻辑表/调度配置.md)。

2.  保存、提交和发布DataX同步任务。

    1.  单击页面右上方的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1197549951/p72337.png)图标，保存代码。

    2.  单击页面右上方的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1197549951/p73470.png)图标，提交代码。

    3.  在**提交备注**对话框，填写备注信息。

    4.  单击**确定并提交**。

    5.  发布DataX同步任务至生产环境。

        -   如果您的开发模式是Dev-Prod模式，则需要发布DataX同步任务至生产环境，详情请参见[管理发布任务](/cn.zh-CN/任务发布/管理发布任务.md)。
        -   如果您的开发模式是Basic模式，则提交成功的DataX同步任务即可进入生产环境。

