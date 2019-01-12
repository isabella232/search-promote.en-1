---
description: null
seo-description: null
seo-title: Search&Promote 8.11.0 Release Notes (10/29/2013)
solution: Target
title: Search&Promote 8.11.0 Release Notes (10/29/2013)
topic: Release Notes,Site search and merchandising
uuid: 973f9608-a5c7-4571-ae2b-6f1fa05bc862
index: y
internal: n
snippet: y
---

# Search&Promote 8.11.0 Release Notes (10/29/2013){#search-promote-release-notes}

<table id="table_27B1D387802541DB80C450DEB838D020"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>New feature </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Danish de-compounder </p> </td> 
   <td colname="col2"> <p> A mechanism is now provided to allow <span class="keyword"> Adobe Search&amp;Promote</span> to access the language (Danish) detection, decompounding, stemming and segmentor services provided by Adobe. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Enhancements and fixes**

* Enhancements made to the existing [!DNL Search&Promote] table matching capabilities. The enhancements provide better support of customer requirements related to increasingly complex relationships between SKU and product data.

  >[!NOTE]
  >
  >This feature is not enabled by default. Contact Adobe Customer Care to activate the feature in Search&Promote for your use.

* Added an option that allows Guided Search to sort Facets using the account's language setting.

  >[!NOTE]
  >
  >This feature is not enabled by default. Contact Adobe Customer Care to activate the feature in Search&Promote for your use.

* Added an option to increase the number of facet values that a user can specify for multi-select facets.

  >[!NOTE]
  >
  >This feature is not enabled by default. Contact Adobe Customer Care to activate the feature in Search&Promote for your use.

* Added the checkbox option **[!UICONTROL Only allow searches that use HTTPS]** to **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]**.

  See [About Restrictions](../c-about-settings-menu/c-about-searching-menu.md#concept_B5B527E04EBF4E9AB5956EEF881DDBF1). 

* Added an option to **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]** > **[!UICONTROL Generic Feed]** to preserve tab characters in the [!DNL File Submission] panel of the wizard.

  See [Creating a feed](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250). 

* Increased the size of data that is accepted in each of the top and bottom fields for the new facet definition form from 80 characters to 1000.

  See [About Facets](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5). 

* Guided Search debug parameters now correctly report business rule numbers. 
* Business rules are now applied on the Live environment. 
* Proximity search is now functional when searching by longitude/latitude, for accounts configured with Language = "Danish (Denmark)". 
* Results-based triggers with no schedule assigned are now triggered. 
* Consistent results are now reported when using the **[!UICONTROL Ignore Apostrophes]** option in **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**.

  See [About Words & Language](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79). 

* Auto-Complete word list user interface now works on large number of facets.

