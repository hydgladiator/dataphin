# Java UDF最佳实践

为了满足复杂的数据开发场景，Dataphin智能研发版支持自定义Java UDF函数。本教程以Java自带函数（toLowerCase）为例，为您介绍如何基于Dataphin自定义Java UDF函数。

下载[JAR包](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/30259/cn_zh/1609818319666/javaudf.jar)。

本教程基于下载的JAR包自定义的Java UDF函数，实现大写字母转换为小写字母。您也可以编写Java UDF代码，以实现更多的功能，请参见[IntelliJ IDEA Java UDF开发最佳实践](/cn.zh-CN/最佳实践/数据开发/IntelliJ IDEA Java UDF开发最佳实践.md)。

本教程中的JAR包的代码如下。

```
package org.alidata.odps.udf.examples;
import com.aliyun.odps.udf.UDF;

public final class javaudf extends UDF {
  public String evaluate(String s) {
    if (s == null) {
        return null;
    }
        return s.toLowerCase();
  }
}
```

其中，

-   JAR包路径为org.alidata.odps.udf.examples。
-   class文件名为javaudf。

## 步骤一：上传JAR包

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  进入**资源管理**页面。

    1.  在Dataphin首页，单击**研发**。

    2.  在数据**开发**页面，单击**数据处理**。

    3.  在左侧导航栏，单击![资源管理](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2987549951/p96911.png)**资源管理**图标。

4.  在**资源管理**页面，单击**资源管理**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72394.png)图标。

5.  在**新建资源**对话框中，配置参数。

    ![faga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7373289061/p208783.png)

    |参数|描述|
    |--|--|
    |类型|选择**jar**。|
    |名称|上传文件的名称需要以文件类型结尾。例如javaudf.jar。|
    |描述|填写资源的描述。|
    |上传文件|选择本地JAR文件，例如javaudf.jar。|
    |计算类型|选择**MaxCompute**。|
    |选择目录|选择用于存放JAR包的目录。系统默认为**资源管理**，保持默认即可。|

6.  单击**提交**，完成资源的提交。

7.  在**提交备注**对话框，填写备注信息。

8.  单击**确定并提交**。

9.  发布资源至生产环境。

    -   如果您的开发模式是Dev-Prod模式，则需要发布资源至生产环境，详情请参见[管理发布任务](/cn.zh-CN/任务发布/管理发布任务.md)。
    -   如果您的开发模式是Basic模式，则提交成功的资源，即可进入生产环境。

## 步骤二：创建MAXC函数

1.  在**数据处理**页签，单击左侧导航栏的![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4056155061/p176396.png)**函数管理**图标。

2.  单击**函数管理**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72394.png)图标，选择**MAXC函数**。

3.  在**新建函数**对话框，配置参数。

    ![gegeg](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7373289061/p208806.png)

    |参数|描述|
    |--|--|
    |名称|填写函数的名称，例如java|
    |选择资源|选择已上传的资源**javaudf.jar**。|
    |类名|类名的格式为JAR包路径.class文件名。填写org.alidata.odps.udf.examples.javaudf。|
    |类型|函数的类型。选择**字符串**。|
    |命令格式|定义引用函数的格式。填写to\_char\(string i\)。|
    |使用文档|填写函数的使用描述，例如javaudf。|
    |选择目录|默认为MAXC函数-用户自定义函数，保持默认。|

4.  单击**提交**，完成资源的提交。

5.  在**提交备注**对话框，填写备注信息。

6.  单击**确定并提交**。

7.  发布函数至生产环境。

    -   如果您的开发模式是Dev-Prod模式，则需要发布函数至生产环境，详情请参见[管理发布任务](/cn.zh-CN/任务发布/管理发布任务.md)。
    -   如果您的开发模式是Basic模式，则提交成功的函数，即可进入生产环境。

## 步骤三：新建SQL任务

1.  在**数据处理**页签，单击左侧导航栏![agaga](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8980863061/p176215.png)**计算任务**图标。

2.  在**计算任务**页面，单击**计算任务**后的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8397549951/p72394.png)图标，选择**MAXC任务** \> **MAX\_COMPUTE\_SQL**。

3.  在**新建文件**对话框，配置参数。

    |参数|描述|
    |--|--|
    |名称|填写计算任务的名称，例如javaudf。|
    |调度类型|选择任务的调度类型为**周期性节点**。|
    |描述|填写对任务的简单描述。|
    |选择目录|系统自动选择为**计算任务**。|

4.  单击**确定**。


## 步骤四：使用Java UDF函数

1.  在SQL任务的代码编写页面，编写代码，例如`select java('ABCGDfagHH');`。

2.  单击页面右上方的**执行**，查看运行结果。

    ![fagag](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8373289061/p208840.png)


## （可选）调度运维

如果需要定期的运行SQL任务，则需要配置SQL任务的调度参数并发布至生产环境，参与生产环境的调度。

1.  在代码编写页面，单击页面上方的**调度配置**，配置调度参数，详情请参见[t159807.md\#](/cn.zh-CN/数据开发/规范建模/逻辑表-维度逻辑表/调度配置.md)。

2.  保存、提交和发布SQL任务。

    1.  单击页面右上方的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1197549951/p72337.png)图标，保存代码。

    2.  单击页面右上方的![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1197549951/p73470.png)图标，提交代码。

    3.  在**提交备注**对话框，填写备注信息。

    4.  单击**确定并提交**。

    5.  发布SQL任务至生产环境。

        -   如果开发模式是Dev-Prod模式，则需要发布SQL任务至生产环境，详情请参见[管理发布任务](/cn.zh-CN/任务发布/管理发布任务.md)。
        -   如果开发模式是Basic模式，则提交成功的SQL任务，即可进入生产环境。

