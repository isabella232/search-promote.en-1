---
description: You can use Full Index to index all the pages of your staged or live website. Indexing helps your customers more easily find what they are looking for or what they need when they perform a search.
seo-description: You can use Full Index to index all the pages of your staged or live website. Indexing helps your customers more easily find what they are looking for or what they need when they perform a search.
seo-title: About Full Index
solution: Target
subtopic: Full Index
title: About Full Index
topic: Index,Site search and merchandising
uuid: dce1eafd-5aea-4945-8305-8f9e7dc392df
---

# About Full Index{#about-full-index}

You can use Full Index to index all the pages of your staged or live website. Indexing helps your customers more easily find what they are looking for or what they need when they perform a search.

## Using Full Index {#concept_C69BD21863FD4856B49326F35DB570D3} 

When you generate a full index, status information is displayed, such as start time, elapsed time, and errors during the indexing process. Information about the status of your last index is also displayed.

If you have changed an account setting that requires an index regeneration, the status may read "Regenerating." During regeneration, account settings are applied to create an updated site index.

You can stop or restart the indexing process at any time.

While the new index is built for a live website, customers can continue to search your site using your last index. Information about the status of your last index is also displayed. 

## Setting the full index schedule for a live website {#task_6760F3256D004A228B38968DF15421F0}

You can specify the time and days that you want to crawl your website and update the index.

<!-- 

t_setting_the_full_index_schedule_for_a_live_website.xml

 -->

The time that you select is local according to the time zone that is configured in Account Settings.

See [Configuring your account settings](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Web servers are often scheduled to go down for maintenance in the middle of the night. If your server is down during a scheduled index time, the indexing process will fail. Be sure that you select a time of day when your web server is available.

The index schedule only applies to your live index; you cannot schedule staged indexes.

**To set the full index schedule for a live website** 

1. On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Schedule]**.
1. In the **[!UICONTROL Time]** drop-down list, select the hour that you want the full indexing to start.
1. Select one or more days that you want the full indexing to run.
1. Click **[!UICONTROL Save Changes]**.

## Running a full index of a live or staged website {#task_F7FE04D8A1654A7787FCCA31B45EB42D}

You can use Full Index to index all the pages of your staged or live website. Indexing helps your customers more easily find what they are looking for or what they need when they perform a search.

<!-- 

t_running_a_full_index_of_a_live_or_stage_website.xml

 -->

**To run a full index of a live or staged website** 

1. On the product menu, do one of the following:

    * Click **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**. 
    
    * Click **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Index]**.

1. Set the indexing options that you want.

   <!-- 
   
   r_indexing_options.xml
   
   -->

    <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>Option </p> </th> 
    <th colname="col2" class="entry"> <p>Description </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Clear Index Cache </p> </td> 
    <td colname="col2"> <p>Removes all documents from the index cache. </p> <p>When selected, every website page is downloaded from your server. If this setting is checked and disabled, your account is set to clear the cache every time a full index is performed. Or, some previously changed account setting now requires a full index. </p> <p>When deselected, all indexed pages stay in the index until the web server says that the page no longer exists. This situation is true even if links to that page are removed. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Regenerate Pending </p> </td> 
    <td colname="col2"> <p>Select If you have made changes to your account settings that have substantially changed the contents of your index. Substantial changes include making changes to any of the following: 
    <ul id="ul_4EB8FF692FEB47BBB9A64D61299380D1"> 
    <li id="li_7CF8D286512F4210BEA3DB9F0EFA097A">Synonyms </li> 
    <li id="li_8178ABC342BB4365B3927E20433756E3">Collections </li> 
    <li id="li_57C8BD06BFA64AFAA2C9EF2CC59520EF">Metadata </li> 
    <li id="li_C4B6A7DA023B4A43991D03EC592170C9">Excluded words </li> 
    <li id="li_9E0AD4B6DDC24A5A8FB5C2C1CCD5348A">Account language </li> 
    <li id="li_338F107547DF48AAA0EF90F4AD8664A5">Ranking </li> 
    <li id="li_7F49B86D94974E79AAD381A64A1400F2">Toggling case-sensitive search </li> 
    <li id="li_E8FE6EE240A840AC826ADF4294AAC6F6">Toggling diacritical support </li> 
    <li id="li_51763D482DCB4ED0972966F492B8C0F2">Toggling number indexing </li> 
    </ul> </p> <p>Before another crawl takes places, a quick pass is done through all the index data to make it conform to the new account settings. </p> <p>This option is only available if you are doing a full index of a staged website. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Count All Pages </p> </td> 
    <td colname="col2"> <p>Allows the crawling of website pages to continue even after you have reached your account page limit. </p> <p>Additional pages are not added to your index, but you can ascertain the total number of documents on your website. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Full Index Now]**.
1. (Optional) If indexing errors occurred, click **[!UICONTROL View Errors]** to view the associated log.

## Viewing the full index log of a live or staged website {#task_02E5E944C56B4EB19CC1FF321F3221B8}

When a live full index or a staged full index is complete, you can view its associated log to troubleshoot any errors that occurred.

<!-- 

t_viewing_the_full_index_log_of_a_live_or_staged_website.xml

 -->

You cannot export logs, nor save them. The log remains available for viewing until the new index occurs.

**To view the full index log of a live or staged website** 

1. On the product menu, do one of the following:

    * Click **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Log]**. 
    
    * Click **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Log]**.

1. On the log page, at the top or bottom, do any of the following:

    * Use the navigation options **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]**, or **[!UICONTROL Go to line]** to move through the log. 
    
    * Use the display options **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]**, or **[!UICONTROL Show]** to refine what you see.

