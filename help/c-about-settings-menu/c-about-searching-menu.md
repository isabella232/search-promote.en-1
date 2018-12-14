---
description: Use the Searching menu to set excluded words, collections, restrictions, preview, and frames.
seo-description: Use the Searching menu to set excluded words, collections, restrictions, preview, and frames.
seo-title: About the Searching menu
solution: Target
title: About the Searching menu
topic: Settings,Site search and merchandising
uuid: 32932ab0-4abd-449c-aab2-e6fcacfb3b38
index: y
internal: n
snippet: y
---

# About the Searching menu{#about-the-searching-menu}

Use the Searching menu to set excluded words, collections, restrictions, preview, and frames.

## About Searches {#concept_207105CF26B1448F8A3D223787C56AB8}

You can use Searches to define and customize the named searches that your presentation templates can reference.

<!-- 

c_about_searches.xml

 -->

In your presentation template you can reference any named search that is defined within the Searches module. In turn, this lets you easily customize the type of a search that is done for a given set of templates.

To exclude frequently used phrases and common words from your search results, see [Configuring Excluded Words](../c-about-linguistics-menu/c-about-excluded-words.md#task_60BF6BB7A66C48479D2BBB32C0F38CDE).

To define specific, searchable areas of your website, see [Adding collections](../c-about-settings-menu/c-about-searching-menu.md#task_07732D0F00104E59AD421297A704B2F6).

To specify a target frame for search result links, see [Using frames with forms](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

To restrict searches based on HTTP referrer, IP address, or request scheme (HTTP or HTTPS) see [Setting values in Preview](../c-about-settings-menu/c-about-searching-menu.md#task_CE267A0FF621474E80AB43B67B1C28D7).

## Search tips {#section_22F0E2BCF259459FA5F49FBCC0F09A7C}

To get more specific search results, you can use the following search tips.

<table id="table_EA3F89EAFF724552916BFB37C1966417"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Search tip </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Check spelling </p> </td> 
   <td colname="col2"> <p>Make sure that your search terms are spelled correctly. If <span class="uicontrol"> Sound-Alike Matching </span> is enabled in <span class="uicontrol"> Linguistics </span> &gt; <span class="uicontrol"> Words &amp; Languages </span>, the search engine attempts to find words that sound similar to your search terms. However, it is always best to try to spell the search terms correctly. </p> <p>See <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> About Words &amp; Language </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use multiple words </p> </td> 
   <td colname="col2"> <p>Example: 
     <userinput>
       our free product 
     </userinput> </p> <p>Multiple-word queries return more refined results than single-word queries. </p> <p>For example, 
     <userinput>
       our free product 
     </userinput> returns more relevant results than just 
     <userinput>
       product 
     </userinput>. </p> <p>Remember that relevant results are returned even if they do not contain all query terms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use similar words </p> </td> 
   <td colname="col2"> <p>Example: 
     <userinput>
       safe secure privacy security 
     </userinput> </p> <p>The more similar words that you can use in a search query, the more relevant are your search results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use appropriate capitalization </p> </td> 
   <td colname="col2"> <p>Example: 
     <userinput>
       Search Template Reference 
     </userinput> </p> <p>Capitalize proper nouns. If you use a lowercase word, the search engine matches any case of the word. </p> <p>For example, if you type 
     <userinput>
       search 
     </userinput>, the search engine returns all documents that contain the words "search", "Search", and "SEARCH". However, if you type 
     <userinput>
       Search 
     </userinput>, the search engine returns documents that only contain the capitalized word. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use quotation marks </p> </td> 
   <td colname="col2"> <p>Example: 
     <userinput>
       "our pledge to you" 
     </userinput> </p> <p>Use quotation marks to find words that must appear adjacent to each other, such as "our pledge to you". Without the surrounding quotes, the search results include the words "our", "pledge", "to", and "you", but not necessarily in that order. Instead, the words may appear anywhere, and in any order, within the document. </p> <p> if you are using the Advanced Search Form with radio buttons for <span class="uicontrol"> any </span>, <span class="uicontrol"> all </span>, and <span class="uicontrol"> phrase </span>, then you can only use quotes when <span class="uicontrol"> any </span> is selected. Quotes are ignored if <span class="uicontrol"> all </span> or <span class="uicontrol"> phrase </span> is selected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use + (plus) or - (minus) </p> </td> 
   <td colname="col2"> <p>Example: 
     <userinput>
       +"template language" 
     </userinput> </p> <p>Use + to indicate that a search term or phrase must appear in the search results. </p> <p>Use - to indicate that a search term or phrase must be absent from the search results. </p> <p>You must contain a phrase within quotation marks. Leave no spaces between the plus or minus sign and the search term, as in the example above. </p> <p> if you are using the Advanced Search Form with radio buttons for <span class="uicontrol"> any </span>, <span class="uicontrol"> all </span>, and <span class="uicontrol"> phrase </span>, then you can only use quotes when <span class="uicontrol"> any </span> is selected. The plus and minus modifiers are ignored if <span class="uicontrol"> all </span> or <span class="uicontrol"> phrase </span> is selected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use field searches </p> </td> 
   <td colname="col2"> <p>Examples: </p> <p> 
     <ul id="ul_F7CFF7652894402E8D19D6BA49792530"> 
      <li id="li_27492EF933C5437CB2C499746EC8CF39"> 
       <userinput>
         title:about 
       </userinput> </li> 
      <li id="li_BD21505122104FD0B16A4DAD777811DA"> 
       <userinput>
         desc:"Our Team" 
       </userinput> </li> 
      <li id="li_8264630F8B3D46BF872EFEB1D69DB6BE"> 
       <userinput>
         keys:login 
       </userinput> </li> 
      <li id="li_EBB81CBFC6DA45E99A524890DCD56E9F"> 
       <userinput>
         body:security 
       </userinput> </li> 
      <li id="li_6A852E35D6984A2C94144AB6C6D2DFA0"> 
       <userinput>
         alt:"join now" 
       </userinput> </li> 
      <li id="li_F4C5699360484D12ACD62BBFB84A7904"> 
       <userinput>
         url:help 
       </userinput> </li> 
      <li id="li_B2DBBA2239E74D98868D92B3EDEF5B51"> 
       <userinput>
         target:Adobe 
       </userinput> </li> 
     </ul> </p> <p>Field searches let you create specific searches for words that appear in a specific part of a document. </p> <p>You can perform a field search on body text (body:), title text (title:), alt text (alt:), meta description (desc:), meta key words (keys:), URL (url:) or meta target key words (target:). Use lowercase for the field name and immediately followed by a colon. There are no spaces between the colon and the search term. </p> <p>The field searches are only followed by a word or phrase. Phrases must be contained within quotation marks. </p> <p>if you are using the Advanced Search Form with a list box for the field name, then you can only enter field names before a word or phrase when <span class="uicontrol"> any </span> is selected. Specific field names are ignored if any other Advanced Search Form field is selected in the list box. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use wildcards </p> </td> 
   <td colname="col2"> <p>Examples: </p> <p> 
     <ul id="ul_D8E3867EB15641B0A6E55AD546CCB4DD"> 
      <li id="li_CB8B8FC15EB14B13BB33BB69F5206303"> 
       <userinput>
         wh* 
       </userinput> </li> 
      <li id="li_5350A934648C4C81BD6C0875061B426B"> 
       <userinput>
         "wh* are" 
       </userinput> </li> 
      <li id="li_7965A2F7186F40039D2F0736299D11B1"> 
       <userinput>
         415-*-* 
       </userinput> </li> 
     </ul> </p> <p>Wildcard searches expand the number of matches for a particular request. The * character is used as the wildcard character. </p> <p>For example, searching for 
     <userinput>
       wh* 
     </userinput> finds the words "what", "why", "when", "whether", and any other word that starts with "wh". Searching for *her* finds the words "here", "whether", "together", "gathering", and any other word that contains "her" anywhere within the word. </p> <p>You can combine wildcards with + and - modifiers, quotes for phrases, as well as the field search specifiers. </p> <p>The search 
     <userinput>
       +wh* -se*ch 
     </userinput> finds all pages that have a word that starts with "wh" and does not contain a word that starts with "se" and ends with "ch". </p> <p>The search 
     <userinput>
       "wh* are" 
     </userinput> finds the phrases "where are", "what are", "why are", and so forth. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adding a new search definition {#task_98D3A168AB5D4F30A1ADB6E0D48AB648}

You can use the [!UICONTROL GS Add Search] panel to configure and add a new search definition for your Guided Search components such as facets, breadcrumbs, page navigation, menus, and recent searches, in the presentation layer.

<!-- 

t_adding_a_new_definition.xml

 -->

After you add your new search definition, be sure you reference it in your presentation template so that it shows up.

See [About Templates](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**To add a new search definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**.
1. On the [!UICONTROL Searches] page, click **[!UICONTROL Add New Search]**.
1. On the **[!UICONTROL GS Add Search]** page, set the options that you want.

   <!-- 

r_gs_search_options.xml

 -->

   Be aware that the processing rules that select your presentation template can override some of these options.

   See [Adding a new search definition](../c-about-settings-menu/c-about-searching-menu.md#task_98D3A168AB5D4F30A1ADB6E0D48AB648) or [Editing a search definition](../c-about-settings-menu/c-about-searching-menu.md#task_AF1FFB1AEF874C13AB359C28F74BF461).

<table id="table_484773DC6C554354A0ECE5901572EF28"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Search Name </p> </td> 
   <td colname="col2"> <p>Identifies the name of the defined search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Source </p> </td> 
   <td colname="col2"> <p>Lets you select the back-end search that you want to use. You can select from <span class="wintitle"> SiteSearch </span> or <span class="wintitle"> Merchandising </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Account </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source. </p> <p>Lets you select the site search/merchandising account that you want to search. Typically, a search searches in the account that you are currently using. However, your presentation template can use a back-end search for any of your other accounts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Name/IP </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Merchandising </span> as your source. </p> <p>Specifies the full name of the <span class="wintitle"> Merchandising </span> server that the <span class="wintitle"> Merchandising </span> search should access. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Port </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Merchandising </span> as your source. </p> <p>Specifies the <span class="wintitle"> Merchandising </span> server port number. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pyramid </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Merchandising </span> as your source. </p> <p>Specifies the pyramid within the <span class="wintitle"> Merchandising </span> server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Number Of Results </p> </td> 
   <td colname="col2"> <p>Specifies the number of search results that you want returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Number Of First Page Results (if different) </p> </td> 
   <td colname="col2"> <p>Specifies the number of results that are returned at first page. Use this option if you need to have it different from other pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Number Of Columns </p> </td> 
   <td colname="col2"> <p>Specifies the number of columns that the search results are split over. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type Of Searching </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source. </p> <p>Lets you select from the following three types of search. </p> <p> 
     <ul id="ul_2F6FA9EFD8DB49EEAB866C3D070E2644"> 
      <li id="li_ECFEBEDD86FF4DE2BB768423B3B91B5E"> <span class="uicontrol"> all </span> <p>Searches for documents that contain all of the words in the query string. </p> <p>Use of "+" and "-" before search words is disabled and those characters are ignored. </p> </li> 
      <li id="li_62EB215BDDE74DF0BF76B3BD5B96776F"> <span class="uicontrol"> any </span> <p>Use of "+" and "-" word prefixes are allowed. </p> </li> 
      <li id="li_3D71982C0BBA41AFA353069AF3F2F6D8"> <span class="uicontrol"> phrase </span> <p>The query string is treated as if it were a quoted phrase, and all user-typed quotes are ignored. </p> <p>Use of "+" and "-" before search words is disabled and those characters are ignored. </p> </li> 
     </ul> </p> <p> If you want each word in a query to potentially select a facet value, then your primary search should always use <span class="uicontrol"> all </span>. </p> <p>You can review search tips regarding the use of the + and - modifiers in a search query. </p> <p>See <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> About Searches </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Collection </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source. </p> <p>Identifies the collection within your index that you want to search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Promosearch </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source. </p> <p>Lets you use a random selection from the search results, subject to the <span class="uicontrol"> Number Of Results </span> that you specified. </p> <p>Promosearch is a legacy concept. As such, we recommend that you use the new banner management system within site search/merchandising. </p> <p>See <a href="../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA" type="concept" format="dita" scope="local"> About Banners </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apply facet parameters </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source, and you selected <span class="uicontrol"> Promosearch </span>. </p> <p>Specifies that a promotional search use the selected facets to narrow down the promotions. Most promosearch accounts do not use this option. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Provide default promotion if no matching promotion </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source, and you selected <span class="uicontrol"> Promosearch </span>. </p> <p>Specifies that another search for a promotion occur if the initial search for a promotion does not find anything. The second search for a promotion drops the keyword. Instead, it looks for any promotion where an "is_default" metadata field is set to "yes". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Highlight Search </p> </td> 
   <td colname="col2"> <p>Pulls out a select number of results from the main search that you want to highlight in a "hero-zone". </p> <p>Typically, highlight searches have a similar search criteria to the main search but with a different ranking mechanism to highlight certain results. The software removes the duplicates from the main search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Base Search </p> </td> 
   <td colname="col2"> <p>This option is only available is you selected <span class="uicontrol"> Highlight Search </span>. </p> <p>Lets you select the search that has the results that you are highlighting results from. Duplicates are removed from this search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DeDupe Priority </p> </td> 
   <td colname="col2"> <p>This option is only available is you selected <span class="uicontrol"> Highlight Search </span>. </p> <p>Lets you have multiple highlight searches. </p> <p>When you have multiple highlight searches you need to specify the priority of de-duplication, where "1" is the highest priority. </p> <p>For example, suppose you have two highlight searches: bestsellers and new products. Theoretically. it is possible that a best-seller is also a new product. In this case, you want the duplicate removed from the new products and the main search. Therefore, you set the priority of bestsellers to 1 and the priority of new products to 2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parameter </p> </td> 
   <td colname="col2"> <p>Lets you add CGI parameters to the search. </p> <p>See <a scope="local" href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Add]**.
1. (Optional) On the [!UICONTROL Searches] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a search definition {#task_AF1FFB1AEF874C13AB359C28F74BF461}

You can use the [!UICONTROL Staged GS Edit Search] panel to reconfigure an existing search definition for your Guided Search presentation layer.

<!-- 

t_editing_a_search_definition.xml

 -->

After you edit the search definition, be sure that you have referenced it in your presentation template so that it shows up.

See [About Templates](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**To edit a search definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**.
1. On the [!UICONTROL Searches] page, in the table, click **[!UICONTROL Edit]** in the row of the definition that you want to change.
1. On the **[!UICONTROL GS Edit Search]** page, set the options that you want.

   <!-- 

r_gs_search_options.xml

 -->

   Be aware that the processing rules that select your presentation template can override some of these options.

   See [Adding a new search definition](../c-about-settings-menu/c-about-searching-menu.md#task_98D3A168AB5D4F30A1ADB6E0D48AB648) or [Editing a search definition](../c-about-settings-menu/c-about-searching-menu.md#task_AF1FFB1AEF874C13AB359C28F74BF461).

<table id="table_5E02B2D46426467ABAAA55863DAB88D7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Search Name </p> </td> 
   <td colname="col2"> <p>Identifies the name of the defined search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Source </p> </td> 
   <td colname="col2"> <p>Lets you select the back-end search that you want to use. You can select from <span class="wintitle"> SiteSearch </span> or <span class="wintitle"> Merchandising </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Account </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source. </p> <p>Lets you select the site search/merchandising account that you want to search. Typically, a search searches in the account that you are currently using. However, your presentation template can use a back-end search for any of your other accounts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Name/IP </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Merchandising </span> as your source. </p> <p>Specifies the full name of the <span class="wintitle"> Merchandising </span> server that the <span class="wintitle"> Merchandising </span> search should access. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Port </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Merchandising </span> as your source. </p> <p>Specifies the <span class="wintitle"> Merchandising </span> server port number. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pyramid </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Merchandising </span> as your source. </p> <p>Specifies the pyramid within the <span class="wintitle"> Merchandising </span> server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Number Of Results </p> </td> 
   <td colname="col2"> <p>Specifies the number of search results that you want returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Number Of First Page Results (if different) </p> </td> 
   <td colname="col2"> <p>Specifies the number of results that are returned at first page. Use this option if you need to have it different from other pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Number Of Columns </p> </td> 
   <td colname="col2"> <p>Specifies the number of columns that the search results are split over. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type Of Searching </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source. </p> <p>Lets you select from the following three types of search. </p> <p> 
     <ul id="ul_E1D8B3DE9DB24DE4813D53F6298A03A6"> 
      <li id="li_C3DD7AA7699B477A9EE0731CFC012630"> <span class="uicontrol"> all </span> <p>Searches for documents that contain all of the words in the query string. </p> <p>Use of "+" and "-" before search words is disabled and those characters are ignored. </p> </li> 
      <li id="li_4C66B9EFEFA042908A4D3730F9F54EB0"> <span class="uicontrol"> any </span> <p>Use of "+" and "-" word prefixes are allowed. </p> </li> 
      <li id="li_37E9AD42A61C4E31A0816DFB8E71118D"> <span class="uicontrol"> phrase </span> <p>The query string is treated as if it were a quoted phrase, and all user-typed quotes are ignored. </p> <p>Use of "+" and "-" before search words is disabled and those characters are ignored. </p> </li> 
     </ul> </p> <p> If you want each word in a query to potentially select a facet value, then your primary search should always use <span class="uicontrol"> all </span>. </p> <p>You can review search tips regarding the use of the + and - modifiers in a search query. </p> <p>See <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> About Searches </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Collection </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source. </p> <p>Identifies the collection within your index that you want to search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Promosearch </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source. </p> <p>Lets you use a random selection from the search results, subject to the <span class="uicontrol"> Number Of Results </span> that you specified. </p> <p>Promosearch is a legacy concept. As such, we recommend that you use the new banner management system within site search/merchandising. </p> <p>See <a href="../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA" type="concept" format="dita" scope="local"> About Banners </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apply facet parameters </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source, and you selected <span class="uicontrol"> Promosearch </span>. </p> <p>Specifies that a promotional search use the selected facets to narrow down the promotions. Most promosearch accounts do not use this option. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Provide default promotion if no matching promotion </p> </td> 
   <td colname="col2"> <p>This option is only available if you chose <span class="uicontrol"> Search&amp;Promote </span> as your source, and you selected <span class="uicontrol"> Promosearch </span>. </p> <p>Specifies that another search for a promotion occur if the initial search for a promotion does not find anything. The second search for a promotion drops the keyword. Instead, it looks for any promotion where an "is_default" metadata field is set to "yes". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Highlight Search </p> </td> 
   <td colname="col2"> <p>Pulls out a select number of results from the main search that you want to highlight in a "hero-zone". </p> <p>Typically, highlight searches have a similar search criteria to the main search but with a different ranking mechanism to highlight certain results. The software removes the duplicates from the main search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Base Search </p> </td> 
   <td colname="col2"> <p>This option is only available is you selected <span class="uicontrol"> Highlight Search </span>. </p> <p>Lets you select the search that has the results that you are highlighting results from. Duplicates are removed from this search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DeDupe Priority </p> </td> 
   <td colname="col2"> <p>This option is only available is you selected <span class="uicontrol"> Highlight Search </span>. </p> <p>Lets you have multiple highlight searches. </p> <p>When you have multiple highlight searches you need to specify the priority of de-duplication, where "1" is the highest priority. </p> <p>For example, suppose you have two highlight searches: bestsellers and new products. Theoretically. it is possible that a best-seller is also a new product. In this case, you want the duplicate removed from the new products and the main search. Therefore, you set the priority of bestsellers to 1 and the priority of new products to 2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parameter </p> </td> 
   <td colname="col2"> <p>Lets you add CGI parameters to the search. </p> <p>See <a scope="local" href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) On the [!UICONTROL Searches] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a search definition {#task_1D8E991E4C4146B7A7311FAE5DAA3742}

You can delete a guide search definition that you no longer need or use.

<!-- 

t_deleting_a_search_definition.xml

 -->

See [About Templates](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**To delete a search definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**.
1. On the [!UICONTROL Searches] page, in the table, click **[!UICONTROL Delete]** in the row of the definition that you want to remove.
1. In the [!UICONTROL Confirmation] dialog box, click **[!UICONTROL OK]**.
1. (Optional) On the [!UICONTROL Searches] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Pinned Results Keyword Manager {#concept_0C5F152C029C485D8872C6795CBCD7C7}

You can manually pin search results to a specific location. These pinned results are associated with a specific search query or keywords. You can use [!UICONTROL Pinned Result Keyword Manager] to manage all of the keywords with pinned results.

<!-- 

c_about_pinned_results_keyword_manager.xml

 -->

## Keyword search rules to follow {#section_ED67A24BE884468286F34FA5DFF826D7}

The search query that you enter in panel has the following rules:

* Leading and trailing spaces are deleted from the query. 
* No special search characters are allowed such as the following:

    * Wildcard matching with asterisks (&#42;). 
    * No must-have's or must-not-have's using plus or minus (+ or -). 
    * No field specifier with the colon character (:). 
    * No commas or double quotes (, or ").

* Multiple terms or words separated by spaces in the query are allowed. 
* Uppercase letters are converted into lowercase letters.

The search terms are remembered exactly as is; you must use the exact same search terms again to get the exact same results.

Pinned results do not support case sensitivity. All keywords have their uppercase letters converted to lowercase letters.

## Reordering the search results {#section_46FBE5279C7740A09D6DC9F54FE104AA}

When you search on a keyword in the [!UICONTROL Stage Add New Keyword] panel or the [!UICONTROL Staged Edit Keyword] panel, the search results reflect what could happen after the next index operation. You can reorder the search results in the table using one of three different methods.

The first method is by using the **[!UICONTROL Pinned]** checkbox. The checkbox is used to pin a result to a specific position. When you select the checkbox, all search results above the checkbox are also pinned. This functionality ensures that all results above that checkbox appear in that specific order. Unpinning a search result causes it to drop below all currently pinned results.

The second method is by using drag-and-drop in the table. You can move a result to a new position with drag-and-drop. After dragging a result to a new location, all results above the new location are pinned. This automatic pinning ensures that the rest of the results will appear above the recently dragged result.

The third method is to set the order of pinned results by entering a specific position in the "#" column. Unlike with drag-and-drop, the order of the simulated search results are only obvious the next time you open the [!UICONTROL Staged Edit Keyword] panel. Setting the order number for a currently unpinned row ensures that at least that many items get pinned. Setting the order number for a currently pinned row sets the order of that item within the items that are currently pinned. However, it does not increase the number of pinned items.

When you save the search results, you can view the results again by entering the exact same query into the Keyword field.

## About the pinned search results {#section_46780B7812F249F3B45503161C4FBDEE}

Search results are often ordered by the relevancy score. However, a pinned search result ignores the relevancy score and attempts to override the natural order with its predetermined position. By ensuring that the result stays relatively where it is, other known search results above it have to be pinned.

The search results that are displayed on the panel simulate what appears after the next index. However, changes from the original document or certain configuration changes in the Member Center can produce results with discrepancies. For example, changing the content of a document are not known until after the index.

Pinned results appear in a similar or same order after the index because they ignore relevancy. Unpinned results fall back to their natural position after an index; the order of unpinned results is not guaranteed. 

## Adding a new keyword {#task_8CED128DADD34D0DAD2C64B64D0D6B06}

You can add new keywords and their pinned results.

<!-- 

t_adding_a_new_keyword.xml

 -->

At the time you add a new keyword, you can reorder the search results and pin them to a specific position.

**To add a new keyword** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]**.
1. On the [!UICONTROL Pinned Keyword Results Manager] page, click **[!UICONTROL Add New Keyword]**.
1. On the [!UICONTROL Add New Keyword] page, in the **[!UICONTROL Keyword]** field, enter a search query, and then click **[!UICONTROL Search Keyword]**.

   <!-- 

r_keyword_options.xml

 -->

   You can use the Edit Table button to adjust how you view the table of search results. For example, you can use the list of columns to reveal or hide specific columns. You can also rearrange the order of the columns using drag-and-drop.

   The following table describes the column properties that are in the table editor.

<table id="table_C7E5CAE8BD9240B1836BAFFDB13BFCB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Column </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Order </p> </td> 
   <td colname="col2"> <p>Specifies the numerical order of the appearance of the columns. You can drag-and-drop the columns to automatically update the order. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Field Name </p> </td> 
   <td colname="col2"> <p>Identifies the name of the column header that appears in the <span class="wintitle"> Simulated Search Results </span> table of the <span class="wintitle"> Staged Add New Keyword </span> panel and the <span class="wintitle"> Staged Edit Keyword </span> panel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Include </p> </td> 
   <td colname="col2"> <p>The column appears in the Pinned Results Table if the box is checked. If the box is empty or deselected, the column disappears from the table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Display URL as Image </p> </td> 
   <td colname="col2"> <p>If the meta field that is assigned to this column has URLs to graphics or pictures, checking this box places HTML image tags around it and the picture appears. Missing pictures or bad links are empty. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Field Length </p> </td> 
   <td colname="col2"> <p>Lets you enter the maximum length of text for display before it is truncated with ellipses (...). If the column is set to display URLs as images, this field has no effect. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Optional) Do any of the following:

    * Reorder the search results. 
    * Click **[!UICONTROL Edit Table]** to adjust the view of the [!UICONTROL Simulated Search Results] table. When you have finished, click **[!UICONTROL Save Changes]** to return to the [!UICONTROL Add New Keyword] panel.

1. Click **[!UICONTROL Save Search Results]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!UICONTROL Pinned Results Keyword Manager] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a keyword {#task_30C550A7350B4394B5B43536368A84B1}

You can edit existing keywords and their pinned results.

<!-- 

t_editing_a_keyword.xml

 -->

At the time you edit a keyword, you can reorder the search results and pin them to a specific position.

**To edit a keyword** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]**.
1. On the [!UICONTROL Pinned Keyword Results Manager] page, in the table, click **[!UICONTROL Edit]** in the row of the keyword that you want to change.
1. On the [!UICONTROL Edit Keyword] page, in the **[!UICONTROL Keyword]** field, enter a search query, and then click **[!UICONTROL Search Keyword]**.

   Be sure that you follow the rules for the keyword search.

   <!-- 

r_keyword_options.xml

 -->

   You can use the Edit Table button to adjust how you view the table of search results. For example, you can use the list of columns to reveal or hide specific columns. You can also rearrange the order of the columns using drag-and-drop.

   The following table describes the column properties that are in the table editor.

<table id="table_77D6160C21AA4173B676B31F4A47C228"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Column </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Order </p> </td> 
   <td colname="col2"> <p>Specifies the numerical order of the appearance of the columns. You can drag-and-drop the columns to automatically update the order. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Field Name </p> </td> 
   <td colname="col2"> <p>Identifies the name of the column header that appears in the <span class="wintitle"> Simulated Search Results </span> table of the <span class="wintitle"> Staged Add New Keyword </span> panel and the <span class="wintitle"> Staged Edit Keyword </span> panel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Include </p> </td> 
   <td colname="col2"> <p>The column appears in the Pinned Results Table if the box is checked. If the box is empty or deselected, the column disappears from the table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Display URL as Image </p> </td> 
   <td colname="col2"> <p>If the meta field that is assigned to this column has URLs to graphics or pictures, checking this box places HTML image tags around it and the picture appears. Missing pictures or bad links are empty. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Field Length </p> </td> 
   <td colname="col2"> <p>Lets you enter the maximum length of text for display before it is truncated with ellipses (...). If the column is set to display URLs as images, this field has no effect. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Optional) Do any of the following:

    * Reorder the search results. 
    * Click **[!UICONTROL Edit Table]** to adjust the view of the [!UICONTROL Simulated Search Results] table.

      See [Adding a new keyword](../c-about-settings-menu/c-about-searching-menu.md#task_8CED128DADD34D0DAD2C64B64D0D6B06).

      When you have finished, click **[!UICONTROL Save Changes]** to return to the [!UICONTROL Add New Keyword] panel.

1. Click **[!UICONTROL Save Search Results]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!UICONTROL Pinned Results Keyword Manager] page, Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a keyword {#task_F17D6357D6DD416495E6D4117899D81D}

You can delete keywords that you no longer need or use.

<!-- 

t_deleting_a_keyword.xml

 -->

At the time you add a new keyword, you can reorder the search results and pin them to a specific position.

**To delete a keyword** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]**.
1. On the [!UICONTROL Pinned Keyword Results Manager] page, in the table, click **[!UICONTROL Delete]** in the row of the keyword that you want to remove.
1. On the [!UICONTROL Delete Keyword] page, click **[!UICONTROL Delete]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!UICONTROL Pinned Results Keyword Manager] page, Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Collections {#concept_62E42ACE53D54EEE9273433B86259127}

You can use Collections to allow customers to search specific areas of a website so that they can quickly find what they are looking for.

<!-- 

c_about_collections.xml

 -->

See [About Searches](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

See [Using collections in search forms](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

For example, customers can search a collection of URLs that are related to product sales or to support services. Before customers can use the collections that you specify, be sure that you update your search form under the Search Form menu.

Before the effects of the Collections settings are visible to customers, rebuild your site index.

You can test your collections by entering one of your website URLs in the optional **[!UICONTROL Test Collections]** field, and then clicking **[!UICONTROL Test]**. The collection to which the specified page belongs is returned.

Each collection is specified on a single line with a name and a URL mask. A URL mask can consist of the following:

* a full path such as `http://www.mydomain.com/products.html` 
* a partial path such as `http://www.mydomain.com/products` 
* a regular expression

  To make a mask a regular expression, you insert the keyword `regexp` between the collection name and the URL mask.

  See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Each line in the Collections field can contain only one URL mask. However, you can specify multiple URL masks for the same collection name on different lines. The following example contains four different collection names and five URL masks:

```
Company Info http://www.yoursite.com/company 
Products http://www.yoursite.com/products 
FAQs regexp ^.*/faqs 
Support http://www.yoursite.com/email_support/ 
Support http://www.yoursite.com/phone_support/
```

In this example, after you have updated the search form to include these collections, customers can select and search each defined collection individually. The `Support` collection includes files that match both the URL masks, so that files in both `www.yoursite.com/email_support/` and `www.yoursite.com/phone_support` are searched when this collection is selected. 

## Adding collections {#task_07732D0F00104E59AD421297A704B2F6}

You can add collections to allow customers to search specific areas of your web site so that they can quickly find what they are looking for.

<!-- 

t_adding_collections.xml

 -->

Be sure that you rebuild your site index so that the results of your URL masks are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To add collections** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Collections]**.
1. In the [!UICONTROL Collections] field, enter a collection name and URL mask address, one per line.
1. (Optional) On the [!UICONTROL Collections] page, in the **[!UICONTROL Test Collections]** field, enter a test URL mask from your website, and then click **[!UICONTROL Test]**.

   A test collection output window is displayed showing you the URL and the name of the collection. 
1. When you are finished adding collections, click **[!UICONTROL Save Changes]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!UICONTROL Collections] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Restrictions {#concept_B5B527E04EBF4E9AB5956EEF881DDBF1}

Before a search is performed, the referring URL and IP address are examined to determine if a search is possible from that location. What you have specified in [!UICONTROL Restrictions] determines whether the search is permitted. If a search is not permitted, a generic error page is returned to the requestor.

<!-- 

c_about_restrictions.xml

 -->

You can specify restriction settings as either referrer URL Masks or IP address masks. Both types of restrictions use include masks to permit searches and exclude masks to deny them.

A search is permitted if it passes both the referrer URL and the IP address restriction criteria. If either setting does not permit the search, the search fails, regardless of other restrictions that allow it.

For example, if the "HTTP referrer" field of a search request matches an "exclude" referrer URL mask, the search fails, even if the requesting IP address matches an "include" IP address mask. If no mask matches the referrer URL or IP address, the location is included by default.

Enter each include mask or exclude mask on a single line. 

## Adding referrer URL mask or IP address mask restrictions {#task_E6FF2DD83E8D4B00A0E2809DC13A56C9}

You can specify restriction settings as either "Referrer URL Masks" or "IP Address Masks." Both types of restrictions use include masks to permit searches and exclude masks to deny them. A search is permitted if it passes both the referrer URL and IP address restriction criteria.

<!-- 

t_adding_url_mask_or_jp_address_restrictions.xml

 -->

**To add referrer URL mask or IP address mask restrictions** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]**.
1. On the [!UICONTROL Restrictions] page, set the restriction options that you want. Enter referrer URL mask addresses, IP address mask addresses or, optionally, a URL address of a customized web page that is displayed to customers who are not permitted to search your site.

   <!-- 

r_restriction_options.xml

 -->

<table id="table_AD2496469F3142DA9A11DF9D6131F535"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Referrer URL Masks </p> </td> 
   <td colname="col2"> <p>The referrer URL from the HTTP referrer header is read. The first mask that matches the referrer URL determines whether to allow the search, if the mask is an include mask. Or, it determines whether to disallow the search, if the mask is an exclude mask. If no mask matches the referrer URL, that URL is included and the search is allowed. </p> <p> If your search template contains a new search form or if your search template can contain links like "Next 10", "Previous 10", or "Hide Summaries", then you list your search results template as an "include" mask. The easiest way to do that is with the regular expression as in the following example: </p> <p> <span class="codeph"> include regexp ^https?://[^/]*\.atomz\.com/.*[?&amp;]sp_a=sp1000130e.*$ </span> </p> <p>The following example contains five different referrer URL masks: </p> <p> 
     <codeblock>
       include&nbsp;http://www.mydomain.com/search/ 
      
include&nbsp;http://search.mydomain.com/ 
      
include&nbsp;regexp&nbsp;^http://www.mydomain.com/help/.*/search/ 
      
include&nbsp;regexp&nbsp;^https?://[^/]*\.atomz\.com/.*[?&amp;]sp_a=sp1000130e.*$ 
      
exclude&nbsp;* 
     </codeblock> </p> <p>If the referrer URL masks are the following: </p> <p> 
     <codeblock>
       http://www.mydomain.com/search/searchpage.html&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
      
http://search.mydomain.com/advanced/&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
      
http://www.mydomain.com/help/products/search/advanced/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
      
http://www.mydomain.com/help/products/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
      
http://www.anotherdomain.com/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
      
blank&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP Address Masks </p> </td> 
   <td colname="col2"> <p>The first mask that matches the IP address determines whether to allow the search, if the mask is an include mask. Or, it determines whether to allow or disallow the search if the mask is an exclude mask. If no mask matches the requesting IP address, that IP address is included and the search is allowed. </p> <p>The following example below shows four different IP address masks. </p> <p> 
     <codeblock>
       include&nbsp;64.128.192.* 
      
include&nbsp;192.168. 
      
include&nbsp;regexp&nbsp;^209\.42\.97\.[1-5]+ 
      
exclude&nbsp;* 
     </codeblock> </p> <p>If the referring IP address masks are the following: </p> <p> 
     <codeblock>
       64.128.192.10&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
      
192.168.10.127&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
      
209.42.97.14&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
      
64.128.193.10&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
      
192.169.10.14&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
      
209.42.97.68&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Only allow searches that use HTTPS </p> </td> 
   <td colname="col2"> <p>Restrict searches to HTTPS. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL to Which Disallowed Requests Should Be Sent </p> </td> 
   <td colname="col2"> <p> Restricted users are redirected to the URL that you enter here. This option provides a means for you to craft your own custom error page to display to customers who are not permitted to search your site. </p> <p>If you do not specify a URL, a generic error page is returned when a restricted user attempts to search your site. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Preview {#concept_DF293FD3B02C467F8842C8C21D62F294}

The query string and parameters that you set in [!UICONTROL Preview] are used any time a search form is tested or previewed in the software.

<!-- 

c_about_preview.xml

 -->

See also [About Searches](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8). 

## Setting values in Preview {#task_CE267A0FF621474E80AB43B67B1C28D7}

The preview values that you set are used any time a search form is tested or previewed in the software.

<!-- 

t_setting_values_in_preview.xml

 -->

**To set values in Preview** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Preview]**.
1. On the [!UICONTROL Preview] page, set the options that you want.

   <!-- 

r_preview_options.xml

 -->

<table id="table_37EC914E7ADA42B69011B5A78CDBD8A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Query </p> </td> 
   <td colname="col2"> <p>By default, the query string is set to <span class="codeph"> * </span>, which usually returns results. However, you can specify a query that is more specific to your website's content. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parameters </p> </td> 
   <td colname="col2"> <p>Parameters are set with a name and value. You can specify as many additional parameters as you need. For example, you can specify additional search criteria with <span class="codeph"> sp_q_1 </span> and <span class="codeph"> sp_x_1 </span> parameters. The parameter value <span class="codeph"> sp_q_1=windows&amp;sp_x_1=platform </span> creates a preview search that looks for the value "windows" in the "platform" meta tag of searched pages, in addition to the main query. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Host </p> </td> 
   <td colname="col2"> <p>If your website uses private domain labeling, set the proper host name to accurately preview your search results. </p> <p>For information about private domain labeling, contact Customer Support. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Feeds {#concept_FEBFEE51A3AB49F88CBA0D16E2AD6916}

The search index is viewed as a large database of your website. With enough information from the correct meta tags, information is collected and organized, or syndicated, into data feeds. You can submit these data feeds to another service, such as a third-party recipient.

<!-- 

c_about_feeds.xml

 -->

After your website is crawled and indexed, you can generate automatic feeds and submit them to third-party organic search engines and shopping engines. You can create the following stream feeds: 

<table id="table_92C18C603E5C40BB84CB790502E00F76"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Feed type </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Recommendations </p> </td> 
   <td colname="col2"> <p>Recommendations feeds provide data syndication capabilities with Adobe Recommendations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generic Feed </p> </td> 
   <td colname="col2"> <p>You can implement many feeds with the Generic Feed type. A custom search query is made against your website's index. The data is returned through customized search templates using the same template language for displaying search results. This kind of flexibility means that you can submit feeds to many more vendors, not just to specific feed types. </p> <p>You can add the transport (search) template by using the instructions in the following Help topic: </p> <p>See <a href="../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012" type="task" format="dita" scope="local"> Adding a new presentation or transport template file </a>. </p> <p> After you add the template, edit it using search template tags to define which search metadata fields that you want to include, along with their format. </p> <p>See <a href="../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3" type="task" format="dita" scope="local"> Editing a presentation or a transport template </a>. </p> <p>See <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Search template tags </a>. </p> <p>Be sure you remember the name of the transport template file. You use the name to bind the generic feed to the template when you specify the feed's criteria. </p> <p>If you have worked previously with other feeds, you remember that you map the feed fields to the search metadata fields. Generic Feeds does not have this specific step in the <span class="uicontrol"> Create Feed </span> wizard. Instead, the template specifies the metadata and the formatting of the metadata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Merchant </p> </td> 
   <td colname="col2"> <p>Google Merchant Center lets people sell products through several Google services. It has a data syndication component where you can submit a list of available products for sale on a periodical basis. </p> <p>As with any third-party feed vendor, Google Merchant Center has specific standards that you meet before they deem the feed legitimate. For more information, please contact your customer representative and visit Google Merchant documentation. Here is a quick summary what Google Merchant Center considers while validating a feed: </p> 
    <ul id="ul_3D84D4A6A4BF4C08860F86403F8F9CD6"> 
     <li id="li_5B6516CC7BC7493B8B8E8AFB454E573F">Each product has a product page; a dedicated URL. </li> 
     <li id="li_5A6D5AD5E1B54A94B224D19E888B5443"> Each product variant has a separate entry in the feed. </li> 
     <li id="li_89748D3241B34A4493576DAC38681988"> Each product has an image URL, preferably originating from your server. Product variants have specific images showing its actual variations. In other words, different shoe colors should not share the same image. </li> 
     <li id="li_A594AD19480F41EAA72181355F28447B"> Each product has specific information such as availability, condition, description, category, and price. </li> 
     <li id="li_0955B3A6ED2746D2B7CB42DC8AB27D3A">In general, each product has a unique identifier such as ISBN, UPC, JAN, or EAN, and so on. </li> 
     <li id="li_2C371653F1C5471FA638F3A3818ABC17">In general, each product is classified with Google's product taxonomy. </li> 
     <li id="li_6EB392A5A0BE490FAED5BC5E83228E32"> Apparel products have extra required fields such as gender, age group, color, and size. </li> 
     <li id="li_44B91FA9A95F4172A2F03F8206E9081E"> Tax and shipping are specified as an account setting within Google Merchant Center or on the product-by-product basis, within this feed. </li> 
     <li id="li_71A63E9905B840C0A04F6CDAA23C9AB0"> Custom-made products and certain apparel products can be exempted from some of the rules, but you must contact Google for permission and details about such exemptions. </li> 
    </ul> <p>There are many details that govern feed validation. See the Google Merchant documentation for information about feed management. Google frequently makes changes to the specifications, so check the documentation often. </p> <p>The feed that is associated with Google Merchant Center is often referred to as the Google Product Search feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Sitemaps </p> </td> 
   <td colname="col2"> <p>Google Sitemaps provides a way for you to influence how Google crawls your website. A syndicated data feed, a sitemap in this case, is periodically submitted to Google Sitemaps. The sitemap contains Internet-reachable URLs and specific information, such as last modification date or page priority, can be associated with each URL. Providing Google with such information can increase the frequency and chance a specific page would be crawled and indexed. In some cases, a sitemap is used to advertise a list of links which cannot be accessed by their crawler under normal circumstances. </p> <p>If you are interested creating a Google Sitemap with our feed feature, please contact your customer representative. Google has made their Google Sitemap service available to the general public and they provide documentation at their Google Webmaster Tools page. </p> <p> <b>Requirements for creating a Google Sitemap feed</b> </p> <p>To create a Google Sitemap feed, be sure you have a Google Webmaster Tools account with Google Sitemap already set up. See the Google Webmaster Tools documentation for setting up Google Sitemap. </p> <p>You also need to determine how the sitemap files are delivered. In general, the sitemap files come from your domain and, specifically, the root of your web site. The simple model is to have the files delivered by way of FTP to your servers. The other solution is to redirect the request of the sitemap files to the site search/merchandising Content Network. Contact your consulting representative about coordinating and setting up the delivery of sitemap feeds. </p> </td> 
  </tr> 
 </tbody> 
</table>

If you are interested in automatic feeds, please contact professional services for assistance. Each feed has stringent requirements when it comes to the quality of data and transmission of the files.

The feed type that you select affects which options appear when you construct a field using the **[!UICONTROL Create Feed]** wizard. Each type of feed has different data formats. Be sure that you follow the proper data format to avoid the rejection of a feed by a feed recipient or posting improper data to your customers. Besides the data format, vendors usually have one or more preferred ways of receiving the data. Consult the vendor's documentation about their feeds.

A challenge with creating a feed is matching the data between site search/merchandising and the feed. Usually the data that is retrieved from index crawling is in the wrong format or it is missing. The following is a list of questions that can help you focus on what to look for when you create a feed.

* What type of business relationship do you have with the feed recipient? 
* Do you have to register and create an account with the feed recipient? 
* Who is going to monitor and take care of issues that come up with the feed in respect to the vendor? In general, it is your responsibility to manage the vendor's account. For example, Google Sitemap requires a WebMaster account and someone to monitor the health of the sitemap. 
* What is the data format of the feed? 
* Does your index match the character encoding of the feed? Tab-delimited and comma-delimited data formats become a problem when your data has tabs or commas. 
* What do you when you have tabs or commas in your data? 
* Are there any pages in your index with empty data? 
* Can the feed recipient accept empty data? You may be able to resolve empty data by editing the criteria how data is retrieved by the software. 
* Does the data format lineup with what the feed recipient wants? For example, some feed recipients are specific about how prices and currency are displayed. 
* Does the vendor have a maximum number of items that they can accept? You can resolve this potential issue by limiting the results with the search criteria. 
* How does the vendor want to receive the feed? FTP submissions and HTTP hosting are supported.

## Creating a feed {#task_63179C1FC359497483CD6CE13FD1C250}

You can create one or more data feeds.

<!-- 

t_creating_a_feed.xml

 -->

**To create a feed** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. On the [!UICONTROL Feeds] page, select a feed type from the **[!UICONTROL Create Feed]** drop-down list.
1. Depending on the feed type you selected, in the [!UICONTROL Create Feed] dialog box, set the options as identified in each panel of the wizard.

   <!-- 

r_feed_options.xml

 -->

   Depending on the feed type that you are creating or editing, the available options differ slightly.

   **Adobe Recommendations**

<table id="table_4BDDAF32704F401899B0A539737807B9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Panel </p> </th> 
   <th colname="col2" class="entry"> <p>Wizard Panel Name </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Feed Name </p> </td> 
   <td colname="col3"> <p>Specifies the name of the feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Field Maps </p> </td> 
   <td colname="col3"> <p>Lets you map vendor-specific feed fields to site search/merchandising metadata fields. This mapping step in the wizard is important because it allows Feeds to correlate the information between the fields in the index and the fields in the feed data. In most cases, except for <span class="wintitle"> Generic Feeds </span>, the correlations are saved in a dynamically generated search template. </p> <p>Each row in the <span class="wintitle"> Field Maps </span> table represents a field mapping. In the Add/Remove column of the table, click <span class="uicontrol"> + </span> to add a new field mapping row; click <span class="uicontrol"> - </span> to delete the currently selected field mapping row from the table. To associate a feed field with a site search/merchandising metadata fields, use the respective drop-down lists to choose the desired fields. </p> <p> <b>Field mappings for Adobe Recommendations</b> </p> <p>The Recommendation data feed is a CSV file, columns of data separated by commas. The order of appearance of each mapping on the Field Maps table is important as they determine the order of the columns in the CSV feed file. Create the rows of mappings in the following order—each row is mandatory: </p> <p> 
     <ol id="ol_49C739D04DD340168DC6C1F794544C35"> 
      <li id="li_A95D9C5A353746A3A0D38F200AC2EEA2"> id </li> 
      <li id="li_044763D4C7054CEB948C94590735D74F"> name </li> 
      <li id="li_832F07CA0E3F4E10A4AE30171F3E8541"> categoryId </li> 
      <li id="li_2A33FB42F7E942ED881BA1F478542C4D"> message </li> 
      <li id="li_A76E66B2366845B0B63ED5C200531ADD"> thumbnailURL </li> 
      <li id="li_518CCD5E7E404521AB8199981BA86F76"> value </li> 
      <li id="li_14A0A8FCC2B34B758E1FBB98E3F2DFB2"> pageURL </li> 
      <li id="li_36D22F1603394AF89E0C7ADB18AAAAB7"> inventory </li> 
      <li id="li_ABDB9C762BBC4F27B82FEA4425A8DDC4"> margin </li> 
     </ol> </p> <p> <b>Advanced usage</b> </p> <p>After you have mapped the first nine required Feed Fields as outlined above, you can create your own custom fields. In the <span class="wintitle"> Feed Fields </span> drop-down list, click <span class="uicontrol"> Custom </span>. In the associated text field, enter a custom tag name for that field. This custom option is useful if a feed needs special vendor-specific fields. </p> <p> <p>Note:  Although the Recommendation Feed specifications states that each field name must be prefixed with "entity", it is not necessary in this case. </p> </p> <p>You can also create a custom metadata field. In the <span class="wintitle"> Metadata Fields </span> drop-down list, click <span class="uicontrol"> Custom </span>. In the associated text field, enter a custom metadata field value. The value is inserted into the pre-generated template and it can also be used to inject custom search template tags. </p> <p>See <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Search template tags </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Search Criteria </p> </td> 
   <td colname="col3"> <p>When the feed files are generated, a search query is used to filter the data. You define the filters that are used for the search query in this panel. </p> 
    <ul id="ul_799ECF61C03A44878C7182F8B88CC3AD"> 
     <li id="li_0763F600A4FB4650ACC28BF337EB50AF"> <span class="uicontrol"> Meta Field </span> <p>Defines which metadata field that you want to filter on. </p> <p> <b>Advanced usage</b> </p> <p>Because the filtering system is a standard search query, you can select <span class="uicontrol"> Free Form </span> from the drop-down list to enter CGI search parameters and their values. URL escaping is required. The search argument <span class="codeph"> sp_q </span> is ignored. You can create multiple rows of Free Form text boxes. Between each row, the arguments are delimited with &amp;'s automatically. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Search CGI parameters </a>. </p> </li> 
     <li id="li_756B776902AE4A0E95524442D663343E"> <span class="uicontrol"> Criteria </span> <p>Defines the filter operation. The filter operation that you select from the drop-down list applies the constant value that is entered in the third column. </p> </li> 
     <li id="li_7ADEDB8747B241D78AC50F1AC75AE695"> <span class="uicontrol"> Value </span> <p>The constant value. </p> </li> 
     <li id="li_4039A9BC2F74460B83BFF662B58DAA1B"> <span class="uicontrol"> Action </span> <p>Adds a new field mapping row, or deletes the currently highlighted row. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>File Submission </p> </td> 
   <td colname="col3"> <p>Lets you configure the schedule for submitting the feed files and set the method that you want to use to upload the files. </p> 
    <ul id="ul_55E253F83BDA46BAABF2BE38F0918E80"> 
     <li id="li_877A376B5B30422FAC816E31D50EA508"> <span class="uicontrol"> Schedule </span> <p>Sets the maximum frequency that a feed is submitted. Selecting <span class="uicontrol"> Never </span> turns off the feed. Other values define the period that the feed waits before submitting again. The decision when to submit the feed is done at each index. In other words, at the end of the index, a feed is checked to see if it has expired and needs to be updated and submitted by the vendor. Also, it is used as a method of preventing an account from over-submitting to a vendor. Some vendors have policies against data feed sources that upload too frequently. Be sure that you check the data feed vendor's policy about the frequency of submissions. 
       <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> 
       <!--ick <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
       <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
     <li id="li_760F5068D3ED46C582AE41392A2CA342"> <span class="uicontrol"> Upload Method </span> <p>Most feeds have two ways of distributing the files: FTP and Hosted Content Network. </p> 
      <ul id="ul_666759EDDD034537AA7C0ED936A2F315"> 
       <li id="li_B4AD5CEEBB7B41C0B8DC291B95DC5F83"> <span class="uicontrol"> FTP </span> <p>Site search/merchandising servers use passive FTP. </p> <p>FTP is the only way to push a file to another server. </p> <p> <span class="uicontrol"> FTP Server </span> - Specifies the name of the FTP server. Do not include the protocol or preceding "ftp://". </p> <p> <span class="uicontrol"> FTP User Name </span> - Specifies the name of the FTP account. </p> <p> <span class="uicontrol"> FTP Password </span> - Specifies the password of the FTP account. </p> <p> <span class="uicontrol"> FTP File Name </span> - Specifies the name of the file to transmit. This name is a template if the feed generates multiple files, usually incrementing a number at the end of the name but before the extension. For example: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> FTP Directory </span> - If a specific directory path is required, you enter it here. Do not include the filename in the path. </p> </li> 
       <li id="li_C082D3993C6C469B9067F207703BE619"> <span class="uicontrol"> Hosted Content Network </span> <p>The Content Network is the means of serving files from the web servers of site search/merchandising. The recipient of the feed pulls it from the web servers using an HTTP request. The only piece of information to set this up is <span class="uicontrol"> Content Network Filename </span>. The filename is the base name of the file that is served. Use only filenames with a filename extension. Depending on the feed, the filename is a template for multiple files where the feed might generate multiple files in the following format: basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml. </p> <p>After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. Multiple files use the same URL path. However, be sure that you replace or change the filename according to the enumeration scheme. </p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Verification </p> </td> 
   <td colname="col3"> <p>When you get to the <span class="wintitle"> Verification </span> panel, your feed is saved at that point. However, the actual feed files are not saved until later. </p> <p>The <span class="wintitle"> Verification </span> panel lets you do the following: </p> 
    <ul id="ul_0C6EFB38E06F401696084863D85CBD0D"> 
     <li id="li_07FC9F04C7F640048546F9DC5D91DA1D"> <span class="uicontrol"> Data View </span> <p>Lets you click the link to check the feed output through a data view that is displayed in table form. The data view can also help you troubleshoot by showing you which meta fields are chosen and how any specified search criteria from the <span class="wintitle"> Search Criteria </span> panel in the wizard, affects the feed output. The data view is generated dynamically, so it is available at all times. </p> </li> 
     <li id="li_67046A56D08C48298E5A3E1F9C4A8AF3"> <span class="uicontrol"> Feed Files </span> <p>After site search/merchandising servers generate the feed files, you can use the <span class="uicontrol"> Feed Files </span> drop-down list to view the files from the servers. A new browser tab or new browser window appears with the content of the feed. This method is useful for helping you troubleshoot feeds that have formatting issues. Note that you do not view the files from the final destination or from the vendors themselves. </p> <p> If the feed is new, then the drop-down list is empty until you generate feed files. </p> </li> 
     <li id="li_99D66C7AD87A475CB3D831D514DB78A0"> <span class="uicontrol"> Content Network Link </span> <p>If you chose <span class="uicontrol"> Hosted Content Network </span> as your upload method in the <span class="wintitle"> File Submission </span> panel of the wizard, the URL is displayed here. If you have not yet generated any feed files, the URL is not valid until the feed is successfully generated. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

   **Generic Feed**

<table id="table_BBD93B631668406895B04E12D8B61D2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Panel </p> </th> 
   <th colname="col2" class="entry"> <p>Wizard Panel Name </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Feed Name </p> </td> 
   <td colname="col3"> <p>Specifies the name of the feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Search Criteria </p> </td> 
   <td colname="col3"> <p>When the feed files are generated, a search query is used to filter the data. You define the filters that are used for the search query in this panel. </p> 
    <ul id="ul_C750687E69A647D0A4440FF1B6CC7E05"> 
     <li id="li_B5C3B8523D71472E9508A04E23AC0211"> <span class="uicontrol"> Meta Field </span> <p>Defines which metadata field that you want to filter on. </p> <p> <b>Advanced usage</b> </p> <p>Because the filtering system is a standard search query, you can select <span class="uicontrol"> Free Form </span> from the drop-down list to enter CGI search parameters and their values. URL escaping is required. The search argument <span class="codeph"> sp_q </span> is ignored. You can create multiple rows of Free Form text boxes. Between each row, the arguments are delimited with &amp;'s automatically. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Search CGI parameters </a>. </p> </li> 
     <li id="li_D1E49834BBEA42CC8C49AE7D72037C53"> <span class="uicontrol"> Criteria </span> <p>Defines the filter operation. The filter operation that you select from the drop-down list applies the constant value that is entered in the third column. </p> </li> 
     <li id="li_D5F0651B834F4EACAD15A2D154A0737B"> <span class="uicontrol"> Value </span> <p>The constant value. </p> </li> 
     <li id="li_FC8F382BD20C4518BC2230D4B4954591"> <span class="uicontrol"> Action </span> <p>Adds a new field mapping row, or deletes the currently highlighted row. </p> </li> 
    </ul> <p>Generic feeds need a special CGI parameter specified. To bind the special template that is associated with this feed, you define the <span class="codeph"> sp_t </span> parameter. Set the value of <span class="codeph"> sp_t </span> to the name of the transport template file. For example, if you added a transport template file named <span class="codeph"> super_feed.tpl </span>, you create a custom CGI search parameter as <span class="codeph"> sp_t=super_feed </span>. The text box for entering the <span class="codeph"> sp_t </span> does not appear until you select <span class="uicontrol"> Free Form </span> from the <span class="wintitle"> Meta Field </span> drop-down list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>File Submission </p> </td> 
   <td colname="col3"> <p>Lets you configure the schedule for submitting the feed files and set the method that you want to use to upload the files. </p> 
    <ul id="ul_30E830C41F6A4526822AF1FD3083075A"> 
     <li id="li_79EAFDBD2B9F411EA985CAEC1BAF3926"> <span class="uicontrol"> Schedule </span> <p>Sets the maximum frequency that a feed is submitted. Selecting <span class="uicontrol"> Never </span> turns off the feed. Other values define the period that the feed waits before submitting again. The decision when to submit the feed is done at each index. In other words, at the end of the index, a feed is checked to see if it has expired and needs to be updated and submitted by the vendor. Also, it is used as a method of preventing an account from over-submitting to a vendor. Some vendors have policies against data feed sources that upload too frequently. Be sure that you check the feed vendor's policy about the frequency of submissions. 
       <!--he time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> 
       <!--<uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
       <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
     <li id="li_20BF70A19E7E45BA91CD972E2FCE0EA4"> <span class="uicontrol"> Upload Method </span> <p>Most feeds have two ways of distributing the files: FTP and Hosted Content Network. </p> 
      <ul id="ul_5888C2E9097645CE89938EE09F8CB4F1"> 
       <li id="li_EA9ED19F3BEA4BEAB1A9F2C2FAFF85F7"> <span class="uicontrol"> FTP </span> <p>Site search/merchandising servers use passive FTP. </p> <p>FTP is the only way to push a file to another server. </p> <p> <span class="uicontrol"> FTP Server </span> - Specifies the name of the FTP server. Do not include the protocol or preceding "ftp://". </p> <p> <span class="uicontrol"> FTP User Name </span> - Specifies the name of the FTP account. </p> <p> <span class="uicontrol"> FTP Password </span> - Specifies the password of the FTP account. </p> <p> <span class="uicontrol"> FTP File Name </span> - Specifies the name of the file to transmit. This name is a template if the feed generates multiple files, usually incrementing a number at the end of the name but before the extension. For example: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> FTP Directory </span> - If a specific directory path is required, you enter it here. Do not include the filename in the path. </p> </li> 
       <li id="li_181268A7EE40456CA1DB768E8C66EEB9"> <span class="uicontrol"> Hosted Content Network </span> <p>The Hosted Content Network is the means of serving files from the web servers of site search/merchandising. The recipient of the feed pulls it from the web servers using an HTTP request. The only piece of information to set this up is <span class="uicontrol"> Content Network Filename </span>. The filename is the base name of the file that is served. Use only filenames with a filename extension. 
         <!--Depending on the feed, the file name is a template for multiple files where the feed might generate multiple files in the following format: basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml. --> </p> <p>After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. </p> </li> 
      </ul> </li> 
     <li id="li_4DF56FA607A7479296CDA042A63C5A2C"> <p> <b>Preserve tabs?</b> </p> <p>Maintain tab characters in the feed. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Verification </p> </td> 
   <td colname="col3"> <p>When you get to the <span class="wintitle"> Verification </span> panel, your feed is saved at that point. However, the actual feed files are not saved until later. </p> <p>The <span class="wintitle"> Verification </span> panel lets you do the following: </p> 
    <ul id="ul_7420C415987448A796DD979CF5FA2EB6"> 
     <li id="li_AF02E8609B7B4F20A01AF4E010308E15"> <span class="uicontrol"> Data View </span> <p>Lets you click the link to check the feed output through a data view that is displayed in table form. The data view can also help you troubleshoot by showing you which meta fields are chosen and how any specified search criteria from the <span class="wintitle"> Search Criteria </span> panel in the wizard, affects the feed output. The data view is generated dynamically, so it is available at all times. </p> </li> 
     <li id="li_32CEB8885C184354BFA1773BA66DB7A7"> <span class="uicontrol"> Feed Files </span> <p>After site search/merchandising servers generate the feed files, you can use the <span class="uicontrol"> Feed Files </span> drop-down list to view the files from the servers. A new browser tab or new browser window appears with the content of the feed. This method is useful for helping you troubleshoot feeds that have formatting issues. Note that you do not view the files from the final destination or from the vendors themselves. </p> <p> If the feed is new, then the drop-down list is empty until you generate feed files. </p> </li> 
     <li id="li_8D1B876B0EC2455C8654EC573EC53FA9"> <span class="uicontrol"> Content Network Link </span> <p>If you chose <span class="uicontrol"> Hosted Content Network </span> as your upload method in the <span class="wintitle"> File Submission </span> panel of the wizard, the URL is displayed here. If you have not yet generated any feed files, the URL is not valid until the feed is successfully generated. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

   **Google Merchant Center**

<table id="table_6215893F2DE04B01B065AE087B4B1974"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Panel </p> </th> 
   <th colname="col2" class="entry"> <p>Wizard Panel Name </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Feed Name </p> </td> 
   <td colname="col3"> <p>Specifies the name of the feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Field Maps </p> </td> 
   <td colname="col3"> <p>Lets you map vendor-specific feed fields to site search/merchandising metadata fields. This mapping step in the wizard is important because it allows Feeds to correlate the information between the fields in the index and the fields in the feed data. In most cases, except for <span class="wintitle"> Generic Feeds </span>, the correlations are saved in a dynamically generated search template. </p> <p>Each row in the Field Maps table represents a field mapping. In the <span class="wintitle"> Add/Remove </span> column of the table, click <span class="uicontrol"> + </span> to add a new field mapping row; click <span class="uicontrol"> - </span> to delete the currently selected field mapping row from the table. To associate a feed field with a site search/merchandising metadata field, use the respective drop-down lists to choose the desired fields. </p> <p> <b>Advanced usage</b> </p> <p>You can create your own custom fields. In the <span class="wintitle"> Feed Fields </span> drop-down list, click <span class="uicontrol"> Custom </span>. In the associated text field, enter a custom tag name for that field. This custom option is useful if a feed needs special vendor-specific fields. </p> <p>You can also create a custom metadata field. In the <span class="wintitle"> Metadata Fields </span> drop-down list, click <span class="uicontrol"> Custom </span>. In the associated text field, enter a custom metadata field value. The value is inserted into the pre-generated template and it can also be used to inject custom search template tags. </p> <p>See <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Search template tags </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Search Criteria </p> </td> 
   <td colname="col3"> <p>When the feed files are generated, a search query is used to filter the data. You define the filters that are used for the search query in this panel. </p> 
    <ul id="ul_8179321A58BB4C72B0CDB2B2BEC58FE4"> 
     <li id="li_9F8008A2398A4667B106BC49C94E5E3E"> <span class="uicontrol"> Meta Field </span> <p>Defines which metadata field that you want to filter on. </p> <p> <b>Advanced usage</b> </p> <p>Because the filtering system is a standard search query, you can select <span class="uicontrol"> Free Form </span> from the drop-down list to enter CGI search parameters and their values. URL escaping is required. The search argument <span class="codeph"> sp_q </span> is ignored. You can create multiple rows of Free Form text boxes. Between each row, the arguments are delimited with &amp;'s automatically. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Search CGI parameters </a>. </p> </li> 
     <li id="li_50C9CE59E9E5418895F8C1A070560063"> <span class="uicontrol"> Criteria </span> <p>Defines the filter operation. The filter operation that you select from the drop-down list applies the constant value that is entered in the third column. </p> </li> 
     <li id="li_9F86D0F5010046A4A9F93DBA5FB158B3"> <span class="uicontrol"> Value </span> <p>The constant value. </p> </li> 
     <li id="li_1051AFD5AEA447D0AF5FAB305E1D1E64"> <span class="uicontrol"> Action </span> <p>Adds a new field mapping row, or deletes the currently highlighted row. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>File Submission </p> </td> 
   <td colname="col3"> <p>Lets you configure the schedule for submitting the feed files and set the method that you want to use to upload the files. </p> 
    <ul id="ul_A6A3C333AADD4438B835BF3E16E2AEFF"> 
     <li id="li_FCC4DAF198E149278B5CFB870CB6218C"> <span class="uicontrol"> Schedule </span> <p>Sets the maximum frequency that a feed is submitted. Selecting <span class="uicontrol"> Never </span> turns off the feed. Other values define the period that the feed waits before submitting again. The decision when to submit the feed is done at each index. In other words, at the end of the index, a feed is checked to see if it has expired and needs to be updated and submitted by the vendor. Also, it is used as a method of preventing an account from over-submitting to a vendor. Some vendors have policies against data feed sources that upload too frequently. Be sure that you check the feed vendor's policy about the frequency of submissions. </p> <p> 
       <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> </p> <p> 
       <!--Click <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
       <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
     <li id="li_2D9ECAFB8E8544D39B486F7BC3DCE589"> <span class="uicontrol"> Upload Method </span> <p>Most feeds have two ways of distributing the files: FTP and Hosted Content Network. </p> <p>The recommended upload method for submitting the data feed is <span class="uicontrol"> FTP </span>. Google Merchant Center hosts an FTP server for this purpose. See the Google Merchant Center Help about setting up a separate Google FTP account for this Google Product Search feed. </p> 
      <ul id="ul_BC0D8B541068407883CAC948496DBD0A"> 
       <li id="li_DB28CA23C94A4AF09E1A0EB06DF8F40C"> <span class="uicontrol"> FTP </span> <p>Site search/merchandising servers use passive FTP. </p> <p>FTP is the only way to push a file to another server. </p> <p> <span class="uicontrol"> FTP Server </span> - Specifies the name of the FTP server. In this case, it is 
         <userinput>
           uploads.google.com 
         </userinput>. Do not include the protocol or preceding "ftp://". </p> <p> <span class="uicontrol"> FTP User Name </span> - Specifies the name of the FTP account. </p> <p> <span class="uicontrol"> FTP Password </span> - Specifies the password of the FTP account. </p> <p> <span class="uicontrol"> FTP File Name </span> - Specifies the name of the file to transmit. This name is a template if the feed generates multiple files, usually incrementing a number at the end of the name but before the extension. For example: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> FTP Directory </span> - If a specific directory path is required, you enter it here. Do not include the filename in the path. </p> </li> 
       <li id="li_5990927146434DAF89273F4636D21437"> <span class="uicontrol"> Hosted Content Network </span> <p>The Content Network is the means of serving files from the web servers of site search/merchandising. The recipient of the feed pulls it from the web servers using an HTTP request. </p> <p> 
         <!--After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. Multiple files use the same URL path. However, be sure that you replace or change the filename according to the enumeration scheme. --> </p> </li> 
      </ul> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Verification </p> </td> 
   <td colname="col3"> <p>When you get to the <span class="wintitle"> Verification </span> panel, your feed is saved at that point. However, the actual feed files are not saved until later. </p> <p>The <span class="wintitle"> Verification </span> panel lets you do the following: </p> 
    <ul id="ul_4A94355A8DF840A3BAF6BD5E9F11C27F"> 
     <li id="li_825697CB36B34C4AB5959B15EDDB55F1"> <span class="uicontrol"> Data View </span> <p>Lets you click the link to check the feed output through a data view that is displayed in table form. The data view can also help you troubleshoot by showing you which meta fields are chosen and how any specified search criteria from the <span class="wintitle"> Search Criteria </span> panel in the wizard, affects the feed output. The data view is generated dynamically, so it is available at all times. </p> </li> 
     <li id="li_91B8B5F5F9DE4A13863CD62F74AA6206"> <span class="uicontrol"> Feed Files </span> <p>After site search/merchandising servers generate the feed files, you can use the <span class="uicontrol"> Feed Files </span> drop-down list to view the files from the servers. A new browser tab or new browser window appears with the content of the feed. This method is useful for helping you troubleshoot feeds that have formatting issues. Note that you do not view the files from the final destination or from the vendors themselves. </p> <p> If the feed is new, then the drop-down list is empty until you generate feed files. </p> </li> 
     <li id="li_4A5EC089628E43029A38F8919888FF0A"> <span class="uicontrol"> Content Network Link </span> <p>If you chose <span class="uicontrol"> Hosted Content Network </span> as your upload method in the <span class="wintitle"> File Submission </span> panel of the wizard, the URL is displayed here. If you have not yet generated any feed files, the URL is not valid until the feed is successfully generated. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

   **Google Sitemaps**

<table id="table_936B085AAA574ABABB80D8ADFD95E636"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Panel </p> </th> 
   <th colname="col2" class="entry"> <p>Wizard Panel Name </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Feed Name </p> </td> 
   <td colname="col3"> <p>Specifies the name of the feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Field Maps </p> </td> 
   <td colname="col3"> <p>Lets you map vendor-specific feed fields to site search/merchandising metadata fields. This mapping step in the wizard is important because it allows Feeds to correlate the information between the fields in the index and the fields in the feed data. In most cases, except for <span class="wintitle"> Generic Feeds </span>, the correlations are saved in a dynamically generated search template. </p> <p>Each row in the Field Maps table represents a field mapping. In the Add/Remove column of the table, click <span class="uicontrol"> + </span> to add a new field mapping row; click <span class="uicontrol"> - </span> to delete the currently selected field mapping row from the table. To associate a Feed Field with a Metadata Field, use the respective drop-down lists to choose the desired fields. </p> <p> <b>Advanced usage</b> </p> <p>You can create your own custom fields. In the <span class="wintitle"> Feed Fields </span> drop-down list, click <span class="uicontrol"> Custom </span>. In the associated text field, enter a custom tag name for that field. This custom option is useful if a feed needs special vendor-specific fields. </p> <p>You can also create a custom metadata field. In the <span class="wintitle"> Metadata Fields </span> drop-down list, click <span class="uicontrol"> Custom </span>. In the associated text field, enter a custom metadata field value. The value is inserted into the pre-generated template and it can also be used to inject custom search template tags. </p> <p>See <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Search template tags </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Search Criteria </p> </td> 
   <td colname="col3"> <p>When the feed files are generated, a search query is used to filter the data. You define the filters that are used for the search query in this panel. </p> 
    <ul id="ul_994585E89A044BD3A89A99D30F277432"> 
     <li id="li_61FA9246B9824E3C8124958C8EBFF0DA"> <span class="uicontrol"> Meta Field </span> <p>Defines which metadata field that you want to filter on. </p> <p> <b>Advanced usage</b> </p> <p>Because the filtering system is a standard search query, you can select <span class="uicontrol"> Free Form </span> from the drop-down list to enter CGI search parameters and their values. URL escaping is required. The search argument <span class="codeph"> sp_q </span> is ignored. You can create multiple rows of Free Form text boxes. Between each row, the arguments are delimited with &amp;'s automatically. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Search CGI parameters </a>. </p> </li> 
     <li id="li_A5D00883738845C8B8F612A7521F160F"> <span class="uicontrol"> Criteria </span> <p>Defines the filter operation. The filter operation that you select from the drop-down list applies the constant value that is entered in the third column. </p> </li> 
     <li id="li_5A312C2984454C2CB518CA453AD9F6D2"> <span class="uicontrol"> Value </span> <p>The constant value. </p> </li> 
     <li id="li_666AAE1BC7A2432E91953B08EC7394DC"> <span class="uicontrol"> Action </span> <p>Adds a new field mapping row, or deletes the currently highlighted row. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>File Submission </p> </td> 
   <td colname="col3"> <p>Lets you configure the schedule for submitting the feed files and set the method that you want to use to upload the files. </p> 
    <ul id="ul_49B3255BE669424B925BBAEE4C9B385F"> 
     <li id="li_939828C774D440EBB0769F6D5B0BBA23"> <span class="uicontrol"> Schedule </span> <p>Sets the maximum frequency that a feed is submitted. Selecting <span class="uicontrol"> Never </span> turns off the feed. Other values define the period that the feed waits before submitting again. The decision when to submit the feed is done at each index. In other words, at the end of the index, a feed is checked to see if it has expired and needs to be updated and submitted by the vendor. Also, it is used as a method of preventing an account from over-submitting to a vendor. Some vendors have policies against data feed sources that upload too frequently. Be sure that you check the feed vendor's policy about the frequency of submissions. </p> <p> 
       <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> </p> <p> 
       <!--Click <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
       <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
     <li id="li_07B5BCF7936241A7915C4898B231184B"> <span class="uicontrol"> Upload Method </span> <p>Most feeds have two ways of distributing the files: FTP and Hosted Content Network. </p> 
      <ul id="ul_74FA98A82754469BA5FADCC63FC364F7"> 
       <li id="li_02940B712D6444A8B65C0A51834187E6"> <span class="uicontrol"> FTP </span> <p>Site search/merchandising servers use passive FTP. </p> <p>FTP is the only way to push a file to another server. </p> <p> <span class="uicontrol"> FTP Server </span> - Specifies the name of the FTP server. Do not include the protocol or preceding "ftp://". </p> <p> <span class="uicontrol"> FTP User Name </span> - Specifies the name of the FTP account. </p> <p> <span class="uicontrol"> FTP Password </span> - Specifies the password of the FTP account. </p> <p> <span class="uicontrol"> FTP File Name </span> - Specifies the name of the file to transmit. This name is a template if the feed generates multiple files, usually incrementing a number at the end of the name but before the extension. For example: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> FTP Directory </span> - If a specific directory path is required, you enter it here. Do not include the filename in the path. </p> </li> 
       <li id="li_EAE504436CD84452BA04BE51855A2BEF"> <span class="uicontrol"> Hosted Content Network </span> <p>The Content Network is the way to serve files from the web servers of site search/merchandising. The recipient of the feed pulls it from the web servers using an HTTP request. </p> <p> 
         <!--After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. Multiple files use the same URL path. However, be sure that you replace or change the filename according to the enumeration scheme. --> </p> </li> 
      </ul> </li> 
    </ul> <p>Note that either upload method requires you to specify the URL that Google uses to retrieve the sitemap, in the <span class="wintitle"> Main Sitemap URL </span> field. The name of the sitemap file is determined here, too. If your sitemap is large, multiple files may exist and the naming convention is to attach an index number at the end of the file starting with the number 1. The first file or index file has no index, as in <span class="codeph"> sitemap.xml </span>, <span class="codeph"> sitemap1.xml </span>, <span class="codeph"> sitemap2.xml </span> ... <span class="codeph"> sitemap12.xml </span>. </p> <p>If you chose <span class="uicontrol"> Hosted Content Network </span> as the upload method, the URL of the files has the same filenames, but the URL has the path and host name of the hosting service. Therefore, you redirect the requests for the sitemap to the Hosted Content Network. You should be able to pull the files from the same location, too. </p> <p>After the feed files are created and submitted to the intermediate destination, Google is pinged and lets them know that the sitemap feed is ready. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Verification </p> </td> 
   <td colname="col3"> <p>When you get to the <span class="wintitle"> Verification </span> panel, your feed is saved at that point. However, the actual feed files are not saved until later. </p> <p>The <span class="wintitle"> Verification </span> panel lets you do the following: </p> 
    <ul id="ul_A1D889A84972419599FC83F39EA2676A"> 
     <li id="li_C8ED077B6DD1461E85A4914C1CFDBE88"> <span class="uicontrol"> Data View </span> <p>Lets you click the link to check the feed output through a data view that is displayed in table form. The data view can also help you troubleshoot by showing you which meta fields are chosen and how any specified search criteria from the <span class="wintitle"> Search Criteria </span> panel in the wizard, affects the feed output. The data view is generated dynamically, so it is available at all times. </p> </li> 
     <li id="li_DACEE40703AF40EFBCD90D43825CE9C1"> <span class="uicontrol"> Feed Files </span> <p>After the feed files are generated, you can use the <span class="uicontrol"> Feed Files </span> drop-down list to view the files from the servers. A new browser tab or new browser window appears with the content of the feed. This method is useful for helping you troubleshoot feeds that have formatting issues. Note that you do no view the files from the final destination or from the vendors themselves. </p> <p> If the feed is new, then the drop-down list is empty until you generate feed files. </p> </li> 
     <li id="li_1C530354B4F34EC79D92CEFEB5B39ED7"> <span class="uicontrol"> Content Network Link </span> <p>If you chose <span class="uicontrol"> Hosted Content Network </span> as your upload method in the <span class="wintitle"> File Submission </span> panel of the wizard, the URL is displayed here. If you have not yet generated any feed files, the URL is not valid until the feed is successfully generated. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. When you complete the steps in the wizard, click **[!UICONTROL Close]**.

## Editing a feed {#task_B855D28CD99B4FA58E2D4D4FD6DC9CEB}

You can edit the configuration of an existing feed.

<!-- 

t_editing_a_feed.xml

 -->

>[!NOTE]
>
>When you edit a feed, you cannot change the feed type. If you need to changed the feed type, delete the existing feed, and then add a new feed with the type you want.

See [Deleting a feed](../c-about-settings-menu/c-about-searching-menu.md#task_7E39A140E69D43C6B61FB42E81051269).

**To edit a feed** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. Do one of the following:

* On the [!UICONTROL Feeds] page, under the [!UICONTROL Name] column of the table, click the drop-down list next to a feed name, and then click **[!UICONTROL Edit feed]**. 

* On the [!UICONTROL Feeds] page, under the [!UICONTROL Name] column, click the name of a feed that you want to change.

1. In the feed's wizard, set the options that you want for each panel in the wizard.

   See the tables of options under **Adding a feed**. 
1. At the end of the wizard, in the [!UICONTROL Verification] panel, click **[!UICONTROL Close]**.

## Deleting a feed {#task_7E39A140E69D43C6B61FB42E81051269}

You can delete a feed that you no longer need or use.

<!-- 

t_deleting_a_feed.xml

 -->

**To delete a feed** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. In the [!UICONTROL Feeds Menu] screen, under the [!UICONTROL Actions] column, click **[!UICONTROL Delete]** for the feed name that you want to remove.
1. In the [!UICONTROL Delete feed] dialog box, click **[!UICONTROL Yes]** to confirm the deletion.

## Viewing feed files {#task_1E413C7650DE466EA68925F72E086884}

You can go the last panel of the Feed wizard to give you quick access for viewing the data view of the feed or to download any current feed files from the server. This functionality is helpful if you want to verify and examine the feed output.

<!-- 

t_viewing_feed_files.xml

 -->

**To view feed files** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. On the [!UICONTROL Feeds] page, under the [!UICONTROL Name] column of the table, click the drop-down list next to a feed name, and then click **[!UICONTROL View Feed Files]**.
1. In the [!UICONTROL Verification] panel of the feed's wizard, click **[!UICONTROL Show Data View]**.
1. Click **[!UICONTROL Close]**.

## Testing a feed with no file upload {#task_F1F390F72E0A4886B6CD4CD86EDB4C8C}

You can test a feed without uploading files to the final destination.

<!-- 

t_testing_a_feed_with_no_file_upload.xml

 -->

**To test a feed with no file upload** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. On the [!UICONTROL Feeds] page, under the [!UICONTROL Name] column of the table, click the drop-down list next to a feed name, and then click **[!UICONTROL Test Feed (No file upload)]**.
1. On the [!UICONTROL Feeds] page, the [!UICONTROL Feed Status] column is updated during and following the test.

## Generating and uploading a feed {#task_C9A57827C7674035B62A22D310DDAA0C}

You can manually generate and submit feed files to the final destination, regardless of the schedule that you set in the [!UICONTROL File Submission] panel of the Feed wizard.

<!-- 

t_generating_and_uploading_a_feed.xml

 -->

See also [Creating a feed](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250).

**To generate and upload a feed** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**.
1. On the [!UICONTROL Feeds] page, under the [!UICONTROL Name] column of the table, click the drop-down list next to a feed name, and then click **[!UICONTROL Generate and Upload Feed]**.
1. On the [!UICONTROL Feeds] page, the [!UICONTROL Feed Status] column is updated during and following the data feed generation and upload.
