---
description: null
seo-description: null
seo-title: Search&Promote 15.1.1 Release Notes (01/15/2015)
solution: Target
title: Search&Promote 15.1.1 Release Notes (01/15/2015)
topic: Release Notes,Site search and merchandising
uuid: 8c7112ce-db85-43ba-9e02-3c772c65b81a

---

# Search&Promote 15.1.1 Release Notes (01/15/2015){#search-promote-release-notes}

## New feature {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Previously, linguistics such as stemming, synonyms, and so forth, were always applied to keywords in Guided Search rules. Now you can disable this expansion so that the keyword is used as is.

  When you want to apply trigger conditions to a business rule, in the [!DNL Advanced Rule Builder], following **[!UICONTROL If any/all of the following conditions are met]**, in the first drop-down list, select **[!UICONTROL keyword]**, and then select the new operator **[!UICONTROL equal exact]** in the second drop-down list.

  See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Fixes and enhancements {#section_22D1AFC99F394D569898828A0D3C419D}

* [!DNL Visual Rule Builder] and [!DNL Advanced Rule Builder] no longer truncates the MDI (Merchandising Document ID) field value. 
* RBTA-related indexing failures are now fixed. 
* Editing an existing business rule that has a status of "approved" now revokes the "approved" status. You must use [!DNL Advanced Rule Builder] to recheck the option **[!UICONTROL Approved]**, and then save the rule as usual. If you do not reapprove an edited rule, the rule's status is automatically set to WIP (Work In Progress) on the [!DNL Business Rules] page. 
* A new **[!UICONTROL Advanced Search]** option is now available on the [!DNL Business Rules] page for improved filtering of rules. 
* Added **[!UICONTROL contains word]** condition to rule triggers in [!DNL Query Cleaning], [!DNL Pre-Search Rules], [!DNL Post Search Rules], and [!DNL Business Rules], to let you easily specify word breaks. 
* Improvements made to business rule notes such as when you view a rule, you can now retrieve the notes history for that rule. Also, notes are now logged in **[!UICONTROL Reports]** > **[!UICONTROL Change Log]**. 
* Queries with nonzero `sp_i` values are no longer run through the [!DNL Adobe Analytics] redirector.

  See row 15 in the table in [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

