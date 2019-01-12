---
description: You can configure Did You Mean so that customers are given suggestions for valid search terms when they have tried searches that have failed. Suggestions are formed by looking for spelling and typing corrections to the search terms that result in a valid search.
seo-description: You can configure Did You Mean so that customers are given suggestions for valid search terms when they have tried searches that have failed. Suggestions are formed by looking for spelling and typing corrections to the search terms that result in a valid search.
seo-title: About Did You Mean
solution: Target
title: About Did You Mean
topic: Linguistics,Site search and merchandising
uuid: c5973541-3d6b-4fc9-bad4-66d4d3559fe8
index: y
internal: n
snippet: y
---

# About Did You Mean{#about-did-you-mean}

You can configure Did You Mean so that customers are given suggestions for valid search terms when they have tried searches that have failed. Suggestions are formed by looking for spelling and typing corrections to the search terms that result in a valid search.

## Configuring Did You Mean {#task_B539D6A0043547EFB1CA19B67E762371}

You can tailor how [!DNL site search/merchandising] makes search suggestions when a customer's query returns no, or minimal, search results.

<!-- 

t_configuring_did_you_mean.xml

 -->

**To configure Did You Mean** 

1. On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Did You Mean]**.
1. On the [!DNL Did You Mean] page, in the **Remove these Words from Suggestions** text field, enter space or line separated words to filter undesirable suggestions.

   These are words in your search index that do not show up as recommended alternative search terms. You can exclude any word matching a pattern through the use of regular expressions. Otherwise, just the exact word is removed. 

1. Set the **Did You Mean** options that you want.

   <!-- 

r_did_you_mean_options.xml

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
   <td colname="col1"> <p>Suggestion Algorithm </p> </td> 
   <td colname="col2"> <p>Adjusts how far the software goes to find suggestions. If a user makes a one-letter mistake, all of the algorithms come up with the same suggestions. The reason why is because it only takes one edit to arrive at a working suggestion, and all algorithms find words that are close to the original. But when the original search terms are not similar to existing terms in the index, the <b>Deep</b> and <b>Bad Spellers</b> Suggestion Algorithms continue to search for possible suggestions. This scenario is useful if a customer tries a proper name that is hard to type, and they sound out the names. However, if you only want similar suggestions to appear, you can choose the <b>Quick</b> algorithm. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default count of suggestions to show </p> </td> 
   <td colname="col2"> <p>Specifies the number of Did You Mean term suggestions (0-20) that you want to show when a customer's search returns no results. The default is 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Minimal suggestion word length </p> </td> 
   <td colname="col2"> <p>Prunes Did You Mean terms by specifying the minimal number of letters for a suggested word. </p> <p>For example, if you set the value to 4, the software does not suggest a word that is 1, 2, or 3 characters long. If you specify a value of 0, no short words are removed from the term suggestions. If you specify a high value, it usually results in no term suggestions. The default value is 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Minimum index frequency </p> </td> 
   <td colname="col2"> <p> Specifies the minimum number of times a word has to appear in the index before it is included in the Did You Mean dictionary. </p> <p>You cannot specify a negative number in the field. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Search for suggest term if no results </p> </td> 
   <td colname="col2"> <p>Automatically re-searches for the first suggested term when a customer's search yields no results and there is at least one Did You Mean term suggestion. </p> <p>You can use the following tags in your presentation template to indicate that site search/merchandising is automatically searching for a different term: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;guided-suggestion-original-query&nbsp;/&gt;
      &nbsp;&lt;/guided-if-suggestion-autosearch&gt;
      </code> </p> <p>You can also show other suggestions here. </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;
      &nbsp;&nbsp;There&nbsp;was&nbsp;0&nbsp;matches&nbsp;for&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt;
      &nbsp;&nbsp;&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&lt;guided-param&nbsp;gsname="q"&gt;?&nbsp;Here&nbsp;are&nbsp;the&nbsp;results&nbsp;for&nbsp;that&nbsp;search.
      &nbsp;&nbsp;&nbsp;Or&nbsp;Did&nbsp;You&nbsp;Mean
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestions&gt;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt;
      &nbsp;&lt;/guided-if-suggestion-autosearch&gt;
      </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Make suggestions due to low results </p> </td> 
   <td colname="col2"> <p>If a customer searches for a term that yields less than ten results, the search engine checks to see if it has a suggestion that can yield more than 100 results. If it does, you can use the following tags to indicate to the user that while they have results, they may have wanted to search for something else: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-low-results&gt;
      &nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;Search&nbsp;for&nbsp;guided-param&nbsp;gsname="q"&gt;.
      &nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestion&gt;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,
      &nbsp;&lt;/guided-if-not-last&gt;&lt;/guided-suggestions&gt;
      &nbsp;&lt;/guided-if-suggestion-low-results&gt;
      </code> </p> <p> In the above scenario, the number of suggestions is controlled by the value that is specified in <span class="uicontrol"> Default count of suggestions to show</span>. The low and high threshold are configurable by the options below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Make suggestions when the initial results are fewer than </p> </td> 
   <td colname="col2"> <p>Controls the number of results when the system starts to offer suggestions. </p> <p>This option appears only when you check <span class="uicontrol"> Make suggestions due to low results</span>. </p> <p>The default is 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A suggestion must generate at least this many results </p> </td> 
   <td colname="col2"> <p>Filters suggestions that are made due to low results in primary search by their result count. </p> <p>This option appears only when you check <span class="uicontrol"> Make suggestions due to low results</span>. </p> <p>The default is 100. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **Save Changes**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

