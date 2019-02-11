---
description: You can use Words & Language to determine how search terms are matched to the content of your web pages.
seo-description: You can use Words & Language to determine how search terms are matched to the content of your web pages.
seo-title: About Words & Language
solution: Target
title: About Words & Language
topic: Linguistics,Site search and merchandising
uuid: 793d7a40-4609-44b8-a170-536eb1434537
index: n
internal: n
snippet: y
---

# About Words & Language{#about-words-language}

You can use [!DNL Words & Language] to determine how search terms are matched to the content of your web pages.

## Using Words & Language {#concept_CEB4B9576F3C4E2EB87B352EEC738D79}

Before the effects of [!DNL Words & Language] settings are available to site visitors, including any changes you make to those settings, you must regenerate your site index. Regenerating, unlike indexing, does not involve crawling your web pages and takes only a few seconds. 

## Configuring how search terms are matched to your web content {#task_351A9144A51F4B41923BDBACDEF3B616}

You can use Words & Language to determine how site search/merchandising matches search terms to the content of your web pages.

<!-- 

t_configuring_how_search_terms_matched_to_your_web_content.xml

 -->

**To configure how search terms are matched to your web content** 

1. On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**.
1. On the [!DNL Words & Languages] page, set the options that you want.

   <!-- 
   
   r_words_and_languages_options.xml
   
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Case Sensitivity </p> </td> 
      <td colname="col2"> <p>Not selected by default. </p> <p>Determines whether uppercase letters are distinguished from lowercase letters. For example, when selected, "Succeed" is distinguished from "succeed", and the search results can vary between the two. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Diacritic Sensitivity </p> </td> 
      <td colname="col2"> <p>Selected by default. </p> <p> Determines whether words that contain diacritic characters are distinguished from words that do not. For example, when selected, "pagina" is distinguished from "página". Deselect this option if you have a website that uses non-English languages. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Numbers </p> </td> 
      <td colname="col2"> <p>Selected by default. </p> <p>Determines whether words that contain digits are indexed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignore Apostrophes </p> </td> 
      <td colname="col2"> <p>Not selected by default. </p> <p>Apostrophes are removed from queries. For example, a search for "Tree's" would return the same results as a search for "Trees". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignore Hyphens </p> </td> 
      <td colname="col2"> <p>Not selected by default. </p> <p>Hyphens are removed from queries. For example, a search for "blue-bell" would return the same results as a search for "bluebell". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Partial Alphanumeric Matching </p> </td> 
      <td colname="col2"> <p>Not selected by default. </p> <p>When selected, this option lets you split tokens on alphabetical-numerical transitions to allow free-text matches on part or product tokens. </p> <p>For example, suppose that you have a product identifier of <span class="codeph"> 910XT </span> in the body content of one or more pages on a website. When this option is <i>not</i> selected, <span class="keyword"> Adobe Search&amp;Promote </span> finds matches for this product identifier when searching for <span class="codeph"> 910XT </span>. And, with <span class="uicontrol"> Search Concat-Div-Enable </span> turned on, <span class="keyword"> Adobe Search&amp;Promote </span> would also find <span class="codeph"> 910 XT </span>. However, it would not find instances of <span class="codeph"> 910 </span> or <span class="codeph"> XT </span> exclusively. </p> <p>When you select <span class="uicontrol"> Partial Alphanumeric Matching </span>, the indexer breaks these mixed alphanumeric tokens into multiple tokens. For example, a product identifier such as <span class="codeph"> XYZ123 </span> is indexed into three tokens: <span class="codeph"> XYZ123 </span>, <span class="codeph"> XYZ </span>, and <span class="codeph"> 123 </span>. Such functionality allows for search-time free-text matching on any of these variants. </p> <p>In another example, suppose that you have the product identifier <span class="codeph"> AB910XT </span>. If you select <span class="uicontrol"> Partial Alphanumeric Matching </span> <i>and</i> have <span class="uicontrol"> Search Concat-Div-Enable </span> turned on, <span class="keyword"> Adobe Search&amp;Promote </span> indexes it as <span class="codeph"> AB910XT </span>, <span class="codeph"> AB </span>, <span class="codeph"> 910 </span>, and <span class="codeph"> XT </span>. Then, when a user searches for <span class="codeph"> 910XT </span>, for example, the search expands to also find instances of <span class="codeph"> 910XT </span>, <span class="codeph"> 910 </span>, or <span class="codeph"> XT </span>. </p> <p> <p>Note:  <span class="uicontrol"> Search Concat-Div-Enable </span> is not enabled by default. Contact Technical Support to activate the feature for your use. </p> </p> <p> <p>Note:  <span class="uicontrol"> Partial Alphanumeric Matching </span> is applied globally to all indexed fields. However, it only affects free-text matching; it does not affect exact matching or range matching. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sound-Alike Matching </p> </td> 
      <td colname="col2"> <p>Selected by default. </p> <p>Words that sound alike are matched such as "health" and "helth". This feature allows your customer to easily search despite misspelling a word. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Alternate Word Forms </p> </td> 
      <td colname="col2"> <p>Default is <b>Default Alternate Word Forms</b>. </p> <p>You can select from the following options in the Alternate Word Forms drop-down list: 
      <ul id="ul_CAC73FB4D1384312BB5DD327D3D66948"> 
      <li id="li_F4E76CD27EA34AC5BC81E648BC6CBA4C"><b>None</b> <p>No stemming or alternative word forms are applied during indexing. </p> </li> 
      <li id="li_3186FD1F3BC94A5CB66FFF8EA6726D81"><b>Default Alternate Word Forms</b> <p>Stemming is automatically done during indexing. </p> </li> 
      <li id="li_5815DE0795E0423C9C84C62B96A3F841"><b>Domain Dictionary</b> <p>Any domain dictionary that you set as a stemming dictionary is used a source of alternate word forms. </p> <p>See <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> About Dictionaries </a>. </p> <p>See <a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074" type="task" format="dita" scope="local"> Configuring a dictionary as a stemming dictionary </a>. </p> </li> 
      </ul> </p> <p>If phrase stemming is enabled in <span class="keyword"> Adobe Search&amp;Promote </span>, be aware that alternate word forms also occur within phrases. </p> <p>See <a href="../c-searchpromote-release-notes/c-rn-06-19-14-version-815.md#concept_E8CEBC65A28A4E61BDE69B4B4DA55E73" format="dita" scope="local"> Search&amp;Promote 8.15.0 Release Notes (6/19/2014) </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Language </p> </td> 
      <td colname="col2"> <p>Default is <b>English (United States)</b>. </p> <p>The selected language ensures that date and numeric values are parsed according to the conventions used in the selected part of the world. </p> <p>When <span class="uicontrol"> Alternate Word Forms </span> is set to <span class="uicontrol"> Default Alternate Word Forms </span> or to <span class="uicontrol"> Domain Dictionary </span>, word forms and word endings change according to the linguistic rules for the selected language. </p> <p>By default, the Language setting is not used to determine the language of pages read from your website. The language for a read page is determined from its HTTP headers or from metatags within the page itself. Your website could contain pages in many different languages. Each page is correctly read and indexed, regardless of the language that is selected here. </p> <p>If you use a Unicode character set encoding such as UTF-8 for some pages on your website, make sure that the language for each of those pages is correctly specified. If the appropriate HTTP headers or metatags do not exist for your Unicode documents, you can use <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Injections </span> to specify the appropriate language. </p> <p>Check <span class="uicontrol"> Apply to documents with no specified language? </span> to use the Language setting for pages read from your website that have no explicit setting. Use this setting when only <i>some</i> of your documents do not have language settings. Use <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Injections </span> if either <i>none</i> of your documents have language settings, or the set of affected documents is a well-known and manageably small list. </p> <p>See <a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5" type="concept" format="dita" scope="local"> About Injections </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Use Decompounder? </p> </td> 
      <td colname="col2"> <p> <p>Note:  This feature is only used for Danish and German. Also, this feature is not enabled by default. Contact Technical Support to activate the feature for your use. After it is enabled, the <b>Use Decompounder?</b> option only appears in the user interface if you select <span class="uicontrol"> Danish </span> or <span class="uicontrol"> German </span> from the <span class="uicontrol"> Language </span> drop-down list described earlier in this table. </p> </p> <p>When you select <span class="uicontrol"> Use Decompounder? </span>, the service breaks down Danish or German compound words, which allow the indexing of component words along with the original compound words. </p> <p>To see how this feature works, enter words into the text field, and then click <span class="uicontrol"> Test </span>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Save Settings]**.
1. To preview the results of your changes, click **[!UICONTROL regenerate your staged site index]** to rebuild your staged website index.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

