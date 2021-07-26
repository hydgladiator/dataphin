---
keyword: Python
---

# 新建Python任务

为了满足丰富的Python应用场景，Dataphin支持创建可以使用Python语法的Python计算任务。本文为您介绍如何基于Dataphin构建Python计算任务和定义Python UDF。

完成上传Python文件，详情请参见[新建资源](/cn.zh-CN/数据开发/数据处理/新建资源.md)。

Python任务中引用到的Python文件需要提前创建，因此您在资源管理中先上传Python文件，然后在Python任务中引用。

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  在Dataphin首页，单击顶部菜单栏的**研发**。

4.  按照下图指引，进入**新建文件**对话框。

    ![agag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4961827261/p298266.png)

    您也可以通过以下方式进入**新建文件**对话框：

    -   单击项目名称后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72706.png)图标，选择**数据处理** \> **计算任务** \> **Python**。

        ![gagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4961827261/p298268.png)

    -   在**开发**首页，单击**任务研发区域**的**Python**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72708.png)图标。

        ![gagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4961827261/p298269.png)

5.  编写并运行代码。

    1.  在**新建文件**对话框，配置参数。

        ![vaffa](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0197549951/p88846.png)

        |参数|描述|
        |--|--|
        |名称|填写代码任务的名称，例如Python。|
        |调度类型|选择任务的调度类型。**调度类型**包括：         -   **周期性节点**，自动参与系统的周期性调度。
        -   **手动节点**，需要手动触发任务的运行。 |
        |描述|填写对任务的简单描述。|
        |选择目录|选择代码任务的目录。|

    2.  单击**确定**。

    3.  在Python任务代码编写页面，进行编写代码任务。

        代码示例如下：

        ```
        #!/usr/bin/python
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

    4.  检查代码。

        代码编写完成后，单击**预编译**，系统帮助您检查编写的Python任务的代码的语法。

        如果预编译失败，您可以单击页面上方的**格式化**，系统自动帮助您调整语法格式。调整完格式，您可以单击**刷新**，刷新页面上的代码。

    5.  单击页面右上角的**执行**，运行代码。

6.  配置调度参数。

    -   如果离线计算任务的调度类型为**周期性节点**，则需要配置调度参数，详情请参见[调度配置](/cn.zh-CN/数据开发/数据处理/调度配置.md)。
    -   如果离线计算任务的调度类型为**手动节点**，需要手动触发任务的调度。
7.  按照下图指引，保存并提交Python任务。

    ![ggga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5961827261/p298257.png)

8.  如果项目空间的模式为Dev-Prod，则发布Python任务至生产环境。具体操作，请参见[管理发布任务](/cn.zh-CN/任务发布/管理发布任务.md)。

9.  查看调度任务。具体操作，请参见[脚本任务](/cn.zh-CN/运维中心/任务运维/周期任务/脚本任务.md)或[手动任务](/cn.zh-CN/运维中心/任务运维/手动任务.md)。


