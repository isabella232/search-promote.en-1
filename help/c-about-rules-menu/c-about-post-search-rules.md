---
description: You can use Post-Search Rules to examine the results of a search and determine how the search affects the displayed content.
seo-description: You can use Post-Search Rules to examine the results of a search and determine how the search affects the displayed content.
seo-title: About Post-Search Rules
solution: Target
title: About Post-Search Rules
topic: Rules,Site search and merchandising
uuid: 312d1e4a-f5b6-4629-8645-17e6f6c09fc4
index: y
internal: n
snippet: y
---

# About Post-Search Rules{#about-post-search-rules}

You can use Post-Search Rules to examine the results of a search and determine how the search affects the displayed content.

## About Post-Search Rules {#concept_AF6ADFCC0ADF4A788003964939917FDE}

You can use Post-Search Rules to examine the results of a search and determine how the search affects the displayed content. 

For example, if a search has no results, a Post-Search Rule can perform a search for a similar item. Or, it can display a web page that recommends other items to customers who search for the item that was not found.

Each Post-Search Rule consists of two main elements: the rule's actions, and its optional conditions. You can specify an unlimited number of rules and conditions. The order of these rules is important because the rule set is looped through rule-by-rule. When a rule's conditions match, all the associated actions are performed.

You can refine the set of search results for a maximum of three rounds of searching. After this, whatever is currently available is used. This limit prevents infinite loops and ensures that the customer receives an efficient response. The more times you redo a search the longer it takes to return your search results. If none of the matching rules alter one of the searches for the currently used presentation template or switch the template, the set of search results is considered finalized and post-search exits.

Post-search processing builds upon the earlier processing modules Query Cleaning and Pre-Search processing. Therefore, any custom variables set in those modules are available for use in the post-search processing rules. Similarly, pre-search processing has instantiated all of the templates where each named search associated with the presentation template has its own local copy of the CGI parameters. In turn, you can customize each search individually.

See [About Query Cleaning Rules](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C).

See [About Pre-Search Rules](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

## About Post-Search Rule conditions {#section_C43EB77CC0AC43B8B9D38569264BF1B5}

Conditions are optional. If you specify that actions are specified for every query, then the actions are always taken. You can base conditions on any CGI query parameter, cookie, search result, or custom variable that a previous rule has set. Or, you can base it on a system condition such as what the currently selected template is or if it is the last search. When you build a condition on the results of a search or a CGI parameter, you specify the template and the name of the search.

## About Post-Search Rule actions {#section_0E15FE683A894ECAAA386267EEC7F7C5}

All of the actions in a Post-Search Rule that have matching conditions are exercised. Actions typically consist of an operation, the data to perform the operation on, and the value to use. The simplest action is to switch which Presentation template to use based on the Post-Search Rule's conditions. You can use more advanced actions to change the parameters for a search that results in the search being redone. When performing an operation on a template's search parameter, specify a Presentation template and search.

## General Rules {#section_AEE923988CC748FF9DEF2233FBF333B5}

When performing operations on a template's search parameter, two special values exist, &#42;targeted and &#42;primary for the Presentation template and the named search respectively. Use these values to build rules based on the current targeted template's primary search. These constructs let you build generic rules where you do not need to worry about what the current targeted template or primary search are called. If this pass is the first through the post-search processing, the targeted template is whatever pre-search processing sets it to.

## Redirects {#section_E5669A2F13C240F2968E31C75591CD6A}

Direct Hits and redirects within Query Cleaning let you redirect to a URL based on the incoming search terms. Redirects within post-search rules extend this idea, except that it lets you check how many results that the search returned before deciding if you want a redirect to take place. With Post-Search Rules, you can redirect to a URL, where you can substitute custom variables or query parameters. Or, you can redirect to a field within the first result. When you redirect to a result's field, you define the field in the Transport template, and it must contain a valid, explicit URL, otherwise the redirect is skipped.

When you use the redirect mechanism within Post-Search Rules , you can detect when a search returns a single result. Rather than returning such a result, you can redirect to the web page that is associated with the result.

See the redirect example below for an example of using redirects with Post-Search Rules.

## Last Rule {#section_FC1E0050C9324278B171038E98F6C335}

When the conditions are met for a rule that has the option **[!UICONTROL Last Rule]** set, the post search processing module does not perform any additional rules after the action of the matching rule. This situation is useful when you have set actions that cause a later rule to match but you want the processing to stop. And, for that later rule to potentially match after the next round of searching.

## Examples {#section_DDB98383690941F9B44AD00FBA55BB56}

In the following example, assume that you have two presentation templates. One template is used to display many search results and the other template is used to display a single result and an additional search for accessories related to the main search. You want to detect when you have a single result and switch to your other presentation template. To accomplish this task, you can use the following rules:

```
On condition: 
  targeted template is default 
  targeted template primary results equal 1 
  not last search 
Perform the following actions: 
  Set targeted template to product_spotlight
```

MegaElectronic is a large electronics store. After analyzing their search data, MegaElectronic notices that many of their customers perform a product search using a product's part number. In such cases, MegaElectronic wants to redirect to the web page that is associated with the product, if the customer searched for it directly and only a single product was found.

To achieve this result, you can use a single rule with three conditions. The first condition checks that the returned search has only a single result. The second condition ensures that the query term matches MegaElectronic's part number format for the results that they want to cause the redirect. The third condition ensures that the customer did not use any facets to drill down to one result, given that the part number might be a partial part number and return more than one result. The action redirects to a field within the result.

```
On condition: 
  targeted template's primary results equal 1 
  query q matches regular expression ^\D\D\D-\d+ 
  no facet selected ^\D\D\D-\d+ 
Perform the following actions: 
  redirect to result field "loc" in template *targeted for search *primary
```

## Best Practices {#section_1BF7DE1BD5664B3BAEC26AA829FDB0BA}

* Any set of rules that trigger a new round of searching should always have a conditional clause to check that this is not the last pass through the module. If you have already performed the maximum number of searches, you cannot redo any searches. 
* If you are on the last pass through the module and the results are still poor, you can switch to a "no results" template. 
* You should base changing a presentation template on the result of a search that potentially has other parameters. If you want to select a template that is based only on the incoming query, a pre-search rule is more efficient. 
* Data mining of the query is done in the Query Cleaning module. You can reference the custom variables in the post-search processing. 
* When you do redirects, always check that the customer has not selected any facets. The reason why is because it is inconvenient when a customer drills into a facet and is suddenly taken away from the search results. The customer may want to deselect the facet when they see that the single result is not want they were looking for.

## Adding a new post-search rule {#task_52F6F9AAD65B45B5ACA1FF245DFFADD9}

You can use [!DNL Post-Search Rules] to select which presentation template is used to display the search results based on the incoming query.

<!-- 

t_adding_a_new_post_search_rule.xml

 -->

**To add a new post-search rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**.
1. On the [!DNL Post-Search Rules] page, click **[!UICONTROL Add New Rule]**.
1. In the [!DNL Name] field, type the name of the new query cleaning rule.
1. On the [!DNL Add Post-Search Rule] page, use the drop-down lists and text fields to build out your query.

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
   <td colname="col2"> <p>An HTTP cookie. Cookie names and values must be Uniform Resource Identifier encoded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom Variable </p> </td> 
   <td colname="col2"> <p>A user-defined variable. You can add, delete, or set an unlimited number of custom variables. </p> <p>You can reference any custom variables that you defined in Query Cleaning and in Pre-Search Rules modules, within Post-Search Rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>System Variable </p> </td> 
   <td colname="col2"> <p>Read-only variables set by the internal system that you can check. The following system variables are supported: </p> <p> 
     <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
      <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> hostname </span> <p>The name of the server host. </p> </li> 
      <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri </span> <p>The requested Uniform Resource Identifier without the query string. </p> </li> 
      <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args </span> <p>The entire query string. </p> </li> 
      <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> environment </span> <p>"Stage" or "live" depending on whether the incoming query was sent to your staged environment or your live environment. </p> </li> 
      <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>The Uniform Resource Locator that the customer came from. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>System Variable </p> </td> 
   <td colname="col2"> <p>Read-only variables that you can use in conditions to determine the current state. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Template's Search Facet </p> </td> 
   <td colname="col2"> <p>A facet that is local to a named search associated with a presentation template. A facet is essentially special CGI parameters used to indicate which value within a facet a customer has selected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Template's Search Parameter </p> </td> 
   <td colname="col2"> <p>A CGI parameter that is local to a named search associated with a presentation template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Template's Backend Parameter </p> </td> 
   <td colname="col2"> <p>Incoming query parameters eventually get translated into backend parameters that are used to perform the search. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> <p>Backend parameters do not show up on navigation elements. As a result, you can hide any additional parameters that you want to apply to a search from your customers. </p> <p>The parameter is local to a specific search within a presentation template. Actions on backend parameters are late-binding; that is, they are applied just before the search is sent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Targeted Template </p> </td> 
   <td colname="col2"> <p>A special instance of a system-defined custom variable that cannot be deleted. This variable contains the current targeted presentation template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rank </p> </td> 
   <td colname="col2"> <p>Lets you specify which ranking rule to use in the search. This option only appears when you have defined ranking fields and ranking rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Last Rule </p> </td> 
   <td colname="col2"> <p>When checked, the post-search processing module does not perform any additional rules after the action of the matching rule. This action is useful for when you have set actions that cause a later rule to match but you do not want the later rule to run. </p> </td> 
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

## Editing a post-search rule {#task_ECB00334C0A74C87AF857DB3EB372119}

You can edit existing post-search rules that you have added to the [!DNL Post-Search Rules] page.

<!-- 

t_editing_a_post_search_rule.xml

 -->

**To edit a post-search rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. On the [!DNL Post-Search Rules] page, under the **[!UICONTROL Actions]** column of the table, click **[!UICONTROL Edit]** for the associated rule that you want to edit.
1. On the [!DNL Edit Post-Search Rule] page, use the drop-down lists and text fields to build out your query.

   See the table of options under [Adding a new post-search rule](../c-about-rules-menu/c-about-post-search-rules.md#task_52F6F9AAD65B45B5ACA1FF245DFFADD9). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a post-search rule {#task_0F4653AB20D54B769A4FA8D1491AB4CF}

You can delete post-search rules that you no longer need or use.

<!-- 

t_deleting_a_post_search_rule.xml

 -->

When you delete a rule, the order that the remaining rules run is adjusted automatically to account for the deletion.

**To delete a post-search rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**.
1. On the [!DNL Post-Search Rules] page, under the **[!UICONTROL Actions]** column of the table, click **[!UICONTROL Delete]** for the associated rule that you want to delete.
1. In the [!DNL Confirmation] dialog box, click **[!UICONTROL OK]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Changing the order that post-search rules run {#task_40542FCD32234BBF881A81BF5477F78F}

You can reorder post-search rules to change the order in which they run on presentation templates.

<!-- 

t_changing_the_order_that_post_search_rules_run.xml

 -->

Post-search rules run in the order that they were defined. The higher a rule's order number, the later it runs in the process, trumping earlier rules. You reorder rules by entering a new number in the Order column of the table on the [!DNL Post-Search Rules] page. You can also use drag-and-drop on rules to change their run order.

**To change the order that post-search rules run** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**.
1. On the [!DNL Post-Search Rules] page, do one of the following:

    * Click the **[!UICONTROL Order]** column header to sort the rules in ascending or descending order. 
    * In the [!DNL Order] column, in the text field to the left of a pre-search rule name, type the order number that you want the rule to run. 
    * Drag-and-drop a table row to the position that you want the rule to run. All the order numbers are updated to reflect the new order in which the rules run.

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

