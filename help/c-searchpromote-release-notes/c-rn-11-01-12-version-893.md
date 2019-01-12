---
description: null
seo-description: null
seo-title: Search&Promote 8.9.3 Release Notes (11/01/2012)
solution: Target
title: Search&Promote 8.9.3 Release Notes (11/01/2012)
topic: Release Notes,Site search and merchandising
uuid: 7bc7bcb6-f47f-4e05-94e5-a22a13a187b7
index: y
internal: n
snippet: y
---

# Search&Promote 8.9.3 Release Notes (11/01/2012){#search-promote-release-notes}

## Search&Promote 8.9.3 Release Notes (11/01/2012) {#concept_85F5B4B4C40C43FEA3AD63E6EA5593CF}

<table id="table_27B1D387802541DB80C450DEB838D020"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>New features and enhancements </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Facet Rail </p> </td> 
   <td colname="col2"> <p> 
     <!--3309390--> Added the new <span class="uicontrol"> Facet Rail</span> option to help give you greater control over the ordering of facet families and facet names (by count, alphabetical). </p> <p>See <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> About Facet Rail</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Nested facets </p> </td> 
   <td colname="col2"> <p> Added support for alternate sorting of nested facets. </p> <p>See <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> About Facet Rail</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Notes field in ranking rules </p> </td> 
   <td colname="col2"> <p> 
     <!--3063772--> Added a multi-line <span class="wintitle"> Notes</span> field to the <span class="wintitle"> Add Ranking Metric</span> dialog box and the <span class="wintitle"> Edit Ranking Metric</span> dialog box for ranking rules and rule group definitions. </p> <p>Ranking rule notes are displayed on the <span class="wintitle"> Define Ranking Rules</span> page. Rule group notes appear when you edit the definition. </p> <p>See <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" format="dita" scope="local"> About Ranking Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Business rules </p> </td> 
   <td colname="col2"> <p> 
     <!--3331637--> Improved landing page support by removing natural results in a business rule using the new <span class="uicontrol"> Remove All Results</span> option. </p> <p>Use this new option in conjunction with other business rule actions to create "canned landing pages." That is, you want to create a page's content by business rule actions exclusively and you need to discard the "natural" results of the search. </p> <p>See <a href="../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7" format="dita" scope="local"> Adding a new business rule</a> or <a href="../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087" format="dita" scope="local"> Editing a business rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Banners and business rules </p> </td> 
   <td colname="col2"> <p> Added a support option where you can conditionally opt out pushing banners live when the business rule that references the banner is pushed live. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes**

* Business rules worked inconsistently when there was a [!DNL Stage] index. 
* Autoranking rules are now applied to canned landing pages.

  See the table of options in [Adding a ranking rule](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A). 

* [!DNL promosearch.cgi] was not returning promotions.

  See [About Searches](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8). 

* Pushing rules that referenced many banners sometimes failed.

  See [About Banners](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA). 

* **[!UICONTROL Did You Mean]** search query caching is now disabled.

  See [About Did You Mean](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E).

