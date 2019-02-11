---
description: Use the Reports menu to view or reset reports of customers' search queries.
seo-description: Use the Reports menu to view or reset reports of customers' search queries.
seo-title: About the Reports menu
solution: Target
title: About the Reports menu
topic: Reports,Site search and merchandising
uuid: 3ea856d7-dc07-455f-8dc7-c7f7f56355d7
index: n
internal: n
snippet: y
---

# About the Reports menu{#about-the-reports-menu}

Use the Reports menu to view or reset reports of customers' search queries.

   + [Data Views](c-about-reports-menu/c-about-data-views.md)
   + [Alerts](c-about-reports-menu/c-about-alerts.md)

## Viewing the Terms Report or the Null Search Terms Report {#task_53B7ED1582DD4B0E8376546A7AFC789A}

Customers' search terms are logged and reports are created for you by day, week, and month. These term reports can help you understand what customers are looking for on your website.

<!-- 

t_viewing_the_terms_report_or_the_null_search_terms_report.xml

 -->

Use this information to improve your site design or to further improve the search results for your customers.

The table in the report shows you the following information:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Column </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Graph </p> </td> 
   <td colname="col2"> <p>Visual representation of the relative number of searches for a particular word or phrase. </p> <p>Use this to quickly determine which search queries matter most to your customers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Count </p> </td> 
   <td colname="col2"> <p>The number of times that customers have searched for a particular phrase or word on your site during the time period of the selected report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Words </p> </td> 
   <td colname="col2"> <p>The number of searches in which visitors searched for a single word or a full phrase. </p> <p>Contains the phrase or word entered by each customer. Each phrase or word is hyperlinked so that you can easily check its actual search results. This column can also contain the value blank query, which indicates that a customer clicked <span class="uicontrol"> Search</span> without typing any search terms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Results Count </p> </td> 
   <td colname="col2"> <p>Contains the average number of search results displayed for each search phrase or word. </p> <p>If the count is zero (or close to zero), your customers are typically finding no results for the search. </p> <p>If the count is large, tune your search settings to ensure that the correct pages are top ranked. You can use the relevance or synonyms settings to tune the search results for the phrase or word. </p> <p>See <a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_AE48035C210145169BE067D396975620" type="concept" format="dita" scope="local"> About Definitions</a>. </p> <p>See <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> About Dictionaries</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**To view the Terms Report or the Null Search Terms Report** 

1. On the product menu, do one of the following:

* Click **[!UICONTROL Reports]** > **[!UICONTROL Terms Report]**. 

* Click **[!UICONTROL Reports]** > **[!UICONTROL Null Terms Report]**.

1. On the report page, in the drop-down list, select a report of either the top phrases or the top words.
1. Click **[!UICONTROL View Report]**.
1. (Optional) In the table, under the [!DNL Words] column, click a word to open the [!DNL Live Simulator for Today] page.

   See [About Simulator](../c-about-simulator.md#concept_020AA6751E32421A96A3455508364C7E) where you can view and test search terms. 
1. (Optional) Click **[!UICONTROL Reset Terms Report]** to clear all terms report information for the currently logged in account.

   All search terms entered by your customers are permanently removed. 

## Setting up Adobe Analytics Report Suites {#task_4A80D97030684C65AC2978B2524DE7F5}

To use Adobe Analytics Report Suite data in a site search/merchandising, you create copies of the Adobe Analytics data in your account.

<!-- 

t_setting_up_adobe_analytics_report_suites.xml

 -->

See [About Adobe Analytics Report Suites](../c-about-settings-menu/c-about-adobe-analytics-menu.md#concept_1A51AEC5D40E459B813E7891D64B1BAE).

See [Loading Adobe Analytics data](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

The [!DNL Staged Adobe Analytics Terms Report] page and the [!DNL Staged Adobe Analytics Report Suites] page displays the following information in a table:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Column </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Report Suite </p> </td> 
   <td colname="col2"> <p>Identifies the name of the Adobe Analytics Report Suite. </p> <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0" type="task" format="dita" scope="local"> Adding an Adobe Analytics Report Suite</a>. </p> <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Editing the Adobe Analytics metrics of a Report Suite</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Type (Adobe Analytics Element) </p> </td> 
   <td colname="col2"> <p>The Adobe Analytics Element, the Classification value, or both, that is used in the Report Suite request. </p> <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Editing the Adobe Analytics metrics of a Report Suite</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cross-Reference Field </p> </td> 
   <td colname="col2"> <p>The optional metadata field, whose values are used as look-up "keys" into the Report Suite. </p> <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Editing the Adobe Analytics metrics of a Report Suite</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actions </p> </td> 
   <td colname="col2"> <p>Lets you preview the most recent copy of the Report Suite's data. </p> <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0" type="task" format="dita" scope="local"> Previewing Adobe Analytics Data</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**To set up Adobe Analytics Report Suites** 

1. On the product menu, do one of the following:

* Click **[!UICONTROL Reports]** > **[!UICONTROL Adobe Analytics Terms Report]**. 

* Click **[!UICONTROL Reports]** > **[!UICONTROL Adobe Analytics Report Suites]**.

1. Click **[!UICONTROL View Live Settings]**.

## Viewing the Search Request Report or the Content Requests Report {#task_4C6EFB4D51474FC1BDE4326D1A726ECC}

You can view the [!DNL Search Requests Report] to see the number of search requests over a specified period of time. You can also view the [!DNL Content Requests Report] to see the number of content requests over a specified period of time.

<!-- 

t_viewing_the_search_request_report_or_the_content_requests_report.xml

 -->

>[!NOTE]
>
>It takes up to 48 hours before the most recent Search Request data or Content Request data becomes available in each respective report.

**To view the Search Requests Report or the Content Requests Report** 

1. On the product menu, do one of the following:

* Click **[!UICONTROL Reports]** > **[!UICONTROL Search Requests]**. 

* Click **[!UICONTROL Reports]** > **[!UICONTROL Content Requests]**.

1. On the report page, in the **[!UICONTROL Period]** drop-down list, select the length of time to include in the report.
1. In the **[!UICONTROL Chart Type]** drop-down list, select one of the following options based on the selected report:

    |Option|Description|
    |--- |--- |
    |Daily Search Request Count or Daily Content Request Count|Shows the number of requests per day.|
    |Monthly Search Request Count or Monthly Content Request Count|Shows the number of requests per month.|
    |Daily Search Request Bandwidth or Daily Content Request Bandwidth|Shows the amount of bandwidth that is required to process the daily search requests or the daily content requests.|
    
1. In the **[!UICONTROL Chart Style]** drop-down list, select how you want the data represented in the report.

## Viewing the Search Index Size Report {#task_90CF717A53D341F49E8DE17505321950}

The Search Index Size report shows the size of the search index over a specified period.

<!-- 

t_viewing_the_search_index_size_report.xml

 -->

>[!NOTE]
>
>It takes up to 48 hours before the most recent Search Index Size data becomes available in the report.

**To view the Search Index Size Report** 

1. On the product menu, click **[!UICONTROL Reports]** > **[!UICONTROL Index Size]**.
1. On the report page, in the **[!UICONTROL Period]** drop-down list, select the length of time to include in the report.
1. In the **[!UICONTROL Chart Style]** drop-down list, select how you want the data represented in the report.

## Viewing the Crawl Performance Report or the Staged Crawl Performance Report {#task_60ED9FD9769C48B1B5EEE7099B1D1899}

The index crawler's performance is logged by recording various metrics across the duration of the crawl's progress. You can choose a crawl period, metric, chart style, and crawl type when you view a live or staged crawl performance report.

<!-- 

t_viewing_the_crawl_performance_report_or_the_staged_crawl_performance_report.xml

 -->

**To view the Crawl Performance Report or the Staged Crawl Performance Report** 

1. On the product menu, do one of the following:

* Click **[!UICONTROL Reports]** > **[!UICONTROL Crawl Performance]**.

  On the report page, in the **[!UICONTROL Crawl Ending]** drop-down list, select the length of time to include in the report. 

* Click **[!UICONTROL Reports]** > **[!UICONTROL Staged Crawl Performance]**.

  On the report page, in the **[!UICONTROL Staged Crawl Ending]** drop-down list, select the length of time to include in the report.

1. In the **[!UICONTROL Metric]** drop-down list, select one of the following metrics:

    |Option|Description|
    |--- |--- |
    |Documents Downloaded|Number of documents downloaded.|
    |Pages Downloaded|Number of pages downloaded.|
    |Bytes Downloaded (KB)|Number of kilobytes downloaded.|
    |Pages Indexed|Number of pages indexed.|
    |Bytes Indexed (KB)|Number of kilobytes indexed.|
    |Average CPS|Average characters-per-second rate during the indexing crawl.|
    |Connect ms|Total time spent waiting for TCP/IP connections to complete, per page.|
    |First Byte ms|Time between sending the fetch request and the first byte received, per page.|
    |Download ms|Total document download time, per page.|
    |Aggregate|Displays Download ms, First Byte ms, Connect ms, and remaining Download times, per page.|
    |filter process ms|Total filter script process time, per page.|
    |download process ms|Total download process time (includes Download and filter), per page.|
    |index process ms|Total indexing process time, per page.|
        
1. In the **[!UICONTROL Chart Style]** drop-down list, select how you want the data represented in the report. You can select **[!UICONTROL Bars]** or **[!UICONTROL Area]**.
1. In the **[!UICONTROL Chart Type]** drop-down list, choose the index level you want to report on. You can select **[!UICONTROL Full]**, **[!UICONTROL Incremental]**, or **[!UICONTROL Full & Incremental]**.

## Viewing the Change Log {#task_166F1156719F4B3D834BEA8E249C8057}

The Change Log shows you a history of recent changes made within your account.

<!-- 

t_viewing_the_change_log.xml

 -->

Only changes that appear under [!DNL History] are shown. The changes are listed in reverse chronological order. Each entry shows the page that was changed, its version number in History, the e-mail address of the user who made the changes, the time of the change, and whether the change was a save or the page's settings pushed live.

See [About Staging](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7). 

1. On the product menu, click **[!UICONTROL Reports]** > **[!UICONTROL Change Log]**.
1. On the [!DNL Change Log] page, use the navigation and viewing options at the top and bottom of the page to view the log information.
