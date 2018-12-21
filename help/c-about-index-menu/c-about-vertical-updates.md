---
description: You can use Vertical Update to quickly update parts of your index without having to process large amounts of data.
seo-description: You can use Vertical Update to quickly update parts of your index without having to process large amounts of data.
seo-title: About Vertical Update
solution: Target
subtopic: Vertical Update
title: About Vertical Update
topic: Index,Site search and merchandising
uuid: aaac616a-532b-4af8-8e6e-9b12967128ab
index: y
internal: n
snippet: y
---

# About Vertical Update{#about-vertical-update}

You can use Vertical Update to quickly update parts of your index without having to process large amounts of data.

## About Vertical Update {#concept_E65A70C9C2E04804BF24FBE1B3CAD899}

You can use **Vertical Update** to quickly update parts of your index without having to process large amounts of data. 

A vertical index takes only seconds to perform and is useful on large capacity eCommerce websites that can take many hours to either completely or incrementally index.

When you generate a vertical index, status information is displayed, such as start time, elapsed time, and errors during the indexing process.

You can stop or restart the vertical indexing process at any time.

While the new vertical index updates your live website, customers can continue to search your site using your current index.

>[!NOTE]
>
>This feature is not enabled in [!DNL Adobe Search&Promote], by default. Contact Technical Support to activate the feature for your use.

Vertical Updates are specifically meant to be used on eCommerce-style [!DNL Adobe Search&Promote] accounts that use IndexConnector to supply the content for the search index. The typical use-case is one where the [!DNL Adobe Search&Promote] index represents a searchable product catalog, and the need exists to be able to quickly update frequently changing values, such as inventory-on-hand, availability and/or price. A Vertical Update is somewhat similar to an Incremental Index, except that it only updates portions of each document, whereas an Incremental Index replaces entire documents with new versions.

The term "Vertical Update" refers to the notion that an [!DNL Adobe Search&Promote] index can be pictured as a columnar table, with each column corresponding to an [!DNL Adobe Search&Promote] Metadata field definition, and each row corresponding to a document. The Vertical Update process replaces one or more columns without the need to alter any of the other columns' content.

Where the main source for content, an IndexConnector feed, contains all of the required data elements needed to create the index, the Vertical Update feed is a subset of the main feed, one that uses the same IndexConnector "schema" to define the data elements, but containing *only* those data items that need to be updated.

At a minimum, the Vertical Update feed needs to contain the "primary key" element (as identified with the **Primary Key** check-box in the IndexConnector configuration) and at least one data element to be updated.

For example, a primary IndexConnector feed might look like the following (but usually with many more data items):

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <title><![CDATA[Title for product 123]]></title>
  <description><![CDATA[Description for product 123.]]></description>
  <price>3.99</price>
  <link><![CDATA[http://www.somewhere.com/products/123]]></link>
  <image><![CDATA[http://www.somewher.com/images/products/123.jpg]]></image>
  <label><![CDATA[PROD123]]></label>
  <inventory>100</inventory>
  <brand><![CDATA[brand123]]></brand>
  ...
</product>
<product>
...
</product>
</products>
```

A requirement is to be able to quickly update just the `<price>` and `<inventory>` values, because these values can change rapidly on the customer's site. A Vertical Update feed might then look like the following:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <price>3.50</price>
  <inventory>90</inventory>
</product>
<product>
...
</product>
</products>
```

This information is typically stored in a separate file on the customer's server, and the IndexConnector "Vertical File Path" configuration setting points to this file. The Vertical Update process reads this new content and updates the existing [!DNL Adobe Search&Promote] index, only updating the values for `<price>` and `<inventory>`, in this case. Subsequent searches returns the newly updated content.

>[!NOTE]
>
>In this example, the `<price>` and `<inventory>` Metadata fields will need to have been defined with the **Vertical Update Field** option checked.

See also [About Remote Control for Indexing](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F) and [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5). 

## Configuring a Vertical Update of a staged website {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

You can configure what Index Connector sources you want to include in your vertical update by specifying URLs.

<!-- 

t_configuring_a_vertical_update_of_a_staged_website.xml

 -->

**To configure a Vertical Update of a staged website** 

1. On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Configuration]**.
1. On the **[!UICONTROL Vertical Update Configuration]** page, in the Update URLs field, specify the URLs of the pages that you want to index.

   The search robot only updates the documents that are identified in the specified Index Connector sources.

   This field must contain Index Connector URLs only as in the following example:

   `index:product_catalog`. 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Viewing the Vertical Update log of a live or staged website {#task_E668E1F1240C476DAA1CA783DC728232}

When a live Vertical Update or a staged Vertical Update is complete, you can view its associated log to troubleshoot any errors that may have occurred.

<!-- 

t_viewing_the_vertical_update_log_of_a_live_or_staged_website.xml

 -->

You cannot export Vertical Update log files, nor can you save them. The log file remains available for viewing until the next index occurs.

**To view the Vertical Update log of a live or staged website** 

1. On the product menu, do one of the following:

    * Click **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Live Log]**. 
    
    * Click **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Staged Log]**.

1. On the log page, at the top or bottom, do any of the following:

    * Use the navigation options **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]**, or **[!UICONTROL Go to line]** to move through the log. 
    
    * Use the display options **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]**, or **[!UICONTROL Show]** to refine what you see.

