---
description: Use the Adobe Analytics menu to setup Adobe Analytics metrics authentication, manage Adobe Analytics metrics of a Report Suite, or use SAINT to enhance Adobe Analytics reports through the acceptance of tabular data from outside sources.
seo-description: Use the Adobe Analytics menu to setup Adobe Analytics metrics authentication, manage Adobe Analytics metrics of a Report Suite, or use SAINT to enhance Adobe Analytics reports through the acceptance of tabular data from outside sources.
seo-title: About the Adobe Analytics menu
solution: Target
subtopic: Adobe Analytics
title: About the Adobe Analytics menu
topic: Settings,Site search and merchandising
uuid: 5536edf1-d3a4-47af-a307-6e46f385f738
index: y
internal: n
snippet: y
---

# About the Adobe Analytics menu{#about-the-adobe-analytics-menu}

Use the Adobe Analytics menu to setup Adobe Analytics metrics authentication, manage Adobe Analytics metrics of a Report Suite, or use SAINT to enhance Adobe Analytics reports through the acceptance of tabular data from outside sources.

## Setting up Adobe Analytics metrics authentication {#task_8AA93F6273B747F9B4DE9E8DFBCBDC42}

To incorporate Adobe Analytics metrics into your site search/merchandising rankings, you must first obtain a Adobe Analytics Web Services login. After you obtain the login information, you can use it to set up Adobe Analytics authentication in site search/merchandising.

<!-- 

t_setting_up_adobe_analytics_authentication.xml

 -->

**To set up Adobe Analytics metrics authentication** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Authentication]**.
1. On the [!DNL Setup Adobe Analytics Metrics Authentication] page, specify the information requested in each field.

   <!-- 

r_setup_adobe_analytics_metrics_authentication_options.xml

 -->

<table id="table_BF76982A31164476BC05E49AE03EF586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Text field </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Analytics Company Name </p> </td> 
   <td colname="col2"> <p>The same Company Name setting that is used to log in to your Adobe Analytics account. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Web Services Username </p> </td> 
   <td colname="col2"> <p>The Web Services Username that is associated with your Adobe Analytics account. </p> <p>You can obtain this information in Adobe Analytics. On the Adobe Analytics menu bar, click <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Admin Console </span> &gt; <span class="uicontrol"> Company </span> &gt; <span class="uicontrol"> Web Services </span>. The information is in the API Access Information table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Web Services Shared Secret </p> </td> 
   <td colname="col2"> <p>The Web Services Shared Secret that is associated with your Adobe Analytics account. </p> <p>You can obtain this information in Adobe Analytics. On the Adobe Analytics menu bar, click <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Admin Console </span> &gt; <span class="uicontrol"> Company </span> &gt; <span class="uicontrol"> Web Services </span>. The information is in the API Access Information table. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Adobe Analytics Report Suites {#concept_1A51AEC5D40E459B813E7891D64B1BAE}

To use Adobe Analytics Report Suite data within site search/merchandising, you must first create copies of the Adobe Analytics data in your site search/merchandising account.

<!-- 

c_about_adobe_analytics_report_suites.xml

 -->

You can create new Adobe Analytics Report Suite definitions, or you can view or modify your existing Adobe Analytics Report Suites and associated metrics.

<a id="section_7A6701D1B23E4E6B82AA073597183916"></a>

The first time you access Adobe Analytics from within site search/merchandising, a list of your company's available Report Suites are downloaded and cached. If new Report Suites have recently been added, or existing ones removed, you can refresh the report suite list to re-download the list of Report Suites.  
## Adding an Adobe Analytics Report Suite {#task_6DE17305EA7146DA8C30FF8FDF68A3C0}

You can select an Adobe Analytics Report Suite on which to base your site search/merchandising Ranking rules.

<!-- 

t_adding_a_adobe_analytics_report_suite.xml

 -->

The list you can select from should correspond to the Report Suites that are available from within your Adobe Analytics account. The Report Suite you select determines the metrics that are available for use within your site search/merchandising Ranking Rules.

See [About Ranking Rules](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

After you add a Adobe Analytics Report Suite, you can edit its metrics.

See [Editing the Adobe Analytics metrics of a Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

**To add an Adobe Analytics Report Suite** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. On the Adobe Analytics Report Suites page, click **[!UICONTROL Add Report Suite]**.
1. In the drop-down list of the newly added table row, select the Report Suite that you want.
1. Edit the Adobe Analytics metrics of a Report Suite.

## Editing the Adobe Analytics metrics of a Report Suite {#task_360904CCBBB140238ADA036C3CC07664}

To incorporate Adobe Analytics metrics into your Ranking Rules in site search/merchandising, you select one or more of the metrics that are associated with the chosen Report Suite. Then you configure the options that are used to fetch metric data by way of the Adobe Analytics Web Service.

<!-- 

t_editing_the_adobe_analytics_metrics_of_a_report_suite.xml

 -->

See [Adding an Adobe Analytics Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0).

See [Configuring advanced Adobe Analytics options](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_C0FF2D69F59D44D8943A7831ED7FEC19).

**To edit the Adobe Analytics metrics of a Report Suite** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. On the [!DNL Adobe Analytics Report Suites] page, under the **[!UICONTROL Actions]** column, click **[!UICONTROL Edit]** for the Report Suite whose metrics you want to configure.
1. On the [!DNL Edit Adobe Analytics Metrics] page, set the metrics that are required. Metrics that do not have an asterisk (&#42;) next to the metric name, are optional.

   <!-- 

r_edit_adobe_analytics_metrics_options.xml

 -->

<table id="table_8A41F708F2B94807B2A8C3079AAB9266"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Report Suite </p> </td> 
   <td colname="col2"> <p>Displays the name of the currently Report Suite that you added. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Suite View Name </p> </td> 
   <td colname="col2"> <p>Provides an "alias" name for the Adobe Analytics Report Suite name. This alternate name is useful if the same Report Suite is used in more than one definition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Select Report Type </p> </td> 
   <td colname="col2"> <p>Specifies the Report Type value to use with the selected Report Suite. The value identifies the key for each returned row of results. </p> <p>The Report Type is also known as the Adobe Analytics Element. </p> <p>This metric is required. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cross-reference Field Name </p> </td> 
   <td colname="col2"> <p>Specifies a metadata field whose values are used as look-up "keys" into the Report Suite's data. </p> <p>If no value is selected ("-- None --"), this Report Suite's data is not available for use in Ranking calculations ( <span class="uicontrol"> Rules </span> &gt; <span class="uicontrol"> Ranking Rules </span> &gt; <span class="uicontrol"> Edit Rules </span>). </p> <p>When you select a value, this field's values are used to cross-reference site search/merchandising documents with this Report Suite's Adobe Analytics data, using the selected Report Type value that you set earlier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Search Terms Report </p> </td> 
   <td colname="col2"> <p>Gives you access to create business rules and simulate search terms from the <b>Stage Adobe Analytics Data Preview</b> page. </p> <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0" type="task" format="dita" scope="local"> Previewing Adobe Analytics Data </a>. </p> <p>A pull-down menu appears on every row that includes two options: <b>Simulate Search Term</b> and <b>Create New Business Rule</b>. </p> <p>Both options use data from the Report Type as the search terms. Therefore, this feature only makes sense if the Report Type represents search terms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metrics </p> </td> 
   <td colname="col2"> <p>Identifies the metric values that you want to download and use within your site search/merchandising Ranking Rules. </p> <p>The metrics that you configure here appear as choices on the <span class="uicontrol"> Rules </span> &gt; <span class="uicontrol"> Ranking Rules </span> &gt; <span class="uicontrol"> Edit Rules </span> member center pages, when the rule's Data Type is set to <span class="uicontrol"> Adobe Analytics Metric (Number) </span>. The choices show a combination of the Report Suite names or Report Suite View Names, if specified, and the individual metric names. </p> <p>This metric is required. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Minimum Metric Value </p> </td> 
   <td colname="col2"> <p>Lets you enter a nonzero value to specify a minimum value for the metric. </p> <p>If blank, or zero, all values for the metric are downloaded; otherwise, the download for this metric stops when the minimum metric value is passed. </p> <p>Adobe Analytics metrics are retrieved in descending order. </p> <p>Click <span class="uicontrol"> + </span> to add additional metric definitions; click <span class="uicontrol"> - </span> to remove metric definitions that you no longer need or want. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adobe Analytics Metric Aggregation Period (Days) </p> </td> 
   <td colname="col2"> <p> Controls the number of days worth of Adobe Analytics metrics to fetch, counting back from yesterday's date. No attempt is made to fetch data from the current day. </p> <p>The default is 7. </p> <p>This metric is required. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adobe Analytics Download Refresh Frequency (Days) </p> </td> 
   <td colname="col2"> <p> Sets the minimum interval between downloads of Adobe Analytics data that is used in ranking calculations. </p> <p>Index-triggered downloads that occur within the download refresh frequency interval are ignored. However, manual downloads ignore this value. </p> <p>When you set this value to the default of 1, Adobe Analytics data does not download more than once within a 24 hour period. All Search indexes that occur within the download refresh frequency interval use the last data set that was downloaded. </p> <p>This metric is required. </p> </td> 
  </tr> 
 </tbody> 
</table>

   See also [About Ranking Rules](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397). 
1. Click **[!UICONTROL Save Changes]**.

   You are returned to the Staged [!DNL Adobe Analytics Report Suites] page. 
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting an Adobe Analytics Report Suite {#task_0ACA172214D14654ABDB139F417B9F7D}

You can use Delete to remove a Report Suite from the [!DNL Adobe Analytics Report Suites] page. Deleting a Report Suite only removes the copy of the data from the site search/merchandising servers; it does not impact the data on Adobe Analytics systems.

<!-- 

t_deleting_a_adobe_analytics_report_suite.xml

 -->

**To delete an Adobe Analytics Report Suite** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. On the [!DNL Adobe Analytics Report Suites] page, under the **[!UICONTROL Actions]** column, click **[!UICONTROL Delete]** for the Report Suite you want to remove.
1. On the [!DNL Adobe Analytics Delete Report Suite] page, click **[!UICONTROL Delete]**.

## Previewing Adobe Analytics Data {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

You can use Preview to view your most recently loaded Adobe Analytics metrics.

<!-- 

t_previewing_adobe_analytics_data.xml

 -->

The Row column in the table shows the number for each row of metric data, indicating the original order that the Adobe Analytics metrics were loaded.

The Product column shows the Adobe Analytics Element that is associated with each row of metric data. The values in this column are used to associate your site search/merchandising pages with their corresponding metric values, as configured in your ranking definitions.

See [About Ranking Rules](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

See [Configuring ranking](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

The remaining columns show the metric values that are associated with each entry.

If the table is empty, it means that you have not loaded any Adobe Analytics data yet. You can close the [!DNL Adobe Analytics Data Preview] page, and then load Adobe Analytics data.

See [Loading Adobe Analytics data](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181). 
If the table was designated as a search term report, a small triangle appears in every row. You can click the drop-down list and select **Simulate Search Term** or **Create New Business Rule**. The action you select is applied to that row's search term, the data residing in the second column

**To preview Adobe Analytics Data** 

1. On the product menu, do one of the following:

* Click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**. On the [!DNL Adobe Analytics Report Suites] page, under the [!DNL Actions] column, click **[!UICONTROL Preview]** for the Report Suite whose downloaded data you want to view. 

* Click **[!UICONTROL Reports]** > **[!UICONTROL Adobe Analytics Terms Reports]**. On the [!DNL Adobe Analytics Terms Report] page, under the [!DNL Actions] column, click **[!UICONTROL Preview]** for the Report Suite whose downloaded data you want to view.

1. On the [!DNL Adobe Analytics Data Preview] page, use the navigation and viewing options at the top and bottom of the page to view the data.

   Click any column heading in the table to sort the data in ascending or descending order. 
1. Do any of the following:

    * Click **[!UICONTROL Download to Desktop]** to download and save the table as a [!DNL .xlt] file. 
    
    * Close the page when you are finish previewing the Adobe Analytics data and return to the previously viewed page.

## Viewing the log from the most recent Adobe Analytics data load {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

You can use View Log to examine the Adobe Analytics data log file of the most recent download process. You can also use the log view to monitor a running download.

<!-- 

t_viewing_the_log_from_the_most_recent_adobe_analytics_data_load.xml

 -->

See [Loading Adobe Analytics data](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**To view the log from the most recent Adobe Analytics data load** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. On the [!DNL Adobe Analytics Report Suites] page, click **[!UICONTROL View Log]**. Log page,
1. On the [!DNL Adobe Analytics Data Log] page, use the navigation and viewing options at the top and bottom of the page to view the log information.
1. When you are finished, close the page to return to the [!DNL Adobe Analytics Report Suites] page.

## Loading Adobe Analytics data {#task_2F3C55189B0A4049AB2113F2291CC181}

You can download the configured Adobe Analytics Report Suite data into site search/merchandising.

<!-- 

t_loading_adobe_analytics_data_from_searchpromote.xml

 -->

The Data Load page shows the status of your last Adobe Analytics Data Load operation with the following information:  

<table id="table_A06CB68645D74CDC8E00E96301085D4F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Status field </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Indicates the success or failure of the last data load attempt. Or, it displays the status of a data load operation that is already in progress. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Results </p> </td> 
   <td colname="col2"> <p>Displays the number of rows of metric data that was downloaded during the last data load attempt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Start Time </p> </td> 
   <td colname="col2"> <p>Displays the date and time that the last data load operation started. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stop Time </p> </td> 
   <td colname="col2"> <p>Displays the completion date and time of the last data load operation. Or, it indicates the current data load operation is still in progress. </p> </td> 
  </tr> 
 </tbody> 
</table>

**To load Adobe Analytics data** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. On the [!DNL Stage Adobe Analytics Report Suites] page, click **[!UICONTROL Load Adobe Analytics Data]**.
1. On the **[!UICONTROL Adobe Analytics Data Load]** page, do one of the following:

    * Click **[!UICONTROL Start Load]** to start the load operation.

      During a data load operation, the**Progress** row provides information on its progress.

    * Click **[!UICONTROL Stop Load]** to stop the load operation.

1. Click **[!UICONTROL Close]** to return to the [!DNL Stage Adobe Analytics Reports Suite] page.

## Refreshing the Report Suite list {#task_EA6215D438CA4185B106657D9712ED34}

The first time you access Adobe Analytics from the site search/merchandising user interface, a list of your company's available Adobe Analytics Report Suites are downloaded and cached. If new Report Suites were recently added, or existing ones deleted, you can use Refresh Report Suite List to update the currently displayed list in site search/merchandising.

<!-- 

t_refreshing_the_report_suite_list.xml

 -->

See [Adding an Adobe Analytics Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0).

See [Deleting an Adobe Analytics Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_0ACA172214D14654ABDB139F417B9F7D).

**To refresh the Report Suite list** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. On the [!DNL Adobe Analytics Report Suites] page, click **[!UICONTROL Refresh Report Suite List]**.

## Configuring advanced Adobe Analytics options {#task_C0FF2D69F59D44D8943A7831ED7FEC19}

You can use [!DNL Advanced Adobe Analytics Options] to control settings that are intended to help you fine tune the behavior of the Adobe Analytics Report Suite download process.

<!-- 

t_configuring_advanced_adobe_analytics_options.xml

 -->

See [Editing the Adobe Analytics metrics of a Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

**To configure advanced Adobe Analytics options** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Advanced Options]**.
1. On the [!DNL Advanced Adobe Analytics Options] page, set the following options:

<table id="table_1F502636027246E48B5867DEFC2D76D4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Maximum Rows, Any Metric </p> </td> 
   <td colname="col2"> <p>An optimization setting that prevents the download of too much Adobe Analytics data. </p> <p>If you set this option to a nonzero value, the Adobe Analytics data fetch is stopped when the total number of rows fetched for each metric exceeds the specified value. </p> <p>The default value is 0; no maximum value applied. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metric Repeating Fetch Size (rows) </p> </td> 
   <td colname="col2"> <p> Controls the number of Adobe Analytics metric values to fetch at a time. The metric data rows are repeatedly fetched until all the data is retrieved or until the maximum rows limit is reached. </p> <p>Normally you do not need to change this setting. However, you may find it helpful to optimize the metric download phase of a full re-index of your site. </p> <p>The default value is 5000. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About SAINT Classification Feeds {#concept_C55609DA24914BBC92CD90ED0259199D}

You can use Adobe Analytics SAINT to enhance your analytics reports through the acceptance of tabular data from outside sources. For example, you can use site search/merchandising to retrieve the data from its own indexes and export that data to Adobe Analytics.

<!-- 

c_about_saint_classification_feeds.xml

 -->

To successfully use the Adobe Analytics SAINT feature in site search/merchandising be aware of the following requirements:

* You must have a Adobe Analytics company and a Report Suite.

  See [About the Adobe Analytics menu](../c-about-settings-menu/c-about-adobe-analytics-menu.md#concept_5FD2D13C9D0D40988E6E51480D690411). 
* The Adobe Analytics user account must have privileges to modify the Report Suite.

  See [Setting up Adobe Analytics metrics authentication](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42). 
* The Adobe Analytics user must belong to the Web API group so that they can use the Adobe Analytics Web API. 
* The search index must have data that Adobe Analytics can use, such as having data in the correct format.

Before you create a feed, review the following questions and information so that you can complete the SAINT Feed wizard successfully:

* Which Report Suite are you going to work with? 
* Which classification set, such as product, e-var, and so on, are you going to provide data for? 
* What classifications exist in the reports? The answer to this question is determined by the type of data that is readily available from site search/merchandising, and the type of reports that Adobe Analytics reports as desirable. 
* SAINT accepts the data from site search/merchandising as a text type. The format of that data impacts the presentation of the Adobe Analytics reports.

## Creating an Adobe Analytics SAINT feed {#task_914B5AB821E84627953D8EF9339A7DD0}

You can use Adobe Analytics SAINT to enhance Adobe Analytics reports through the acceptance of tabular data from outside sources.

<!-- 

t_creating_a_adobe_analytics_saint_feed.xml

 -->

For example, you can use site search/merchandising to retrieve data from its own indexes and export that data to Adobe Analytics.

**To create an Adobe Analytics SAINT feed** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. On the [!DNL SAINT Classification Feeds] page, click **[!UICONTROL Create SAINT Feed]**.
1. In the [!DNL Create Feed] dialog box, in the **Feed Name** text field, enter the new feed name, and then click **[!UICONTROL Next]**.

   At this point, the feed is saved and added to the [!DNL SAINT Classification Feed] page. If you choose, you can exit, and edit the feed later to complete the wizard. 
1. On the [!DNL Authentication] page, specify the Adobe Analytics company name, user name, and web secret in the respective text fields, and then click **[!UICONTROL Next]**.

   Make sure that it is authorized to use the Web API with Adobe Analytics. 
1. On the **[!UICONTROL Report Suite]** page, choose a report suite and its classification data set, and then click **[!UICONTROL Next]**.
1. On the [!DNL Field Maps] page, map Adobe Analytics classifications with site search/merchandising meta data fields, and then click **[!UICONTROL Next]**.

   To adjust Adobe Analytics classifications, click **[!UICONTROL Edit]** Adobe Analytics Classifications to log in to Adobe Analytics. When you have finished making your changes, click **[!UICONTROL Refresh Classifications]** to refresh the choices of classifications. 
1. On the [!DNL Search Criteria] page, data from site search/merchandising can be filtered before it is submitted to Adobe Analytics SAINT. Construct filter rules here using the rule builder interface, and then click **[!UICONTROL Next]**.
1. On the [!DNL Configure FTP] page, select the FTP server. Specify the frequency for how often you want to upload data, and then click **[!UICONTROL Next]**.

   As a best practice, each feed has its own FTP account to avoid accidental lost of data. You can create a new Adobe Analytics FTP account here. 
1. On the [!DNL Verification] page, click **[!UICONTROL Show Data View]** to review the data view representation of the output. If any actual feed files exist, they are listed here and are available for you to download.
1. Click **[!UICONTROL Close]**.

## Editing an Adobe Analytics SAINT feed {#task_5BF34D02D0D14359B1CF4B3C1B0ACC84}

You can edit all aspects of an existing SAINT feed that you have created.

<!-- 

t_editing_a_adobe_analytics_saint_feed.xml

 -->

**To edit an Adobe Analytics SAINT feed** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. On the [!DNL Saint Classification Feeds] page, under the **[!UICONTROL Name]** column, in the drop-down list next to a feed, click **[!UICONTROL Edit feed]**.
1. In the SAINT feed dialog box, in the **Feed Name** text field, enter the new feed name, and then click **[!UICONTROL Next]**.

   At this point, the feed is saved and added to the [!DNL SAINT Classification Feed] page. If you choose, you can exit, and edit the feed later to complete the wizard. 
1. On the [!DNL Authentication] page, specify the Adobe Analytics company name, user name, and web secret in the respective text fields, and then click **[!UICONTROL Next]**.

   Make sure that it is authorized to use the Web API with Adobe Analytics. 
1. On the **[!UICONTROL Report Suite]** page, choose a report suite and its classification data set, and then click **[!UICONTROL Next]**.
1. On the [!DNL Field Maps] page, map Adobe Analytics classifications with site search/merchandising meta data fields, and then click **[!UICONTROL Next]**.

   To adjust Adobe Analytics classifications, click **[!UICONTROL Edit]** Adobe Analytics Classifications to log in to Adobe Analytics. When you have finished making your changes, click **[!UICONTROL Refresh Classifications]** to refresh the choices of classifications. 
1. On the [!DNL Search Criteria] page, data from site search/merchandising can be filtered before it is submitted to Adobe Analytics SAINT. Construct filter rules here using the rule builder interface, and then click **[!UICONTROL Next]**.
1. On the [!DNL Configure FTP] page, select the FTP server. Specify the frequency for how often you want to upload data, and then click **[!UICONTROL Next]**.

   As a best practice, each feed has its own FTP account to avoid accidental lost of data. You can create a new Adobe Analytics FTP account here. 
1. On the [!DNL Verification] page, click **[!UICONTROL Show Data View]** to review the data view representation of the output. If any actual feed files exist, they are listed here and are available for you to download.
1. Click **[!UICONTROL Close]**.

## Deleting an Adobe Analytics SAINT feed {#task_5319B1F4CA1A406393CFD7AE97258CEB}

You can delete an existing Adobe Analytics SAINT feed that you no longer need or use.

<!-- 

t_deleting_a_adobe_analytics_saint_feed.xml

 -->

**To delete an Adobe Analytics SAINT feed** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. On the [!DNL Saint Classification Feeds] page, under the **[!UICONTROL Name]** column, in the drop-down list next to a feed that you want to remove, click **[!UICONTROL Delete feed]**.
1. In the Delete dialog box, click **Yes** to verify the feed deletion.

## Viewing an Adobe Analytics SAINT feed file {#task_F0C8BADD25E14E5DB30BF31D1F879FDB}

You can open the [!DNL Verification] page of an existing SAINT feed to review the data view representation of the output.

<!-- 

t_viewing_a_adobe_analytics_saint_feed_file.xml

 -->

If any actual feed files exist, they are listed here and are available for you to download as a text file.

**To view an Adobe Analytics SAINT feed file** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. On the [!DNL Saint Classification Feeds] page, under the **[!UICONTROL Name]** column, in the drop-down list next to a feed, click **[!UICONTROL View Feed Files]**.
1. (Optional) Click **[!UICONTROL Download File]** to save the feed file as a text file.
1. Click **[!UICONTROL Close]** to return to the [!DNL SAINT Classification Feeds] page.

## Testing an Adobe Analytics SAINT feed {#task_9864D69BE3824FC29C10B36EE4855D25}

You can test an existing Adobe Analytics SAINT feed with no file upload.

<!-- 

t_testing_a_adobe_analytics_saint_feed.xml

 -->

See [Generating and uploading an Adobe Analytics SAINT feed](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_47AED946AA964334A877FDC8D4F6F00A).

See [Viewing an Adobe Analytics SAINT feed file](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB).

**To test an Adobe Analytics SAINT feed file** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. On the [!DNL Saint Classification Feeds] page, under the **[!UICONTROL Name]** column, in the drop-down list next to a feed, click **[!UICONTROL Test Feed (No file upload)]**.
1. When the feed finishes processing, from the feed name's drop-down list, click **[!UICONTROL View Feed Files]**.
1. On the [!DNL Verification] page, click **[!UICONTROL Download File]** to download the feed file.
1. Click **[!UICONTROL Close]** to return to the [!DNL SAINT Classification Feeds] page.

## Generating and uploading an Adobe Analytics SAINT feed {#task_47AED946AA964334A877FDC8D4F6F00A}

You can generate and upload feed files for an existing Adobe Analytics feed that you have created.

<!-- 

t_generating_and_uploading_a_adobe_analytics_saint_feed.xml

 -->

See [Testing an Adobe Analytics SAINT feed](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_9864D69BE3824FC29C10B36EE4855D25).

See [Viewing an Adobe Analytics SAINT feed file](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB).

**To generate and upload a Adobe Analytics SAINT feed file** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. On the [!DNL Saint Classification Feeds] page, under the **[!UICONTROL Name]** column, in the drop-down list next to a feed, click **[!UICONTROL Generate and Upload Feed]**.
1. When the feed finishes processing, from the feed name's drop-down list, click **[!UICONTROL View Feed Files]**.
1. On the [!DNL Verification] page, click **[!UICONTROL Download File]** to download the feed file.
1. Click **[!UICONTROL Close]** to return to the [!DNL SAINT Classification Feeds] page.
