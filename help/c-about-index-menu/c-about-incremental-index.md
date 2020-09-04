---
description: You can use Incremental Index to index "pieces" of your live or staged website, such as a collection of frequently changed pages.
seo-description: You can use Incremental Index to index "pieces" of your live or staged website, such as a collection of frequently changed pages.
seo-title: About Incremental Index
solution: Target
subtopic: Incremental Index
title: About Incremental Index
topic: Index,Site search and merchandising
uuid: b1ee9b08-dcbe-4ffe-b0b4-d379daaac9b5
---

# About Incremental Index{#about-incremental-index}

You can use Incremental Index to index "pieces" of your live or staged website, such as a collection of frequently changed pages.

## Using Incremental Index {#concept_A7770F0552D14C47B3DDB65DB78FFFEE}

An incremental index takes only seconds to perform and is useful on large capacity websites that can take many hours to completely index.

When you generate an incremental index, status information is displayed, such as start time, elapsed time, and errors during the indexing process. Information about the status of your last index is also displayed.

You can stop or restart the incremental indexing process at any time.

While the new incremental index builds for your live website, customers can continue to search your site using your last incremental index. 

## Configuring an incremental index of a staged website {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

You can configure what website pages you want to include in your incremental Index by specifying website URLs and URL masks.

**To configure an incremental index of a staged website** 

1. On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Configuration]**.
1. On the **[!UICONTROL Incremental Index Configuration]** page, use the various fields to specify which pages that you want to index.

    <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Field </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Add or Update URLs </p> </td> 
      <td colname="col2"> <p>Specify URLs. </p> <p>The search robot only indexes the specified documents that have changed since the last time you indexed. </p> <p>Additionally, the search robot follows links that are contained within the specified documents and indexes only those documents that have changed. </p> <p>This field must contain document URLs only and not masks as in the following example: </p> <p> 
        <code>
          https://www.mydomain.com/products/new.html 
        </code> </p> <p>You can use the following keywords with the URL: </p> <p> 
        <ul id="ul_62D1082ACBD547D092B10D72C56A3A1E"> 
          <li id="li_32C2B21DE75C4459908384CC44822F7D"> 
          <code>
            noindex 
          </code> <p>If you do not want to index the text on the page that matches a specified URL, but you want to follow the page's links, add 
            <code>
              noindex 
            </code> after the URL as in the following example: </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html noindex 
            </code> </p> <p>Be sure you separate 
            <code>
              noindex 
            </code> from the URL with a space; a comma is not a valid separator. </p> </li> 
          <li id="li_33AB62B669084BF7B976F4308715E435"> 
          <code>
            nofollow 
          </code> <p>If you want to index the text on the page that matches the specified URL, but you do not want to follow the page's links, add 
            <code>
              nofollow 
            </code> after the URL as in the following example: </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html nofollow 
            </code> </p> <p> Be sure you separate 
            <code>
              nofollow 
            </code> from the URL with a space; a comma is not a valid separator. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Find and Update URL Masks </p> </td> 
      <td colname="col2"> <p>Specify simple URL masks—full path, partial path, or paths that use wild cards or regular expressions. </p> <p>The search robot finds all matching documents and indexes only those documents that have changed since the last time you indexed. </p> <p>Additionally, the search robot follows links that are contained within the matching documents and indexes only those pages that have changed. For example: </p> <p> 
      <code>
        https://www.mydomain.com/products/household/*.html 
      </code> </p> <p>You can also use regular expressions as in the following example: </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/household/.*\.html$ 
      </code> </p> <p>See <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Regular Expressions</a>. </p> <p>You can also use the keywords 
      <code>
        nofollow 
      </code> and 
      <code>
        noindex 
      </code> as described in <span class="uicontrol"> Add or Update URLs </span> above. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Include and Exclude URL Masks </p> </td> 
      <td colname="col2"> <p>Specify simple include or exclude URL masks—full path, partial path, or paths that use wild cards or regular expressions. </p> <p>The search robot finds and indexes ("include") or ignores ("exclude") documents based on the type of mask that is specified. </p> <p> When indexing a site, directions are followed in order of appearance. For example, the following list of masks: </p> <p> 
      <code>
        include https://www.mydomain.com/products/household/lightbulbs*.html 
      </code> </p> <p> 
      <code>
        exclude https://www.mydomain.com/products/ 
      </code> </p> <p>indexes the pages 
      <code>
        lightbulbs1.html 
      </code> and 
      <code>
        lightbulbs2.html 
      </code>. However, it does not index any other pages that are listed under the products directory. </p> <p>A URL mask that appears first always takes precedence over one that appears later in the list. Additionally, if the search robot encounters a document that matches both an include mask and an exclude mask, the mask that is listed first takes precedence. </p> <p>You can also use the keywords 
      <code>
        nofollow 
      </code> and 
      <code>
        noindex 
      </code> as described in <span class="uicontrol"> Add or Update URLs </span> above. </p> <p>See <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> About URL Masks</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Include and Exclude Date Masks </p> </td> 
      <td colname="col2"> <p>Specify simple include or exclude date masks—full path, partial path, or paths that use wild cards or regular expressions. </p> <p>The search robot finds and indexes ("include") or ignores ("exclude") documents based on both the URL and the date of documents. </p> <p>You can use the following types of date masks: </p> <p> 
      <ul id="ul_8958ED54C8EF405AA259236595ED3ABA"> 
      <li id="li_0A7841767E004F088CA6FA42E99B9F32"> 
      <code>
        include-days NNN 
      </code> <p>The search robot indexes all documents that match the specified URL mask and are NNN days or more old. </p> <p>You can follow the URL mask with one or more of the following keywords: 
        <ul id="ul_22A38D5F38B344ABB02B16EB1865813B"> 
        <li id="li_B89CC37DC2A1428185E86FFCB9DDB193">nofollow </li> 
        <li id="li_C2579B3A338D4AF987C3F518806734B0">noindex </li> 
        <li id="li_0527BF7103F34B83AC3E684069B899F7">server-date </li> 
        </ul> </p> <p>For example, the following mask includes all documents in the /archive/support folder that are 0 days or older: </p> <p> 
        <code>
          include-days 0 https://www.mydomain.com/archive/support/ 
        </code> </p> </li> 
      <li id="li_7663ABED40DD4E159F746E4F92BB6407"> 
      <code>
        include-date YYYY-MM-DD 
      </code> <p>The search robot indexes all documents that match the specified URL mask and are as old or older than the YYYY-MM-DD date. </p> <p>You can follow the URL mask with one or more of the following keywords: </p> <p> 
        <ul id="ul_57BF37A413BB4A4D962863DACE56F395"> 
        <li id="li_88CAB9AB583B4754A5C53478BD1108FF">nofollow </li> 
        <li id="li_999E1CD34FDE4A1B9C332B4AA8C2887D">noindex </li> 
        <li id="li_05646FACF3524D2A9E201A23770E357F"> server-date </li> 
        </ul> </p> <p>The following mask example includes all documents in the /archive/ folder dated on or before July 25, 2011: </p> <p> 
        <code>
          include-date 2011-07-25 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      <li id="li_172692DEDA8744B3AA492701D24C2D80"> 
      <code>
        exclude-days NNN 
      </code> <p>Disable indexing of all documents that match the specified URL mask and are NNN days or more old. </p> <p>Optionally, you can follow the URL mask by the keyword 
        <code>
          server-date 
        </code>. </p> <p>The following mask example excludes all PDF files that are 90 days old or older from your index: </p> <p> 
        <code>
          exclude-days 90 *.pdf 
        </code> </p> </li> 
      <li id="li_26078517744D4AECBE1351008926CBAE"> 
      <code>
        exclude-date YYYY-MM-DD 
      </code> <p>Disable indexing of all documents that match the specified URL mask and are as old or older than the date YYYY-MM-DD. </p> <p>Optionally, you can follow the URL mask by the keyword 
        <code>
          server-date 
        </code>. </p> <p>The following mask example excludes all documents in the /archive/ folder dated on or before April 23, 2004: </p> <p> 
        <code>
          exclude-date 2004-04-23 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      </ul> </p> <p>See <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_F4F1F58A646F4A86B8650EC46FDCEF66" type="concept" format="dita" scope="local"> About Date Masks</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delete URLs </p> </td> 
      <td colname="col2"> <p>Specify URLs. </p> <p>The search robot finds and deletes the specified documents from your search index. If a specified page is already in your search index, the robot deletes it before it adds or updates any other pages. </p> <p>This field must contain only document URLs, and not masks. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Find and Delete URL Masks </p> </td> 
      <td colname="col2"> <p>Specify simple URL masks—full path, partial path, or ones that use wild cards or regular expressions. </p> <p>If the specified URL mask matches pages in your search index, the search robot deletes the pages before it adds or updates any other pages. For example: </p> <p> 
      <code>
        https://www.mydomain.com/products/1998/household/* 
      </code> </p> <p>You can also use regular expressions as in the following example: </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/199[567]/.*$ 
      </code> </p> <p>See <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Regular Expressions</a>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Setting the incremental index schedule for a live website {#task_2A46BA189ECC4317A9D5C6E99A336F33}

You can select the Incremental Index frequency and the base time that is used to crawl and update your incremental index.

The time that you select is local according to the time zone that is configured in Account Settings.

See [Configuring your account settings](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Web servers are often scheduled to go down for maintenance in the middle of the night. If your server is down during a scheduled index time, the indexing process will fail. Be sure that you select a time of day when your web server is available.

The index schedule only applies to your live index; you cannot schedule staged indexes.

**To set the incremental index schedule for a live website** 

1. On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Schedule]**.
1. On the In the **[!UICONTROL Incremental Index Schedule]** page, in the **[!UICONTROL Incrementally Index]** drop-down list, select the indexing frequency in hours or minutes.
1. In the **[!UICONTROL Base Time]** drop-down list, select the starting time when you want to regenerate a new incremental index.
1. Click **[!UICONTROL Save Changes]**.

## Running an incremental index of a live or staged website {#task_9BFB6157F3884B2FAECB7E0E9CA318CB}

You can use Incremental Index to index "pieces" of your live or staged website, such as a collection of frequently changed pages.

**To run an incremental index of a live or staged website** 

1. On the product menu, do one of the following:

    * Click **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Index]**. 
    
    * Click **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Index]**.

1. Click **[!UICONTROL Incremental Index Now]**.
1. (Optional) If indexing errors occurred, click **[!UICONTROL View Errors]** to view the associated log.

## Viewing the incremental index log of a live or staged website {#task_E668E1F1240C476DAA1CA783DC728232}

When a live incremental index or a staged incremental index is complete, you can view its associated log to troubleshoot any errors that occurred.


You cannot export logs, nor save them. The log remains available for viewing until the new index occurs.

**To view the incremental index log of a live or staged website** 

1. On the product menu, do one of the following:

    * Click **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Log]**. 
    
    * Click **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Log]**.

1. On the log page, at the top or bottom, do any of the following:

    * Use the navigation options **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]**, or **[!UICONTROL Go to line]** to move through the log. 
    
    * Use the display options **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]**, or **[!UICONTROL Show]** to refine what you see.

