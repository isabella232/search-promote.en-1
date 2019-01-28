---
description: null
seo-description: null
seo-title: Search&amp;Promote 15.3.1 Release Notes (03/24/2015)
solution: Target
title: Search&amp;Promote 15.3.1 Release Notes (03/24/2015)
topic: Release Notes,Site search and merchandising
uuid: f02da5a4-2207-4603-aa05-5cff7be16dd5
index: n
internal: n
snippet: y
---

# Search&amp;Promote 15.3.1 Release Notes (03/24/2015){#search-promote-release-notes}

## New features and enhancements {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Searching product model numbers - Added a new Linguistics setting that lets you optionally split tokens on alphabetical-numerical transitions. This functionality allows more flexible free-text matches on part or product style tokens.

  See **[!UICONTROL Partial Alphanumeric Matching]** in [Configuring how search terms are matched to your web content...](../c-about-linguistics-menu/c-about-words-and-language.md#task_351A9144A51F4B41923BDBACDEF3B616). 

* Added ability to export data view results.

  See [About Data Views](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3). 

* Dynamically Generated Ranges for ranged attributes auto-facet-value bucketing features.

  Adobe Systems currently requires you to provide content identifying range values to do this. For example, for a price of 10, generate a range string "Between $10 and $20"). Or, Adobe Systems requires you to use Scripted Filtering. Added new attributes to a metadata field definition, for `Type=Number` fields only. The new options associate the numeric field with a `Type=Text` field, and specify configuration information describing how the range description is built.

  See [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Fixes {#section_22D1AFC99F394D569898828A0D3C419D}

* Facet rail edit dialog should include staged facets. 
* Empty core search results for "embedded" search mode, for a search containing Japanese characters. 
* Tika conversion of Word .docx files now populates the `title` attribute. 
* Corrected erroneous "duplicate banner" messages in the **[!UICONTROL Banner]** manager. 
* Scene7 banners are now protocol-agnostic. 
* The **[!UICONTROL Table Name]** field attribute was sometimes hidden when editing user-defined fields in the Metadata user interface, even when **[!UICONTROL Dynamic Facets]** was enabled for the account. 
* **[!UICONTROL Recent Searches]** no longer multiply-encodes non-ASCII characters. 
* MDI fields can be populated without resorting to Scripted Filtering. 
* Wrong encoding in suggestions. 
* "other facet selected" trigger now works correctly with complex business rules.

