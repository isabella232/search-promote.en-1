---
description: null
seo-description: null
seo-title: Search&Promote 8.9.8 Release Notes (05/23/2013)
solution: Target
title: Search&Promote 8.9.8 Release Notes (05/23/2013)
topic: Release Notes,Site search and merchandising
uuid: ff4bfc53-1d0e-4b7d-83ad-54c81d3f9769
index: y
internal: n
snippet: y
---

# Search&Promote 8.9.8 Release Notes (05/23/2013){#search-promote-release-notes}

<table id="table_27B1D387802541DB80C450DEB838D020"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>New feature </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Common phrases - exact match support </p> </td> 
   <td colname="col2"> <p> Common phrases contain terms of two or more words that are searched on as a whole-such as "boot cut" or "tank top"-and not as separate parts. A common phrase has a meaning that is unique and different from any of its individual parts. </p> <p> You maintain a dictionary of common phrases related to your business. When a customer performs a search query that contains multiple words, a search is performed on the dictionary for the exact same match. </p> <p>You can add, edit, or delete common phrases. You can also group common phrases similar to domain dictionaries. For example you can group common phrases by apparel, fabric, jewelry, measurements, shopping, and general. </p> <p>See <a href="../c-about-linguistics-menu/c-about-common-phrases.md#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local"> About Common Phrases </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes and enhancements**

* The backend search CGI parameter `sp_date_range_#` did not work for user-defined fields.

  See [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). 

* Reverting **[!UICONTROL History]** version did not update the URL entrypoints field content.

  See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

  See also [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573). 

* JSON encoding was not managing wrongly encoded characters. 
* Support now added that lets you remotely push live a staged index.

  See [About Remote Control for Indexing](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

