---
description: Use Query Cleaning Rules to analyze and modify the incoming query.
seo-description: Use Query Cleaning Rules to analyze and modify the incoming query.
seo-title: About Query Cleaning Rules
solution: Target
title: About Query Cleaning Rules
topic: Rules,Site search and merchandising
uuid: 683af81f-f7c0-45f8-9212-e5e7cb82ccca
index: y
internal: n
snippet: y
---

# About Query Cleaning Rules{#about-query-cleaning-rules}

Use Query Cleaning Rules to analyze and modify the incoming query.

## About Query Cleaning Rules {#concept_17F3CDDC3C8A4128AF092A82B777B86C}

Use Query Cleaning Rules to analyze and modify the incoming query. 

This feature is often used when you want to modify site search/merchandising behavior. For example, you could change a blank search to a popular keyword instead of a "&#42;" search, thus promoting a popular product. You can also use query cleaning rules to perform a direct hit, where you redirect to a URL. This can be particularly useful when you detect that someone is searching for a product SKU and you want to skip the search and redirect to that product's page. Query Cleaning can also mine the query and set custom variables that can be used in later processing flow steps. Query cleaning rules are executed in sequence for every query. To alter the order of your rules you can use drag-and-drop. The actual order is not changed until you save it.

The query cleaning rules in a query cleaning module are examined to determine if any of the query parameters must be modified or if any custom variables must be set. Each query cleaning rule consists of two main elements: the rule's actions and optional conditions. An unlimited number of rules and conditions can be specified. The order of these rules is important, as site search/merchandising loops through the rule set rule by rule. When a rule's conditions match, all the associated actions are performed.

After query cleaning is completed, the resulting CGI parameters are used going forward. Any custom variables that were set are available for use by later stages in the processing flow. By default, the system automatically removes leading and trailing white space from the query term.

## About Query Cleaning Conditions {#section_BF6F25F94FED4DDEA8600D921EA43A66}

Conditions are optional. If you decide that actions are specified for every query, the actions are always taken. Conditions can be based on any CGI query parameter, existing cookie, or custom variable that a previous rule has set. It is considered "best practice" for the first query cleaning rule to run for every query, where it defines and initializes all of the custom variables you plan to use.

## About Query Cleaning Actions {#section_78F74A9B48DE484191CDA95F5B4E7154}

All of the actions within a query cleaning rule that has matching conditions are exercised. Actions typically consist of an operation, the data on which to perform the operation, and the value to use.

See the table of options in [Adding a query cleaning rule](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54).

## About Redirects {#section_597481E6194440C0A7B9E6FC901A81C0}

The Direct-Hits interface lets you define a set of redirects based on the incoming query term. Redirects within Query Cleaning extends this idea. However, redirects give you finer granularity on when a redirect takes place via specifying conditions and lets you redirect to a dynamic URL rather than a static URL. When you select the redirect action, the row is updated to have a text box where you specify the URL you would like to redirect to. In the URL, you can specify variables or parameters that you would like to substitute via enclosing them in double curly brackets. Custom variables are of higher precedence than CGI parameters in the substitution.

## Examples {#section_DB5047CC38FB4A57B15CAAF9848073E3}

Assume you have a clothing retail store with a website. If the user clicks Search without any search terms, you want to return a search against jeans, because that's what you are internationally known for. You also want to parse the query term for a gender so that you can create a pre-search rule later, based on the custom variable that uses a different presentation template for each gender.

```
On condition: 
  query q equal 
Perform the following actions: 
  Set query parameter q to value jeans 
 
On condition: 
  Query q matches regular expression wom[e|a]n[s]|girl[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value female 
 
On condition: 
  Query q matches regular expression men[s]|boy[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value male
```

MegaElectronic is a large electronics store. From analyzing their search data, MegaElectronic has noticed that many their savvy customers often search for a product using the product's SKU, rather than returning a search result for the single product, MegaElectronic would like to redirect to the web page associated with that SKU.

```
On condition: 
  query q matches regular expression ^\D\D\D-\d\d\d\d$ 
Perform the following actions: 
  redirect to http://www.megaelectronic.com/?sku={{q}}
```

## Adding a query cleaning rule {#task_47F43988D3D9485F8AE1DFDA7E00BF54}

You can define rules that clean-up or edit the incoming search query from a customer.

<!-- 

t_adding_a_query_cleaning_rule.xml

 -->

You can only select templates that currently exist. If you do not have any templates, you must first define them.

See [About Templates](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**To add a query cleaning rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**.
1. On the [!DNL Query Cleaning Rules] page, click **[!UICONTROL Add New Rule]**.
1. In the [!DNL Name] field, type the name of the new query cleaning rule.
1. On the [!DNL Add Query Cleaning Rule] page, use the drop-down lists and text fields to build out your query.

<table id="table_9AA09226950540A39A088037E9461A88"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie </p> </td> 
   <td colname="col2"> <p>An HTTP cookie. You can define conditions based on cookies that are associated with your domain. Or, you can set a cookie that is written with outgoing search results. Cookies name and values must be Uniform Resource Identifier encoded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom Variable </p> </td> 
   <td colname="col2"> <p>A user-defined variable. Add, delete, or set an unlimited amount of user-defined variables. You can reference any user-defined variables here within Pre-Search Rules and Post-Search Rules. </p> </td> 
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
      <li id="li_6FEE352DB7A842FCB2EBE1398AD03666"> <span class="uicontrol"> user agent </span> <p>The "user-agent" string of the customer's browser. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Query Parameter </p> </td> 
   <td colname="col2"> <p>CGI parameters passed to the query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Backend Parameter </p> </td> 
   <td colname="col2"> <p>Incoming query parameters eventually get translated into backend parameters that are used to perform the search. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> <p>Backend parameters do not show up on navigation elements. As a result, you can hide any additional parameters that you want to apply to a search from your customers. Actions on backend parameters are late-binding; that is, they are applied just before the search is sent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Facet </p> </td> 
   <td colname="col2"> <p>Special CGI parameters associated with a given facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rank </p> </td> 
   <td colname="col2"> <p>Lets you specify which ranking rule to use in the search. This option only appears when you have some ranking fields and ranking rules defined. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Store </p> </td> 
   <td colname="col2"> <p>The search engine automatically detects what store the user is in based on the host name or the <span class="codeph"> gs_store </span> query parameter, with the latter having precedence. You can create conditions off of the store. In query cleaning only, you can also use an action to over-ride the current store. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Last Rule </p> </td> 
   <td colname="col2"> <p>When the conditions are met for a rule that has last rule set, the query cleaning processing module does not perform any additional rules after the action of the matching rule. This is useful when you have set actions that will cause a later rule to match but you do not want the later rule to fire. Note that, if a rule's action is to perform a redirect, the redirect takes place immediately, so it essentially acts as if the last rule were set. </p> </td> 
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

## Editing a query cleaning rule {#task_FA2FF1A7E2634350AD703485CBC27CB3}

You can edit existing query cleaning rules that you have added to the Query Cleaning Rules page.

<!-- 

t_editing_a_query_cleaning_rule.xml

 -->

**To edit a query cleaning rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**.
1. On the [!DNL Query Cleaning Rules] page, under the **[!UICONTROL Actions]** column of the table, click **[!UICONTROL Edit]** for the associated rule that you want to edit.
1. On the [!DNL Edit Query Cleaning Rule] page, use the drop-down lists and text fields to build out your query.

   See the table of options under [Adding a query cleaning rule](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a query cleaning rule {#task_C52D17226B824590B087CAB6970CBB01}

You can delete query cleaning rules that you no longer need or use.

<!-- 

t_deleting_a_query_cleaning_rule.xml

 -->

When you delete a rule, the order that the remaining rules run is adjusted automatically to account for the deletion.

**To delete a query cleaning rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**.
1. On the [!DNL Query Cleaning Rules] page, under the **[!UICONTROL Actions]** column of the table, click **[!UICONTROL Delete]** for the associated rule that you want to delete.
1. In the [!DNL Confirmation] dialog box, click **[!UICONTROL OK]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Changing the order that query cleaning rules run {#task_C24012C45A4445468A7FD998017388CA}

You can reorder query cleaning rules to change the order in which they run on presentation templates.

<!-- 

t_changing_the_order_that_query_cleaning_rules_run.xml

 -->

Query cleaning rules run in the order that they were defined. The higher a rule's order number, the later it runs in the process, trumping earlier rules. You reorder rules by entering a new number in the Order column of the table on the [!DNL Query Cleaning Rules] page. You can also use drag-and-drop on rules to change their run order.

**To change the order that query cleaning rules run** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**.
1. On the [!DNL Query Cleaning Rules] page, do one of the following:

    * Click the [!DNL Order] column header to sort the rules in ascending or descending order. 
    * In the [!DNL Order] column, in the text field to the left of a query cleaning rule name, type the order number that you want the rule to run. 
    * Drag-and-drop a table row to the position that you want the rule to run. All the order numbers are updated to reflect the new order in which the rules run.

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

