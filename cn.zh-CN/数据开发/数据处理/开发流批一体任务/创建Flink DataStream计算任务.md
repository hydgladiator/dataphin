# 创建Flink DataStream计算任务

Flink DataStream计算任务是基于Java环境研发的计算任务，用于进行数据的实时处理。本文为您介绍如何基于JAR资源文件，构建Flink DataStream实时计算任务。

在您开始执行操作前，请确认已上传已经完成开发的Datstream作业的JAR包至Dataphin平台，详情请参见[新建资源](/cn.zh-CN/数据开发/数据处理/新建资源.md)。

## 使用限制

Dataphin支持超级管理员、项目管理员和开发者创建Flink DataStream计算任务。

## 步骤一：新建Flink DataStream任务

1.  登录[Dataphin控制台](https://dataphin.console.aliyun.com/workingArea)。

2.  在Dataphin控制台页面，选择工作区地域后，单击**进入Dataphin\>\>**。

3.  在Dataphin首页，单击顶部菜单栏**研发**。

4.  按照下图指引，进入**新建 Flink DataStream**对话框。

    ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/3946428261/p300201.png)

5.  在**新建Flink\_DataStream**对话框，配置参数后，单击**确定**。

    ![tset](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8397549951/p112698.png)

    |参数|描述|
    |--|--|
    |**名称**|名称的命名规则如下：     -   只能包含小写英文字母、数字、下划线（\_）。
    -   名称的长度范围为3~62个字符。
    -   项目内的名称不支持重复。
    -   名称仅支持以英文字母开头。 |
    |**选择目录**|实时计算任务所属的目录。|
    |**选择资源**|该实时任务依赖的资源包。|
    |**类名**|使用资源的完整类名。|
    |**资源队列**|该项目所绑定的实时计算源中的资源队列。|
    |**引擎版本**|当前资源队列所支持的版本。|


## 步骤二：开发Flink DataStream任务的代码

1.  在Flink DataStream任务代码页面，编写任务的代码。

    您可以单击页面右上方的**格式化**，系统自动调整SQL代码格式。

2.  单击页面右上方的**预编译**，校验代码任务的语法及权限问题。

3.  单击页面右上方的**调试**，代码任务采样数据并进行本地调试，保障代码任务的正确性。

    1.  在**调试配置**对话框的**选择采样模式**页签中，选择调试的模式后，单击**下一步**。

        ![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7928624261/p285192.png)

    2.  在**采样调试数据**页签中，为元数据进行采样调试。

        您可以通过自动抽样和上传数据的方式，为元数据进行采样调试。适用场景说明如下：

        -   自动抽样：自动抽样到的数据是随机的，所以适用于对采集到的数据没有限制的场景。选择**自动抽样**后，需要配置**抽样条数**。

            **说明：** 如果元数据表中没有数据，则自动抽样将采集不到数据。

        -   上传本地数据：自动抽样时元数据采集不到或数据抽样的逻辑比较严格，例如从100万条数据中抽取其中1条数据，这样采集效率就很低，可以选择手动上传本地数据。

            上传本地数据前需要先下载样例，根据下载的样例编辑需要上传的数据，单击**上传**后，数据自动填充至**元数据采样**区域。

            ![ggaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7928624261/p285577.png)

        -   手动输入：适用于采集的数据比较少，或者需要修改已采集到的数据的场景。
    3.  完成所有数据表的元数据采样后，单击页面下方的**确定**。

    4.  在**Result**页面，查看调试数据、中间结果和调试结果。

        ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/7928624261/p285604.png)


## 步骤三：配置Flink DataStream任务的资源

1.  在Flink DataStream任务代码开发页面，单击页面上方的**任务配置**。

2.  在**任务配置**页面，确认在**实时模式**页签。

    在**实时模式**页签，为您展示任务运行所使用的资源队列、引擎版本、资源配置类型及自动调优。

    ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9824367261/p300065.png)

    **资源队列**和**引擎版本**默认为创建Flink DataStream任务时选择的配置。同时，您也可以修改资源队列和引擎版本。

3.  选中**自定义配置**为**资源配置类型**，并单击**去配置**。

4.  在资源配置页面，为您展示一张拓扑图，图中每个方框代表了一个计算任务，都可以进行独立配置。每个Group代表着Group内部的节点可以存放在一台机器进行计算，可以有效避免数据的网络传播，提升性能。图中当前的资源配置就是默认为您展示系统推荐的资源配置。

    ![gagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9824367261/p300105.png)

    1.  单击需要配置资源的Group右上角的①后，在**自定义配置Group执行参数**对话框配置参数后，单击**确定**。

        ![fdagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9824367261/p300110.png)

        |参数|描述|
        |--|--|
        |core|通常，core配置成0.25。即一个CPU可以支持4个线程同时运算，因此core的取值不能超过1，0.25即可，0.125是最低下限了，同时支持8个线程。|
        |heap\_memory|单位为MB，heap\_memory是堆内存，供Java应用程序使用的内存。heap\_memory及其内部各组成的大小可以通过JVM的一系列命令行参数来控制，在一般的blink程序中，都会需要一定的heap\_memory开销,，例如申请一定的heap\_memory作为程序的缓存等，因此您可以按程序的规模来设置其大小。 |
        |parallel|表示同时并发的线程数量，用户可以选择合适的数量来运行自己的任务，并不是越大越好，越大代表你资源申请的越多，反而对性能有抑制。通常，一个简单计算节点每秒可以处理2000~4000条之间的数据。

**说明：** 如果源头是tt，tt的queue大小决定了parallel的上限，不能超过这个数字，否则程序将报错。 |
        |direct\_memory|单位为MB，direct\_memory并不是虚拟机运行时数据区的一部分，也不是Java虚拟机规范中定义的内存区域。但是这部分内存也被频繁的使用，而且也可能导致OutOfMemoryError异常出现。如果您的程序有使用igraph或者swift，可以适当配置其大小，如16-32MB。在Java NIO（New Input/Output）类，引入了一种基于通道（Channel）与缓冲区（Buffer）的I/O方式，direct\_memory可以使用Native函数库直接分配堆外内存，然后同一个存储在Java堆中的DirectByteBuffer对象作为这块内存的引用进行操作。这样能在一场场景中显著提高性能，因为避免了在Java堆和Native堆中来回复制数据。 |
        |native\_memory|单位为MB，native\_memory没有相应的参数来控制大小，其大小依赖于操作系统进程的最大值（对于32位系统就是3~4G，各种系统的实现并不一样），以及生成的Java字节码大小、创建的线程数量、维持Java对象的状态信息大小（用于GC）以及一些第三方的包。native memory存放下面4种信息：

        -   管理Java heap的状态数据（用于GC）。
        -   JNI调用，也就是Native Stack。
        -   JIT（即使编译器）编译时使用native memory，并且JIT的输入（Java字节码）和输出（可执行代码）也都是保存在native memory。
        -   NIO direct buffer。 |

    2.  按照下图指引，进入**自定义配置Operator执行参数**对话框并配置参数。完成参数配置后单击**确定**。

        ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9824367261/p300114.png)

        **自定义配置Operator执行参数**对话框中core、heap\_memory、parallel、direct\_memory和native\_memory参数解释请参见上一步骤，下表仅对state\_size、chain\_strategy参数进行解释。

        |参数|描述|
        |--|--|
        |state\_size|保持默认0即可。|
        |chain\_strategy|chain\_strategy用于定义多个节点的链接策略，Dataphin支持的链接策略包括：        -   Always：默认参数，即和其他节点均部署在一台机器上，没有特殊要求。
        -   Never：节点不会和其他节点放在一台机器上，即需要独立部署。
        -   Head：可以接受和其他节点放在一台机器上，但是只能作为Group的头节点。
**说明：** 目前，Head和Never极少出现，默认Always即可。 |

    3.  配置完成后，单击页面右上方的**保存**。

        **说明：** 如果您想继续使用系统推荐的资源配置，则单击页面右上方的**重置为系统初始**。

5.  保存资源配置记录。

    **说明：** 仅实时模式支持保存资源配置记录。

    如果**资源配置类型**为**自定义配置**，则单击**资源信息记录**后的**保存当前配置为新纪录**。在**保存资源记录**对话框中，输入**资源记录名称**后，单击**确定**。

    对已有的资源信息记录，您可以执行以下操作。

    |操作|描述|
    |--|--|
    |查看版本信息|单击某个记录**操作**列下的![tesga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9397549951/p112980.png)图标，查看版本信息。|
    |启用记录|    1.  单击某个记录的**操作**列下的![taga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9397549951/p112981.png)图标。
    2.  在**提示**对话框中，单击**确定**。 |
    |删除记录|    1.  单击某个记录**操作**列下的![teag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9397549951/p112985.png)图标。
    2.  在**提示**对话框中，单击**确定** |

6.  打开**自动调优**开关，配置**最大CU数**和**期望最大内存**，开启自动调优。

    **说明：** 仅实时模式支持自动调优功能。


## 步骤四：配置实时任务的时间参数

![faga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/0924367261/p300152.png)

实时任务的时间参数为stat\_date，用于方式实时计算任务的运行时间的偏移，例如，您需要计算当天某个指标聚合值，为了防止时间偏移，则您需要设置state\_date大于当天零点，过滤掉偏移的时间点。

为了规避在**任务参数**处经常漏掉配置stat\_date，您只需要在实时任务配置的属性配置中新增stat\_date的kv配置，其中Value是一个基于业务时间的表达式，同时您也可以配置多个时间参数，使用半角分号（;）分割。例如，stat\_date=$\{yyyyMMdd-1\}，则任务运行过程中的开始执行时间为$\{yyyyMMdd-1\}。

![fagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/8928624261/p285616.png)

## 步骤五：配置依赖关系

1.  在Flink DataStream任务代码开发页面，单击页面上方的**任务配置**。

2.  在**任务配置**面板的**依赖关系**区域，配置依赖关系。

    ![fa'ga'gfagag](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/1334955061/p176321.png)

    |参数|描述|
    |--|--|
    |**上游依赖**|您可以通过自动解析和手动添加两种方式，为Flink DataStream任务节点添加上游依赖的节点：    -   单击**自动解析**，Dataphin会解析Flink DataStream任务代码中的表，并查找到与该表名相同的输出名称。输出名称所在的节点作为当前节点的上游依赖。

如果代码中引用项目变量或不指定项目，则系统默认解析为生产项目名，以保证生成调度的稳定性。例如，开发项目名称为`onedata_dev`：

        -   如果代码里指定`select * from s_order`，则调度解析依赖为`onedata.s_order`。
        -   如果代码里指定`select * from ${onedata}.s_order`，则调度解析依赖为`onedata.s_order`。
        -   如果代码里指定`select * from onedata.s_order`，则调度解析依赖为`onedata.s_order`。
        -   如果代码里指定`select * from onedata_dev.s_order`，则调度解析依赖为`onedata_dev.s_order`。
    -   如果需要添加其他节点作为当前标签的上游节点，则需要手动添加上游依赖的物理节点。

**说明：** Dataphin不支持手动添加逻辑表节点。

单击**新增上游依赖**，在**新建上游依赖**对话框中，输入所依赖节点的输出名称的关键字进行搜索节点，搜索到后单击**确定新增**。 |
    |**当前节点**|通过执行如下操作，设置当前节点的输出名称，根据需要您可以设置多个输出名称，供其他节点依赖使用：    1.  单击**手动添加输出**。
    2.  在**新增当前节点输出**对话框中，填写输出名称。输出名称的命名规则请尽量统一，一般命名规则为`生成项目名.表名`且不区分大小写，以标识本节点产出的表，同时其他节点更好地选择调度依赖关系。

例如，开发项目名称为`onedata_dev`，建议将输出名称设置为`onedata.s_order`。如果您将输出名称设置为`onedata_dev.s_order`，则仅限代码`select * from onedata_dev.s_order`能解析出上游依赖节点。

    3.  单击**确定新增**。
同时您还可以对当前节点已添加的输出名称执行如下操作：    -   单击**操作**列下的![fagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5197549951/p88054.png)图标，删除已添加的输出名称。
    -   如果该节点已提交或发布。且被任务所依赖（任务已提交），则单击**操作**列下的![](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5197549951/p76297.png)图标，查看下游节点。 |


## 步骤六：配置任务参数

Flink DataStream任务代码中的通用参数，您可以通过任务参数进行批量配置。

1.  在Flink DataStream任务代码开发页面，单击页面上方的**任务配置**。

2.  在**任务配置**面板，任务参数配置区域，配置参数。


## 步骤七：提交或发布Flink DataStream任务

1.  按照下图指引，提交Flink DataStream任务至生产环境。

    ![gagaga](https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/5830628261/p300187.png)

2.  如果项目空间的开发模式为Dev-Prod，则需要发布Flink DataStream任务至生产环境。如何发布Flink DataStream任务至生产环境，请参见[发布任务]()。


在运维中心查看并运维Flink DataStream任务，保证任务的正常运行。具体操作，请参见[实时任务](/cn.zh-CN/发布与运维/运维中心/任务运维/实时任务.md)或[实时实例](/cn.zh-CN/发布与运维/运维中心/实例运维/实时实例.md)。

