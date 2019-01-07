---
description: null
seo-description: null
seo-title: Search&Promote 8.9 Release Notes (07/19/2012)
solution: Target
title: Search&Promote 8.9 Release Notes (07/19/2012)
topic: Release Notes,Site search and merchandising
uuid: 7d83e0ba-e621-4b6a-823f-8598737f397e
index: y
internal: n
snippet: y
---

# Search&Promote 8.9 Release Notes (07/19/2012){#search-promote-release-notes}

 **New features**

* Metadata management improvements - Dynamic metadata definition from customer feeds

  Create a scheme to dynamically re-configure your Search&Promote account based on customer-provided metadata definitions. 
* Indexing performance improvements - Index Loader

  Index Loader is a new way to import XML content directly into a Search&Promote index. It is a subset of the existing Index Connector functionality that is designed to quickly import our standard XML feed files.

**Fixes and enhancements**

* Added support for changing the sort option by a business rule. 
* In the Help system `<search-description>` tag shows the body instead when the meta tag for the description has empty content. 
* Added ability to track applicable table hits for results that were added by way of results-based actions. 
* Added support for submitting query parameters via POST 
* When crawling, a final mirror_account operation can be skipped in some cases. 
* Adobe Analytics URLs do not include CGI arguments and the Search&Promote code that does Adobe Analytics look-ups needed to similarly strip CGI arguments from URL keys. 
* Rewrite rules disappeared intermittently from the user interface after they were pushed to live. 
* Search&Promote accounts with Did You Mean settings that were set to make suggestions due to low results may have intermittent results. 
* Rewrite rule test output did not have line breaks. 
* The Search URL Rules page and the Crawl List Store URL Rules page pointed to the wrong History page. 
* Clicking Edit on some banners did not display the Edit page. 
* Re-ranking update code could sometimes be extraordinarily slow. 
* Removing or pushing a facet item did not work if the facet name used mixed case.

