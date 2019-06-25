# Create resources {#concept_yxk_1jb_fhb .concept}

Resource management refers to the central management of various files required during code development. These files include JAR packages, Shell, Python, and other script files, which are required by UDF creation. The MaxCompute computing engine uses OSS to store files, and the Hadoop computing engine uses the open-source distributed storage system such as Ceph to store files.

To create a resource, follow these steps:

1.  Choose **R&D** \> **Develop** \> **Data Processing** \> **Resource Management** to open the Resource Management page.
2.  Create a resource. You can open the resource creation page by clicking one of the three icons in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149565/156134684141552_en-US.png)

3.  Click one of the icons to open the resource creation dialog box In the dialog box that appears, select a resource type, and enter a unique resource name. Select a directory, upload a file, and then click **Submit**.

    **Note:** The size of the uploaded file is not limited. However, if the network connection is unstable, we do not recommend that you upload a file that is larger than 10 MB. By default, you can upload the following resource types: File, JAR, Python, and other file types. The maximum size of each file is 50 MB. The maximum number of files is 1,000.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/149565/156134684141553_en-US.png)


