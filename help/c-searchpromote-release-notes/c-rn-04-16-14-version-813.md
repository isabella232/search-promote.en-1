---
description: null
seo-description: null
seo-title: Search&amp;Promote 8.13.0 Release Notes (04/16/2014)
solution: Target
title: Search&amp;Promote 8.13.0 Release Notes (04/16/2014)
topic: Release Notes,Site search and merchandising
uuid: b3524992-ff00-4a7c-a404-078242456734
index: y
internal: n
snippet: y
---

# Search&amp;Promote 8.13.0 Release Notes (04/16/2014){#search-promote-release-notes}

<table id="table_27B1D387802541DB80C450DEB838D020"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>New feature and enhancement </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dynamic Facets with full table match support </p> </td> 
   <td colname="col2"> <p> </p> <p> Some customers had many "SKU level" attributes that they wanted to select and display by way of Dynamic Facets. As such, you can now optionally associate each dynamic facet field with up to one table name in a static account configuration. Those table relationships can then be applied at search-time for any dynamic facet fields involved in the search. </p> <p>See <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> About Dynamic Facets</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes**

* Changed the data view description field to use the tag `<search-display-field>` instead of the `<search-description>`. 
* Added a feature into Index Connector to make the Primary Key the concatenation of two or more fields. 
* Changed the AttributeLoader-Regen-Enabled script `attributeloader-regen.pl` to not HTML-encode values. 
* Matched index-time and search-time whitespace treatment for "range search" queries. 
* Adding a business rule sometimes resulted in an error when Dynamic Facets was enabled.

  See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD). 

* A Javascript error prevented adding or editing a definition in **Settings** > **SPIN** > **IndexConnector**. 
* After a Business Rule was saved it appeared that when the time was selected during the Business Rule creation it was defaulting to the GMT time zone. After it was saved it appeared that the Time Zone of the Account then took effect.

  See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD). 

* The sorting of business rules in Stage was not working correctly.

  See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD). 

* Search performance reporting was enhancement by giving you the ability to schedule reports for email delivery. 
* Business rule fixed schedule was automatically changing to Daylight Saving Time.

  See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD). 

* If a large number of dynamic facet fields were defined, users experienced slow core search response times. 
* False range index errors were occurring. 
* Scene7 access in non-North American datacenters was broken. 
* The SPIN XPath validation function was returning a false-positive error.

* After a SPIN enable/disable operation, the user was redirected to the member center login page.

