---
description: You can define Common Phrases that are used on your website so that when a customer enters a search query, they do not need to enter quotes around any of the phrases you have defined.
seo-description: You can define Common Phrases that are used on your website so that when a customer enters a search query, they do not need to enter quotes around any of the phrases you have defined.
seo-title: About Common Phrases
solution: Target
title: About Common Phrases
topic: Linguistics,Site search and merchandising
uuid: c7ca6f22-855e-4dc7-9abc-884a405d22e7
index: y
internal: n
snippet: y
---

# About Common Phrases{#about-common-phrases}

You can define Common Phrases that are used on your website so that when a customer enters a search query, they do not need to enter quotes around any of the phrases you have defined.

## About Common Phrases {#concept_4946E53586DF492EAEB1B7F757FD440F}

You can define Common Phrases that are used on your website so that when a customer enters a search query, they do not need to enter quotes around any of the phrases you have defined.

>[!NOTE]
>
>The Common Phrase feature does not appear in the user interface because it is not enabled by default. Contact Technical Support to activate this feature for your use.

Common Phrases are a collection of multiple-word phrases that are recognized during a customer's search. It treats the phrases as a combined group of words instead of individual words. When a customer enters a search query on your website, they can identify phrases by surrounding the terms with double-quotes, such as "Pacific Ocean". However, when you add groups of common phrases, the quoting steps are performed automatically for the customer as it finds matching phrases in the search query.

For example, suppose a customer to your website enters the following search query:

`hotels near the pacific ocean`

Without the addition of quotation marks around `pacific ocean`, the customer's search returns results for hotels near any ocean in the world, which is not what the customer intended.

However, when you add the common phrase "Pacific Ocean," their search query is automatically converted to the following:

`hotels near the "pacific ocean"`

The use of Common Phrases does not preclude your customers from explicitly using quotation marks around phrases of words, Instead, it simply adds quotes, when those defined phrases are found in their search query.

This search query expansion applies to backend search CGI parameters `sp_q` and `sp_q_#`,

See table rows 25, 26, and 32 in [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).  

## Adding a Common Phrase Group {#task_35C84FABCD9042C5B48C5C788B752871}

You can add Common Phrase Groups to ensure that search queries accurately return web pages that have all the words, in the exact order and proximity, that a customer typed. 

As you add Common Phrase Groups, you can use the Find feature on the main Common Phrase Group page. The Find feature lets you search for an existing phrase and find out in which group it resides.

See [Finding groups that contain particular words in a phrase](../c-about-linguistics-menu/c-about-common-phrases.md#task_20714969274740A7BB4DC71E705EA15E).

**To add a Common Phrase Group** 

1. On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. On the [!UICONTROL Common Phrases Groups] page, click **Add Phrase Group**.
1. On the [!UICONTROL Add Common Phrase Group] page, set the options that you want and add all the phrases that make up the group.

   <!-- 

r_add_common_phrase_group_options.xml

 -->

<table id="table_C5641613476D4B0B8A4916C84FB4ACD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Group Name </p> </td> 
   <td colname="col2"> <p>Required. </p> <p>The unique name of the Common Phrase Group. </p> <p>If you edit a Common Phrase Group later, note that you cannot change the Group Name. To change the Group Name, use the <span class="uicontrol"> Rename</span> feature. </p> <p>See <a href="../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB" format="dita" scope="local"> Renaming a Common Phrase Group</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Notes </p> </td> 
   <td colname="col2"> <p>Optional. </p> <p>Add information that pertains to the Common Phrase Group. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Phrases </p> </td> 
   <td colname="col2"> <p>Required. </p> <p>Lets you specify a phrase up to a maximum of five words. To adjust the maximum word setting, contact Technical Support. </p> <p>Each phrase that you enter must be unique within any Common Phrase Group. </p> <p>Use the plus (+) and minus (-) icons in the Action column to add the entered phrase or to delete a phrase. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **Add**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testing a Common Phrase {#task_A0C344E051CA45A9A0588242F9DA675D}

If you selected metadata fields to associate with a phrase group, you can test a particular phrase's expansion.

<!-- 

t_testing_common_phrases.xml

 -->

When you test a phrase's expansion, you search for an exact phrase against the metadata fields that you associated with the phrase group. The phrase is searched as if it had quotation marks around it. All other metadata fields search for only the words within the phrase, without the quotation marks. For example, suppose you tested the phrase `audi TT`. The returned results could appear as follows:

`title|body|field3:"Audi TT" url|desc|keys|target|alt:Audi TT`

**To test a common phrase** 

1. On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. On the [!UICONTROL Common Phrases Groups] page, in the **Test phrase that contains** text field, enter the phrase whose metadata expansion you want to test.
1. Click **[!UICONTROL Test]**.

   The expansion results are displayed in the text box. 
1. (Optional) Drag the lower right-corner of the text box to expand the display region.

## Finding groups that contain particular words in a phrase {#task_20714969274740A7BB4DC71E705EA15E}

You can use [!UICONTROL Find] to search for specific words in a phrase among all existing groups that you have added.

<!-- 

t_finding_common_phrases.xml

 -->

When you use Find, it locates the following:

* Where the exact same phrase is found among all the groups. 
* Any of the words in the phrase among all the groups, regardless of the word order and proximity in the phrase.

See also [Editing a Common Phrase Group](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61).

**To find groups that contain particular words in a phrase** 

1. On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. On the [!UICONTROL Common Phrases Groups] page, in the **[!UICONTROL Find groups with phrases that contain]** text field, enter a phrase.
1. Click **[!UICONTROL Find]**.

   The results are displayed in the text box. 
1. (Optional) Do one or more of the following:

* Drag the lower right-corner of the text box to expand the display region. 
* In the results window, click a hyperlinked phrase to open the Edit Common Phrase Group page of the associated group.

## Editing a Common Phrase Group {#task_5CAC3A133C5342EEAFE55A7EABCBCD61}

You can edit the existing Fields, Notes, and Phrases of a common phrase group that you have added. However, to edit the Group Name, you must use the [!UICONTROL Rename] feature. 

See also [Renaming a Common Phrase Group](../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB).

**To edit a Common Phrase Group** 

1. On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. On the [!UICONTROL Common Phrases Groups] page, click **[!UICONTROL Edit]** to the far right of a group name.
1. On the [!UICONTROL Edit Common Phrase Group] page, set the options that you want.

   See the table of options under [Adding a Common Phrase Group](../c-about-linguistics-menu/c-about-common-phrases.md#task_35C84FABCD9042C5B48C5C788B752871). 
1. Click **Save Changes**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Renaming a Common Phrase Group {#task_168E07C59C0F40989D43E7010EFF22EB}

You can change the name of an existing Common Phrase Group. However, if you want to change the existing Fields, Notes, and Phrases of a common phrase group, you must use the [!UICONTROL Edit] feature.

<!-- 

t_renaming_common_phrase_group.xml

 -->

See [Editing a Common Phrase Group](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61) .

**To rename a Common Phrase Group** 

1. On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. On the [!UICONTROL Common Phrases Groups] page, click **[!UICONTROL Rename]** to the far right of a group name.
1. On the [!UICONTROL Rename Common Phrase Group] page, in the **[!UICONTROL Group Name]** text field, enter the new name of the group.
1. Click **Rename**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a Common Phrase Group {#task_4106D282A2ED4A27B09EE5A8CAAEDA36}

You can delete any Common Phrase Group that you have added. If you delete a group by mistake, you can use [!UICONTROL History] to restore the group.

<!-- 

t_deleting_common_phrase_group.xml

 -->

See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

**To delete a Common Phrase Group** 

1. On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. On the [!UICONTROL Common Phrases Groups] page, click **[!UICONTROL Delete]** to the far right of a group name.
1. On the [!UICONTROL Delete Common Phrase Group] page, click **[!UICONTROL Delete]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

