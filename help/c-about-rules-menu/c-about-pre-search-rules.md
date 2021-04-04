---
description: Use Pre-Search Rules to analyze the incoming query and determine which presentation template to use. Pre-Search Rules are executed in sequence for every query. To alter the order of your rules you can use drag-and-drop. The actual order does not change until you save it.
solution: Target
title: About Pre-Search Rules
topic: Rules,Site search and merchandising
uuid: e75f9d9e-e8ca-4184-bf79-b1fdadb5c0fe
exl-id: 23e7feda-956a-48ce-8c61-fe0498c1bbda
---
# About Pre-Search Rules{#about-pre-search-rules}

Use Pre-Search Rules to analyze the incoming query and determine which presentation template to use. Pre-Search Rules are executed in sequence for every query. To alter the order of your rules you can use drag-and-drop. The actual order does not change until you save it.

## Using Pre-Search Rules {#concept_5BF84BB6FACB4645BA9CB7496A01CD1F} 

Pre-Search Rules are typically used to select which presentation template displays the results based on the incoming query. More advanced features can be used to alter the query that is used for a search that is being done for a presentation template. You can add, delete, or change the value of query parameters as needed. For every incoming query a pre-search-processing module examines the pre-search rules to determine if the query is modified and what presentation template is used. Each Pre-Search Rule consists of two main elements: the rule's actions and optional conditions. You can specify an unlimited number of rules and conditions. The order of these rules is important, because the rule set is looped through rule by rule. When a rule's conditions is matched, all the associated actions are performed.

In the Pre-Search Processing module all defined templates and their associated named searches are instantiated where each search is given a local copy of the cgi parameters. As a result, you can customize a search by adding, deleting, or altering one of the cgi parameters that search uses without altering any other named search the template uses or affecting any of the other templates. As a result, if you have a presentation template that displays more than one result set, you can customize each search individually. If you want to perform changes on the global CGI parameters before they are copied to each search for each template, use the Query Cleaning module.

## Pre-Search Rule Conditions {#section_B5568ADEB28546A280720309498B045D}

Conditions are optional. If you choose to have actions specified for every query then the actions are always taken. It is considered best practice for your first rule to run for every query, where it selects your default presentation template. This way you can be assured that, regardless what the incoming query is, you have selected a worst-case scenario presentation template to use. Conditions can be based on any CGI query parameter, cookie, or custom variable that a previous rule has set or a system variable.

## Pre-Search Rule Actions {#section_3B8E19D287554C1C969F5B8D81226981}

All of the actions within a Pre-Search Rule that has matching conditions are exercised. Actions typically consist of an operation, the data to perform the operation on, and the value to use. The simplest action is to specify which presentation template to use when the query matches the Pre-Search Rule's conditions. Then set the targeted template to the name of the presentation template. More complicated actions can be used to change the search that is being used for a given template via performing an operation on a template's search parameter. When performing an operation on a template's search parameter, you specify a presentation template and search.

## Generic Rules {#section_885ECB9DBF0C4D539C14F82BCAA35B4E}

When performing operations on a template's search parameter, two special values exist: &#42;targeted and &#42;primary for the presentation template and the named search respectively. With these values, you can build rules based on the current targeted template's primary search. These constructs allow for building generic rules where you do not have to worry about what the current targeted template or primary search are called. Obviously, a previous Pre-Search Rule defines what the current targeted template is. Otherwise, an initial presentation template is selected for you, which produces undesired results.

## Examples {#section_EA153A151987454EA44A4A6862466DF6}

Set the default template to guided.tmpl, when the user passes in a cgi parameter called lang, set to a known language, use that language's template.

```
    On condition: 
      Every Query 
    Perform the following actions: 
      Set targeted template to guided 
 
    On condition: 
      Query lang matches regular expression fr 
    Perform the following actions: 
      Set targeted template to guided_french 
 
    On condition: 
      Query lang matches regular expression de 
    Perform the following actions: 
      Set targeted template to guided_german
```

## Best Practices {#section_31EBAE5E54174DEE8986CBB636746A98}

* The first rule selects a default template for every query. 
* Data mining of the query is done within query cleaning rules. You can reference them in the pre-search processing. 
* Add any new custom variables that you introduced in Pre-Search Rules to a pre-search rule that is run for every query before any other Pre-Search Rules reference them.

## Adding a new pre-search rule {#task_182B95918462490D8BDA7F16A81CAC11}

You can use [!DNL Pre-Search Rules] to select which presentation template is used to display the search results based on the incoming query.

**To add a new pre-search rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. On the [!DNL Pre-Search Rules] page, click **[!UICONTROL Add New Rule]**.
1. In the [!DNL Name] field, type the name of the new query cleaning rule.
1. On the [!DNL Add Pre-Search Rule] page, use the drop-down lists and text fields to build out your query.

    <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Cookie </p> </td> 
      <td colname="col2"> <p>An HTTP cookie. Cookies name and values must be Uniform Resource Identifier encoded. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Custom Variable </p> </td> 
      <td colname="col2"> <p>A user-defined variable. Add, delete, or set an unlimited amount of user-defined variables. </p> <p>You can reference any variables that you defined in the Query Cleaning module within the Pre-Search Rules. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>System Variable </p> </td> 
      <td colname="col2"> <p>Read-only variables set by the internal system that you can check. The following system variables are supported: </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> hostname </span> <p>The name of the server host. </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri </span> <p>The requested uri without the query string. </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args </span> <p>The entire query string. </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> environment </span> <p>"Stage" or "live" depending on whether the incoming query was sent to your staged or live environment. </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>The URL that the customer came from. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet </p> </td> 
      <td colname="col2"> <p>Special CGI Parameters in the global collection that are associated with a particular facet. All CGI parameters are copied to each named search within a template after Query Cleaning. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Query Parameter </p> </td> 
      <td colname="col2"> <p>CGI Parameter in the global collection. These parameters are copied to each named search within a template after Query Cleaning. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Template's Search Parameter </p> </td> 
      <td colname="col2"> <p>A CGI parameter that is local to a named search associated with a presentation template. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Template's Backend Parameter </p> </td> 
      <td colname="col2"> <p>Incoming query parameters eventually get translated into backend parameters that are used to perform the search. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> <p>Backend parameters do not show up on navigation elements. As a result, you can hide any additional parameters that you want to apply to a search from your customers. The parameter is local to a specific search within a presentation template. Actions on backend parameters are late-binding; that is, they are applied just before the search is sent. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Targeted Template </p> </td> 
      <td colname="col2"> <p>A special instance of a system-defined custom variable that cannot be deleted. This variable contains the current targeted presentation template. You can read or set this variable by specifying the custom variable "targeted_template". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rank </p> </td> 
      <td colname="col2"> <p>Lets you specify which ranking rule to use in the search. This option only appears when you have defined ranking fields and ranking rules. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Store </p> </td> 
      <td colname="col2"> <p>The search engine automatically detects what store the customer is in based on the host name or the <span class="codeph"> gs_store </span> query parameter, with the latter having precedence. You can create conditions off of the store. In query cleaning only, you can also use an action to over-ride the current store. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Last Rule </p> </td> 
      <td colname="col2"> <p>When checked, the pre-search processing module does not perform any additional rules after the action of the matching rule. This action is useful for when you have set actions that cause a later rule to match but you do not want the later rule to run. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suspend </p> </td> 
      <td colname="col2"> <p>Turns off the running of the rule but does not delete the rule. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Add]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a pre-search rule {#task_25F77050C5DA42B29DFD1C9718FB8C64}

You can edit existing pre-search rules that you have added to the [!DNL Pre-Search Rules] page.

**To edit a pre-search rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. On the [!DNL Pre-Search Rules] page, under the **[!UICONTROL Actions]** column of the table, click **[!UICONTROL Edit]** for the associated rule that you want to edit.
1. On the [!DNL Edit Pre-Search Rule] page, use the drop-down lists and text fields to build out your query.

   See the table of options under [Adding a new pre-search rule](../c-about-rules-menu/c-about-pre-search-rules.md#task_182B95918462490D8BDA7F16A81CAC11). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a pre-search rule {#task_128B6A79CA6C451C991AEDAD58F51743}

You can delete pre-search rules that you no longer need or use.

When you delete a rule, the order that the remaining rules run is adjusted automatically to account for the deletion.

**To delete a pre-search rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. On the [!DNL Pre-Search Rules] page, under the **[!UICONTROL Actions]** column of the table, click **[!UICONTROL Delete]** for the associated rule that you want to delete.
1. In the [!DNL Confirmation] dialog box, click **[!UICONTROL OK]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Changing the order that pre-search rules run {#task_C18817276A3C459089C97448076365D1}

You can reorder pre-search rules to change the order in which they run on presentation templates.

Pre-search rules run in the order that they were defined. The higher a rule's order number, the later it runs in the process, trumping earlier rules. You reorder rules by entering a new number in the Order column of the table on the [!DNL Pre-Search Rules] page. You can also use drag-and-drop on rules to change their run order.

**To change the order that pre-search rules run** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. On the [!DNL Pre-Search Rules] page, do one of the following:

    * Click the **[!UICONTROL Order]** column header to sort the rules in ascending or descending order. 
    * In the **[!UICONTROL Order]** column, in the text field to the left of a pre-search rule name, type the order number that you want the rule to run. 
    * Drag-and-drop a table row to the position that you want the rule to run. All the order numbers are updated to reflect the new order in which the rules run.

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
