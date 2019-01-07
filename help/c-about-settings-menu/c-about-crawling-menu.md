---
description: Use the Crawling menu set date and URL masks, passwords, content types, connections, form definitions, and URL entrypoints.
seo-description: Use the Crawling menu set date and URL masks, passwords, content types, connections, form definitions, and URL entrypoints.
seo-title: About the Crawling menu
solution: Target
subtopic: Crawling
title: About the Crawling menu
topic: Settings,Site search and merchandising
uuid: 090cc27e-e8de-4417-a0bf-dda48e136e2f
index: y
internal: n
snippet: y
---

# About the Crawling menu{#about-the-crawling-menu}

Use the Crawling menu set date and URL masks, passwords, content types, connections, form definitions, and URL entrypoints.

## About URL Entrypoints {#concept_5D857E3B5C124E85BC0B5AE77A509573}

Most websites have one primary entry point or home page that a customer initially visits. This main entry point is the URL address from which the search robot begins index crawling. However, if your website has multiple domains or subdomains, or if portions of your site are not linked from the primary entry point, you can use URL Entrypoints to add more entry points.

<!-- 

c_about_url_entrypoints.xml

 -->

All website pages below each specified URL entry point are indexed. You can combine URL entry points with masks to control exactly which portions of a website that you want to index. You must rebuild your website index before the effects of URL Entrypoints settings are visible to customers.

The main entry point is typically the URL of the website that you want to index and search. You configure this main entry point in Account Settings.

See [Configuring your account settings](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

After you have specified the main URL entry point, you can optionally specify additional entry points that you want to crawl in order. Most often you will specify additional entry points for web pages that are not linked from pages under the main entry point. Specify additional entry points when your website spans more than one domain as in the following example:

`http://www.domain.com/`

`http://www.domain.com/not_linked/but_search_me_too/`

`http://more.domain.com/`

You qualify each entry point with one or more of the following space-separated keywords in the table below. These keywords affect how the page is indexed.

**Important**: Be sure that you separate a given keyword from the entry point and from each other by a space; a comma is not a valid separator.

<table id="table_5A938198E089480784807150A5D530CF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Keyword </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> If you do not want to index the text on the entry point page, but you do want to follow the page's links, add 
     <userinput>
       noindex 
     </userinput> after the entry point. </p> <p>Separate the keyword from the entry point with a space as in the following example: </p> <p> 
     <codeblock>
       http://www.my-additional-domain.com/more_pages/main.html&amp;nbsp;noindex 
     </codeblock> </p> <p>This keyword is equivalent to a robots meta tag with 
     <userinput>
       content="noindex" 
     </userinput>) between the 
     <userinput>
       &lt;head&gt; 
     </userinput>... 
     <userinput>
       &lt;/head&gt; 
     </userinput> tags of the entry point page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> If you want to index the text in the entry point page but you do not want to follow any of the page's links, add 
     <userinput>
       nofollow 
     </userinput> after the entry point. </p> <p>Separate the keyword from the entry point with a space as in the following example: </p> <p> 
     <codeblock>
       http://www.domain.com/not_linked/directory_listing&amp;nbsp;nofollow 
     </codeblock> </p> <p>This keyword is equivalent to a robots meta tag with 
     <userinput>
       content="nofollow" 
     </userinput> between the 
     <userinput>
       &lt;head&gt; 
     </userinput>... 
     <userinput>
       &lt;/head&gt; 
     </userinput> tag of an entry point page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>form </p> </td> 
   <td colname="col2"> <p> When the entry point is a login page, 
     <userinput>
       form 
     </userinput> is typically used so that the search robot can submit the login form and receive the appropriate cookies before crawling the website. When the "form" keyword is used, the entry point page is not indexed and the search robot does not mark the entry point page as crawled. Use 
     <userinput>
       nofollow 
     </userinput> if you do not want the search robot to follow the page's links. </p> </td> 
  </tr> 
 </tbody> 
</table>

See also [About Content Types](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

See also [About Index Connector](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84). 

## Adding multiple URL entry points that you want indexed {#task_2338A47387D74CFDAC4D4EF4A367ED45}

If your website has multiple domains or subdomains and you want them crawled, you can use URL Entrypoints to add more URLs.

<!-- 

t_adding_multiple_url_entrypoints_that_you_want_indexed.xml

 -->

To set your website's main URL entry point, you use Account Settings.

See [Configuring your account settings](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

**To add multiple URL entry points that you want indexed** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**.
1. On the [!DNL URL Entrypoints] page, in the [!DNL Entrypoints] field, enter one URL address per line.
1. (Optional) In the **[!UICONTROL Add Index Connector Configurations]** drop-down list, select an index connector that you want to add as an entry point for indexing.

   The drop-down list is only available if you have previously added one or more index connector definitions.

   ![](assets/url_entrypoints_index_connector.png)

   See [Adding an Index Connector definition](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About URL Masks {#concept_8039DFC53FF3410AA494D602F71BA164}

URL masks are patterns that determine which of your website documents the search robot indexes or not indexes.

<!-- 

c_about_url_masks.xml

 -->

Be sure that you rebuild your site index so that the results of your URL masks are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

The following are two kinds of URL masks that you can use:

* Include URL masks 
* Exclude URL masks

Include URL masks tell the search robot to index any documents that match the mask's pattern.

Exclude URL masks tell the search robot to index matching documents.

As the search robot travels from link to link through your website, it encounters URLs and looks for masks that match those URLs. The first match determines whether to include or exclude that URL from the index. If no mask matches an encountered URL, that URL is discarded from the index.

Include URL masks for your entrypoint URLs are automatically generated. This behavior ensures that all encountered documents on your website are indexed. It also conveniently does away with links that "leave" your website. For example, if an indexed page links to http://www.yahoo.com, the search robot does not index that URL because it does not match the include mask automatically generated by the entrypoint URL.

Each URL mask that you specify must be on a separate line.

The mask can specify any of the following:

* A full path as in `http://www.mydomain.com/products.html`. 
* A partial path as in `http://www.mydomain.com/products`. 
* A URL that uses wild cards as in `http://www.mydomain.com/*.html`. 
* A regular expression (for advanced users).

  To make a mask a regular expression, insert the keyword `regexp` between the mask type ( `exclude` or `include`) and the URL mask.

The following is a simple exclude URL mask example:

```
exclude http://www.mydomain.com/photos
```

Because this example is an exclude URL mask, any document that matches the pattern is not indexed. The pattern matches any encountered item, both files and folders, so that `http://www.mydomain.com/photos.html` and `http://www.mydomain.com/photos/index.html`, both of which match the exclude URL, are not indexed. To match only files in the `/photos/` folder, the URL mask must contain a trailing slash as in the following example:

```
exclude http://www.mydomain.com/photos/
```

The following exclude mask example uses a wild card. It tells the search robot to overlook files with the ".pdf" extension. The search robot does not add these files to your index.

```
exclude *.pdf
```

A simple include URL mask is the following:

```
include http://www.mydomain.com/news/
```

Only documents that are linked by way of a series of links from a URL entrypoint, or that are used as a URL entrypoint themselves, are indexed. Solely listing a document's URL as an include URL mask does not index an unlinked document. To add unlinked documents to your index, you can use the URL Entrypoints feature.

See [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Include masks and exclude masks can work together. You can exclude a large portion of your website from indexing by creating an exclude URL mask yet include one or more of those excluded pages with an include URL mask. For example, suppose your entrypoint URL is the following:

```
http://www.mydomain.com/photos/
```

The search robot crawls and indexes all of the pages under `/photos/summer/`, `/photos/spring/` and `/photos/fall/` (assuming that there are links to at least one page in each directory from the `photos` folder). This behavior occurs because the link paths enable the search robot to find the documents in the `/summer/`, `/spring/`, and `/fall/`, folders and the folder URLs match the include mask that is automatically generated by the entrypoint URL.

You can choose to exclude all pages in the `/fall/` folder with an exclude URL mask as in the following example:

```
exclude http://www.mydomain.com/photos/fall/
```

Or, selectively include only `/photos/fall/redleaves4.html` as part of the index with the following URL mask:

```
include http://www.mydomain.com/photos/fall/redleaves4.html
```

For the above two mask examples to work as intended, the include mask is listed first, as in the following:

```
include http://www.mydomain.com/photos/fall/redleaves4.html 
exclude http://www.mydomain.com/photos/fall/
```

Because the search robot follows directions in the order that they are listed, the search robot first includes `/photos/fall/redleaves4.html`, and then excludes the rest of the files in the `/fall` folder.

If the instructions are specified in the opposite way as in the following:

```
exclude http://www.mydomain.com/photos/fall/ 
include http://www.mydomain.com/photos/fall/redleaves4.html
```

Then `/photos/fall/redleaves4.html` is not included, even though the mask specifies that it is included.

A URL mask that appears first always takes precedence over a URL mask that appears later in the mask settings. Additionally, if the search robot encounters a page that matches an include URL mask and an exclude URL mask, the mask that is listed first always takes precedence.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## About using keywords with URL masks {#section_7609A7A6D79B482ABCA8900886541AAB}

You can qualify each include mask with one or more space-separated keywords, which affect how the matched pages are indexed.

A comma is not valid as a separator between the mask and the keyword; you can only use spaces.

<table id="table_1A60D535EF404E38950BBF9A9BE22C0E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Keyword </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> If you do not want to index the text on the pages that match the URL mask, but you want to follow the matched pages links, add 
     <userinput>
       noindex 
     </userinput> after the include URL mask. Be sure that you separate the keyword from the mask with a space as in the following example: </p> <p> 
     <codeblock>
       include&amp;nbsp;*.swf&amp;nbsp;noindex 
     </codeblock> </p> <p>The above example specifies that the search robot follow all links from files with the 
     <userinput>
       .swf 
     </userinput> extension, but disables indexing of all text contained within those files. </p> <p>The 
     <userinput>
       noindex 
     </userinput> keyword is equivalent to a robot meta tag with 
     <userinput>
       content="noindex" 
     </userinput> between the 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> tags of matched pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> If you want to index the text on the pages that match the URL mask, but you do not want to follow the matched page's links, add 
     <userinput>
       nofollow 
     </userinput> after the include URL mask. Be sure that you separate the keyword from the mask with a space as in the following example: </p> <p> 
     <codeblock>
       include&amp;nbsp;http://www.mydomain.com/photos&amp;nbsp;nofollow 
     </codeblock> </p> <p>The 
     <userinput>
       nofollow 
     </userinput> keyword is equivalent to a robot meta tag with 
     <userinput>
       content="nofollow" 
     </userinput> between the 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> tags of matched pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p>Used for both include and exclude masks. </p> <p>Any URL mask preceded with 
     <userinput>
       regexp 
     </userinput> is treated as a regular expression. If the search robot encounters documents that match an exclude regular expression URL mask, those documents are not indexed. If the search robot encounters documents that match an include regular expression URL mask, those documents are indexed. For example, suppose you have the following URL mask: </p> <p> 
     <codeblock>
       exclude&amp;nbsp;regexp&amp;nbsp;^.*/products/.*\.html$ 
     </codeblock> </p> <p>The search robot excludes matching files such as 
     <userinput>
       http://www.mydomain.com/products/page1.html 
     </userinput> </p> <p>If you had the following exclude regular expression URL mask: </p> <p> 
     <codeblock>
       exclude&amp;nbsp;regexp&amp;nbsp;^.*\?..*$ 
     </codeblock> </p> <p>The search robot does not to include any URL containing a CGI parameter such as 
     <userinput>
       http://www.mydomain.com/cgi/prog/?arg1=val1&amp;arg2=val2 
     </userinput>. </p> <p>If you had the following include regular expression URL mask: </p> <p> 
     <codeblock>
       include&amp;nbsp;regexp&amp;nbsp;^.*\.swf$&amp;nbsp;noindex 
     </codeblock> </p> <p>The search robot follows all links from files with the ".swf" extension. The 
     <userinput>
       noindex 
     </userinput> keyword also specifies that the text of matched files are not indexed. </p> <p>See <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Regular Expressions </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adding URL masks to index or not index parts of your website {#task_E1AFC17C746048B8843013D979E082C1}

You can use [!DNL URL Masks] to define which parts of your website that you want or do not want crawled and indexed.

<!-- 

t_adding_url_masks_to_index_or_not_index_parts_of_your_website.xml

 -->

Use the Test URL Masks field to test whether a document is or is not included after you index.

Be sure that you rebuild your site index so that the results of your URL masks are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To add URL masks to index or not index parts of your website** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**.
1. (Optional) On the [!DNL URL Masks] page, in the **[!UICONTROL Test URL Masks]** field, enter a test URL mask from your website, and then click **[!UICONTROL Test]**.
1. In the [!DNL URL Masks] field, type `include` (to add a website that you want crawled and indexed), or type `exclude` (to block a website from getting crawled and indexed), followed by the URL mask address.

   Enter one URL mask address per line. Example:

   ```
   include http://www.mycompany.com/summer 
   include http://www.mycompany.com/spring 
   exclude regexp .*\.xml 
   exclude http://www.mycompany.com/fall
   ```

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Date Masks {#concept_F4F1F58A646F4A86B8650EC46FDCEF66}

You can use Date Masks to include or exclude files from your search results based on the age of the file.

<!-- 

c_about_date_masks.xml

 -->

Be sure that you rebuild your site index so that the results of your URL masks are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

The following are two kinds of date masks that you can use:

* Include date masks ("include-days" and "include-date")

  Include date masks index files that are dated on or before the specified date. 
* Exclude date masks ("exclude-days" and "exclude-date")

  Exclude date masks index files that are dated on or before the specified date.

By default, the file date is determined from meta tag information. If no Meta tag is found, the date of a file is determined from the HTTP header that is received from the server when the search robot downloads a file.

Each date mask that you specify must be on a separate line.

The mask can specify any of the following:

* A full path as in `http://www.mydomain.com/products.html` 
* A partial path as in `http://www.mydomain.com/products` 
* A URL that uses wild cards `http://www.mydomain.com/*.html` 
* A regular expression. To make a mask a regular expression, insert the keyword `regexp` before the URL.

Both include and exclude date masks can specify a date in one of the two following ways. The masks are only be applied if the matched files were created on or before the specified date:

1. A number of days. For example, suppose your date mask is the following:

   ```
   exclude-days 30 http://www.mydomain.com/docs/archive/)
   ```

   The number of specified days is counted back. If the file is dated on or before the arrived upon date, the mask is applied. 

1. An actual date using the format YYYY-MM-DD. For example, suppose your date mask is the following:

   ```
   include-date 2011-02-15 http://www.mydomain.com/docs/archive/)
   ```

   If the matched document is dated on or before the specified date, the date mask is applied.

The following is a simple exclude date mask example:

```
exclude-days 90 http://www.mydomain.com/docs/archive
```

Because this is an exclude date mask, any file that matches the pattern is not indexed and is 90 days old or older. When you exclude a document, no text is indexed and no links are followed from that file. The file is effectively ignored. In this example, both files and folders might match the specified URL pattern. Notice that both `http://www.mydomain.com/docs/archive.html` and `http://www.mydomain.com/docs/archive/index.html` match the pattern and are not indexed if they are 90 days old or older. To match only files in the `/docs/archive/` folder, the date mask must contain a trailing slash as in the following:

```
exclude-days 90 http://www.mydomain.com/docs/archive/
```

Date masks can also be used with wild cards. The following exclude mask tells the search robot to overlook files with the ".pdf" extension that are dated on or before 2011-02-15. The search robot does not add any matched files to your index.

```
exclude-date 2011-02-15 *.pdf
```

Include date mask looks similar, only matched files are added to the index. The following include date mask example tells the search robot to index the text from any files that are zero days old or older in the `/docs/archive/manual/` area of the website.

```
include-days 0 http://www.mydomain.com/docs/archive/manual/
```

Include masks and exclude masks can work together. For example, you can exclude a large portion of your website from indexing by creating an exclude date mask yet include one or more of those excluded pages with an include URL mask. If your entrypoint URL is the following:

```
http://www.mydomain.com/archive/
```

The search robot crawls and indexes all of the pages under `/archive/summer/`, `/archive/spring/`, and `/archive/fall/` (assuming that there are links to at least one page in each folder from the `archive` folder). This behavior occurs because the link paths enable the search robot to "find" the files in the `/summer/`, `/spring/`, and `/fall/` folders and the folder URLs match the include mask automatically generated by the entrypoint URL.

See [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

See [Configuring your account settings](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

You may choose to exclude all pages over 90 days old in the `/fall/` folder with an exclude date mask as in the following:

```
exclude-days 90 http://www.mydomain.com/archive/fall/
```

You can selectively include only `/archive/fall/index.html` (regardless of how old it is--any file 0 days or older are matched) as part of the index with the following date mask:

```
include-days 0 http://www.mydomain.com/archive/fall/index.html
```

For the above two mask examples to work as intended, you must list the include mask first as in the following:

```
include-days 0 http://www.mydomain.com/archive/fall/index.html 
exclude-days 90 http://www.mydomain.com/archive/fall/
```

Because the search robot follows directions in the order they are specified, the search robot first includes `/archive/fall/index.html`, and then excludes the rest of the files in the `/fall` folder.

If the instructions are specified in the opposite way as in the following:

```
exclude-days 90 http://www.mydomain.com/archive/fall/ 
include-days 0 http://www.mydomain.com/archive/fall/index.html 
```

Then `/archive/fall/index.html` is not included, even though the mask specifies that it should be. A date mask that appears first always takes precedence over a date mask that might appear later in the mask settings. Additionally, if the search robot encounters a page that matches both an include date mask and an exclude date mask, the mask that is listed first always takes precedence.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## About using keywords with date masks {#section_CCBB3E3FDBDE4725B2B571FD6594470C}

You can qualify each include mask with one or more space-separated keywords, which affect how the matched pages are indexed.

A comma is not valid as a separator between the mask and the keyword; you can only use spaces.

<table id="table_64DD11CCE5B0418C92A1CA0DE628C969"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Keyword </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> If you do not want to index the text on the pages that are dated on or before the date that is specified by the include mask, add 
     <userinput>
       noindex 
     </userinput> after the include date mask as in the following: </p> <p> 
     <codeblock>
       include-days&amp;nbsp;10&amp;nbsp;*.swf&amp;nbsp;noindex 
     </codeblock> </p> <p>Be sure you separate the keyword from the mask with a space. </p> <p>The above example specifies that the search robot follow all links from files with the ".swf" extension that are 10 days old or older. However, it disables indexing of all text contained in those files. </p> <p>You may want make sure that the text for older files is not indexed but still follow all links from those files. In such cases, use an include date mask with the "noindex" keyword instead of using an exclude date mask. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> If you want to index the text on the pages that are dated on or before the date that is specified by the include mask, but you do not want to follow the matched page's links, add 
     <userinput>
       nofollow 
     </userinput> after the include date mask as in the following: </p> <p> 
     <codeblock>
       include-days&amp;nbsp;8&amp;nbsp;http://www.mydomain.com/photos&amp;nbsp;nofollow 
     </codeblock> </p> <p>Be sure you separate the keyword from the mask with a space. </p> <p>The 
     <userinput>
       nofollow 
     </userinput> keyword is equivalent to a robot meta tag with 
     <userinput>
       content="nofollow" 
     </userinput> between the 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> tag of matched pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server-date </p> </td> 
   <td colname="col2"> <p>Used for both include and exclude masks. </p> <p>The search robot generally downloads and parses every file before checking the date masks. This behavior occurs because some file types can specify a date inside the file itself. For example, an HTML document can include meta tags that set the date of the file. </p> <p>If you are going to exclude many files based on their date, and you do not want to put an unnecessary load on your servers, you can use 
     <userinput>
       server-date 
     </userinput> after the URL in the date mask. </p> <p>This keyword instructs the search robot to trust the date of the file that is returned by your server instead of parsing each file. For example, the following exclude date mask ignores pages that match the URL if the documents are 90 days or older, according to the date that is returned by the server in the HTTP headers: </p> <p> 
     <codeblock>
       exclude-days&amp;nbsp;90&amp;nbsp;http://www.mydomain.com/docs/archive&amp;nbsp;server-date 
     </codeblock> </p> <p> If the date that is returned by the server is 90 days or more past, 
     <userinput>
       server-date 
     </userinput> specifies that the excluded documents not be downloaded from your server. The result means faster indexing time for your documents and a reduced load placed on your servers. If 
     <userinput>
       server-date 
     </userinput> is not specified, the search robot ignores the date that is returned by the server in the HTTP headers. Instead, each file is downloaded and checked to see if the date is specified. If no date is specified in the file, then the search robot uses the date that is returned by the server. </p> <p>You should not use 
     <userinput>
       server-date 
     </userinput> if your files contain commands that override the server date. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p> Use for both include and exclude masks. </p> <p>Any date mask that is preceded by 
     <userinput>
       regexp 
     </userinput> is treated as a regular expression. </p> <p>If the search robot encounters files that match an exclude regular expression date mask, it does not index those files. </p> <p>If the search robot encounters files that match an include regular expression date mask, it indexes those documents. </p> <p>For example, suppose you have the following date mask: </p> <p> 
     <codeblock>
       exclude-days&amp;nbsp;180&amp;nbsp;regexp&amp;nbsp;.*archive.* 
     </codeblock> </p> <p>The mask tells the search robot to exclude matching files that are 180 days or older. That is, files that contain the word "archive" in their URL. </p> <p>See <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Regular Expressions </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adding date masks to index or not index parts of your website {#task_0010543C55F648D2B5DEFEFAD60FAF04}

You can use Date Masks to include or exclude files from customer search results based on the age of the files.

<!-- 

t_adding_date_masks_to_index_or_not_index_parts_of_your_website.xml

 -->

Use the **[!UICONTROL Test Date]** and **[!UICONTROL Test URL]** fields to test whether a file is or is not included after you index.

Be sure that you rebuild your site index so that the results of your URL masks are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To add date masks to index or not index parts of your website** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Date Masks]**.
1. (Optional) On the [!DNL Date Masks] page, in the **[!UICONTROL Test Date]** field, enter a date formatted as YYYY-MM-DD (for example, `2011-07-25`); in the **[!UICONTROL Test URL]** field, enter a URL mask from your website, and then click **[!UICONTROL Test]**.
1. In the [!DNL Date Masks] field, enter one date mask address per line.
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Passwords {#concept_3EDBD731725D46B891F834D4472774DC}

To access portions of your website that are protected with HTTP Basic Authentication, you can add one or more passwords.

<!-- 

c_about_passwords.xml

 -->

Before the effects of the Password settings is visible to customers, you must rebuild your site index.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

On the [!DNL Passwords] page, you type each password on a single line. The password consists of a URL or realm, a user name, and a password, as in the following example:

```
http://www.mydomain.com/ myname mypassword
```

Instead of the using a URL path, like above, you could also specify a realm.

To determine the correct realm to use, open a password-protected web page with a browser and look at the "Enter Network Password" dialog box.

![](assets/realms.gif)

The realm name, in this case, is "My Site Realm."

Using the realm name above, your password might look like the following:

```
My Site Realm myusername mypassword
```

If your web site has multiple realms, you can create multiple passwords by entering a user name and password for each realm on a separate line as in the following example:

```
Realm1 name1 password1 
Realm2 name2 password2 
Realm3 name3 password3
```

You can intermix passwords that contain URLs or realms so that your password list might look like the following:

```
Realm1 name1 password1 
http://www.mysite.com/path1/path2 name2 password2 
Realm3 name3 password3 
Realm4 name4 password4 
http://www.mysite.com/path1/path5 name5 password5 
http://www.mysite.com/path6 name6 password6
```

In the list above, the first password is used that contains a realm or URL that matches the server's authentication request. Even if the file at `http://www.mysite.com/path1/path2/index.html` is in `Realm3`, for example, `name2` and `password2` are used because the password that is defined with the URL is listed above the one defined with the realm. 

## Adding passwords for accessing areas of your website that require authentication {#task_DED19D476FF04B48BB6456D5ECB8628A}

You can use Passwords to access password-protected areas of your website for crawling and indexing purposes.

<!-- 

t_adding_passwords_to_access_areas_of_your_website_that_require_authentication.xml

 -->

Before the effects of your password are additions are visible to customers, be sure you rebuild your site index

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To add passwords for accessing areas of your website that require authentication** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Passwords]**.
1. On the [!DNL Passwords] page, in the **[!UICONTROL Passwords]** field, enter a realm or URL, and its associated user name, and password, separated by a space.

   Example of a realm password and a URL password on separate lines:

   ```
   Realm1 name1 password1 
   http://www.mysite.com/path1/path2 name2 password2
   ```

   Only add one password per line. 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Content Types {#concept_6FEA1355C0374500B4C53090C34A8A07}

You can use [!DNL Content Types] to select which types of files that you want to crawl and index for this account.

<!-- 

c_about_content_types.xml

 -->

Content types that you can choose to crawl and index include PDF documents, text documents, Adobe Flash movies, files from Microsoft Office applications such as Word, Excel, and Powerpoint, and text in MP3 files. The text that is found within the selected content types is searched along with all of the other text on your website.

Before the effects of the Content Types settings is visible to customers, you must rebuild your site index.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## About indexing MP3 music files {#section_AD2E28BEEE3E46629E2B05C34A963673}

If you select the option **[!UICONTROL Text in MP3 Music Files]** on the [!DNL Content Types] page, an MP3 file is crawled and indexed in one of two ways. The first and most common way is from an anchor href tag in an HTML file as in the following:

```
<a href="MP3-file-URL"></a>
```

The second way is to enter the URL of the MP3 file as a URL entrypoint.

See [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

An MP3 file is recognized by its MIME type "audio/mpeg".

Be aware that MP3 music file sizes can be quite large, even though they usually contain only a small amount of text. For example, MP3 files can optionally store such things as the album name, artist name, song title, song genre, year of release, and a comment. This information is stored at the very end of the file in what is called the TAG. MP3 files containing TAG information are indexed in the following way:

* The song title is treated like the title of an HTML page. 
* The comment is treated like a description that is defined for an HTML page. 
* The genre is treated like a keyword that is defined for an HTML page. 
* The artist name, album name, and year of release are treated like the body of an HTML page.

Note that each MP3 file that is crawled and indexed on your website counts as one page.

If your website contains many large MP3 files, you may exceed the indexing byte limit for your account. If this happens, you can deselect **[!UICONTROL Text in MP3 Music Files]** on the [!DNL Content Types] page to prevent the indexing of all MP3 files on your website.

If you only want to prevent the indexing of certain MP3 files on your website, you can do one of the following:

* Surround the anchor tags that link to the MP3 files with `<nofollow>` and `</nofollow>` tags. The search robot does not follow links between those tags.

* Add the URLs of the MP3 files as exclude masks.

  See [About URL Masks](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

## Selecting content types to crawl and index {#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8}

You can use [!DNL Content Types] to select which types of files that you want to crawl and index for this account.

<!-- 

t_seleting_content_types_to_crawl_and_index.xml

 -->

Content types that you can choose to crawl and index include PDF documents, text documents, Adobe Flash movies, files from Microsoft Office applications such as Word, Excel, and Powerpoint, and text in MP3 files. The text that is found within the selected content types is searched along with all of the other text on your website.

Before the effects of the Content Types settings is visible to customers, you must rebuild your site index.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

To crawl and index Chinese, Japanese, or Korean MP3 files, complete the steps below. Then, in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**, specify the character set that is used to encode the MP3 files.

See [About Injections](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

**To select content types to crawl and index** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**.
1. On the [!DNL Content Types] page, check the file types that you want to crawl and index on your website.
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Connections {#concept_E2F3B7E7521147479E5948A94BB3A40B}

You can use Connections to add up to ten HTTP connections that the search robot uses to index your website.

<!-- 

c_about_connections.xml

 -->

Increasing the number of connections can significantly reduce the amount of time that it takes to complete a crawl and index. However, be aware that each additional connection increases the load on your server. 

## Adding connections to increase indexing speed {#task_3E9B83E43C1842A19066355A15C4A6FB}

You can reduce the amount of time it takes to index your website by using Connections to increase the number of simultaneous HTTP connections that the crawler uses. You can add up to ten connections.

<!-- 

t_adding_connections_to_increase_indexing_speed.xml

 -->

Be aware that each additional connection increases the load that is placed on your server.

**To add connections to increase indexing speed** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Connections]**.
1. On the [!DNL Parallel Indexing Connections] page, in the **[!UICONTROL Number of Connections]** field, enter the number of connections (1-10) that you want to add.
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Form Submission {#concept_CADD5D7CF373497DAA6F8564D7BC8502}

You can use Form Submission to help you recognize and process forms on your website.

<!-- 

c_about_form_submission.xml

 -->

During the crawling and indexing of your website, each encountered form is compared with the form definitions that you have added. If a form matches a form definition, the form is submitted for indexing. If a form matches more than one definition, the form is submitted once for each matched definition. 

## Adding form definitions for indexing forms on your website {#task_62FBCE9E6DBE4BDA8D1249233ADFC00F}

You can use [!DNL Form Submission] to help process forms that are recognized on your website for indexing purposes.

<!-- 

t_adding_form_definitions_for_indexing_forms_on_your_website.xml

 -->

Be sure that you rebuild your site index so that the results of your changes are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To add form definitions for indexing forms on your website** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. On the [!DNL Form Submission] page, click **[!UICONTROL Add New Form]**.
1. On the [!DNL Add Form Definition] page, set the [!DNL Form Recognition] and [!DNL Form Submission] options.

   <!-- 

r_form_definition_options.xml

 -->

   The five options in the [!DNL Form Recognition] section on the [!DNL Form Definition] page are used to identify forms in your web pages that can be process.

   The three options in the [!DNL Form Submission] section are used to specify the parameters and values that are submitted with a form to your web server.

   Enter one recognition or submission parameter per line. Each parameter must include a name and a value.

<table id="table_3B1FD82A1CD74891885B4E0A7846F7A8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Form Recognition</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page URL Mask </p> </td> 
   <td colname="col2"> <p>Identify the web page or pages that contain the form. To identify a form that appears on a single page, enter the URL for that page as in the following example: </p> <p> 
     <codeblock>
       http://www.mydomain.com/login.html 
     </codeblock> </p> <p>To identify forms that appear on multiple pages, specify a URL mask that uses wildcards to describe the pages. To identify forms encountered on any ASP page under 
     <codeblock>
       http://www.mydomain.com/register/ 
     </codeblock>, for example, you would specify the following: </p> <p> 
     <codeblock>
       http://www.mydomain.com/register/*.asp&amp;nbsp; 
     </codeblock> </p> <p>You can also use a regular expression to identify multiple pages. Just specify the 
     <userinput>
       regexp 
     </userinput> keyword before the URL mask as in the following example: </p> <p> 
     <codeblock>
       regexp&amp;nbsp;^http://www\.mydomain\.com/.*/login\.html$ 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Action URL Mask </p> </td> 
   <td colname="col2"> <p>Identifies the action attribute of the 
     <userinput>
       &lt;form&gt; 
     </userinput> tag. </p> <p>Like the page URL mask, the action URL mask can take the form of a single URL, a URL with wildcards, or a regular expression. </p> <p>The URL mask can be any of the following: 
     <ul id="ul_EDFE7688D3DD4C0BBACCE5D4648D8E44"> 
      <li id="li_77550A448D954EF29FF33EE5E8B5E0F5"> A full path as in the following: 
       <codeblock>
         http://www.mydomain.com/products.html 
       </codeblock> </li> 
      <li id="li_F84E25553BBA41419BE153DC0709E011"> A partial path as in the following: 
       <codeblock>
         http://www.mydomain.com/products 
       </codeblock> </li> 
      <li id="li_8DADA1C8604740FCACBA30B4AAADB2A1"> A URL that uses wild cards as in the following: 
       <codeblock>
         http://www.mydomain.com/*.html 
       </codeblock> </li> 
      <li id="li_1EF637B450654B509AA4B618F7FD3C2B"> A regular expression as in the following: 
       <codeblock>
         regexp&amp;nbsp;^http://www\.mydomain\.com/.*/login\.html$ 
       </codeblock> </li> 
     </ul> </p> <p>If you do not want to index the text on pages that are identified by a URL mask or by an action URL mask, or if you do not want links followed on those pages, you can use the 
     <userinput>
       noindex 
     </userinput> and 
     <userinput>
       nofollow 
     </userinput> keywords. You can add these keywords to your masks using URL masks or entrypoints. </p> <p>See <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573" type="concept" format="dita" scope="local"> About URL Entrypoints </a>. </p> <p>See <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> About URL Masks </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Form Name Mask </p> </td> 
   <td colname="col2"> <p>Identifies forms if the 
     <userinput>
       &lt;form&gt; 
     </userinput> tags in your web pages contain a name attribute. </p> <p>You can use a simple name ( 
     <userinput>
       login_form 
     </userinput>), a name with a wildcard ( 
     <userinput>
       form* 
     </userinput>), or a regular expression ( 
     <userinput>
       regexp ^.*authorize.*$ 
     </userinput>). </p> <p>You can usually leave this field empty because forms typically do not have a name attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Form ID Mask </p> </td> 
   <td colname="col2"> <p>Identifies forms if the 
     <userinput>
       &lt;form&gt; 
     </userinput> tags in your web pages contain an id attribute. </p> <p>You can use a simple name ( 
     <userinput>
       login_form 
     </userinput>), a name with a wildcard ( 
     <userinput>
       form* 
     </userinput>), or a regular expression ( 
     <userinput>
       regexp ^.*authorize.*$ 
     </userinput>). </p> <p>You can usually leave this field empty because forms typically do not have a name attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parameters </p> </td> 
   <td colname="col2"> <p>Identify forms that contain, or do not contain, a named parameter or a named parameter with a specific value. </p> <p>For example, to identify a form that contains an e-mail parameter that is preset to rick_brough@mydomain.com, a password parameter, but not a first-name parameter, you would specify the following parameter settings, one per line: </p> <p> 
     <codeblock>
       email=rick_brough@mydomain.com 
      password 
      not&nbsp;first-name 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Form Submission</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Override Action URL </p> </td> 
   <td colname="col2"> <p>Specify when the target of the form submission is different from what is specified in the form's action attribute. </p> <p>For example, you might use this option when the form is submitted by way of a JavaScript function that constructs a URL value that is different from what is found in the form. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Override Method </p> </td> 
   <td colname="col2"> <p>Specify when the target of the form submission is different from what is used in the form's action attribute and when the submitting JavaScript has changed the method. </p> <p>The default values for all form parameters ( 
     <userinput>
       &lt;input&gt; 
     </userinput> tags, including hidden fields), the default 
     <userinput>
       &lt;option&gt; 
     </userinput> from a 
     <userinput>
       &lt;select&gt; 
     </userinput> tag, and the default text between 
     <userinput>
       &lt;textarea&gt;...&lt;/textarea&gt; 
     </userinput> tags) are read from the web page. However, any parameter that is listed in the <span class="wintitle"> Form Submission </span> section, in the <span class="uicontrol"> Parameters </span> field, is replaced with the form defaults. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parameters </p> </td> 
   <td colname="col2"> <p>You can prefix form submission parameters with the 
     <userinput>
       not 
     </userinput> keyword. </p> <p>When you prefix a parameter with 
     <userinput>
       not 
     </userinput>, it is not submitted as part of the form submission. This behavior is useful for check boxes that should be submitted deselected. </p> <p>For example, suppose you want to submit the following parameters: </p> <p> 
     <ul id="ul_962D12BACF464FF189DB12BFAFCC93A6"> 
      <li id="li_830C6C3EC8D2448388A453BB8EDE5940"> The e-mail parameter with the value 
       <userinput>
         nobody@mydomain.com 
       </userinput> </li> 
      <li id="li_905497E3FACE472DBDD49392D5B45E01"> The password parameter with the value 
       <userinput>
         tryme 
       </userinput> </li> 
      <li id="li_AAA411708ADC464793EADF0D821E282E"> The mycheckbox parameter as deselected. </li> 
      <li id="li_0D3DDE641E2B4BEF9F570C03FDB40ED2"> <p>All other 
        <userinput>
          &lt;form&gt; 
        </userinput> parameters as their default values </p> </li> 
     </ul> </p> <p>Your form submission parameter would look like the following: </p> <p> 
     <codeblock>
       email=nobody@mydomain.com 
      password=tryme 
      not&nbsp;mycheckbox 
     </codeblock> </p> <p>The method attribute of the 
     <userinput>
       &lt;form&gt; 
     </userinput> tag on the web page is used to decide if the data is sent to your server using the GET method or the POST method. </p> <p>If the 
     <userinput>
       &lt;form&gt; 
     </userinput> tag does not contain a method attribute, the form is submitted using the GET method. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Add]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a form definition {#task_9FB34E9C8A814DFE9BF7F8F8F69BF314}

You can edit an existing form definition if a form on your website has changed or if you just need to change the definition.

<!-- 

t_editing_a_form_definition.xml

 -->

Be aware that there is no [!DNL History] feature on the [!DNL Form Submission] page to revert any changes that you make to a form definition.

Be sure that you rebuild your site index so that the results of your changes are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To edit a form definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. On the [!DNL Form Submission] page, click **[!UICONTROL Edit]** to the right of a form definition that you want to update.
1. On the [!DNL Edit Form Definition] page, set the [!DNL Form Recognition] and [!DNL Form Submission] options.

   See the table of options under [Adding form definitions for indexing forms on your website](../c-about-settings-menu/c-about-crawling-menu.md#task_62FBCE9E6DBE4BDA8D1249233ADFC00F). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a form definition {#task_C350FC0CDE344F2786215D544C048B5E}

You can delete an existing form definition if the form no longer exists on your website, or if you no longer want to process and index a particular form.

<!-- 

t_deleting_a_form_definition.xml

 -->

Be aware that there is no [!DNL History] feature on the [!DNL Form Submission] page to revert any changes that you make to a form definition.

Be sure that you rebuild your site index so that the results of your changes are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To delete a form definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. On the [!DNL Form Submission] page, click **[!UICONTROL Delete]** to the right of a form definition that you want to remove.

   Make sure you choose the right form definition to delete. There is no delete confirmation dialog box when you click **[!UICONTROL Delete]** in the next step. 
1. On the [!DNL Delete Form Definition] page, click **[!UICONTROL Delete]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Index Connector {#concept_CA6921E2FBF641F9B4F60C92B32AFA84}

Use [!DNL Index Connector] to define additional input sources for indexing XML pages or any kind of feed.

<!-- 

c_about_index_connector.xml

 -->

You can use a data feed input source to access content that is stored in a form that is different from what is typically discovered on a website using one of the available crawl methods. Each document that is crawled and indexed directly corresponds to a content page on your website. However, a data feed either comes from an XML document or from a comma- or tab-delimited text file, and contains the content information to index.

An XML data source consists of XML stanzas, or records, that contain information that corresponds to individual documents. These individual documents are added to the index. A text data feed contains individual new-line-delimited records that correspond to individual documents. These individual documents are also added to the index. In either case, an index connector configuration describes how to interpret the feed. Each configuration describes where the file resides and how the servers access it. The configuration also describes "mapping" information. That is, how each record's items are used to populate the metadata fields in the resulting index.

After you add an Index Connector definition to the [!DNL Staged Index Connector Definitions] page, you can change any configuration setting, *except* for the Name or Type values.

The [!DNL Index Connector] page shows you the following information:

* The name of defined index connectors that you have configured and added. 
* One of the following data source types for each connector that you have added:

    * **Text** - Simple "flat" files, comma-delimited, tab-delimited, or other consistently delimited formats. 
    * **Feed** - XML feeds. 
    * **XML** - Collections of XML documents.

* Whether the connector is enabled or not for the next crawl and indexing done. 
* The address of the data source.

See also [About Index Connector](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)

## How the indexing process works for Text and Feed configurations in Index Connector {#section_E059A33D61EE4DB0972A37B8A35E9E16}

<table id="table_5D18B78A98294FB4BEC91533DD0711C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Step </p> </th> 
   <th colname="col2" class="entry"> <p>Process </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Download the data source. </p> </td> 
   <td colname="col3"> <p>For Text and Feed configurations, it is a simple file download. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Break down the downloaded data source into individual pseudo-documents. </p> </td> 
   <td colname="col3"> <p>For <span class="uicontrol"> Text </span>, each newline-delimited line of text corresponds to an individual document, and is parsed using the specified delimiter, such as a comma or tab. </p> <p>For <span class="uicontrol"> Feed </span>, each document's data is extracted using a regular expression pattern in the following form: </p> <p> 
     <codeblock>
       &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; 
     </codeblock> </p> <p>Using <span class="uicontrol"> Map </span> on the <span class="wintitle"> Index Connector Add </span> page, create a cached copy of the data and then create a list of links for the crawler. The data is stored in a local cache and is populated with the configured fields. </p> <p>The parsed data is written to the local cache. </p> <p>This cache is read later to create the simple HTML documents that the crawler needs. For example, </p> <p> 
     <codeblock>
       &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; 
     </codeblock> </p> <p>The <span class="codeph"> &lt;title&gt; </span> element is only generated when a mapping exists to the Title metadata field. Similarly, the <span class="codeph"> &lt;body&gt; </span> element is only generated when a mapping exists to the Body metadata field. </p> <p> <b>Important</b>: There is no support for the assignment of values to the pre-defined URL meta tag. </p> <p>For all other mappings, <span class="codeph"> &lt;meta&gt; </span> tags are generated for each field that has data found in the original document. </p> <p>The fields for each document are added to the cache. For each document that is written to the cache, a link is also generated as in the following examples: </p> <p> 
     <codeblock>
       &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... 
     </codeblock> </p> <p>The configuration's mapping must have one field identified as the Primary Key. This mapping forms the key that is used when data is fetched from the cache. </p> <p>The crawler recognizes the URL <span class="codeph"> index: </span> scheme prefix, which can then access the locally cached data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Crawl the cached document set. </p> </td> 
   <td colname="col3"> <p>The <span class="codeph"> index: </span> links are added to the crawler's pending list, and are processed in the normal crawl sequence. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Process each document. </p> </td> 
   <td colname="col3"> <p>Each link’s key value corresponds to an entry in the cache, so crawling each link results in that document’s data being fetched from the cache. It is then “assembled” into an HTML image that is processed and added to the index. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How the indexing process works for XML configurations in Index Connector {#section_7F1551EA51854C5C99F284CE260526EB}

The indexing process for XML configuration is similar to the process for Text and Feed configurations with the following minor changes and exceptions.

Because the documents for XML crawls are already separated into individual files, steps 1 and 2 in the table above do not directly apply. If you specify a URL in the **[!UICONTROL Host Address]** and **[!UICONTROL File Path]** fields of the [!DNL Index Connector Add] page, it is downloaded and processed as a normal HTML document. The expectation is that the download document contains a collection of `<a href="{url}"...` links, each of which points to an XML document that is processed. Such links are converted to the following form:

```
<a href="index:<ic_config_name>?url="{url}">
```

For example, if the Adobe setup returned the following links:

```
<a href="http://www.adobe.com/somepath/doc1.xml">doc 1</a> 
<a href="http://www.adobe.com/otherpath/doc2.xml">doc 2</a>
```

In the table above, step 3 does not apply and step 4 is completed at the time of crawling and indexing.

Alternately, you can intermix your XML documents with other documents that were discovered naturally through the crawl process. In such cases, you can use rewrite rules ( **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**) to change the XML documents’ URLs to direct them to Index Connector.

See [About Crawl List Retrieve URL Rules](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA).

For example, supposed you have the following rewrite rule:

```
RewriteRule (^http.*[.]xml$) index:Adobe?key=$1
```

This rule translates any URL ending with `.xml` into an Index Connector link. The crawler recognizes and rewrites the `index:` URL scheme. The download process is redirected through the Index Connector Apache server on the master. Each downloaded document is examined using the same regular expression pattern that is used with Feeds. In this case, however, the manufactured HTML document is not saved in the cache. Instead, it is handed directly to the crawler for index processing.

## How to configure multiple Index Connectors {#section_C2B14C0F06354A57AEF6238FF3814E5D}

You can define multiple Index Connector configurations for any account. The configurations are automatically added to the drop-down list in **[!UICONTROL Settings]** > **[!UICONTROL Crawl]** > **[!UICONTROL URL Entrypoints]** as shown in the following illustration:

![](assets/url_entrypoints_index_connector.png)

Selecting a configuration from the drop-down list adds the value to the end of the list of URL entry points.

>[!NOTE]
>
>While disabled Index Connector configurations are added to the drop-down list, you cannot select them. If you select the same Index Connector configuration a second time, it is added to the end of the list, and the previous instance is deleted.

To specify an Index Connector entry point for an incremental crawl, you can add entries using the following format:

```
index:<indexconnector_configuration_name>
```

The crawler processes each added entry if it is found on the Index Connectors page and is enabled.

Note: Because each document's URL is constructed using the Index Connector configuration name and the document's primary key, be sure you use the same Index Connector configuration name when performing Incremental updates! Doing so permits [!DNL Adobe Search&Promote] to correctly update previously indexed documents.

See also [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

**The use of Setup Maps when you add an Index Connector**

At the time you add an Index Connector, you can optionally use the feature **[!UICONTROL Setup Maps]** to download a sample of your data source. The data is examined for indexing suitability.

<table id="table_B3636C789F2641D4A922B24E6815EAB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>If you chose the Index Connector type... </p> </th> 
   <th colname="col2" class="entry"> <p>The Setup Maps feature... </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Text </p> </td> 
   <td colname="col2"> <p>Determines the delimiter value by trying tabs first, then vertical-bars ( <span class="codeph"> | </span>), and finally commas ( <span class="codeph"> , </span>). If you already specified a delimiter value before you clicked <span class="uicontrol"> Setup Maps </span>, that value is used instead. </p> <p>The best-fit scheme results in the Map fields being filled out with guesses at the appropriate Tag and Field values. Additionally, a sampling of the parsed data is displayed. Be sure to select <span class="uicontrol"> Headers in First Row </span> if you know that the file includes a header row. The setup function uses this information to better identify the resulting map entries. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Downloads the data source and performs simple XML parsing. </p> <p>The resulting XPath identifiers are displayed in the Tag rows of the Map table, and similar values in Fields. These rows only identify the available data, and do not generate the more complicated XPath definitions. However, it is still helpful because it describes the XML data and identifies Itemtag values. </p> <p> <p>Note:  The Setup Maps function downloads the entire XML source to perform its analysis. If the file is large, this operation could time out. </p> </p> <p>When successful, this function identifies all possible XPath items, many of which are not desirable to use. Be sure that you examine the resulting Map definitions and remove the ones that you do not need or want. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XML </p> </td> 
   <td colname="col2"> <p>Downloads the URL of a representative individual document, not the master link list. This single document is parsed using the same mechanism that is used with Feeds, and the results are displayed. </p> <p>Before you click <span class="uicontrol"> Add </span> to save the configuration, be sure that you change the URL back to the master link list document. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Important**: The Setup Maps feature may not work for large XML data sets because its file parser attempts to read the entire file into memory. As a result, you could experience an out-of-memory condition. However, when the same document is processed at the time of indexing, it is not read into memory. Instead, large documents are processed “on the go,” and are not read entirely into memory first.

**The use of Preview when you add an Index Connector**

At the time you add an Index Connector, you can optionally use the feature **[!UICONTROL Preview]** to validate the data, as though you were saving it. It runs a test against the configuration, but without saving the configuration to the account. The test accesses the configured data source. However, it writes the download cache to a temporary location; it does not conflict with the main cache folder that the indexing crawler uses.

Preview only processes a default of five documents as controlled by Acct:IndexConnector-Preview-Max-Documents. The previewed documents are displayed in source form, as they are presented to the indexing crawler. The display is similar to a “View Source" feature in a Web browser. You can navigate the documents in the preview set using standard navigation links.

Preview does not support XML configurations because such documents are processed directly and not downloaded to the cache. 

## Adding an Index Connector definition {#task_96779B651A654E1F871F55D6DBBC8886}

Each Index Connector configuration defines a data source and mappings to relate the data items defined for that source to metadata fields in the index.

<!-- 

t_adding_an_index_connector_definition.xml

 -->

Before the effects of the new and enabled definition is visible to customers, rebuild your site index.

See [About the Index menu](../c-about-index-menu/c-about-index-menu.md#concept_113F5790AE1C4356B3564768F39F43EF).

**To add an Index Connector definition ** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. On the [!DNL Stage Index Connector Definitions] page, click **[!UICONTROL Add New Index Connector]**.
1. On the [!DNL Index Connector Add] page, set the connector options that you want. The options that are available depend on the **[!UICONTROL Type]** that you selected.

   <!-- 

r_index_connector_options.xml

 -->

<table id="table_DE548B74D8CD40679FF1CCD05E91E46C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2"> <p>The unique name of the Index Connector configuration. You can use alphanumeric characters. The characters "_" and "-" are also allowed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type </p> </td> 
   <td colname="col2"> <p>The source of your data. The data source type that you select affects the resulting options that are available on the <span class="wintitle"> Index Connector Add </span> page. You can choose from the following: </p> <p> 
     <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Text </span> <p>Simple flat text files, comma-delimited, tab-delimited, or other consistently delimited formats. Each newline-delimited line of text corresponds to an individual document, and is parsed using the specified delimiter. </p> <p>You can map each value, or column, to a metadata field, referenced by the column number, starting at 1 (one). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Downloads a master XML document that contains multiple "rows" of information. </p> </li> 
      <li id="li_5A61C53522D74D4C9A5F65989604BDEF"> <span class="uicontrol"> XML </span> <p>Downloads a master XML document that contains links ( 
        <userinput>
          &lt;a&gt; 
        </userinput>) to individual XML documents. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Data source type: Text</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enabled </p> </td> 
   <td colname="col2"> <p>Turns the configuration "on" to crawl and index. Or, you can turn "off" the configuration to prevent crawling and indexing. </p> <p> <b>Note</b>: Disabled Index Connector configurations are ignored if they are found in an entrypoint list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Host Address </p> </td> 
   <td colname="col2"> <p>Specifies the address of the server host where your data is located. </p> <p>If desired, you can specify a full URI (Uniform Resource Identifier) path to the data source document as in the following examples: </p> <p> 
     <codeblock>
       http://www.somewhere.com/some_path/some_file.xml 
     </codeblock> </p> <p>or </p> <p> 
     <codeblock>
       ftp://user:password@ftpserver.somewhere.com/some_path/some_file.xml 
     </codeblock> </p> <p>The URI is broken down into the appropriate entries for the Host Address, File Path, Protocol, and, optionally, Username, and Password fields. </p> <p>Specifies the IP address or the URL address of the host system where the data source file is found. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Path </p> </td> 
   <td colname="col2"> <p>Specifies the path to the simple flat text file, comma-delimited, tab-delimited, or other consistently delimited format file. </p> <p>The path is relative to the root of the host address. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Incremental File Path </p> </td> 
   <td colname="col2"> <p>Specifies the path to the simple flat text file, comma-delimited, tab-delimited, or other consistently delimited format file. </p> <p>The path is relative to the root of the host address. </p> <p>This file, if specified, is downloaded and processed during Incremental Index operations. If no file is specified, the file listed under File Path is used instead. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical File Path </p> </td> 
   <td colname="col2"> <p>Specifies the path to the simple flat text file, comma-delimited, tab-delimited, or other consistently delimited format file to be used during a Vertical Update. </p> <p>The path is relative to the root of the host address. </p> <p>This file, if specified, is downloaded and processed during Vertical Update operations. </p> <p> <b>Note</b>: This feature is not enabled by default. Contact Technical Support to activate the feature for your use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deletes File Path </p> </td> 
   <td colname="col2"> <p>Specifies the path to the simple flat text file, containing a single document identifier value per line. </p> <p>The path is relative to the root of the host address. </p> <p>This file, if specified, is downloaded and processed during Incremental Index operations. The values found in this file are used to construct "delete" requests to remove previously indexed documents. The values in this file must correspond to the values found in the Full or Incremental File Path files, in the column identified as the <span class="uicontrol"> Primary Key </span>. </p> <p> <b>Note</b>: This feature is not enabled by default. Contact Technical Support to activate the feature for your use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Protocol </p> </td> 
   <td colname="col2"> <p>Specifies the protocol that is used to access the file. You can choose from the following: </p> <p> 
     <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>If necessary, you may enter proper authentication credentials to access the HTTP server. </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>If necessary, you may enter proper authentication credentials to access the HTTPS server. </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>You must enter proper authentication credentials to access the FTP server. </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>You must enter proper authentication credentials to access the SFTP server. </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> File </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Timeout </p> </td> 
   <td colname="col2"> <p>Specifies the timeout, in seconds, for FTP, SFTP, HTTP or HTTPS connections. This value must be between 30 and 300. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Retries </p> </td> 
   <td colname="col2"> <p>Specifies the maximum number of retries for failed FTP, SFTP, HTTP or HTTPS connections. This value must be between 0 and 10. </p> <p>A value of zero (0) will prevent retry attempts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Encoding </p> </td> 
   <td colname="col2"> <p>Specifies the character encoding system that is used in the specified data source file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Delimiter </p> </td> 
   <td colname="col2"> <p>Specifies the character that you want to use to delineate each field in the specified data source file. </p> <p>The comma character ( <span class="codeph"> , </span>) is an example of a delimiter. The comma acts as a field delimiter that helps to separate data fields in your specified data source file. </p> <p>Select <span class="uicontrol"> Tab? </span> to use the horizontal-tab character as the delimiter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Headers in First Row </p> </td> 
   <td colname="col2"> <p>Indicates that the first row in the data source file contains header information only, not data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Minimum number of documents for indexing </p> </td> 
   <td colname="col2"> <p>If set to a positive value, this specifies the minimum number of records expected in the file downloaded. If fewer records are received, the index operation is aborted. </p> <p> <b>Note</b>: This feature is not enabled by default. Contact Technical Support to activate the feature for your use. </p> <p> <b>Note</b>: This feature is only used during full Index operations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Map </p> </td> 
   <td colname="col2"> <p>Specifies column-to-metadata mappings, using column numbers. </p> <p> 
     <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Column </span> <p> Specifies a column number, with the first column being 1 (one). To add new map rows for each column, under <span class="wintitle"> Action </span>, click <span class="uicontrol"> + </span>. </p> <p>You do not need to reference each column in the data source. Instead, you can choose to skip values. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Field </span> <p>Defines the name attribute value that is used for each generated &lt;meta&gt; tag. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadata? </span> <p>Causes <span class="uicontrol"> Field </span> to become a drop-down list from which you can select defined metadata fields for the current account. </p> <p>The <span class="uicontrol"> Field </span> value can be an undefined metadata field, if desired. An undefined metadata field is sometimes useful to create content used by <span class="wintitle"> Filtering Script </span>. </p> <p>See <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> About Filtering Script </a>. </p> <p>When Index Connector processes XML documents with multiple hits on any map field, the multiple values are concatenated into a single value in the resulting cached document. By default, these values are combined using a comma delimiter. However, suppose that the corresponding <span class="wintitle"> Field </span> value is a defined metadata field. In addition, that field has the <span class="wintitle"> Allow Lists </span> attribute set. In this case, the field's List Delimiters value, which is the first delimiter defined, is used in the concatenation. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Primary Key? </span> <p>Only one map definition is identified as the primary key. This field becomes the unique reference that is presented when this document is added to the index. This value is used in the document’s URL in the Index. </p> <p>The <span class="uicontrol"> Primary Key </span> values must be unique across all of the documents represented by the Index Connector configuration - any duplicates encountered will be ignored. If your source documents don't contain a single unique value for use as <span class="uicontrol"> Primary Key </span>, but two or more fields taken together <i>can</i> form a unique identifier, you can define the <span class="uicontrol"> Primary Key </span> by combining multiple <span class="uicontrol"> Column </span> values with a vertical bar ("|") delimiting the values. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> Strip HTML? </span> <p>When this option is checked, any HTML tags found in this field's data is removed. </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> Action </span> <p>Lets you add rows to the map or remove rows from the map. The order of the rows is not important. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Data source type: Feed</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enabled </p> </td> 
   <td colname="col2"> <p>Turns the configuration "on" to crawl and index. Or, you can turn "off" the configuration to prevent crawling and indexing. </p> <p> <b>Note</b>: Disabled Index Connector configurations are ignored if they are found in an entrypoint list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Host Address </p> </td> 
   <td colname="col2"> <p>Specifies the IP address or the URL address of the host system where the data source file is found. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Path </p> </td> 
   <td colname="col2"> <p>Specifies the path to the master XML document that contains multiple "rows" of information. </p> <p>The path is relative to the root of the host address. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Incremental File Path </p> </td> 
   <td colname="col2"> <p>Specifies the path to the incremental XML document that contains multiple "rows" of information. </p> <p>The path is relative to the root of the host address. </p> <p>This file, if specified, is downloaded and processed during Incremental Index operations. If no file is specified, the file listed under File Path is used instead. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical File Path </p> </td> 
   <td colname="col2"> <p>Specifies the path to the XML document that contains multiple sparse "rows" of information to be used during a Vertical Update. </p> <p>The path is relative to the root of the host address. </p> <p>This file, if specified, is downloaded and processed during Vertical Update operations. </p> <p> <b>Note</b>: This feature is not enabled by default. Contact Technical Support to activate the feature for your use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deletes File Path </p> </td> 
   <td colname="col2"> <p>Specifies the path to the simple flat text file, containing a single document identifier value per line. </p> <p>The path is relative to the root of the host address. </p> <p>This file, if specified, is downloaded and processed during Incremental Index operations. The values found in this file are used to construct "delete" requests to remove previously indexed documents. The values in this file must correspond to the values found in the Full or Incremental File Path files, in the column identified as the <span class="uicontrol"> Primary Key </span>. </p> <p> <b>Note</b>: This feature is not enabled by default. Contact Technical Support to activate the feature for your use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Protocol </p> </td> 
   <td colname="col2"> <p>Specifies the protocol that is used to access the file. You can choose from the following: </p> <p> 
     <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>If necessary, you may enter proper authentication credentials to access the HTTP server. </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>If necessary, you may enter proper authentication credentials to access the HTTPS server. </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>You must enter proper authentication credentials to access the FTP server. </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>You must enter proper authentication credentials to access the SFTP server. </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> File </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Itemtag </p> </td> 
   <td colname="col2"> <p>Identifies the XML element that you can use to identify individual XML lines in the data source file that you specified. </p> <p>For example, in the following Feed fragment of an Adobe XML document, the Itemtag value is <span class="codeph"> record </span>: </p> <p> 
     <codeblock>
       &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
      &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; 
      &lt;gsafeed&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
      &lt;record&nbsp;url=http://www.adobe.com/cfusion/marketplace_gsa/ 
      index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="http://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt; 
      &lt;metadata&gt; 
      &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
      &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
      dbreferenced/marketplaceicons/icn_air.png"/&gt; 
      &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
      &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; 
      &lt;/metadata&gt; 
      &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
      &lt;/record&gt; 
      &lt;record&nbsp;url=http://www.adobe.com/cfusion/marketplace_gsa/ 
      index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="http://www.adobe.com/cfusion/ 
      marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
      &lt;metadata&gt; 
      &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
      &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
      dbreferenced/marketplaceicons/icn_photoshop.png"/&gt; 
      &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt; 
      &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
      &lt;/metadata&gt; 
      &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
      &lt;/record&gt; 
      ... 
      &lt;record&gt; 
      ... 
      &lt;/record&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/group&gt; 
      &lt;/gsafeed&gt; 
       
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Minimum number of documents for indexing </p> </td> 
   <td colname="col2"> <p>If set to a positive value, this specifies the minimum number of records expected in the file downloaded. If fewer records are received, the index operation is aborted. </p> <p> <b>Note</b>: This feature is not enabled by default. Contact Technical Support to activate the feature for your use. </p> <p> <b>Note</b>: This feature is only used during full Index operations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Map </p> </td> 
   <td colname="col2"> <p>Lets you specify XML-element-to-metadata mappings, using XPath expressions. </p> <p> 
     <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tag </span> <p>Specifies an XPath representation of the parsed XML data. Using the example Adobe XML document above, under the option Itemtag, it could be mapped using the following syntax: </p> <p> 
        <codeblock>
          /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
         /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
         /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
         /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body 
        </codeblock> </p> <p>The above syntax translates as the following: </p> <p> 
        <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
         <li id="li_9958F9B40D42434195597DBA9F2AF28F"> 
          <codeblock>
            /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url 
          </codeblock> <p>The <span class="codeph"> displayurl </span> attribute of the <span class="codeph"> record </span> element maps to the metadata field <span class="codeph"> page-url </span>. </p> </li> 
         <li id="li_759013EA02CD48BE971A55B0A6A11424"> 
          <codeblock>
            /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title 
          </codeblock> <p>The <span class="codeph"> content </span> attribute of any <span class="codeph"> meta </span> element that is contained inside a <span class="codeph"> metadata </span> element, that is contained inside a <span class="codeph"> record </span> element, whose name attribute is <span class="codeph"> title </span>, maps to the metadata field <span class="codeph"> title </span>. </p> </li> 
         <li id="li_E741CA59197D462EB2946EDE874AFDC8"> 
          <codeblock>
            /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc 
          </codeblock> <p>The <span class="codeph"> content </span> attribute of any <span class="codeph"> meta </span> element that is contained inside a <span class="codeph"> metadata </span> element, that is contained inside the <span class="codeph"> record </span> element, whose name attribute is <span class="codeph"> description </span>, maps to the metadata field <span class="codeph"> desc </span>. </p> </li> 
         <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> 
          <codeblock>
            /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body 
          </codeblock> <p>The <span class="codeph"> content </span> attribute of any <span class="codeph"> meta </span> element that is contained within a <span class="codeph"> metadata </span> element, that is contained within the <span class="codeph"> record </span> element, whose name attribute is <span class="codeph"> description </span>, maps to the metadata field <span class="codeph"> body </span>. </p> </li> 
        </ul> </p> <p>XPath is a relatively complicated notation. More information is available at the following location: </p> <p>See <a href="http://www.w3schools.com/xpath/" scope="external" format="html"> http://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Field </span> <p>Defines the name attribute value that is used for each generated <span class="codeph"> &lt;meta&gt; </span> tag. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadata? </span> <p>Causes <span class="uicontrol"> Field </span> to become a drop-down list from which you can select defined metadata fields for the current account. </p> <p>The <span class="uicontrol"> Field </span> value can be an undefined metadata field, if desired. An undefined metadata field is sometimes useful to create content used by <span class="wintitle"> Filtering Script </span>. </p> <p>See <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> About Filtering Script </a>. </p> <p>When Index Connector processes XML documents with multiple hits on any map field, the multiple values are concatenated into a single value in the resulting cached document. By default, these values are combined using a comma delimiter. However, suppose that the corresponding <span class="wintitle"> Field </span> value is a defined metadata field. In addition, that field has the <span class="wintitle"> Allow Lists </span> attribute set. In this case, the field's List Delimiters value, which is the first delimiter defined, is used in the concatenation. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Primary Key? </span> <p>Only one map definition is identified as the primary key. This field becomes the unique reference that is presented when this document is added to the index. This value is used in the document’s URL in the Index. </p> <p>The <span class="uicontrol"> Primary Key </span> values must be unique across all of the documents represented by the Index Connector configuration - any duplicates encountered will be ignored. If your source documents don't contain a single unique value for use as <span class="uicontrol"> Primary Key </span>, but two or more fields taken together <i>can</i> form a unique identifier, you can define the <span class="uicontrol"> Primary Key </span> by combining multiple <span class="uicontrol"> Tag </span> definitions with a vertical bar ("|") delimiting the values. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC81F"> <span class="uicontrol"> Strip HTML? </span> <p>When this option is checked, any HTML tags found in this field's data are removed. </p> </li> 
      <li id="li_5E829D1D0DBD4BB7AAB5DB983053D248"> <span class="uicontrol"> Use for Delete? </span> <p>Used during Incremental Index operations, only. Records matching this XPath pattern identify items for deletion. The <span class="uicontrol"> Primary Key </span> value for each such record is used to construct "delete" requests, as with Delete File Path. </p> <p> <b>Note</b>: This feature is not enabled by default. Contact Technical Support to activate the feature for your use. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Action </span> <p>Lets you add rows to the map or remove rows from the map. The order of the rows is not important. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Data source type: XML</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enabled </p> </td> 
   <td colname="col2"> <p>Turns the configuration "on" to crawl and index. Or, you can turn "off" the configuration to prevent crawling and indexing. </p> <p> <b>Note</b>: Disabled Index Connector configurations are ignored if they are found in an entrypoint list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Host Address </p> </td> 
   <td colname="col2"> <p>Specifies the URL address of the host system where the data source file is found. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File Path </p> </td> 
   <td colname="col2"> <p>Specifies the path to the master XML document that contains links ( 
     <userinput>
       &lt;a&gt; 
     </userinput>) to individual XML documents. </p> <p>The path is relative to the root of the host address. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Protocol </p> </td> 
   <td colname="col2"> <p>Specifies the protocol that is used to access the file. You can choose from the following: </p> <p> 
     <ul id="ul_EA4EB7953D68483FAD75753B2EE70E74"> 
      <li id="li_537F24C6B2AB435CB7C14117663D7B3F"> HTTP <p>If necessary, you may enter proper authentication credentials to access the HTTP server. </p> </li> 
      <li id="li_8C13C93C52364FFA8B9B18830CDB223C"> HTTPS <p>If necessary, you may enter proper authentication credentials to access the HTTPS server. </p> </li> 
      <li id="li_2F967B5675254C949B31EAB19910751C"> FTP <p>You must enter proper authentication credentials to access the FTP server. </p> </li> 
      <li id="li_C24BE4C1DE79488AA64C7133D78CD3A6"> SFTP <p>You must enter proper authentication credentials to access the SFTP server. </p> </li> 
      <li id="li_7581C21CFC104986A361F62BD7A370C1"> File </li> 
     </ul> </p> <p> <b>Note</b>: The Protocol setting is only used when there is information specified in the Host Address and/or File Path fields. Individual XML documents are downloaded using either HTTP or HTTPS, according to their URL specifications. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Itemtag </p> </td> 
   <td colname="col2"> <p>Identifies the XML element that defines a "row" in the data source file that you specified. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Map </p> </td> 
   <td colname="col2"> <p>Lets you specify column-to-metadata mappings, using column numbers. </p> <p> 
     <ul id="ul_06F50CBA0AA64C7CB1AFAE076E629A64"> 
      <li id="li_0FA2502869BA40DC93D790B79E15A9D2"> <span class="uicontrol"> Tag </span> <p>Specifies an XPath representation of the parsed XML data. Using the example Adobe XML document above, under the option Itemtag, you can map it using the following syntax: </p> <p> 
        <codeblock>
          /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
         /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
         /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
         /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body 
        </codeblock> </p> <p>The above syntax translates as the following: </p> <p> 
        <ul id="ul_F8C536E6E54546D9AA5B22B879C0AF39"> 
         <li id="li_78A35DFFF1B4496CAC6EDC7B1E991F29"> 
          <codeblock>
            /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url 
          </codeblock> <p>The <span class="codeph"> displayurl </span> attribute of the <span class="codeph"> record </span> element maps to the metadata field <span class="codeph"> page-url </span>. </p> </li> 
         <li id="li_FA7DF3D1942248B98660F3D0C82F4563"> 
          <codeblock>
            /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title 
          </codeblock> <p>The <span class="codeph"> content </span> attribute of any <span class="codeph"> meta </span> element that is contained inside a <span class="codeph"> metadata </span> element, that is contained inside a <span class="codeph"> record </span> element, whose name attribute is <span class="codeph"> title </span>, maps to the metadata field <span class="codeph"> title </span>. </p> </li> 
         <li id="li_D8000A116FF84DE59ED19C656DDD3BC1"> 
          <codeblock>
            /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc 
          </codeblock> <p>The <span class="codeph"> content </span> attribute of any <span class="codeph"> meta </span> element that is contained inside a <span class="codeph"> metadata </span> element, that is contained inside the <span class="codeph"> record </span> element, whose name attribute is <span class="codeph"> description </span>, maps to the metadata field <span class="codeph"> desc </span>. </p> </li> 
         <li id="li_7FA6A53DFD3D42A98B7BA17CC29DDB81"> 
          <codeblock>
            /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body 
          </codeblock> <p>The <span class="codeph"> content </span> attribute of any <span class="codeph"> meta </span> element that is contained within a <span class="codeph"> metadata </span> element, that is contained within the <span class="codeph"> record </span> element, whose name attribute is <span class="codeph"> description </span>, maps to the metadata field <span class="codeph"> body </span>. </p> </li> 
        </ul> </p> <p>XPath is a relatively complicated notation. More information is available at the following location: </p> <p>See <a href="http://www.w3schools.com/xpath/" scope="external" format="html"> http://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_84999D07E0AE4265BC7928BBB49957B9"> <span class="uicontrol"> Field </span> <p>Defines the name attribute value that is used for each generated &lt;meta&gt; tag. </p> </li> 
      <li id="li_E125788D0F5242958BD790E26A675C20"> <span class="uicontrol"> Metadata? </span> <p>Causes <span class="uicontrol"> Field </span> to become a drop-down list from which you can select defined metadata fields for the current account. </p> <p>The <span class="uicontrol"> Field </span> value can be an undefined metadata field, if desired. An undefined metadata field is sometimes useful to create content used by <span class="wintitle"> Filtering Script </span>. </p> <p>See <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> About Filtering Script </a>. </p> <p>When Index Connector processes XML documents with multiple hits on any map field, the multiple values are concatenated into a single value in the resulting cached document. By default, these values are combined using a comma delimiter. However, suppose that the corresponding <span class="wintitle"> Field </span> value is a defined metadata field. In addition, that field has the <span class="wintitle"> Allow Lists </span> attribute set. In this case, the field's List Delimiters value, which is the first delimiter defined, is used in the concatenation. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824609F"> <span class="uicontrol"> Primary Key? </span> <p>Only one map definition is identified as the primary key. This field becomes the unique reference that is presented when this document is added to the index. This value is used in the document’s URL in the Index. </p> <p>The <span class="uicontrol"> Primary Key </span> values must be unique across all of the documents represented by the Index Connector configuration - any duplicates encountered will be ignored. If your source documents don't contain a single unique value for use as <span class="uicontrol"> Primary Key </span>, but two or more fields taken together <i>can</i> form a unique identifier, you can define the <span class="uicontrol"> Primary Key </span> by combining multiple <span class="uicontrol"> Tag </span> definitions with a vertical bar ("|") delimiting the values. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824610G"> <span class="uicontrol"> Strip HTML? </span> <p>When this option is checked, any HTML tags found in this field's data are removed. </p> </li> 
      <li id="li_6302D18971AD439FBECE27742649C56B"> <span class="uicontrol"> Action </span> <p>Lets you add rows to the map or remove rows from the map. The order of the rows is not important. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Optional) Click **[!UICONTROL Setup Maps]** to download a sample of your data source. The data is examined for indexing suitability. This feature is available for Text and Feed Types, only.
1. (Optional) Click **[!UICONTROL Preview]** to test the actual working of the configuration. This feature is available for Text and Feed Types, only.
1. Click **[!UICONTROL Add]** to add the configuration to the [!DNL Index Connector Definitions] page and to the [!DNL Index Connector Configurations] drop-down list on the [!DNL URL Entrypoints] page.

   See [About URL Entrypoints](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573). 
1. On the [!DNL Index Connector Definitions] page, click **[!UICONTROL rebuild your staged site index]**.
1. (Optional) On the [!DNL Index Connector Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing an Index Connector definition {#task_DCFC9C6A9964421DB5AB6C25DEE98DE9}

You can edit an existing Index Connector that you have defined.

<!-- 

t_editing_an_index_connector_definition.xml

 -->

>[!NOTE]
>
>Not all options are available for you to change, such as the Index Connector Name or Type from the [!DNL Type] drop-down list.

**To edit an Index Connector definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. On the [!DNL Index Connector] page, under the [!DNL Actions] column heading, click **[!UICONTROL Edit]** for an Index Connector definition name whose settings you want to change.
1. On the [!DNL Index Connector Edit] page, set the options you want.

   See the table of options under [Adding an Index Connector definition](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) On the [!DNL Index Connector Definitions] page, click **[!UICONTROL rebuild your staged site index]**.
1. (Optional) On the [!DNL Index Connector Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Viewing the settings of an Index Connector definition {#task_D0B71A7426E54247BDB3468EC576D871}

You can review the configuration settings of an existing index connector definition.

<!-- 

t_viewing_the_settings_of_an_index_connector_definition.xml

 -->

After an Index Connector definition is added to the [!DNL Index Connector Definitions] page, you cannot change its Type setting. Instead, you must delete the definition and then add a new one.

**To view the settings of an Index Connector definition ** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. On the [!DNL Index Connector] page, under the [!DNL Actions] column heading, click **[!UICONTROL Edit]** for an Index Connector definition name whose settings you want to review or edit.

## Copying an Index Connector definition {#task_3AD55DF07FC44A748D0EFDAB7B35699B}

You can copy an existing Index Connector definition to use as the basis for a new Index Connector that you want to create.

<!-- 

t_copying_an_index_connector_definition.xml

 -->

When copying an Index Connector definition, the copied definition is disabled by default. To enable or "turn on" the definition, you must edit it from the [!DNL Index Connector Edit] page, and select **[!UICONTROL Enable]**.

See [Editing an Index Connector definition](../c-about-settings-menu/c-about-crawling-menu.md#task_DCFC9C6A9964421DB5AB6C25DEE98DE9).

**To copy an Index Connector definition ** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. On the [!DNL Index Connector] page, under the [!DNL Actions] column heading, click **[!UICONTROL Copy]** for an Index Connector definition name whose settings you want to duplicate.
1. On the [!DNL Index Connector Copy] page, enter the new name of the definition.
1. Click **[!UICONTROL Copy]**.
1. (Optional) On the [!DNL Index Connector Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Renaming an Index Connector definition {#task_5132118FC21B47D99881E0ED425225D7}

You can change the name of an existing Index Connector definition.

<!-- 

t_renaming_an_index_connector_definition.xml

 -->

After you rename the definition, check **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. You want to ensure that the new definition name is reflected in the drop-down list on the [!DNL URL Entrypoints] page.

See [Adding multiple URL entry points that you want indexed](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

**To rename an Index Connector definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. On the [!DNL Index Connector] page, under the [!DNL Actions] column heading, click **[!UICONTROL Rename]** for Index Connector definition name that you want to change.
1. On the [!DNL Index Connector Rename] page, enter the new name of the definition in the [!DNL Name] field.
1. Click **[!UICONTROL Rename]**.
1. Click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. If the previous Index Connector's name is present in the list, remove it, and add the newly renamed entry.

   See [Adding multiple URL entry points that you want indexed](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45). 1. (Optional) On the [!DNL Index Connector Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting an Index Connector definition {#task_6B0BD5D0C09F4597A401B0F3AC7C7EA7}

You can delete an existing Index Connector definition that you no longer need or use.

<!-- 

t_deleting_an_index_connector_definition.xml

 -->

**To delete an Index Connector definition ** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. On the [!DNL Index Connector Definitions] page, under the [!DNL Actions] column heading, click **[!UICONTROL Delete]** for the Index Connector definition name you want to remove.
1. On the [!DNL Index Connector Delete] page, click **[!UICONTROL Delete]**.
