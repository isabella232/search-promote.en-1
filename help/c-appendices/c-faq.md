---
description: null
seo-description: null
seo-title: Frequently asked questions
solution: Target
title: Frequently asked questions
topic: Appendices,Site search and merchandising
uuid: 4ce454a4-e770-4587-91a0-a25491818ac6
index: y
internal: n
snippet: y
---

# Frequently asked questions{#frequently-asked-questions}

## Adobe Flash {#reference_4A25BBDE32214AF5A1A454F38FD51243}

A frequently asked questions page that discusses support of the indexing and searching of SWF files on a website.

<a id="section_BEFC5E108BBC4771B4670CBA9CA08A98"></a>

<!-- 

r_faq_adobe_flash.xml

 -->

The following are common questions regarding SWF files:

* [When is a SWF file crawled and indexed?](../c-appendices/c-faq.md#section_01BB5259140D4D5FB04CCB7A1A63DE99) 
* [What do I have to do to index a SWF...](../c-appendices/c-faq.md#section_0A6A52CC70D4495BBE14D91906318F95) 
* [How are SWF files recognized?](../c-appendices/c-faq.md#section_B36C0536AB544F509601DC6A11A8E656) 
* [How are SWF files indexed?](../c-appendices/c-faq.md#section_36856058A4B54FA5ABF921344F50410C) 
* [Does a SWF file count as a page?](../c-appendices/c-faq.md#section_0158D6DE70BC40D78E2374787B9F58AB) 
* [How do I prevent the indexing of individual SWF files...](../c-appendices/c-faq.md#section_E38AD37989EF410B97AF5125057BFD22) 
* [How do I prevent SWF files from being indexed on...](../c-appendices/c-faq.md#section_DF2606A50E9A44859CFA0D44D7C5F2E4) 
* [How come I cannot search the Chinese, Japanese, or Korean SWF files on my website?](../c-appendices/c-faq.md#section_EE1A3A705AE74148BD195A0CE513A5C4)

## When is a SWF file crawled and indexed? {#section_01BB5259140D4D5FB04CCB7A1A63DE99}

A SWF file is crawled and indexed if it is contained in an embed or object tag on an HTML page, as in the following example:

```
<embed src="Flash-file-URL">  
 
<object>  
<param name=movie value="Flash-file-URL">  
</object> 
```

A SWF file is also recognized if you list the file URL as an entrypoint.

See [Adding multiple URL entry points that you want indexed](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## What do I have to do to index a SWF file? {#section_0A6A52CC70D4495BBE14D91906318F95}

To crawl and index SWF files, select the content type **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

As long as your Flash file is referenced from an `<embed>` tag or an `<object>` tag in an HTML document, the text is indexed and all of the URLs listed in the file are crawled.

If your file is not referenced from either an `<embed>` tag or an `<object>` tag, you can list the SWF file in an `<a href=...>` tag in an HTML document or as a URL entrypoint.

See [Adding multiple URL entry points that you want indexed](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## How are SWF files recognized? {#section_B36C0536AB544F509601DC6A11A8E656}

SWF files are identified by the following MIME type:

`application/x-shockwave-flash`

SWF files are also recognized with `application/octet-stream`" or `text/plain` MIME types, provided that the file extension is .swf.

A misconfigured server might use a different MIME type for SWF files. Be sure that you check your server configuration if you are having problems crawling and indexing SWF files.

## How are SWF files indexed? {#section_36856058A4B54FA5ABF921344F50410C}

Text contained in a SWF file is indexed as if it were `<body>` text in the enclosing HTML page. If a search result finds text contained in an embedded SWF file, the result actually links to the enclosing HTML page and not the SWF file. This way, the SWF file is displayed in the correct context.

If a SWF file contains a URL as a "Load Movie" action, the text in the referenced SWF file is indexed as a part of the enclosing HTML page.

If a SWF file contains a URL as a "Get URL" action, the URL is crawled and indexed later, just as an HTML `<a href=...>` reference is crawled and indexed later.

If a SWF file is listed as a URL entrypoint, the SWF file text is indexed as a single page. A search result that finds text from an entrypoint SWF links directly to the movie, not to an enclosing HTML page.

See [Adding multiple URL entry points that you want indexed](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Does a SWF file count as a page? {#section_0158D6DE70BC40D78E2374787B9F58AB}

No. A SWF file is considered to be a part of its enclosing HTML page. All "Load Movie" URLs contained in SWF files are also considered part of the enclosing HTML page. Therefore, SWF files that are referenced from an HTML page do not count as a "page" for the account's page total.

If a SWF file is listed as a URL entrypoint, then that SWF file and all "Load Movie" URLs listed in that SWF file are counted as one "page" for the account's page total.

## How do I prevent the indexing of individual SWF files? {#section_E38AD37989EF410B97AF5125057BFD22}

To prevent the indexing of a SWF file, you can add either a robots meta tag ( `<meta name="ROBOTS" content="NOINDEX">`) or a `<noindex>` tag to the enclosing HTML document. That is, the document that contains the `<embed>` or `<object>` tag.

You can also use the robots meta tag ( `<meta name="ROBOTS" content="NOFOLLOW">`) to prevent following URLs that are contained in the SWF file. If the enclosing HTML document has following disabled, the URLs listed as "Get URL" actions in the SWF file are not followed.

## How do I prevent SWF files from being indexed on my website? {#section_DF2606A50E9A44859CFA0D44D7C5F2E4}

To disable SWF indexing deselect the content type **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

You can also choose to use [!DNL URL Masks] to disable the indexing of SWF files.

See [Adding URL masks to index or not index parts of...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

To disable SWF indexing, enter one of the following URL masks:

* `exclude *.swf` (if you are not using regular expressions) 
* `exclude regexp ^.*\.swf$` (if you are using regular expressions)

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## How come I cannot search the Chinese, Japanese, or Korean SWF files on my website? {#section_EE1A3A705AE74148BD195A0CE513A5C4}

Site search/merchandising obtains UTF-8 from SWF files created with Adobe Flash. The UTF-8 contains no indication of language. If you selected the the content type **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), you must use metadata injections to specify the language that is used by the SWF file.

See [Adding field injection definitions](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

Older SWF files do not specify a character set either. If you selected the SWF content type **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), you must use metadata Injections to specify the character set that is used in the SWF file. 

## General search {#reference_E2C675162789452A9B99C6633B12CBEF}

A frequently asked questions page that discusses how site search/merchandising helps customers who visit your website find what they are looking for.

<a id="section_5DA1C144CB3D44F09A22DDE9080BD05F"></a>

<!-- 

r_faq_general_search.xml

 -->

The following are common questions regarding general searching:

* [Do I have to install any software to use site...](../c-appendices/c-faq.md#section_02AB2AFF71984F9DAA3AF2B7C0847A22) 
* [What happens when my site exceeds the page limit?](../c-appendices/c-faq.md#section_ECA5FA01032D4322BABA4E2C7FE498C1) 
* [How do I change the email address where the weekly...](../c-appendices/c-faq.md#section_AE27F63DD13F425B940C8E7D9ED5C614) 
* [How secure is my customer information on site search/merchandising?](../c-appendices/c-faq.md#section_5484CB954167412BB7F0480CB0C504B8) 
* [What about the privacy of my customer information?](../c-appendices/c-faq.md#section_8FB493F15E51454BA92A0C83E14C0CC7) 
* [Can I show my own banner ads on the search...](../c-appendices/c-faq.md#section_611EB8B32C16418386CB7DC7FB6954B8)

The following are common questions regarding search features:

* [Can I customize the search results for my site?](../c-appendices/c-faq.md#section_A64B3A621B794DF78D35ED06D9C43D0B) 
* [Can I see what customers are searching for on my...](../c-appendices/c-faq.md#section_73709E1B0E82478DA7B4D15B6C845F33) 
* [How can I control which content types (PDF, text, Flash, MP3 and Microsoft Office) are indexed and searched?](../c-appendices/c-faq.md#section_0AB8CB4B6BFA4286AA082055FEBFBE1C) 
* [Are dynamically generated web pages by way of ASP, JSP, PHP, CFM, or Perl-based content supported?](../c-appendices/c-faq.md#section_E279F004F1C542A2B9773B832E7B013F) 
* [How can I use synonyms to improve the search results...](../c-appendices/c-faq.md#section_E6E36E12514F4D7BAB01F8D1AB61D57B) 
* [Do I have control over the ordering of search results...](../c-appendices/c-faq.md#section_C6361048502745779D9749A842C4C370) 
* [Can I change the language of the search results page...](../c-appendices/c-faq.md#section_6EE41DA8241247D48BBEB061A50599C5) 
* [Can I have more than one site on my Adobe...](../c-appendices/c-faq.md#section_AFA8825182094660A71EEC84B8329D6D) 
* [Can I search more than one domain?](../c-appendices/c-faq.md#section_BFBB0E9861D942F095B56CF0A8F16596) 
* [Can I subdivide my site into separate sections so that...](../c-appendices/c-faq.md#section_52153A9DE9F9493B967A70583848B2A4) 
* [How do I exclude parts of my website from being...](../c-appendices/c-faq.md#section_D452EDE153654EF398F4A87780C6D43B) 
* [What character sets are supported?](../c-appendices/c-faq.md#section_A62A6F8F15804F968C77F2DEBDE8F8FD) 
* [What if I change or update my website?](../c-appendices/c-faq.md#section_489050E0EBC14D0594DBBAA0CCF4F6BA) 
* [Can my site be automatically indexed?](../c-appendices/c-faq.md#section_9C7D41636238488691ECDFEE4D4E5103) 
* [I use passwords on my website. Can I still use site search/merchandising?](../c-appendices/c-faq.md#section_4618EB5B66704640B5502D1B5CB4B32E) 
* [Do you support the crawling and indexing of https or...](../c-appendices/c-faq.md#section_D5BB8B8FBEA4405583E86B4AEC37151B) 
* [Does site search/merchandising honor the robots.txt file on my website?](../c-appendices/c-faq.md#section_73BBF6FE93C64C109F45CBC2FA394DB2) 
* [Certain portions of my website must be updated frequently so...](../c-appendices/c-faq.md#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3) 
* [Can I use scripts or programs to initiate an incremental...](../c-appendices/c-faq.md#section_0B6BB039557A42AA876D35D748E17DD0)

## Do I have to install any software to use site search/merchandising? {#section_02AB2AFF71984F9DAA3AF2B7C0847A22}

No. This is the primary advantage of site search/merchandising. The engine is a professional application hosted and maintained entirely on our high-performance servers. This makes the software easier to use than other search solutions. The only thing you have to do is add a small amount of HTML code to your pages so that customers to your website can enter searches. Site search/merchandising takes care of all the rest.

## What happens when my site exceeds the page limit? {#section_ECA5FA01032D4322BABA4E2C7FE498C1}

We keep serving your searches so your visitors can search your website without interruption. To see if your website exceeds the page limit, review your Full Index status or Live Log.

See [About Full Index](../c-about-index-menu/c-about-full-index.md#concept_C69BD21863FD4856B49326F35DB570D3).

See [Viewing the full index log of a live or staged...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

## How do I change the email address where the weekly reports are sent? {#section_AE27F63DD13F425B940C8E7D9ED5C614}

Weekly reports are sent to the owner of each active account. You can change the email address by clicking **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**. If you have more than one active search account, then all newsletters are sent to the new address.

See [Configuring your personal user information](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

## How secure is my customer information on site search/merchandising? {#section_5484CB954167412BB7F0480CB0C504B8}

Site search/merchandising is secure, fast, stable, and easy to use. You are not forced to use cookies (although you can if you want) to use our products, and sensitive information, such as passwords, are never put on any URL link that can be later retrieved from your browser.

## What about the privacy of my customer information? {#section_8FB493F15E51454BA92A0C83E14C0CC7}

Adobe is committed to honoring the privacy of their customers and visitors. See the Adobe [Privacy Center](https://www.adobe.com/privacy.html).

## Can I show my own banner ads on the search results pages? {#section_611EB8B32C16418386CB7DC7FB6954B8}

Yes. You control the appearance and the content of the search results. Within the search results template for your website, you can create links to your own banner exchange network such as LinkExchange or SmartClicks. Any hits made by your visitors are properly credited to your banner exchange account.

## Can I customize the search results for my site? {#section_A64B3A621B794DF78D35ED06D9C43D0B}

Yes. This is an exclusive feature of site search/merchandising. With our advanced template technology and a little knowledge of HTML, you can control exactly how the search results appear.

See [Search template tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

The transition between your own servers and site search/merchandising servers is completely seamless and invisible to your customers. If you do not know HTML or you do not have time to create a custom template, you can choose from an assortment of attractive, ready-to-use templates that Adobe's in-house team of professional web developers create.

## Can I see what customers are searching for on my site? {#section_73709E1B0E82478DA7B4D15B6C845F33}

Yes. We keep search statistics for searches made by visitors on your website over the last two months. You can review these statistics at any time under Reports on the product menu. Search reports give you vital information regarding exactly what visitors are looking for on your website. You can use this information to improve the design or to tune the site search/merchandising engine to better serve your visitors.

## How can I control which content types (PDF, text, Flash, MP3 and Microsoft Office) are indexed and searched? {#section_0AB8CB4B6BFA4286AA082055FEBFBE1C}

You can easily configure accounts to enable or disable the indexing and searching of text found within PDF documents, plain text documents, Flash movies, MP3 files, or Microsoft Office documents.

These settings are controlled on the [!DNL Staged Content Types] page.

See [About Content Types](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Are dynamically generated web pages by way of ASP, JSP, PHP, CFM, or Perl-based content supported? {#section_E279F004F1C542A2B9773B832E7B013F}

Static or dynamically generated HTML web pages are indexed, including pages built from databases, or any other back-end process. Because the HTML code that a browser sees is indexed, you can use site search/merchandising on websites as long as these back-end architectures results in HTML pages.

The search robot crawls your website by starting with the first page at the website address that is specified in [!DNL Account Settings], and follows links from page to page.

See [Configuring your account settings](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

When the search robot crawls and indexes all the pages of your website, then you can use the search engine to search your site. In other words, if dynamically generated documents are woven into your website with links from other pages, the search robot can still crawl and index the dynamic content.

After your website content is crawled and indexed, customers to your website can search for information within the indexed content.

## How can I use synonyms to improve the search results for my site? {#section_E6E36E12514F4D7BAB01F8D1AB61D57B}

You can use synonyms when you want visitors to find pages that are related to their search query.

For example, suppose that you have a page that contains a price list of products for sale on your site. However, after examining the search reports that are provided by site search/merchandising, you find that customers are looking for the word "cost," "expense," "charge," or "fee" in their searches. These words do not display your price list page in the search results. With the [!DNL Add Synonyms] feature in [!DNL Dictionaries], you can specify that these words are all synonyms, and your customer can find your price list, regardless of which search term they use.

See [About Dictionaries](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034).

## Do I have control over the ordering of search results? {#section_C6361048502745779D9749A842C4C370}

Yes. Using the advanced relevancy interface, you can control which pages are returned for a specific search query. This feature is useful if you want to be sure that customers see a specific page when they query for certain words.

See [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Can I change the language of the search results page? {#section_6EE41DA8241247D48BBEB061A50599C5}

Yes. The site search/merchandising template is flexible when it comes to letting you construct a results page that uses the language of your choice and matches the appearance of your website.

The template consists of a combination of text, standard HTML tags, and special tags that are defined to display the search results. When a customer performs a search, the search robot reads the template, outputs the text using standard HTML tags, and inserts the results links based on the special template tags.

See [Search template tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

If you want to change the results language, you can edit the English text that appears on the template.

See [Editing a presentation or a transport template](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).

## Can I have more than one site on my Adobe Customer Login? {#section_AFA8825182094660A71EEC84B8329D6D}

Yes. With a single Adobe Customer Login, you can manage a different search engine for many different websites. Select and manage accounts under "Accounts."

See [Selecting a different account to use](../c-about-accounts-menu.md#task_03C0FE918E2D44529CDC3B8DB75D1B26).

## Can I search more than one domain? {#section_BFBB0E9861D942F095B56CF0A8F16596}

Yes. You can configure access more than one domain by using [!DNL URL Entrypoints]. Provide URL entrypoints for additional domains that you own. Remember that you must have permission to index domains that you do not own.

See [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Can I subdivide my site into separate sections so that customers can search any of these areas individually or the whole site? {#section_52153A9DE9F9493B967A70583848B2A4}

Yes. A "Collections" feature is included that lets customers search specific areas of your website to quickly find what they are looking for.

See [About Collections](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127).

For example, customers can search a collection of URLs related to product sales information or a collection of URLs related to support services. You can set up collections so that your customers see a drop-down list of collections or a group of check boxes.

## How do I exclude parts of my website from being searched? {#section_D452EDE153654EF398F4A87780C6D43B}

Yes. Specify URL masks to determine which website pages you want to include or excluded from indexing. URL masks determine whether website pages appear in your search results.

See [About URL Masks](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

See [About URL Masks script](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

To prevent parts of individual web pages from being searched, you can exclude portions of a page from indexing. Surround the text with `<noindex>` and `</noindex>` tags. This method is useful if you want to exclude navigation text from searches.

## What character sets are supported? {#section_A62A6F8F15804F968C77F2DEBDE8F8FD}

Web pages typically specify the character set with a meta tag similar to the following:

`<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-1">`

The site search/merchandising engine properly indexes web pages using all of the common character sets in use on the Internet today. Some of the supported character sets include the following:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Arabic (ISO-8859-6) </p> </td> 
   <td colname="col2"> <p>Chinese (Traditional; Big5) </p> </td> 
   <td colname="col3"> <p>Japanese (Shift_JIS) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Arabic (Windows-1256) </p> </td> 
   <td colname="col2"> <p>Chinese (Traditional; EUC-TW) </p> </td> 
   <td colname="col3"> <p>Russian (KOI8-R) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Baltic (ISO-8859-4) </p> </td> 
   <td colname="col2"> <p>Cyrillic (ISO-8859-5) </p> </td> 
   <td colname="col3"> <p>Southern European (ISO-8859-3) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Baltic (Windows-1257) </p> </td> 
   <td colname="col2"> <p>Cyrillic (Windows-1251) </p> </td> 
   <td colname="col3"> <p>Turkish (ISO-8859-9) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Central European (ISO-8859-2) </p> </td> 
   <td colname="col2"> <p>Greek (ISO-8859-7) </p> </td> 
   <td colname="col3"> <p>Turkish (Windows-1254) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Central European (Windows-1250) </p> </td> 
   <td colname="col2"> <p>Greek (Windows-1253) </p> </td> 
   <td colname="col3"> <p>Unicode (UTF-8) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (ISO-2022-CN) </p> </td> 
   <td colname="col2"> <p>Hebrew (ISO-8859-8) </p> </td> 
   <td colname="col3"> <p>US-ASCII (us-ascii) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (ISO-2022-CN-EXT) </p> </td> 
   <td colname="col2"> <p>Hebrew (Windows-1255) </p> </td> 
   <td colname="col3"> <p>Western European (ISO-8859-1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (Simplified; EUC-CN) </p> </td> 
   <td colname="col2"> <p>Japanese (EUC-JP) </p> </td> 
   <td colname="col3"> <p>Western European (ISO-8859-15) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (Simplified; GB2312) </p> </td> 
   <td colname="col2"> <p>Japanese (ISO-2022-JP) </p> </td> 
   <td colname="col3"> <p>Western European (Windows-1252) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (Simplified; GBK) </p> </td> 
   <td colname="col2"> <p>Japanese (ISO-2022-JP-1) </p> </td> 
   <td colname="col3"> <p>Western European (x-mac-roman) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (Simplified; HZ-GB-2312) </p> </td> 
   <td colname="col2"> <p>Japanese (ISO-2022-JP-2) </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Contact Technical Support to ask about character sets that are not listed above.

## What if I change or update my website? {#section_489050E0EBC14D0594DBBAA0CCF4F6BA}

After you have changed the content of your website, you can perform either a full index or an incremental index. Site search/merchandising downloads and indexes any changed website content. After indexing is complete, your customers can search the new content. You can also schedule an automatic indexing of your site at a certain time and on a specific day.

See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

See [Setting the full index schedule for a live website](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

See [Setting the incremental index schedule for a live website](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Can my site be automatically indexed? {#section_9C7D41636238488691ECDFEE4D4E5103}

Yes. You can schedule an automatic index of your site every day.

Besides daily automatic indexing, you can choose to have frequently changed portions of their site incrementally indexed. On days that you have an automatic index scheduled, you can control the time of day the index takes place. Also, you can always manually initiate a site index whenever you want.

See [Setting the full index schedule for a live website](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

See [Setting the incremental index schedule for a live website](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## I use passwords on my website. Can I still use site search/merchandising? {#section_4618EB5B66704640B5502D1B5CB4B32E}

If you use HTTP Basic Authentication to password-protect certain portions of your website, you can specify realms and passwords that site search/merchandising can use to index your site.

See [Adding passwords for accessing areas of your website that require...](../c-about-settings-menu/c-about-crawling-menu.md#task_DED19D476FF04B48BB6456D5ECB8628A).

## Do you support the crawling and indexing of https or secure server content? {#section_D5BB8B8FBEA4405583E86B4AEC37151B}

Yes. You can crawl and index content on secure servers (https).

## Does site search/merchandising honor the robots.txt file on my website? {#section_73BBF6FE93C64C109F45CBC2FA394DB2}

Yes. The Robots Exclusion Protocol is compliant. The search robot examines the robots.txt file if it is present on your website. If your robots.txt file excludes all robots from crawling your site, the site search/merchandising robot is also excluded. To allow only the site search/merchandising robot to crawl your site, set the contents of your robots.txt file to the following:

```
User-agent: Atomz/1.0 
Disallow:
```

```
User-agent: * 
Disallow: /
```

You can learn more about web robots and the Robots Exclusion Protocol at the following:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

## Certain portions of my website must be updated frequently so that my customers get the most accurate search results. Does incremental indexing help with this issue? {#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3}

Yes. This scenario is what the incremental indexing feature was built to facilitate site search/merchandising. Incremental indexing's primary benefit is that it allows companies to frequently index dynamically changing portions of their website. Such functionality ensures that you are displaying search results with "up to the minute" accuracy.

See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

See [Setting the incremental index schedule for a live website](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Are dynamically generated web pages supported from a back-end database, such as product catalogs or inventory management systems? {#section_26896C556483457E879785E751583B16}

Static or dynamically generated HTML web pages, including pages built from databases, or any other back-end process are indexed. Because the HTML code, as viewed by a browser, is indexed, you can use site search/merchandising on websites as long as the back-end database information results in HTML pages.

The search robot crawls your website by starting with the first page at the website address that is specified in [!DNL Account Settings], and follows links from page to page.

See [Configuring your account settings](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

When the search robot crawls and indexes all the pages of your website, then you can use the search engine to search your site. In other words, if dynamically generated documents are woven into your website with links from other pages, the search robot can still crawl and index the dynamic database content.

After your website content is crawled and indexed, customers to your website can search for information within the indexed content.

You can easily enable full-content searching or a more narrow topic-based search restricted to information in the title, or the meta-description, or the meta-keywords document tags, or all three. Using metadata definitions, you can also create custom display fields, such as a product image, in the actual search results.

See [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Can I use scripts or programs to initiate an incremental index of my site? {#section_0B6BB039557A42AA876D35D748E17DD0}

Yes. You can use scripts or programs to initiate an incremental index of your website, as well as to ping the servers to index the site whenever content is changed or updated.

See [About Scripted Index](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D). 

## Feature implementations {#reference_2D0C4A80B8D64051BA9694D562DCE663}

A frequently asked questions page that discusses various feature implementations in [!DNL Search&amp;Promote].

<a id="section_EABF95A63E1A420080C1BECE1B1A7B0F"></a>

<!-- 

r_faq_implementation.xml

 -->

The following are common questions regarding feature implementations in [!DNL Search&amp;Promote] on a website:

* [Why are my business rules not running?](../c-appendices/c-faq.md#section_7FEB60383D8A4B11A60DFF9067274699) 
* [Why do I have problems scheduling indexing, errors starting indexing, and issues starting staged indexing?](../c-appendices/c-faq.md#section_E05758193DF5436784B0145839989F75) 
* [My index size limit exceeds my permitted boundary. Why is this happening and how do I fix it?](../c-appendices/c-faq.md#section_12E7DA979C4C4B1D8A3A6415FC3DDA70)

## Why are my business rules not running? {#section_7FEB60383D8A4B11A60DFF9067274699}

Configure business rules when banners appear, or to help decide what results appear and in what order. You can also configure the position of an item in your facet, and what template is used for a given search. 
Reorder business rules to change the order in which they run on presentation templates. Business rules run in the order that they were defined; that is, the higher a rule's order number, the later it runs in the process, trumping earlier rules. You reorder rules by entering a new number in the Order column of the table on the Business Rules page.

See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Why do I have problems scheduling indexing, errors starting indexing, and issues starting staged indexing? {#section_E05758193DF5436784B0145839989F75}

When you generate an index, whether it is full or incremental, index crawl status information is displayed in real-time. For example, you can view the start time, elapsed time, and any errors that have occurred during the indexing process. Information about the status of your last index is also displayed. Use this information to troubleshoot any indexing errors you encounter.

For scheduling an index, see [Setting the full index schedule for a live website](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0) and [Setting the incremental index schedule for a live website](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

For starting a staged index, see [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D) or [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## My index size limit exceeds my permitted boundary. Why is this happening and how do I fix it? {#section_12E7DA979C4C4B1D8A3A6415FC3DDA70}

A web site can tend to grow and over time Search&amp;Promote "discovers" more documents and web pages that were added. Eventually, your account may exceed your indexing size limit, In such cases, you can consider using **[!UICONTROL URL Mask]**. This feature hides docs and web pages from index crawling that you do not want or do not need to have indexed, thereby reducing your index size. Another option may be to contact Technical Support to have your indexing size limit set larger in your account.

See [About URL Masks](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

If you are unsure what to do, you should contact Technical Support. There may be many other variables affecting your index size that, if adjusted, may also affect the billing of your account.

## International {#reference_F017C2968BFB446499EF1D3CE2CAC0FE}

A frequently asked questions page that discusses support of the indexing and searching of more than 19 languages, including multi-byte Asian languages such as Chinese (Simplified and Traditional), Japanese, and Korean.

<a id="section_48FB87B40FC241879AE0C3AF63429325"></a>

<!-- 

r_faq_international.xml

 -->

The following are common questions regarding languages and character sets:

* [What controls the character set encoding of the search query...](../c-appendices/c-faq.md#section_DF2E8570AFC2480FA199FD26C941A22F) 
* [Are only pages searched whose encoding matches the encoding of...](../c-appendices/c-faq.md#section_9E544F3DB7DE41618DC1BC8224B32C5A) 
* [What encoding is used for the search results page?](../c-appendices/c-faq.md#section_DA68670F35D54EAABF7DBB010F4409BF) 
* [Can I use site search/merchandising on Unicode, UTF-8, encoded pages?](../c-appendices/c-faq.md#section_130997CB08934A13A5261D85CF88040C) 
* [How come I cannot search the Chinese, Japanese, or Korean PDF files on my website?](../c-appendices/c-faq.md#section_539AFF482F814D28B5929F683D2F2175) 
* [How come I cannot search the Chinese, Japanese, or Korean SWF files on my website?](../c-appendices/c-faq.md#section_9C0849528AFF4C10AA97A2C912992638) 
* [How come I cannot search the Chinese, Japanese, or Korean Microsoft Office files on my website?](../c-appendices/c-faq.md#section_6764BA6863AF492EBA9BE5CCC12CDD1F) 
* [How come I cannot search the Chinese, Japanese, or Korean MP3 files on my website?](../c-appendices/c-faq.md#section_DB6D60CF46F94125BF4E54AF3036DBFC) 
* [Do I need to do anything special to get the...](../c-appendices/c-faq.md#section_A8BA6DDD3A6048319D3530BCFD6DA1A5) 
* [How come Chinese, Japanese, or Korean fonts appear in search results under Netscape 4.7 and earlier?](../c-appendices/c-faq.md#section_DF42567063304F918D406AC76529DFB7)

## What controls the character set encoding of the search query? {#section_DF2E8570AFC2480FA199FD26C941A22F}

The "Web Forms" section of your Search account contains sample search forms that you use to add search functionality to your website. If you look this search forms code, you can find a line similar to the following:

`<input type=hidden name="sp_f" value="iso-8859-1">`

This line of code tells the search engine that the incoming query is encoded in iso-8859-1, a common encoding for Western European languages. You can change this setting by going to the product menu and clicking **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**. On the [!DNL Personal Information] page, in the **[!UICONTROL Character Encoding]** drop-list, select a new encoding.

See [Configuring your personal user information](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

You can also manually change the encoding value on your web pages by editing the `sp_f` line of the search form. Remember that the `sp_f` value of the search form must match the character set encoding of the page in which it appears.

## Are only pages searched whose encoding matches the encoding of the search query? {#section_9E544F3DB7DE41618DC1BC8224B32C5A}

By default, no. As long as your website pages correctly identify their character set encoding, the necessary conversions are made between the encoding of the search query and that of the pages, even when pages use multiple encodings.

## What encoding is used for the search results page? {#section_DA68670F35D54EAABF7DBB010F4409BF}

The character set encoding of your account determines the default encoding for your results template.

See [Configuring your personal user information](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

You can learn more about specifying a character set in an HTML template.

See [Search template tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## Can I use site search/merchandising on Unicode, UTF-8, encoded pages? {#section_130997CB08934A13A5261D85CF88040C}

Yes. However, Unicode character sets, such as UTF-8, do not provide enough information to determine the language that the pages are written in. To correctly search these pages, it is necessary to specify the language. To determine the document language, information is processed in the following order:

* Content-Language HTTP header delivered for the document by your server. 
* META elements (for example, `META HTTP-EQUIV="Content-Language" Content="ja_JP"`) in the `<HEAD>` section of the document. 

* LANG attribute of the `<HTML>` tag (for example, `<HTML LANG="ja_JP">`).

If your server is not configured to deliver the Content-Language HTTP header, and your documents contain neither the language META element, nor the language attribute for the `<HTML>` tag, you can use metadata injections to specify the appropriate language.

See [Adding field injection definitions](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## How come I cannot search the Chinese, Japanese, or Korean PDF files on my website? {#section_539AFF482F814D28B5929F683D2F2175}

Site search/merchandising obtains UTF-8 from Adobe PDF files with no indication of language. If you selected **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), you must use metadata injections to specify the language that is used in the PDF file.

See [Adding field injection definitions](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## How come I cannot search the Chinese, Japanese, or Korean SWF files on my website? {#section_9C0849528AFF4C10AA97A2C912992638}

Site search/merchandising obtains UTF-8 from Adobe Flash movie files that were created with Adobe Flash with no indication of language. If you selected the content type **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), you must use metadata injections to specify the language that is used in the SWF file.

For Flash version 4 or older versions of SWF files, the character set of the characters in the file is not specified. If you selected the content type **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), you must use metadata injections to specify the character set that is used in the SWF file.

See [Adding field injection definitions](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## How come I cannot search the Chinese, Japanese, or Korean Microsoft Office files on my website? {#section_6764BA6863AF492EBA9BE5CCC12CDD1F}

Site search/merchandising obtains UTF-8 from Microsoft Office files (Microsoft Word, Microsoft Excel, and Microsoft PowerPoint) with no indication of language. If you selected the content type **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), you must use metadata injections to specify the language used in the Microsoft Office files.

See [Adding field injection definitions](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## How come I cannot search the Chinese, Japanese, or Korean MP3 files on my website? {#section_DB6D60CF46F94125BF4E54AF3036DBFC}

If you select the content type **[!UICONTROL Text in MP3 Music Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), you must use metadata injections to specify the character set that is used to encode the MP3 files.

See [Adding field injection definitions](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Do I need to do anything special to get the .txt files on my website to index correctly? {#section_A8BA6DDD3A6048319D3530BCFD6DA1A5}

If you selected the content type **[!UICONTROL Text Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), you must use metadata injections to specify the character set used to encode the .txt files.

See [Adding field injection definitions](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## How come Chinese, Japanese, or Korean fonts appear in search results under Netscape 4.7 and earlier? {#section_DF42567063304F918D406AC76529DFB7}

If your account uses the default template, one of the ready-to-use templates, or a template based on any of those templates, it may contain font tags that specify Arial or Helvetica as font faces. For example, `<font face="arial, helvetica" size="+1">`. Netscape 4.7 and earlier does not display Chinese, Japanese, or Korean characters when the Arial or Helvetica font face is used. Remove the `face` attribute or replace the font face with one that is more appropriate for Chinese, Japanese, or Korean. 

## Low page count {#reference_4344E3E3CB2948939860F8C078BD7773}

A frequently asked questions page that discusses common problems associated with a low indexing page count.

<a id="section_2F4B95651C6F41BE888DC85D95A39974"></a>

<!-- 

r_faq_low_page_count.xml

 -->

The following are common questions regarding low indexing page counts:

* [Have you examined your index log?](../c-appendices/c-faq.md#section_D6626536DC3D40DDA4A1224F1CB276BF) 
* [Do you have typing mistakes in your URL?](../c-appendices/c-faq.md#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676) 
* [Does the entrypoint web page have links to other pages...](../c-appendices/c-faq.md#section_1C2D6ED54E7249268B555D9DC33352B3) 
* [Are links to other pages on your website embedded in...](../c-appendices/c-faq.md#section_EE34A67D60A844EBB0921C03544FF63E) 
* [Are the HTML tags on your web page in an...](../c-appendices/c-faq.md#section_F31A2F5D2C284AC084158A5BD763DC5D) 
* [Do you have improperly formed HTML comment tags in your...](../c-appendices/c-faq.md#section_D1C39D79341845CB9C38579AABDF3A24) 
* [Does your web page contain links to pages on another...](../c-appendices/c-faq.md#section_F8082759184049AAA8FA6342C1F84389) 
* [Are you using a virtual domain service for your URL...](../c-appendices/c-faq.md#section_2861F09EA21A45E6B7E15F032739CDF3) 
* [Does your web page use a meta refresh tag?](../c-appendices/c-faq.md#section_5A2F544C237C49B8B1A7FE0C45371C0D) 
* [Does your web page use a meta robots tag?](../c-appendices/c-faq.md#section_36275A33DDFE4620BABA948F8A63DBD2) 
* [Does your website use a robots exclusion file?](../c-appendices/c-faq.md#section_BF7B663347814F58AD736066C86B7D25)

## Have you examined your index log? {#section_D6626536DC3D40DDA4A1224F1CB276BF}

The index log contains detailed information that the site search/merchandising robot collects as it indexes your website. The log includes a list of links crawled and errors encountered. Examining the index log is the best place to start to determine why all the pages on your website are not indexed.

See [Viewing the full index log of a live or staged...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

See [Viewing the incremental index log of a live or staged...](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

## Do you have typing mistakes in your URL? {#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676}

When you type lengthy URLs into HTML forms, it can introduce one or more typographical errors. Remember that URLs should not contain any spaces. Also, be aware that some web servers handle URLs in a case-sensitive manner.

On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. On the [!DNL Staged URL Entrypoints] page, verify the following:

* You do not have any typographical errors in your URLs. 
* The characters in the URLs are all using the correct casing. 
* There are no space characters in the URLs.

To test your URL entrypoints, copy and paste a URL into a web browser to see if your website appears. If it does not appear, check again to ensure that you have not made any mistakes in your URL path.

See [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Does the entrypoint web page have links to other pages on your website? {#section_1C2D6ED54E7249268B555D9DC33352B3}

The site search/merchandising robot crawls your website just like your customer do; by following links from page to page. Links must be present in the entrypoint web page before the search robot can find and index other pages on your site.

See [Adding multiple URL entry points that you want indexed](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Are links to other pages on your website embedded in JavaScript? {#section_EE34A67D60A844EBB0921C03544FF63E}

You can use sophisticated navigation techniques on your website, such as roll-over actions and menus, that use JavaScript to link to other pages. However, the site search/merchandising robot cannot follow links embedded in JavaScript.

One solution you can use to overcome this issue is to place hidden links to other pages in the HTML that contains the JavaScript. Although customers to your website do not see these links, the search robot still finds and crawls them. You can place hidden tags at the bottom of the page just before the `</body>` tag. They might look like the following:

```
<a href="/mydir/mypag1.html"></a> 
<a href="/mydir/mypag2.html"></a>
```

Another solution is to list the URLs of the additional pages on your website as entrypoints to crawl and index. Begin the URLs with `https://` as shown in the following:

```
https://www.mydomain.com/mydir/mypag1.html 
https://www.mydomain.com/mydir/mypag2.html
```

See [Adding multiple URL entry points that you want indexed](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Are the HTML tags on your web page in an invalid sequence? {#section_F31A2F5D2C284AC084158A5BD763DC5D}

The HTML specification requires that the `<html>`, `<head>`, and `<body>` tags follow a specific sequence in an HTML document. Tags in all your web pages must have the following sequence:

```
<html> 
<head> 
...  
<i>head tags go here</i> ... 
</head> 
<body> 
...  
<i>body tags go here</i> ... 
</body> 
</html>
```

If the HTML tags are not in proper order the site search/merchandising robot is unable to properly parse and index your web page. The following is an example of tags that are not in the right sequence:

```
<body> 
<head> 
...  
<i>head tags are here</i> ... 
</head> 
...  
<i>body tags are here</i> ... 
</body>
```

In such case, place the `<html>`, `<head>`, and `<body>` tags into the proper sequence on your web page.

## Do you have improperly formed HTML comment tags in your web page? {#section_D1C39D79341845CB9C38579AABDF3A24}

Be sure that you carefully review and correct any invalid HTML comments in your web pages.

The HTML specification requires that an HTML comment begin with the characters `<!--` and end with the characters `-->`. It is easy to overlook incorrectly formatted comments that cause the site search/merchandising robot to improperly parse the tags on your web page. An improperly formed comment can cause the site search/merchandising robot to miss other important tags that must be parsed. Be mindful of comments just before the `<body>` tag in your web page.

The following is an example of a properly formed comment:

`<!-- This HTML comment is OK. -->`

The following is an example of an improperly formed comments:

```
<!- This HTML comment is improperly formed. -> 
<! This HTML comment is also improperly formed. >
```

## Does your web page contain links to pages on another domain? {#section_F8082759184049AAA8FA6342C1F84389}

Often a website can consist of pages that actually exist on a web server with a different domain address. For example, if your main website address is the following:

`https://www.mydomain.com/`

Your website may also have pages on another domain such as the following:

`https://www.otherdomain.com/`

By default, the site search/merchandising robot does not follow links on a domain other than the main one. However, by setting additional entrypoints for your search account, you can easily index multiple domains.

On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Add the "main website entrypoint" URL of your site. Then, add additional URL entrypoints to any other domains that contain site pages. For example, you would set your main URL entrypoint to:

`https://www.mydomain.com/`

and add the following additional site URL entrypoint:

`https://www.otherdomain.com/`

## Are you using a virtual domain service for your URL? {#section_2861F09EA21A45E6B7E15F032739CDF3}

You might be using a virtual domain service (sometimes called a "domain redirection service") to provide a better URL for customers to get to your website. For example, suppose the real address of your website is the following:

`https://www.myispdomain.com/~myname/mywebpages/`

However, you use a virtual domain service so customers can get to your site at following addresses:

`https://myname.adomain.com/`

or

`https://adomain.com/myname/`

By default, the site search/merchandising robot does not follow links on a domain other than the main one. However, by setting additional entrypoints for your search account, you can easily index multiple domains.

On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Add the "main website URL entrypoint" to the virtual domain name of your site. Then, add additional entrypoints to the domain where your website actually lives.

For example, you would set your main URL entrypoint to the following:

`https://myname.adomain.com/`

And add the following additional website URL entrypoint:

`https://www.myispdomain.com/~myname/mywebpages/`

## Does your web page use a meta refresh tag? {#section_5A2F544C237C49B8B1A7FE0C45371C0D}

Many websites have a front page that includes a meta refresh tag between the `<head>...</head>` tags similar to the following:

`<meta http-equiv="Refresh" content="0;URL=https://www.adomain.com/apath/afile.html">`

Under certain circumstances, the site search/merchandising robot is unable to follow the meta refresh URL to index the content of your website. This issue is easy to work around by setting additional entrypoints.

On the product menu, click **[!UICONTROL Settings]** > Crawling > **[!UICONTROL URL Entrypoints]**. Add another entrypoint to the URL of the meta refresh tag.

## Does your web page use a meta robots tag? {#section_36275A33DDFE4620BABA948F8A63DBD2}

Sometimes web pages use meta robots tags to control web robots that periodically attempt to crawl a website. Meta robots tags appear between the `<head>...</head>` tags of a web page and look similar to the following tag:

`<meta name="robots" content="noindex, nofollow">`

Because the site search/merchandising robot is itself a web robot, it follows the directions of the meta robots tag. By excluding other robots in this manner you also exclude the site search/merchandising robot.

You can learn more about web robots and the Robots Exclusion Protocol at the following:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

Remove or modify the meta robots tag on the web pages that you want indexed on your website.

## Does your website use a robots exclusion file? {#section_BF7B663347814F58AD736066C86B7D25}

Sometimes a website has a page called robots.txt that excludes all or certain robots from crawling it. To see if your website has a robots.txt file, look for it just under the top-level domain as shown in the following:

`https://www.yourdomain.com/robots.txt`

The contents of the robots.txt file looks similar to the following text:

```
User-agent: * 
Disallow: /
```

Because the site search/merchandising robot is itself a web robot, it follows the directions in the robots.txt file-it excludes the site search/merchandising robot. To work around this issue, edit the robots exclusion file (robots.txt) to permit the site search/merchandising robot to crawl and index your website as follows:

```
User-agent: Atomz/1.0 
Disallow: 
 
User-agent: * 
Disallow: /
```

## Microsoft Office {#reference_A85FCC8A96514A7584F4D2A8AC8111D1}

A frequently asked questions page that discusses support of the indexing and searching of Microsoft® Office files on a website.

<a id="section_A59C82699DB84747B2364FA4FE7EF042"></a>

<!-- 

r_faq_microsoft_office.xml

 -->

The following are common questions regarding Microsoft Office files:

* [What gets indexed in a Microsoft Office file?](../c-appendices/c-faq.md#section_8681DADFCFE24B7787B1FC08D431EE28) 
* [What does not get indexed in a Microsoft Office file...](../c-appendices/c-faq.md#section_BD53BDABFDD94D7EB0E1F55EC18017BB) 
* [How are Microsoft Office files indexed differently from HTML pages...](../c-appendices/c-faq.md#section_C104B44684F340549A6B9EB8F39EDDBB) 
* [How do I prevent Microsoft Office files from being indexed...](../c-appendices/c-faq.md#section_FEBA71274CD14CB99731ADF982087F4C)

## What gets indexed in a Microsoft Office file? {#section_8681DADFCFE24B7787B1FC08D431EE28}

The full content of Microsoft Word files, Microsoft Excel files, and Microsoft PowerPoint files are indexed.

The following parts of a Microsoft Word file are indexed:

* Title 
* Keywords 
* Subject (Description) 
* Text-based content 
* Hyperlinks to other documents

The following parts of a Microsoft Excel file are indexed:

* Title 
* Keywords 
* Subject (Description) 
* Text in cells 
* Values from numeric formulas in cells

The following parts of a Microsoft PowerPoint file are indexed:

* Title 
* Keywords 
* Subject (Description) 
* Text on each slide

## What does not get indexed in a Microsoft Office file? {#section_BD53BDABFDD94D7EB0E1F55EC18017BB}

Graphics that are contained in Microsoft Office files, or any text that is part of a contained graphic are not indexed. Custom property definitions are not indexed as metadata. Some text in special fields, such as headers and footers in a PowerPoint file, are also not indexed.

## How are Microsoft Office files indexed differently from HTML pages? {#section_C104B44684F340549A6B9EB8F39EDDBB}

The difference between how the search robot indexes Microsoft Office files and HTML files is that each HTML file is an individual page and a single Microsoft Office file can represent hundreds of pages. For this reason, each page is counted within a Microsoft Office file as a separate page under your search account.

## How do I prevent Microsoft Office files from being indexed on my website? {#section_FEBA71274CD14CB99731ADF982087F4C}

If you do not want the search robot to crawl and index Microsoft Office files, deselect the content type **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

You can also use [!DNL URL Masks] to disable the indexing of Microsoft Office files.

Enter the following URL masks:  

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>If you are not using regular expressions </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DFEC911DA11C484C8E4671A0F00E1F88"> 
     <li id="li_2E50374E3869426B97353A5A8CBE09EC">exclude *.doc </li> 
     <li id="li_9089D11161524D90849CA88F703772B6">exclude *.xls </li> 
     <li id="li_7F6CFC6212E64C04AAF38E21A667C763">exclude *.ppt </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>If you are using regular expressions </p> </td> 
   <td colname="col2"> 
    <ul id="ul_012A45C3EC04460EA09C0ECFB49A8FA9"> 
     <li id="li_0C239F0A536D465F85A98EBF7B6ADF27">exclude regexp ^.*\.doc$ </li> 
     <li id="li_9F91DA35A2A646ACAFF2BA37F9136E2A">exclude regexp ^.*\.xls$ </li> 
     <li id="li_9D768D9EA2DB44FBB00A1979E21672E2">exclude regexp ^.*\.ppt$ </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

See [Adding URL masks to index or not index parts of...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A). 

## MP3 {#reference_7614250EE81C4EEFA43E57A6A74E83D7}

A frequently asked questions page that discusses support of the indexing and searching of MP3 music files on a website.

<a id="section_8BF68DE0215B4981A0BA10DD17298458"></a>

<!-- 

r_faq_mp3.xml

 -->

The following are common questions regarding MP3 files.

* [When is an MP3 file crawled and indexed?](../c-appendices/c-faq.md#section_538EA1682C9C47E3A62640BB25D84C36) 
* [What do I have to do to crawl and index...](../c-appendices/c-faq.md#section_3CD794446E3545379C14E9F222118665) 
* [How is an MP3 file recognized?](../c-appendices/c-faq.md#section_230E7336965A424F96C5CCF1D3C2D103) 
* [What is indexed in an MP3 file?](../c-appendices/c-faq.md#section_E99D252B27CA4946AED3FCD3ABD8779D) 
* [Does an MP3 file count as a page?](../c-appendices/c-faq.md#section_9910BEB6617D4D2090558CDF6C65D16B) 
* [How do I prevent the indexing of individual MP3 files...](../c-appendices/c-faq.md#section_C989DC1D3D3841B38F683A462195DC05) 
* [How do I prevent MP3 files from being indexed?](../c-appendices/c-faq.md#section_305D2B28D1124776B6DC0C62A17827C6) 
* [Why can't I search the Chinese, Japanese, or Korean MP3 files on my site?](../c-appendices/c-faq.md#section_06A48DA3F9E742CC93CC8B5CCD7382FA)

## When is an MP3 file crawled and indexed? {#section_538EA1682C9C47E3A62640BB25D84C36}

MP3 files are crawled and index in one of two ways. The most common way is from an anchor href tag in an HTML file:

`<a href="MP3-file-URL"></a>`

A second way is to enter the URL of the MP3 file as a URL entrypoint.

See [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## What do I have to do to crawl and index the MP3 files on my site? {#section_3CD794446E3545379C14E9F222118665}

To activate MP3 crawling and indexing for your account, on the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**. On the [!DNL Staged Content Types] page, select **[!UICONTROL Text in MP3 Music Files]**.

See [About Content Types](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## How is an MP3 file recognized? {#section_230E7336965A424F96C5CCF1D3C2D103}

An MP3 file is recognized by its MIME type which is "audio/mpeg".

## What is indexed in an MP3 file? {#section_E99D252B27CA4946AED3FCD3ABD8779D}

MP3 files optionally store a small amount of textual information. That information can include the album name, artist name, song title, song genre, year of release, and a comment. This information is stored at the very end of the file in what is called the TAG. MP3 files that contain TAG information are indexed by in the following way:

* The song title is treated like the title of an HTML page. 
* The comment is treated like a description defined for an HTML page. 
* The genre is treated like a keyword defined for an HTML page. 
* The artist name, album name, and year of release is treated like the body of an HTML document.

## Does an MP3 file count as a page? {#section_9910BEB6617D4D2090558CDF6C65D16B}

Yes, each MP3 file that is crawled and indexed on your website is counted as one page.

## How do I prevent the indexing of individual MP3 files? {#section_C989DC1D3D3841B38F683A462195DC05}

Surround the anchor tags that link to the MP3 files with `<nofollow>` and `</nofollow>` tags. The search robot does not follow links between those tags.

Another method is to add the URLs of the MP3 files as exclude masks.

See [About URL Masks](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

See [About URL Masks script](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

## How do I prevent MP3 files from being indexed? {#section_305D2B28D1124776B6DC0C62A17827C6}

The easiest way to control MP3 indexing for your account is by deselecting **[!UICONTROL Text in MP3 Music Files]** on the [!DNL Staged Content Types] page.

See [Selecting content types to crawl and index](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

You can also use the URL Masks feature to disable MP3 indexing by file extension. To do this, on the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. Enter one of the following masks:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>If your account... </p> </th> 
   <th colname="col2" class="entry"> <p>Enter the following URL mask </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Does not use regular expressions </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exclude *.mp3 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uses regular expressions </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exclude regexp ^.*\.mp3$ </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Why can't I search the Chinese, Japanese, or Korean MP3 files on my site? {#section_06A48DA3F9E742CC93CC8B5CCD7382FA}

To search Chinese, Japanese, or Korean MP3 files, on the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** > **[!UICONTROL Text in MP3 Music Files]**. Then, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**, and specify the character set that is used to encode the MP3 files.

See [Selecting content types to crawl and index](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

See [About Injections](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5). 

## PDF {#reference_F127C4915A0D436DA34E5D75ABFBB21B}

A frequently asked questions page the discusses support of the indexing and searching of PDF files on a website.

<a id="section_B57108860F7A41B98B49E884028C8868"></a>

<!-- 

r_faq_pdf.xml

 -->

The following are common questions regarding PDF files:

* [What gets indexed in a PDF file?](../c-appendices/c-faq.md#section_62BFCD7158B44F2BB3B1864224B50174) 
* [What does not get indexed in a PDF file?](../c-appendices/c-faq.md#section_A14B353AE503408896BACBBF3F748FA0) 
* [How are indexed PDF files counted?](../c-appendices/c-faq.md#section_C35DE36A65D649BD8FF314E9EFD990A6) 
* [Can the search results display a PDF icon?](../c-appendices/c-faq.md#section_829CE82CC3544502A13D27C4DB820189) 
* [Can the search results link to a particular page in...](../c-appendices/c-faq.md#section_A06E7F7017E6441E98209D288EE57BF6) 
* [How do I prevent PDF files from being indexed on...](../c-appendices/c-faq.md#section_96671419A822486AAC654D8DAD819940) 
* [How come I cannot search the Chinese, Japanese, or Korean PDF files on my website?](../c-appendices/c-faq.md#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8)

## What gets indexed in a PDF file? {#section_62BFCD7158B44F2BB3B1864224B50174}

The full content of PDF files are indexed. The following parts of a PDF file are indexed:

* Title 
* Keywords 
* Subject (Description) 
* Text-based content

## What does not get indexed in a PDF file? {#section_A14B353AE503408896BACBBF3F748FA0}

The PDF table of contents, any graphics within the file, or any text that is part of a contained graphic are not indexed.

## How are indexed PDF files counted? {#section_C35DE36A65D649BD8FF314E9EFD990A6}

Each PDF file is counted, including PDFs that contain multiple pages, as a single document.

## Can the search results display a PDF icon? {#section_829CE82CC3544502A13D27C4DB820189}

Yes. Use the `<search-if-link-extension>` tag within your template to include a PDF icon, or other graphics or text, in the search results:

```
<search-results> 
  ... 
  <search-if-link-extension value=".pdf"> 
    <img src="/search/i/pdficon.gif"> 
  </search-if-link-extension> 
  ... 
</search-results>
```

PDF icons help your customers know that a search result links to a PDF file that might be very large. File size may matter to customers who are accessing your website over a modem or on a mobile device.

## Can the search results link to a particular page in a PDF file? {#section_A06E7F7017E6441E98209D288EE57BF6}

Yes. Using the smart links template tag ( `<search-smart-link>...</search-smart-link>`), customers can click to open the first PDF page that contains the search result.

To use smart links, replace the `<search-link>...</search-link>` tags in the search results section of your template with `<search-smart-link>...</search-smart-link>` tags. When a customer clicks a link that the smart-link tags generate, they go to the first PDF page relevant to their search query.

>[!NOTE]
>
>To use this feature, the customer must use a recent version of the Adobe Acrobat, or Adobe Acrobat Reader, which must include the highlight plug-in and the External Window Handler (EWH) plug-in. In addition, their web browser must use the Adobe Acrobat plug-in for Netscape Navigator (you can use any browser that accepts this Netscape Navigator plug-in) or the Acrobat ActiveX control for Internet Explorer 4.0 and later.

See [Search template tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## How do I prevent PDF files from being indexed on my website? {#section_96671419A822486AAC654D8DAD819940}

If you do not want the search robot to crawl and index PDF files, deselect the content type **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

You can also choose to use [!DNL URL Masks] to disable PDF indexing.

See [Adding URL masks to index or not index parts of...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

To disable PDF indexing, enter one of the following URL masks:

* `exclude *.pdf` (if you are not using regular expressions) 
* `exclude regexp ^.*\.pdf$` (if you are using regular expressions)

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## How come I cannot search the Chinese, Japanese, or Korean PDF files on my website? {#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8}

Site search/merchandising obtains UTF-8 from PDF files with no indication of language. If you selected the content type **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**), you must use metadata injections to specify the language that is used in the PDF file.

See [Adding field injection definitions](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE). 

## Too many pages {#reference_48A748BC1ED14844ACAC2735C8388E8A}

A frequently asked questions page that explains some of the reasons why the indexer has counted more pages than you actually have, and what the solution is in each case.

<a id="section_ADEF7169D7DA4754B8BD5CFCCB05C2DF"></a>

<!-- 

r_faq_too_many_pages.xml

 -->

If you are certain your website is below your page limit, but the indexer is telling you that the limit is reached, you should review these common questions and answers for possible solutions.

* [Have you examined your various index logs?](../c-appendices/c-faq.md#section_C929BF9FDA6B4C9A9078C45AFE80EFE8) 
* [Are CGI programs being indexed on your website?](../c-appendices/c-faq.md#section_86ED8A641B3841EC80153B4F107548FD) 
* [Does your server have directory browsing enabled?](../c-appendices/c-faq.md#section_073C88EEE74F4CA0AD2C7145D4810B22) 
* [Are there forums or newsgroups on your website?](../c-appendices/c-faq.md#section_8DCB94F0850A41B9B2EA885F779E2F84) 
* [Are there PDF or Microsoft Office files on your website...](../c-appendices/c-faq.md#section_455FC5438DF74E68AB9A31D359EAD4D9) 
* [Do you have multiple URL entrypoints?](../c-appendices/c-faq.md#section_8C54AFD7DF56472A9364D516482B534C) 
* [Have you exceeded the internal bytes or time limits of...](../c-appendices/c-faq.md#section_AE1BE61A58864FFE81F0BCEED2EBB15D)

## Have you examined your various index logs? {#section_C929BF9FDA6B4C9A9078C45AFE80EFE8}

The index log contains detailed information collected by the site search/merchandising robot as it indexes your website. The log includes a list of all crawled links and encountered errors. Examining the index log is the best place to start when you are trying to determine which pages are getting indexed.

See [Viewing the full index log of a live or staged...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

See [Viewing the incremental index log of a live or staged...](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

See [Viewing the scripted incremental index log of a live or...](../c-about-index-menu/c-about-scripted-index.md#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7).

See [Viewing the regenerated index log of a live or staged...](../c-about-index-menu/c-about-regenerate-index.md#task_61CE8F9E7BF84BA89A8D482B2106BB15).

See [Viewing the re-ranked index log of a live or staged website](../c-about-index-menu/c-about-re-rank-index.md#task_3C76107DFAC1495FACD3ABB0A688208D).

## Are CGI programs being indexed on your website? {#section_86ED8A641B3841EC80153B4F107548FD}

CGI programs use URL parameters that sometimes cause the indexer to crawl multiple "fake" URLs. If site search/merchandising is reading your CGI programs and following URLs with CGI parameters in them, there are probably several multiples of pages being crawled and indexed that are not useful for your search index. Typical CGI parameters appear in URLs with `?` or `&` characters.

You can mask the CGI programs from being indexed using the URL Masks feature. You can mask a URL prefix or use regular expressions to mask your CGI scripts.

See [About URL Masks](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

See [About URL Masks script](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Does your server have directory browsing enabled? {#section_073C88EEE74F4CA0AD2C7145D4810B22}

When a web server has directory browsing enabled and there is no index.html file present in a given directory, a visit to that directory can show the listing of files in that directory. Usually, there are links at the top of the page to let you sort the list in different ways just by clicking **[!UICONTROL Name]**, **[!UICONTROL Last modified]**, **[!UICONTROL Size]**, and so on. Typically, these appear in the site search/merchandising index log as URLs with characters such as `?M=A` at the end. The site search/merchandising indexer follows these as links, and this can lead to indexing multiple "fake" URLs.

Typically, a well-designed website either has index files located in every directory, or it has directory browsing disabled for those directories without index files. Fortunately, there is an easy way to mask these "fake" URLs if you are unable to change your pages or disable directory listings on the server side.

To accomplish this task, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. Add a mask to mask any URL that contains the character `?`. You can do this task by entering the following regular expression mask:

`exclude regexp ^.*\?.*$`

After you have created the mask, be sure that you reindex your website.

See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Are there forums or newsgroups on your website? {#section_8DCB94F0850A41B9B2EA885F779E2F84}

If forums or newsgroups are being crawled on your website, it might be following URLs for different display options or sort options. This behavior means that the same page is indexed multiple times.

Typically, forums or newsgroups come with their own search engines. In such case, you can use [!DNL URL Masks] to mask the forums from site search/merchandising.

On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. On the [!DNL Staged URL Masks] page, mask your forums by entering their URLs as exclude URL masks.

See [Adding URL masks to index or not index parts of...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

After you have created the masks, be sure that you re-index your website.

See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Are there PDF or Microsoft Office files on your website? {#section_455FC5438DF74E68AB9A31D359EAD4D9}

If you have PDF files or [!DNL Microsoft Office] files on your website, you might notice that the index size of only a few files counts many pages. The reason there are more pages getting indexed than documents you have is because each page in a PDF or Microsoft Office file is counted as a separate page.

On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**. On the [!DNL Full Index] page, select **[!UICONTROL Count All Pages]**, and then click **[!UICONTROL Full Index Now]** to see a total page count. If you do not want PDF files or Microsoft Office files indexed, you can disable this content type under **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**.

See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

See [About Content Types](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Do you have multiple URL entrypoints? {#section_8C54AFD7DF56472A9364D516482B534C}

The site search/merchandising robot begins crawling at specified URL entrypoints and follows all found links to all content in that particular domain. If you have specified many URL entrypoints, a significant number of pages may be crawled.

Use the Robots Exclusion Protocol's `nofollow` tag in the headers of the entrypoint documents on the additional domains as follows:

```
<html> 
<head> 
<meta name="robots" content="nofollow"> 
</head>
```

The code above tells the site search/merchandising robot to index the contents of the page, but not to follow the links to additional pages.

You can learn more about web robots and the Robots Exclusion Protocol at the following:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

If you do not have access to the source of the pages on additional domains, you can remove the multiple URL entrypoints. Doing so helps you to limit indexing activity only to those domains whose content you want customers to be able to search.

See [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Have you exceeded the internal bytes or time limits of site search/merchandising? {#section_AE1BE61A58864FFE81F0BCEED2EBB15D}

Check to see if your account has reached its limit on the "Full Index Status" screen. If the status reports that your index is larger than allowed or that it took more time than allowed, your website is not fully indexed. You can correct this error so that you get proper coverage and count of website pages.

To protect site search/merchandising servers, there are internal limits on bytes and time. Only when crawled files are very large, or when the server that site search/merchandising is trying to reach is slow are these limits reached.

If you hit a time limit, make sure that your server is online, and attempt the index again at a later time. If you hit a bytes limit, check the crawled files by viewing your index log. Are they unusually large? Contact Technical Support if you see either of these messages. 
