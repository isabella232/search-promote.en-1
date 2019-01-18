---
description: You can use Templates to manage your presentation templates and transport templates.
seo-description: You can use Templates to manage your presentation templates and transport templates.
seo-title: About Templates
solution: Target
title: About Templates
topic: Design,Site search and merchandising
uuid: f5805d3e-43bf-4e13-95df-b6bd6b762d11
index: y
internal: n
snippet: y
---

# About Templates{#about-templates}

You can use Templates to manage your presentation templates and transport templates.

## About Templates {#concept_06EB481B14864E18A8AE2BCD1D6EF0B5}

You can use **[!UICONTROL Templates]** to manage your presentation templates and transport templates.

<!-- 

c_about_templates.xml

 -->

You can add, edit, copy, rename, or delete presentation templates and transport templates. When you click an existing template name in the Templates table, it is opened in an editor (or viewer) window where you can make your changes.

You can revert any changes you make to templates using the History feature from the template name's drop-down list in the Templates table.

You can reduce the page weight of a presentation template by checking the template's corresponding **[!UICONTROL Minimize]** checkbox in the template table. By reducing the template's page weight, you dynamically minimize inline JavaScript and CSS. You also remove redundant whitespace in the HTML. Minimizing the page weight of your presentation template can help to deliver your search results faster.

You can preview the appearance of the minimized template by clicking the drop-down list next to the filename and then clicking **[!UICONTROL Preview minimized]**. If you minimize the main presentation template, be sure that you remember to enable minimizing for included (with `guided-include` tag) templates because this option is not inheritable.

Even if you minimize a presentation template, you can still edit the "unminimized" version of the same template.

You can use the pre-search rules, post-search rules, and business rules to determine when to use one of your other presentation templates. It is common to have a rule such as "For every search, set the targeted template to xxxx". With such a rule in place, when you change the "Default" template in the Templates table, it appears to have no effect.

See [About Pre-Search Rules](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

See [About Post-Search Rules](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## About presentation templates {#section_ACDDEA5C499E481C828A517C230D4596}

Presentation templates are HTML templates that a customer sees when they are viewing the results of their search on your website.

In your presentation layer, you can have a single presentation template that presents the results of multiple searches from various sources. You can define as many presentation templates as you want and even define presentation templates that other templates share using `include` commands. The presentation template is where all of the Design components such as facets, menus, and breadcrumbs, come together. To display the various design components, you must use presentation template tags.

See [Presentation template tags](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

When you have more than one presentation template, you define under what conditions the various presentation templates are used. You can select which presentation template to use based on the incoming CGI parameters and cookies. Or, you can switch what presentation template you are using based on the outcome of a previous search.

When you use multiple presentation templates, be sure that you indicate which template that you want the search results to appear initially. You can do this using the **[!UICONTROL Default]** column of the Templates table.

## About transport templates {#section_35FD3E8AAA4E4695A737DB7E00C3258B}

Transport templates can be either XML or JSON templates that pass data from the back-end search to the Guided Search presentation layer.

By default, your account is configured to use XML transport templates. However, if you prefer to use JSON to pass your data to Guided Search, contact Adobe Consulting who can assist you.

In your presentation layer, you can have a single presentation template that presents the results of multiple searches. Each search can use the same transport template or a custom transport template to pass the data to the presentation layer. Because the transport template is only used to pass data to the presentation layer, it must not have any HTML that is used to display the search results. The template uses transport template tags to pass the results of the search and results for populating the facets. Within these tags, standard search template tags are used to display the actual values.

See [Search template tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

**XML Transport Template-specific tags**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>XML transport template tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>These are the root XML tags that the presentation layer uses to detect what it must parse out of the transport template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>This set of tags surround search template tags that provide summary data based on the result set. Typically, these tags contain search tags for the total number of results, lowest result, and highest result. You can define any number of additional global fields that you want with the <span class="codeph"> general-field </span> tag. </p> <p> <b>Example</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;general&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>This set of tags are wrapped around the search results, so that Guided Search knows where to look for them. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>This set of tags are wrapped around each search result, so that Guided Search recognizes where the content for a single search result starts and ends. </p> <p> <b>Example</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>This tag lets you loop through each item in a multi-value list for a single result. Use the tag only within a result. Its primary purpose is to let you iterate over attributes belonging to a result field. </p> <p> <b>Example</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>This set of tags pass over the results that populate the facets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>Each facet must have its own facet tags where the name parameter matches the facet name. Search tags are used within the facet tags for the facet values. </p> <p>See <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" type="concept" format="dita" scope="local"> About Facets </a>. </p> <p> <b>Example</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;facets&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/facets&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestions&gt;&lt;/suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>This set of tags wrap your Did You Mean suggestions so that Guided Search recognizes which XML nodes contain suggestions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestion&gt;&lt;/suggestion&gt; </span> </p> </td> 
   <td colname="col2"> <p>This set of tags wrap each Did You Mean suggestion. </p> <p> <b>Example</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-if-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;value&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/value&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;count&gt;&lt;search-suggestion-result-count&nbsp;/&gt;&lt;/count&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-if-suggestions&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**JSON transport template-specific tags**

Passing JSON versus XML from the search-engine is known to be faster because it is smaller payload and a faster parser. Use care, however, when you use JSON to ensure that what is output is strict JSON because the parser is not forgiving.

If you are new to JSON, you can use the following links and examples to help you get started:

* An introduction to JSON. See [https://www.json.org/](https://www.json.org/). 
* Test your JSON to ensure that it is valid. See [https://jsonlint.com/](https://jsonlint.com/).

**Example JSON template**

```
{ 
 "general": 
 { 
  "total" : "<search-total />", 
  "lower" : "<search-lower />", 
  "upper" : "<search-upper />", 
  "rbt-trigger-list" : "<search-rbta-trigger-id-list>", 
  "fields" :  
  [ 
   { 
    "name" : "seo_search_title", 
    "value" : "<search-include file="seo/seo_search_title.tpl" />" 
   }, 
   { 
    "name" : "seo_search_keywords", 
    "value" : "<search-include file="seo/seo_search_keywords.tpl" />" 
   } 
  ] 
 }, 
 
 <search-if-suggestions> 
 "suggestions": 
  [ 
  <search-suggestions> 
  { 
   "suggestion":"<search-suggestion-text />", 
   "count": "<search-suggestion-result-count>" 
  }<search-if-not-last-suggestion>,</search-if-not-last-suggestion> 
  </search-suggestions> 
 ], 
 </search-if-suggestions> 
 
 "facets" : 
 [ 
  { 
   "name" : "leveli", 
   "values" : [ <search-field-value-list name="leveli" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="leveli" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" :"levelii", 
   "values" : [<search-field-value-list name="levelii" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="levelii" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" : "brand", 
   "values" : [<search-field-value-list name="brand" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="brand" quotes="no" sortby="values" data="results" />] 
  }, 
 ], 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    }, 
    { 
     "name" : "title", 
     "value" : "<search-display-field name="title" encoding="json"/>" 
    }, 
    { 
     "name" : "img_url_thumbnail", 
     "value" : "<search-display-field name="img_url_thumbnail" encoding="json"/>" 
    }, 
    { 
     "name" : "description", 
     "value" : "<search-display-field name="description" encoding="json"/>" 
    }, 
    { 
     "name" : "mdi", 
     "value" : "<SEARCH-RBTA-DISPLAY-MDI-FIELD>" 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**Example JSON result section with a results attribute table**

```
{ 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    } 
   ], 
   "tables" : 
   [ 
    { 
     "name" : "downloads", 
     "fields" : 
     [ 
      { 
       "name" : "download_title", 
       "value" : <search-display-field name="download_title" encoding="json"/> 
      }, 
      { 
       "name" : "download_link", 
       "value" : <search-display-field name="download_link" encoding="json"/> 
      } 
     ] 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**Example JSON Facet section for a facet with associated fields**

```
{ 
 facets" : 
 [ 
  { 
   "name" : "t1", 
   "values" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
   "counts" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="results" sortby="values" />], 
   "custom-fields" : 
   [ 
    { 
     "name" : "taxonmyId", 
     "value" : [<search-field-value-list name="tax1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />] 
    } 
   ] 
  } 
 ] 
}
```

**Example JSON Facet section for slotted facets**

```
{ 
  "facets" : 
  [  
   { 
    "name" : "fvalue0", 
                  "dynamic" : 1, 
                  "display-names" : [<search-field-value-list name="fname0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "values" : [<search-field-value-list name="fvalue0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "counts" : [<search-field-value-list name="fvalue0" quotes="no" commas="yes" data="results" sortby="values" />] 
   } 
  ] 
} 

```

## Adding a new presentation or transport template file {#task_73199757B6E748CAA604902FF913F012}

You can use **[!UICONTROL Add Template]** to add presentation templates (.tmpl) or transport templates (.tpl) to the [!DNL Templates] page.

<!-- 

t_adding_a_new_presentation_or_transport_template_file.xml

 -->

**To add a new presentation or transport template file** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. On the [!DNL Templates] page, click **[!UICONTROL Add New Template]**.
1. In the [!DNL Add Template] dialog box, set the options that you want.

   <!-- 
   
   r_add_template_options.xml
   
   -->

    | Option  | Description  |
|--- |--- |
|New file name|Specifies the name of the template that you want to add. The proper file extension is automatically added to the file name, based on the template type you select.  Presentation templates have a .tmpl file extension; Transport templates have a .tpl file extension.|
|New template type|Lets you choose a presentation or a transport template that you want to add.  See [About Templates](../c-about-design-menu/c-about-templates.md).|

   See also [Editing a presentation or a transport template](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3). 
1. Click **[!UICONTROL Add]**.
1. (Optional) On the [!DNL Templates] page, do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a presentation or a transport template {#task_800E0E2265C34C028C92FEB5A1243EC3}

You can use the Template Editor to view and edit the content of your presentation and transport template files.

<!-- 

t_editing_a_template.xml

 -->

You can edit and test your staged presentation and transport templates, while your website visitors continue to use the live versions of your templates. You test your staged template using the staged version of your search domain URL. For example, you can test your staged transport template by running a staged query ( `sp_staged=1`) with `sp_t` that is set to the name of your transport template. When you are satisfied with how the layout appears, you can use **[!UICONTROL Push Live]** from within the template editor to push the template live. After the template is live, site visitors begin to use it.

Use the presentation template tag reference to learn how to hook up your presentation template to Guided Search components such as facets, breadcrumbs, and menus.

See [Presentation template tags](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

Use the transport template tag reference to learn more about the tags to use in transport templates.

See [Transport template tags](../c-appendices/c-templates.md#reference_227D199F5A7248049BE1D405C0584751)

**[!UICONTROL To edit a presentation or a transport template]** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. On the [!DNL Templates] page, click a presentation or a transport template file name.  
1. On the [!DNL Template Editor] page, make the changes you want to the tags and coding.

   Be careful about the changes you make in the [!DNL Template Editor]; there is no Undo feature. If you make an undesired change and want to go back to the previous version of the file, you can click **[!UICONTROL Cancel]** to return to the table of templates (assuming you did not save any of your changes up to that point). If you have already saved your changes, you can use **[!UICONTROL History]** in the editor to revert those changes. 
1. (Optional) Click **[!UICONTROL Insert Symbol]** to enter special characters and symbols that do not have corresponding keys on US English keyboards.
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

1. Close the Template Editor page when you are finished; you are returned to the Templates page.

## Copying a presentation or a transport template file {#task_B744AB3384C84DD59C33CD25E18C2C90}

You can use **[!UICONTROL Copy Template]** to save time by duplicating an existing Presentation template (.tmpl) or Transport template (.tpl) and add it to the Templates page.

<!-- 

t_copying_a_presentation_or_a_transport_template.xml

 -->

You must change the template name, the template type, or both. If you make no changes, the template is not copied.

You must have a template already added to be able to copy a template.

See [Adding a new presentation or transport template file](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

**To copy a presentation or a transport template file** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. On the [!DNL Templates] page, in the drop-down list next to a template name that you want to copy, click **[!UICONTROL Copy]**.
1. In the [!DNL Copy Template] dialog box, set one or more of the options that you want.
1. Click **[!UICONTROL Copy]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Renaming a presentation or a transport template file {#task_CC30050FC2DE4898BF44379D8378EB31}

You can use [!DNL Rename Template] to change the name of an existing presentation template (.tmpl) or a transport template (.tpl).

<!-- 

t_renaming_a_presentation_or_a_transport_template_file.xml

 -->

You can also change the template type, if desired.

You must have a template already added to rename a template.

See [Adding a new presentation or transport template file](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

**To rename a presentation or a transport template file** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. On the [!DNL Templates] page, in the drop-down list next to a template name that you want to rename, click **[!UICONTROL Rename]**.
1. In the [!DNL Rename Template] dialog box, set one or more of the options that you want.
1. Click **[!UICONTROL Rename]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a presentation or a transport template file {#task_67E532C2B83A449687737E3B06C5AA58}

You can use **[!UICONTROL Delete Template]** to remove an existing presentation template (.tmpl) or a transport template (.tpl).

<!-- 

t_deleting_a_presentation_or_a_transport_template_file.xml

 -->

You may already have a corresponding version of the staged template that is pushed live. If so, be sure you push the deleted template live using **[!UICONTROL Staging]** so that it is also deleted from the live environment. Or, you can use **[!UICONTROL Push Live]** on the Templates page.

See [About Staging](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7)

See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

You must have a template already added to be able to delete a template.

See [Adding a new presentation or transport template file](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

**To delete a presentation or a transport template file** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. On the [!DNL Templates] page, in the drop-down list next to a template name that you want to delete, click **[!UICONTROL Delete]**.
1. In the [!DNL Delete Template] dialog box, click **[!UICONTROL Delete.]**
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Previewing the presentation template minimized {#task_1757B6207CC74221AE4BFFE5674D320B}

You can use **[!UICONTROL Preview minimized]** to see what the reduced page weight of a presentation template would look like if you choose to minimize it.

<!-- 

t_previewing_the_presentation_template_minimized.xml

 -->

If you minimize the main presentation template, be sure that you remember to enable minimizing for included (with guided-include tag) templates because this option is not inheritable.

See [Reducing the page weight of a presentation template on your...](../c-about-design-menu/c-about-templates.md#task_B09BB3CE89714DEAAE8D9A899CF3009E)

You must have a template already added to preview the template minimized.

See [Adding a new presentation or transport template file](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

You can preview the XML code of a transport template file.

See [Previewing the XML of a transport template file](../c-about-design-menu/c-about-templates.md#task_58C6C52078E14AD88D2B2F0B3C439AE8)

**To preview the presentation template minimized** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. On the [!DNL Templates] page, in the drop-down list next to a presentation template name, click **[!UICONTROL Preview minimized]**.

   Use the **[!UICONTROL Type]** column in the Templates table to sort the templates by Presentation and Transport. 1. (Optional) On the [!DNL Preview Minimized Template] page, check **[!UICONTROL Wrap lines]** to read the tags within the defined window.
1. Click **[!UICONTROL Close]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Reducing the page weight of a presentation template on your website {#task_B09BB3CE89714DEAAE8D9A899CF3009E}

You can reduce the page weight of a presentation template by using the **[!UICONTROL Minimize]** option in the template table.

<!-- 

t_reducing_the_page_weight_of_a_presentation_template.xml

 -->

By reducing the template's page weight, you dynamically minimize inline JavaScript and CSS. You also remove redundant whitespace in the HTML. Minimizing the page weight of your presentation template can help to deliver your search results faster.

You can also preview the appearance of the minimized presentation template by using **[!UICONTROL Preview minimized]**.

See [Previewing the presentation template minimized](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**[!UICONTROL To reduce the page weight of a presentation template on your website]** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. On the [!DNL Templates] page, under the [!DNL Minimize] column, check the box for one or more presentation template files that you want to push as minimize on your website.

   Use the **[!UICONTROL Type]** column in the [!DNL Templates] table to sort the templates by Presentation and Transport. 1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Setting the default presentation template file to use on your website {#task_C1E8CE817E4D43E096167A347C54DD53}

When you have multiple presentation templates, you can indicate what template is initially be used to display search results.

<!-- 

t_setting_the_default_presentation_template_file_to_use.xml

 -->

You can use the pre-search rules, post-search rules, and business rules to determine when one of your other presentation templates should be used.

See [About Pre-Search Rules](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

See [About Post-Search Rules](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

It is common to have a rule such as "For every search, set the targeted presentation template to xxxx." With such a rule in place, changing the "default" template on the Templates page will appear to have no effect.

**[!UICONTROL To set the default presentation template file to use on your website]** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. On the [!DNL Templates] page, under the [!DNL Default] column, click the radio button to the corresponding presentation template file that you want to serve as the default.

   Use the **[!UICONTROL Type]** column in the [!DNL Templates] table to sort the templates by Presentation and Transport. 1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Previewing the XML of a transport template file {#task_58C6C52078E14AD88D2B2F0B3C439AE8}

You can use [!DNL Preview] to review the XML of a transport template that you have added.

<!-- 

t_previewing_the_xml_of_a_transport_template_file.xml

 -->

You must have a transport template already added to preview the template's XML.

See [Adding a new presentation or transport template file](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

You can preview minimized presentation template files to view their reduced page weight.

See [Previewing the presentation template minimized](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**To preview the XML of a transport template file** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. On the [!DNL Templates] page, in the drop-down list next to a transport template name, click **[!UICONTROL Preview]**.

   Use the **[!UICONTROL Type]** column in the [!DNL Templates] table to sort the templates by Presentation and Transport. 1. Close the viewing window and return to [!DNL site search/merchandising].
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

