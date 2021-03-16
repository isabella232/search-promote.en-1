---
description: With Scripted Index you can write, update, and maintain incremental indexing options without the need to log in. The search robot reads instructions from a text file that is hosted on your server.
solution: Target
subtopic: Scripted Index
title: About Scripted Index
topic: Index,Site search and merchandising
uuid: 51e726ad-414b-4cbd-8a68-fefc3cf9b565
---

# About Scripted Index{#about-scripted-index}

With Scripted Index you can write, update, and maintain incremental indexing options without the need to log in. The search robot reads instructions from a text file that is hosted on your server.

## Using Scripted Index {#concept_34F58D551BC04BFB8ADC294B9DA9199D}

## About configuring scripted incremental indexing {#section_161D254065E143F3A39F3FC09C400090}

To use Scripted Index, you use the Scripted Incremental Index Configuration page to specify the URL to a script file (a plain text file) that is located on your server. For example, `https://www.mysite.com/indexlist.txt`. As your site changes, you can add command blocks to the text file either manually or automatically (with a script triggered by the arrival of information from a news feed, stock ticker, or other altered file).

When the scripted incremental index begins, the search robot reads the text file and runs the new commands that are found in that file. By default, the search robot processes only the new commands, which are determined by the file date. Unless you check **[!UICONTROL Clear Date]** at the time you configure Scripted Index, the search robot "remembers" the date-specifier of the most recently processed block.

## About the script file {#section_B312E40539F44C6583B4F9637D428E19}

The script file that you specify in the URL is a plain text file that is located on your server. You can use carriage returns, line feeds, or both for the end-of-line sequence. A blank line contains zero or more white space characters followed by an end-of-line sequence. All commands are case-insensitive.

The text file is organized in blocks that describe the information that the search robot uses when it performs a scripted incremental index.

Blocks are ordered by date, with the oldest blocks at the top of the text file, and the most recent blocks at the bottom. Each block begins with a single line date-command and a date-specifier command, and ends with a blank-line separator as in the following block example (in between are several commands):

A leading zero is required for all ordinal dates lower than the 10th when using the HTTP 1.1 style. For example, November 6th is 06 Nov, not 6 Nov.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Command </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>date-command </p> </td> 
   <td colname="col2"> <p>The first line of each block starts with one of two date commands: </p> <p> 
     <ul id="ul_9C1B229B7F1846C490B853FC34989E77"> 
      <li id="li_31FEF1A7163842BDBB0ABE779D07045A"> <span class="codeph"> date </span> <p>Use the "date" command to indicate that the date-specifier will consist of a day, date, time, and time zone. </p> </li> 
      <li id="li_0918D5B090014C1A852CB80BB7C2867C"> <span class="codeph"> seconds </span> <p>Use <span class="codeph"> seconds </span> to indicate that the date-specifier will consist of a time in epoch seconds (for example, 784111777). When using <span class="codeph"> seconds </span>, make sure that the number of seconds increases between blocks. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>date-specifier </p> </td> 
   <td colname="col2"> <p>The <span class="codeph"> date-specifier </span> command typically records either the ordinal date and time (date command) or the time in epoch seconds (seconds command) that the block information was added to the file. For example: </p> <p> <code> date&nbsp;Sun,&nbsp;06&nbsp;Nov&nbsp;1994&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.1&nbsp;style) 
      date&nbsp;Sunday,&nbsp;06-Nov-94&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.0&nbsp;style) 
      date&nbsp;Sun&nbsp;Nov&nbsp;6&nbsp;08:49:37&nbsp;1994&nbsp;(Unix&nbsp;asctime()&nbsp;date&nbsp;style) 
      seconds&nbsp;784111777&nbsp;(Unix&nbsp;epoch-seconds&nbsp;style) </code> </p> <p>A leading zero is required for all ordinal dates lower than the 10th when using the HTTP 1.1 style. For example, November 6th is 06 Nov, not 6 Nov. </p> <p>The search robot "remembers" the date-specifier of the most recently processed block and only indexes information that it considers to be "newer." (Real-time does not matter to the search robot. Instead, the time in relation to other previously processed times is what matters.) </p> <p>After the search robot reads a block with a date-specifier of 10:00 p.m, for example, it does not read any blocks that record times before 10:00 p.m., regardless of when the index operation runs. In a worst-case scenario, you might mistakenly enter the year "2040" instead of "2004" in your date-specifier. In such an instance, the search robot indexes the 2040 block during the next indexing operation and then refuses to read any other blocks of information (unless one post-dates 2040). If this should happen, remove all previously processed blocks from the text file, click <span class="uicontrol"> Clear Date </span>, and then push it live. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>comment line </p> </td> 
   <td colname="col2"> <p>Begin comment lines with the "#" character. </p> <p>Each comment line must be a line of its own; you cannot type end-of-line comments. </p> <p>A comment line is not considered a blank line. It can also appear anywhere in a block, even before a date or seconds command as in the following example: </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;#Added&nbsp;by&nbsp;Cathy&nbsp;Read&nbsp;after&nbsp;the&nbsp;Y2K&nbsp;seminar 
      &nbsp;&nbsp;&nbsp;&nbsp;date&nbsp;Mon,&nbsp;29&nbsp;Dec&nbsp;1999&nbsp;09:32:20&nbsp;GMT&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>action-command </p> </td> 
   <td colname="col2"> <p>Each text block can contain as many action commands as you want. The following action-command options correspond to those for standard incremental indexing: </p> <p> 
     <ul id="ul_8E1435350A0F416BB8F7826CD3886E74"> 
      <li id="li_22181666628C48A28A6A0BA1F7CA8E77"> 
       <code>
         add 
       </code> <p>Use with URL. The search robot only indexes the specified URLs that have changed since your last indexing operation. Additionally, the search robot follows links that are contained within specified documents and indexes only those documents that have changed. </p> <p>You can follow the URL with 
        <code>
          nofollow 
        </code> or 
        <code>
          noindex 
        </code> keywords as in the following example: </p> <p> <code> add&amp;nbsp;https://www.mydomain.com/&amp;nbsp;noindex </code> </p> </li> 
      <li id="li_8E47BF07DB24417083883F5BF40D6B9E"> 
       <code>
         update 
       </code> <p>Use with URL mask. The search robot finds and updates all documents that match the specified URL mask. </p> <p>You can follow the URL with 
        <code>
          nofollow 
        </code> or 
        <code>
          noindex 
        </code> keywords as in the following example: </p> <p> <code> update&amp;nbsp;https://www.mydomain.com/products/ </code> </p> </li> 
      <li id="li_B3EC8B1670D54F66A1D8411A694EF7E4"> 
       <code>
         include 
       </code> or 
       <code>
         exclude 
       </code> <p>Use with URL mask. The search robot finds and indexes ("include") or ignores ("exclude") documents based on the type of mask specified. </p> <p>For example, </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/products/household/lightbulbs*.html </code> </p> <p>or </p> <p> <code> exclude&amp;nbsp;https://www.mydomain.com/archive/ </code> </p> </li> 
      <li id="li_050B54B735F0475E93806455FA6DC6A5"> 
       <code>
         include-date 
       </code> or 
       <code>
         exclude-date 
       </code> <p>Use with URL mask. The search robot finds and indexes ("include") or ignores ("exclude") documents based on the both the URL and the date of documents. The following types of masks are available: </p> <p> 
        <ul id="ul_23A15CB492214B86BE84D8E6EA1820AE"> 
         <li id="li_0C7051AC3B5A4C57A3E477F7B6246611"> 
          <code>
            include-days NNN 
          </code> <p>The search robot indexes all documents that match the specified URL mask and are NNN days or more old. </p> <p>You can follow the URL mask with the keywords 
           <code>
             nofollow 
           </code>, 
           <code>
             noindex 
           </code>, and/or 
           <code>
             server-date 
           </code>. </p> </li> 
         <li id="li_983A10E2ED5D434EA9031F32143F4EF4"> 
          <code>
            include-date YYYY-MM-DD 
          </code> <p> The search robot indexes all documents that match the specified URL mask and are as old or older than the date YYYY-MM-DD, where "YYYY" is the 4 digit year, "MM" is the one- or two-digit month (1-12), and "DD" is the one- or two-digit day (1-31). </p> <p>You can follow the URL mask with the keywords 
           <code>
             nofollow 
           </code>, 
           <code>
             noindex 
           </code>, and/or 
           <code>
             server-date 
           </code>. </p> </li> 
         <li id="li_733CE1B748024CECA7FBE00D7BC7B88A"> 
          <code>
            exclude-days NNN 
          </code> <p> Disables indexing of all documents that match the specified URL mask and are NNN days or more old. </p> <p>You can follow the URL mask with the keyword 
           <code>
             server-date 
           </code>. </p> </li> 
         <li id="li_90056A0B96CC4DA3854711860A15CE89"> 
          <code>
            exclude-date YYYY-MM-DD 
          </code> <p>Disables indexing of all documents that match the specified URL mask and are as old or older than the date YYYY-MM-DD. </p> <p>You can follow the URL mask with the keyword 
           <code>
             server-date 
           </code>. </p> </li> 
        </ul> </p> </li> 
      <li id="li_AA78F22B60FE4535BE73BA87A8992C08"> 
       <code>
         delete 
       </code> <p>Specify URLs. The search robot removes documents from the index that are identified by the URL. </p> </li> 
      <li id="li_9C63061568AA4D57A4FEBCF6DB9194EC"> 
       <code>
         deletemask 
       </code> <p>The search robot removes documents from the index that match the specified URL mask. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

See also [About URL Masks](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

## Script file example {#section_9F580F20E7214751B157A28B392BD64E}

In the following script file example, the search robot processes the blocks provided that the date-specifiers post-date the date-specifier of the most recently processed block. If that is the case, then the following indexing operations occur:

* Deletes `y2k-problems.html` from the index. 
* Adds `no-y2k-problems.html` to the search index and does not follow any of the links for `no-y2k-problems.html`. 

* While crawling, exclude URLs that match `housewares.htm` and `lightfixtures.htm`l from the search index. 

* Include all other directories and documents under `www.mydomain.com`. 
* Update all documents within the `products` and `information` directories, crawling and indexing all subsidiary links that have changed since the last indexing operation. 

* While crawling, exclude URLs in the `archive` section of the website if they are dated on or before January 1, 1999. 
* Exclude URLs that match `housewares.html` and `lightfixtures.html` from the search index. 

* Index files in the `help` directory, but do not crawl or index any links from those files. 
* Crawl and index any other files encountered for `www.mydomain.com`.

```
# Start of file. 
# Added by John Smith 
date Sat, 01 Jan 2004 16:05:53 PST 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/ 
delete https://www.mydomain.com/y2k-problems.html 
add https://www.mydomain.com/no-y2k-problems.html nofollow 
 
date Sun, 02 Jan 2004 20:19:08 PST 
# Added by the wire service updater 
exclude-date 1999-01-01 https://www.mydomain.com/archive server-date 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/help/ nofollow 
include https://www.mydomain.com/ 
# no add files, just update existing files 
# update all files in the "products" directory 
update https://www.mydomain.com/products/ 
# update all files in the "information" directory 
update regexp ^https://www\.mydomain\.com/information/.*$ 
# End of file.
```

## Configuring a scripted incremental index {#task_05AE040FE75E40FFAA5E10B6B6D4D255}

You can specify a script that you have created that writes, updates, and maintains an incremental index, without the need to log in. The search robot reads instructions from the text file that is hosted on your server to perform the incremental index.

**To configure a scripted incremental index** 

1. On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Configuration]**.
1. On the **[!UICONTROL Scripted Incremental Index Configuration]** page, in the **[!UICONTROL Script File URL]**, enter the URL to the text file script that is located on your server.

   See [About Scripted Index](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D). 
1. (Optional) Check **[!UICONTROL Clear Date]** if you do not want the search robot to "remember" the date-specifier of the most recently processed block.

   By default, the search robot processes only new blocks of commands that are found in the text file, which is determined by the file's date. If you do not want the default, check **[!UICONTROL Clear Date]**. 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Setting the scripted incremental index schedule for a live website {#task_B3A87AC4AC784507859C23B9062BA11C}

You can schedule scripted incremental indexing to occur at regular intervals throughout the day.

The base time that you select is local according to the time zone that is configured in Account Settings.

See [Configuring your account settings](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Web servers are often scheduled to go down for maintenance in the middle of the night. If your server is down during a scheduled index time, the indexing process will fail. Be sure that you select a time of day when your web server is available.

The index schedule only applies to your live index; you cannot schedule staged incremental indexes.

**To set the scripted incremental index schedule for a live website** 

1. On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Schedule]**.
1. On the **[!UICONTROL Scripted Incremental Index Schedule]** page, in the **[!UICONTROL Read the Scripted Incrementally Indexing File]** drop-down list, select the frequency that you want the scripted incremental index text file to run, in hours or minutes.
1. In the **[!UICONTROL Base Time]** drop-down list, select the starting time when you want to regenerate a new scripted incremental index.
1. Click **[!UICONTROL Save Changes]**.

## Running a scripted incremental index of a live or staged website {#task_6E6FC76EE1E84A5FADB3B67AD7B1DACB}

You can use Scripted Incremental Index to index "pieces" of your live or staged website, such as a collection of frequently changed pages, all without the need to log in.

To use this feature, be sure that you have configure a scripted incremental index text file.

See [Configuring a scripted incremental index](../c-about-index-menu/c-about-scripted-index.md#task_05AE040FE75E40FFAA5E10B6B6D4D255).

**To run a scripted incremental index of a live or staged website** 

1. On the product menu, do one of the following:

    * Click **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Index]**. 
    * Click **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Index]**.

1. Click **[!UICONTROL Scripted Index Now]**.
1. (Optional) If indexing errors occurred, click **[!UICONTROL View Errors]** to view the associated log.

## Viewing the scripted incremental index log of a live or staged website {#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7}

When a live full scripted index or a staged full scripted index is complete, you can view its associated log to troubleshoot any errors that occurred.

You cannot export logs, nor save them. However, the log remains available for viewing until the new index occurs.

**To view the incremental index log of a live or staged website** 

1. On the product menu, do one of the following:

    * Click **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Log]**. 
    
    * Click **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Log]**.

1. On the log page, at the top or bottom, do any of the following:

    * Use the navigation options **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]**, or **[!UICONTROL Go to line]** to move through the log. 
    
    * Use the display options **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]**, or **[!UICONTROL Show]** to refine what you see.

