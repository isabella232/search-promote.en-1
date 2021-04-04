---
description: Search&amp;Promote 8.9.4 release notes.
solution: Target
title: Search&amp;Promote 8.9.4 Release Notes (01/17/2013)
topic: Release Notes,Site search and merchandising
uuid: a9d550f6-0a23-4c71-b123-c31b997e7384
exl-id: cb5d93d9-54ac-4b41-96ad-66f18ee1e934
---
# Search&amp;Promote 8.9.4 Release Notes (01/17/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>New features and enhancements </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Rules </p> </td> 
   <td colname="col2"> <p> Added the ability to create inline notes when you create Query Cleaning Rules, Pre-Search Rules, and Post-Search Rules. The notes field lets you document and explain the rules. </p> <p>See <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" format="dita" scope="local"> About Query Cleaning Rules</a>. </p> <p>See <a href="../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F" format="dita" scope="local"> About Pre-Search Rules</a>. </p> <p>See <a href="../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE" format="dita" scope="local"> About Post-Search Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guided Search </p> </td> 
   <td colname="col2"> <p> Added Guided Search tags to indicate the total time that a search took. </p> <p> <span class="codeph"> &lt;guided-search-time&gt;</span> - Identifies how long the search took. The returned search time value is specified in ms. </p> <p> <span class="codeph"> &lt;guided-fall-through-searches&gt;</span> - Returns the count of cores searches that are used to build the page of search results. </p> <p> <span class="codeph"> &lt;guided-if-fall-through-search&gt;</span> - Tests if the count of core searches is greater than 1. </p> <p>See also Miscellaneous Language in <a href="../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64" format="dita" scope="local"> Presentation template tags</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes**

* The Terms Report now ignores the asterisk character.

  See [Viewing the Terms Report or the Null Search Terms Report...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A). 

* Open **[!UICONTROL Reports > Null Search Terms Report]**, select a time slot and then view the report. Clicked one word in the report to open the search, and then click View Report again. The search count of the keyword you clicked increased twice. This is now fixed.

  See [Viewing the Terms Report or the Null Search Terms Report...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A). 

* A performance optimization was made for when you push business rules live.

  See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD). 

* The ability to remove in [!DNL Breadcrumbs] did not work all the time.

  See [About Breadcrumbs](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03). 

* Unless you used regenerate, the re-rank feature did not allow any changed ranking rules to take effect in search results.

  See [About Ranking Rules](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

  See [About Re-Rank Index](../c-about-index-menu/c-about-re-rank-index.md#concept_147B0A9FCD51451787DA898E06F7C692).
