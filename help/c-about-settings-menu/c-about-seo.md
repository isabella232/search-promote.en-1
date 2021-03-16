---
description: You can use SEO (Search Engine Optimization) meta tags to help tailor certain elements of your pages and thereby improve search engine placement.
solution: Target
subtopic: SEO
title: About SEO
topic: Settings,Site search and merchandising
uuid: 5c5d64f5-fe79-4489-85c6-399d1437f2c4
---

# About SEO{#about-seo}

You can use SEO (Search Engine Optimization) meta tags to help tailor certain elements of your pages and thereby improve search engine placement.

## Using SEO {#concept_C58BFCE720824A2B9B5F5E613CFD4C0B} 

You can define each such element as a piece of starting text followed by a list of words. The list of words can include the following:

* Popular search phrases on your site over a selected time period (for example, "last month"), subject to your custom exclusions. 
* Value sets of one or more fields from the search the page came from. 
* Static words and phrases that you define in a list

The most common page elements that people use for SEO are the page title, and the "keywords" and "description" meta tags. You can define settings for these three page elements. Additionally, you can define these three settings for each of the three types of pages: Search Result Pages, Browse Pages, and Item Detail Pages.

When you save or preview your SEO settings, small segments of search (transport) templates are generated that you can include in your other search templates with the `<search-include>` template tag. By way of example, you can include the Search Results Pages Title field into another template with the following: 

```
<search-include file="seo/seo_search_title.tpl" />
```

The nine possible values for the `file` attribute of the `<search-include>` tag for SEO fields are the following:

* `seo/seo_search_title.tpl` 
* `seo/seo_search_description.tpl` 
* `seo/seo_search_keywords.tpl` 
* `seo/seo_browse_title.tpl` 
* `seo/seo_browse_description.tpl` 
* `seo/seo_browse_keywords.tpl` 
* `seo/seo_item_title.tpl` 
* `seo/seo_item_description.tpl` 
* `seo/seo_item_keywords.tpl`

To use SEO fields in a presentation template, you complete several steps.

First, you use `<search-include>` as described above to include the desired fields in an XML search template, within a `<general>` element.

Then, surround each `<search-include>` tag with `<general-field>` and `</general-field>` tags, giving the field names in the `name` attribute as in the following example:

```
<general> 
    <general-field name="seo_search_title"><search-include file="seo/seo_search_title.tpl" /></general-field> 
    <general-field name="seo_search_description"><search-include file="seo/seo_search_description.tpl" /></general-field> 
    <general-field name="seo_search_keywords"><search-include file="seo/seo_search_keywords.tpl" /></general-field> 
</general>
```

Then, in your presentation template, you can use `<guided-general-field>` tags to insert the named fields wherever you need as in the following example:

```
<title><guided-general-field gsname="default" field="seo_search_title"></title> 
<meta name="description" content="<guided-general-field gsname="default" field="seo_search_description">"/> 
<meta name="keywords" content="<guided-general-field gsname="default" field="seo_search_keywords">"/>
```

Notice the use of the `gsname` attribute to specify, in this case, the "default" search.

Altogether, you can define nine different SEO fields that you can use in your web pages. They include the following:

* Search Result pages - title, description, and keywords 
* Browse pages - title, description, and keywords 
* Item Detail pages - title, description, and keywords

All nine fields are defined with similar settings. In fact, the names of the nine fields, such as the "title" field in "Search Results Pages", are only suggestions of how you might use them. You can use any of the fields in any context in your presentation templates and search templates.

See also [About Templates](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

See also [Presentation template tags](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

See also [Search template tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

See also [Configuring a search results word list](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4). 

## Configuring a search results word list {#task_A459A3734EC04042BA52C81184251DD4}

You can configure the list of search result words and phrases that are included in page titles, descriptions, and keywords.

**To configure a search results word list** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**.
1. On the [!DNL SEO Browse Pages Word List] page, in the respective [!DNL Title], [!DNL Description], and [!DNL Keywords] groups, set the options that you want.

    <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Title | Description | Keywords Starts With </p> </td> 
      <td colname="col2"> <p>The text that you want to display in front of the word list. </p> <p>For example, you might want the Keywords list to begin with the word "Brands". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Include Popular Searches During </p> </td> 
      <td colname="col2"> <p>The time period for which searches are included. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximum Search Count </p> </td> 
      <td colname="col2"> <p>The maximum number of searches that are included. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Include Field Values </p> </td> 
      <td colname="col2"> <p>The field values that are included in the results word list. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Add These Words &amp; Phrases </p> </td> 
      <td colname="col2"> <p>List the words that you want to add to the search results page title, the browse page title, or the item detail page title. </p> <p>Click <b>Edit</b> to add words to the list. </p> <p>You can add one word or phrase per line. When you are finished, click <b>Save Changes</b>, and then close the page to return to the main SEO page. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Remove These Words &amp; Phrases (except from included field values) </p> </td> 
      <td colname="col2"> <p>List the words that you want to remove from the search results page title, the browse page title, or the item detail page title. </p> <p>Click <b>Edit</b> to add words to the remove list. </p> <p>You can add one word or phrase per line. When you are finished, click <b>Save Changes</b>, and then close the page to return to the main SEO page. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Optional) Click **Preview Sample Output** to preview the resulting values for the SEO fields that you set.

   See [Previewing the SEO meta tags that you configured](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621). 
1. Click **Save Changes**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL SEO Search Results Word List] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configuring a browse pages word list {#task_D7A1D765A92A4D6C94E672B3A86ECB5A}

You can configure the list of browse pages words and phrases that are included in page titles, descriptions, and keywords.

**To configure a browse pages word list** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Browse Pages]**.
1. On the [!DNL SEO Browse Pages Word List] page, in the respective [!DNL Title], [!DNL Description], and [!DNL Keywords] groups, set the options that you want.

   See the table of options under [Configuring a search results word list](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4). 
1. (Optional) Click **Preview Sample Output** to preview the resulting values for the SEO fields that you set.

   See [Previewing the SEO meta tags that you configured](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621). 
1. Click **Save Changes**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL SEO Browse Pages Word List] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configuring an item detail word list {#task_761538C519B34164BE189F13C39B2495}

You can configure the list of item detail words and phrases that are included in page titles, descriptions, and keywords.

**To configure an item detail word list** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Item Detail Pages]**.
1. On the [!DNL SEO Item Detail Word List] page, in the respective [!DNL Title], [!DNL Description], and [!DNL Keywords] groups, set the options that you want.

   See the table of options under [Configuring a search results word list](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4). 
1. (Optional) Click **Preview Sample Output** to preview the resulting values for the SEO fields that you set.

   See [Previewing the SEO meta tags that you configured](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621). 
1. Click **Save Changes**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL SEO Item Detail Word List] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Previewing the SEO meta tags that you configured {#task_3F97949E193C4F92A104AD117FE49621}

You can preview the resulting values for the SEO fields that you set to see what is inserted where you use them. 

SEO fields can contain included field values, so the search results may depend on the search query that you specify.

**To preview the SEO meta tags that you configured** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**.
1. On the SEO page, click **Preview Sample Output**.
1. On the [!DNL SEO Preview] page, in the [!DNL Enter sample query] field, type the query term you want to search on.
1. Click **Search**.

   The resulting Title, Description, and Keywords fields show the content that is inserted into a page based on the search query you just entered. 
1. Click **Close** to return to the main SEO page.
