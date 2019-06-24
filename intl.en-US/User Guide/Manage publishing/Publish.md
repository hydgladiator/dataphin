# Publish {#concept_dfh_t4k_bhb .concept}

Tasks generated in the development environment during standard modeling and data processing are listed in the **List of objects to be published** page. You can click **Publish** on the page to publish the tasks. After tasks are published, the tasks will be brought online in the production environment. The development environment is relatively independent from the production environment. You can change, debug, execute and verify the tasks in the development environment, and then copy the tasks to the production environment. This ensures that the data in the production and development environments are isolated and not affected by each other.

**Note:** The publishing function is only available in the development environment.

## Objects to be published {#section_c2k_dcr_dhb .section}

1.  Log on to Dataphin.
2.  In the top navigation bar of the Dataphin homepage, click **R&D**. Alternatively, you can access the R&D page from the quick access area located in the middle of the homepage, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136286/156135727841057_en-US.png)

3.  In the top navigation bar, select **Publish** to go to the Publish page, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136654/156135727841203_en-US.png)

4.  On the List of objects to be published page, you can search for, view, and publish submitted tasks.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136654/156135727941224_en-US.png)

    Objects to be published are displayed on different tab pages by type \(standard modeling and data processing\).

    -   At the top of the right-side workspace, you can enter keywords in the search box to search for the object to be published. In the area below the search box, click the show more arrow to expand more filtering conditions. You can select the person who submits publish requests, the submission time, an object type, and an action type to filter the search results.
    -   The object name, object ID, object type, version number, action type, the latest submission time, the person who submits the request, and other information are listed in the search results.
5.  Publish objects.
    -   **Publish an object** 

        In the list of search results, click the **Publish** in the **Actions** column to publish the object to the production environment.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136654/156135727941229_en-US.png)

    -   **Publish objects** 

        In the list of search results, select the objects to be published, and then click **Publish** to publish these objects.

        **Note:** There are limits on the number of objects to be published at the same time. If you select more than 10 objects, the publishing may fail. You can change the number of objects and try again. For more information, see **Note** in the upper-right corner of the page.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136654/156135727941237_en-US.png)

6.  To check the publishing history, click **View History** in the **Actions** column to go to the [Publishing history](#section_jtr_dpw_dhb) page. To edit an object, click **Edit** to go to the editing page of the object in the development environment.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136654/156135727941238_en-US.png)

    **Note:** 

    -   When publishing objects, some objects have special constraints during publishing to ensure that the relative objects are published and made available in the production environment. For more information, see Note in the upper-right corner of the **Objects to Publish** page.
    -   When the data processing objects in the development environment are published to the production environment, the production environment does not record folder information. To avoid publishing failure because of duplicate object names in the production environment, ensure that the object does not have the same name.

## Publishing history {#section_jtr_dpw_dhb .section}

In the left-side navigation pane, select **Publishing History** to go the Publishing History page. On the page, you can search for objects by status, view objects, and view details. You can also click Edit to go to the editing page of the object in the development environment.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/136654/156135728041244_en-US.png)

