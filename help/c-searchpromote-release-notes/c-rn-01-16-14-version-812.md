---
description: null
seo-description: null
seo-title: Search&Promote 8.12.0 Release Notes (01/16/2014)
solution: Target
title: Search&Promote 8.12.0 Release Notes (01/16/2014)
topic: Release Notes,Site search and merchandising
uuid: 4db10eb4-11bf-4483-a7f2-87981d9c7a50
index: y
internal: n
snippet: y
---

# Search&Promote 8.12.0 Release Notes (01/16/2014){#search-promote-release-notes}

<table id="table_27B1D387802541DB80C450DEB838D020"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>New features and enhancements </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Stemming dictionaries added </p> </td> 
   <td colname="col2"> <p> </p> <p> Stemming dictionaries were added for Indonesian and Turkish languages. </p> <p>See <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" format="dita" scope="local"> About Dictionaries</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Export reports </p> </td> 
   <td colname="col2"> <p> 
     <!--3683368-->You can now export data to CSV from the following reports: 
     <ul id="ul_93B619DBB3444F64BD6D7F9E969AB1E1"> 
      <li id="li_96DDE1A196834845A0FA319903C5934B"> <p>Terms Report </p> </li> 
      <li id="li_4F1A19DE98C84F8CAD963EEA2B38ED7A"> <p>Null Search Terms Report </p> </li> 
      <li id="li_A7716C62C4D44CD69D411C3FEE246D96"> <p>Search Request Report </p> </li> 
     </ul> </p> <p>See <a href="../c-about-reports-menu/c-about-reports-menu.md#concept_5F901459C7AB461BAB30B305957EB00C" format="dita" scope="local"> About the Reports menu</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Do not associate </p> </td> 
   <td colname="col2"> <p>You can now control which two words should not be associated together in search results, such as "Sweatshirt" and "Shirt". </p> <p> <p>Note:  This feature is not enabled by default. Contact Adobe Customer Care to activate the feature in Search&amp;Promote for your use. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes**

* You could not add results in a Recommended zone that were outside the currently selected faceting criteria. 
* You could not save results-based rules for an account with HTTPS-only searching. 
* Setting up a Business rule for "is not a mobile phone" did not work.

  See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD). 

* Performing an inventory filter search did not return results. 
* The Size facet order was not getting updated. 
* Added the option for a "custom" rule definition to the Query Cleaning page.

  See [About Query Cleaning Rules](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C). 

* The Terms report was repeating entries if there was not enough data.

  See [Viewing the Terms Report or the Null Search Terms Report...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A). 

* Pushing a single business rule live was working in Staging mode, but failing in Live mode. 
* Auto-complete edits to Include or Exclude lists were not saved in History and, therefore, could not be reverted.

  See [About Auto-Complete](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578).

