---
keyword: [Python 2.7, Python 3.7]
---

# 创建Python计算任务

为了满足丰富的Python应用场景，Dataphin支持创建可以使用Python语法的Python计算任务。本文为您介绍如何基于Dataphin构建Python计算任务和定义Python UDF。

## 使用限制

Python 3.7无法向下兼容python 2.7，无法直接升级历史的python 2任务。

2.9.3版本后，Dataphin默认支持研发Python 3.7计算任务。系统仅支持草稿状态的Python任务修改版本。

## 注意事项

Python UDF在SQL任务中执行时，需要指定特定执行版本的兼容。系统默认执行Python 2.7版本，如果需要执行Python 3.7，则执行以下命令，在任务级别开启版本Python 3.7。

```
set odps.isolation.session.enable=true;
set odps.sql.python.version=cp37;
```

## 背景信息

Python 3.7更能满足更多样化的大数据处理的诉求，例如`list.clear()`。Python 2.7和Python 3.7的更多信息，请参见[Python](https://www.python.org/)。

## 前提条件

如果您需要定义Python UDF，则需要上传Python文件，详情请参见[新建资源](/cn.zh-CN/数据开发/数据处理/新建资源.md)。

## 操作步骤

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  在Dataphin首页，单击顶部菜单栏的**研发**。

4.  按照下图指引，进入**新建文件**对话框。

    ![agag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/4961827261/p298266.png)

    您也可以通过以下方式进入**新建文件**对话框：

    -   单击项目名称后的![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8397549951/p72706.png)图标，选择**数据处理** \> **计算任务** \> **Python**。

        ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/4961827261/p298268.png)

    -   在**开发**首页，单击**任务研发区域**的**Python**后的![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8397549951/p72708.png)图标。

        ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/4961827261/p298269.png)

5.  编写并运行代码。

    1.  在**新建文件**对话框，配置参数。

        ![vaffa](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0197549951/p88846.png)

        |参数|描述|
        |--|--|
        |名称|填写代码任务的名称，例如Python。|
        |调度类型|选择任务的调度类型。**调度类型**包括：         -   **周期性节点**，自动参与系统的周期性调度。
        -   **手动节点**，需要手动触发任务的运行。 |
        |描述|填写对任务的简单描述。|
        |选择目录|选择代码任务的目录。|

    2.  单击**确定**。

    3.  在Python任务代码编写页面，选择需要创建的Python任务版本后，编写代码。

        ![test](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9996506161/p239969.png)

        定义Python UDF时，需要在代码中添加`import Python文件名`语句，导入上传的Python文件。

        开发Python 3.7计算任务时，需要根据业务场景安装如下资源包。以下安装包已经预制至系统内，您在开发代码过程中，只需要在代码开始部分添加`import 资源包名`语句即可，例如`import configparser`。

        |资源包|版本|适用场景|
        |---|--|----|
        |configparser|\>=3.5.0|读取配置文件|
        |DateTime|无|数据处理|
        |jumpssh|无|使用跳板机连接服务器|
        |mysql-connector-python|\>=8.0.11|连接并操作MySQL|
        |numpy|无|算法基础处理|
        |pandas|无|算法基础处理|
        |psycopg2|\>=2.7.4|连接操作PostgreSQL|
        |pyhs2|\>=0.6.0|连接并操作HDFS|
        |pyodps|\>=0.7.16|ODPS操作，适用ODPS|
        |requests|\>=2.4.0|算法基础处理|
        |scikit-learn|无|算法基础处理|
        |scipy|无|算法基础处理|
        |setuptools|\>=3.0|Pthon基础功能库|
        |yarn-api-client|\>=0.2.3|Yarn-api客户端|
        |Matplotlib|无|算法基础处理|

        需要选择代码示例如下。

        ```
        #!/usr/bin/Python
        # -*- coding: latin-1 -*-
        import time
        import datetime
        import base64
        import hashlib
        import json
        import sys
        import csv
        from odps import ODPS
        def main():   
            print "Hello World"
        ```

        建议您在Python文件前两行对编码进行主动注释 ，防止执行代码时使用系统编码，导致执行结果报错。

    4.  单击页面右上角的**执行**，运行代码。

6.  配置调度参数。

    -   如果离线计算任务的调度类型为**周期性节点**，则需要配置调度参数，详情请参见[调度配置](/cn.zh-CN/数据开发/数据处理/调度配置.md)。
    -   如果离线计算任务的调度类型为**手动节点**，需要手动触发任务的调度。
7.  按照下图指引，保存并提交Python任务。

    ![ggga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5961827261/p298257.png)

8.  如果项目空间的模式为Dev-Prod，则发布Python任务至生产环境。具体操作，请参见[管理发布任务](/cn.zh-CN/任务发布/管理发布任务.md)。

9.  查看调度任务。具体操作，请参见[脚本任务](/cn.zh-CN/运维中心/任务运维/周期任务/脚本任务.md)或[手动任务](/cn.zh-CN/运维中心/任务运维/手动任务.md)。


