---
description: You can override the expansion of search query results.
seo-description: You can override the expansion of search query results.
seo-title: About Query Expansion Overrides
solution: Target
title: About Query Expansion Overrides
topic: Linguistics,Site search and merchandising
uuid: c46b1972-ab88-48a0-848f-366485a5bf4c
index: y
internal: n
snippet: y
---

# About Query Expansion Overrides{#about-query-expansion-overrides}

You can override the expansion of search query results.

## About Query Expansion Overrides {#concept_6895B469B0E044299E93361BFA06B554}

You can override the expansion of search query results. 

When you configure a query expansion override, you create a set of "rules". Each rule says, essentially, "Do not expand `<this>` into `<that>` at the time of search" where `<this>` is a simple text word or phrase, and `<that>` is text word or phrase, or a classification.

>[!NOTE]
>
>This feature is not enabled in Search&Promote, by default. Contact Technical Support to activate the feature for your use. After the Query Expansion Overrides feature is enabled, you must "turn it on" in the user interface.

**How a Query Expansion Override works**

When a Text and Term value is specified in the Query Expansion Overrides Add page, the code acts on the specific pairing. When a classification type is specified as a Term, such as Dictionaries or Alternate Word Forms, the Do Not Expand value is not converted into any form created by the indicated classification.

For example, suppose that you have the following definition:

`Do Not Expand = "dog"`

`Type = Text`

`Term = "dogs"`

A search query for "dog", which expands to include "dog's" and "dogs" by way of Alternate Word Forms, would not include "dogs".

However, if the definition was the following:

`Do Not Expand = "dog"`

`Type = Alternate Word Forms`

The query does not include "dog's" or "dogs" (the available Alternate Word Forms for "dog".)

You can specify multiple terms, multiple classifications, or both. However, if you select All as the Type, any multiple-term list is collapsed to just a single "All" entry.

If Text and classification entries are mixed in any rule, they are reorganized in the user interface to show text values first. However, this does not imply or affect the order of evaluation at the time of search.

Text terms are validated to remove meaningless references. That is, it compares the term with the Do Not Expand value and removes the term if there is a match. Additionally, duplicate Term values, either text or classification, are removed.

If you add a new rule with a Do Not Expand value replicating an earlier definition, the new definition's Terms are added to the original. 

## Configuring Query Expansion Overrides {#task_A087354A509D4997BA275186C224160E}

Defining and adding a Query Expansion override in Search&Promote.

<!-- 

t_configuring_query_expansion_overrides.xml

 -->

>[!NOTE]
>
>This feature is not enabled in Search&Promote, by default. Contact Technical Support to activate the feature for your use. After the Query Expansion Overrides feature is enabled, you must "turn it on" in the user interface. The first few steps below outline how to do that.

**To configure Query Expansion Overrides** 

1. In Search&Promote, click **Settings** > **User** > **View Roles**.
1. On the View Roles page, in the Actions column of the table, click **Edit** to the right of the role whom you want to give access to Query Expansion Overrides on the Linguistics menu.
1. On the Edit Role page, expand the Linguistics tree.
1. Check **Query Expansion Overrides**, and then click **Save Changes**.
1. Click **Linguistics** > **Query Expansion Overrides**.
1. Click **Add Query Expansion Overrides**.
1. In the Query Expansion Overrides Add page, set the options you want.

   <!-- 

r_query_expansion_override_definitions.xml

 -->

<table id="table_9497D57A5F0E4D02A215B4E32AA60F2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Do Not Expand </p> </td> 
   <td colname="col2"> <p>Specifies the word or phrase that you do not want to expand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type </p> </td> 
   <td colname="col2"> <p>Select <b>Text</b> to specify a specific word or phrase pairing. Or, select a classification to specify that the Do Not Expand word or phrase is not converted by way of the selected classification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Term </p> </td> 
   <td colname="col2"> <p>Only available if you selected <b>Text</b> as the Type. Specifies the word or phrase to exclude from the search expansion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Action </p> </td> 
   <td colname="col2"> <p> Click <b>+</b> or <b>-</b> to add or delete Terms, respectively, to the definition. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. When you are finished, click **Add**.

   From the Query Expansion Overrides Definitions page, you can edit or delete the definitions you have added. 
1. To preview the results of your additions, click **regenerate your staged site index** in the blue box to quickly rebuild your staged website index.
1. (Optional) Do one of the following:

    * Click **Live**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F) 
    
    * Click **Push Live**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

