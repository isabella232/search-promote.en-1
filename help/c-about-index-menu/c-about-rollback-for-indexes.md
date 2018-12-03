---
description: You can use Rollback to back up and archive website indexes that you have generated. You can also restore the backup of an index at any time.
seo-description: You can use Rollback to back up and archive website indexes that you have generated. You can also restore the backup of an index at any time.
seo-title: About Rollback for indexes
solution: Target
subtopic: Rollback
title: About Rollback for indexes
topic: Index,Site search and merchandising
uuid: 1fafeece-d7b7-4ccc-bde9-e117d49d0020
index: y
internal: n
snippet: y
---

# About Rollback for indexes{#about-rollback-for-indexes}

You can use Rollback to back up and archive website indexes that you have generated. You can also restore the backup of an index at any time.

## About Rollback for indexes {#concept_0BC4BC975DB045A986C3607CF32705D8}

You can use [!UICONTROL Rollback] to back up and archive website indexes that you have generated. You can also restore the backup of an index at any time. 

The archive contains four indexes: the current site index, and three previous site indexes, which the search robot automatically archives based on the rollback configuration settings. Each time your website is indexed, the archive is updated. Newer indexes replace existing archived indexes so that the archive always remains current.

Each archived index is listed in the archive with the following information:

* Date and time the index was finalized. 
* Index age. 
* Number of documents indexed. 
* Indexing operation type (full, incremental, and so on). 
* Index status such as whether the index is currently active, and whether it will be kept or removed after the next index.

Each time your website is indexed, the new index is added to the archive, and an existing archived index is removed. Note, however, that the oldest index is not necessarily the one that is removed. When a new index is added to the archive, an age comparison is made of each archived index to the ages that are specified in the rollback configuration settings. The index that is furthest from the desired schedule is removed. For example, suppose the configuration setting is 24,48,72 and the ages of the saved indexes are 5, 23, 47, and 71. The most recent index (aged five hours) is removed when a new index is added to the archive because its age is furthest from the settings. For convenience, the archive notes which index is removed when the site is indexed again.

You can navigate to other areas within the user interface while an index is activated. A status indicator keeps track of the activation progress and is available when you view the [!UICONTROL Rollback] page. If an archived index is restored, users are notified at the top of the Full Index, Incremental Index, Scripted Index, and Regenerate pages. No indexing operation can occur while an index is being restored. If a rollback operation conflicts with a scheduled site index, the scheduled indexing is deferred until the rollback has finished. If an index is already in progress, then it is canceled, provided the user confirms that the rollback receive priority.

To maintain the integrity of the archive, the search robot does not update the rollback archive if errors are found during a crawl. There is also no update if a user cancels an indexing operation. If an indexing operation exceeds the maximum time, bytes, pages, or documents, the crawler finalizes the index and adds it to the archive. In addition, if the minimum number of pages is not met during an indexing operation, the crawler cancels the index and the previous index remains active. 

## Configuring the rollback archiving schedule of indexes {#task_CD403B9AE2244B13A6B3861B5F9B055C}

You can use [!UICONTROL Configure] to determine which index files that you want to store in the rollback archive. The archive can store the current index and three backup indexes.

<!-- 

t_configuring_the_rollback_archiving_schedule_of_indexes.xml

 -->

The **[!UICONTROL Schedule]** field contains three comma-separated values that represent hours from the present. For example, the schedule values 24,48,72 specify 24 hours from the present or yesterday, 48 hours from the present or two days ago, and 72 hours from the present or three days ago.

Search continually archives the site indexes that are the closest to one day, two days, and three days old. The actual times and dates of the archived indexes can vary depending on your website's indexing schedule.

**To configure the rollback archiving schedule of indexes** 

1. On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Configure]**.
1. On the [!UICONTROL Rollback Configuration] page, in the **[!UICONTROL Schedule]** field, enter a command separated list of three index ages, in hours. The indexes closest to these ages is saved.
1. Click **[!UICONTROL Save Changes]**.

## Activating an archived index {#task_5DCE3D660F6F4197993E92AA59227332}

You can use Rollback to activate an archived index.

<!-- 

t_activating_an_archived_index.xml

 -->

When you click **[!UICONTROL Activate]** to rollback an index, the currently active index is moved into the archive.

Following the activation of the archived index, you are returned to the [!UICONTROL Activate Index] page. Information about the index rollback is displayed. Also, the [!UICONTROL Activate] column in the [!UICONTROL Available Indexes] table identifies the rolled back index with the status "Active Index". 

1. On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Rollback]**.
1. On the [!UICONTROL Activate Index] page, in the [!UICONTROL Available Indexes] table, click **[!UICONTROL Activate]** for the associated archived index type that you want to make active.

   Use the Date, Age, Pages, and Operation columns to help you determine which index to activate. 
1. On the [!UICONTROL Verify Rollback] page, review the index information to verify that you have selected the correct index, and then click **[!UICONTROL Activate Now]**.

## Viewing the log of all index rollbacks {#task_D2D9AA7203F0465FB5AE0D49212AC41C}

View the date and time of all rollback-related operations.

<!-- 

t_viewing_the_log_of_all_index_rollbacks.xml

 -->

**To view the log of all index rollbacks** 

1. On the product menu, do one of the following:

    * Click **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Live Log]**. 
    
    * Click **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Staged Log]**.

1. On the log page, at the top or bottom, do any of the following:

    * Use the navigation options **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]**, or **[!UICONTROL Go to line]** to move through the log. 
    
    * Use the display options **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]**, or **[!UICONTROL Show]** to refine what you see.

