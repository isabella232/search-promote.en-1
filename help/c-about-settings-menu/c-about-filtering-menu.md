---
description: Use the Filtering menu to use scripts that change the content of a web document before it is indexed.
solution: Target
subtopic: Filtering
title: About the Filtering menu
topic: Settings,Site search and merchandising
uuid: ebb08fa8-4e17-417d-868b-11fc2af9f284
---

# About the Filtering menu{#about-the-filtering-menu}

Use the Filtering menu to use scripts that change the content of a web document before it is indexed.

## About Filtering Script {#concept_E56B73D625854AB2A899EF2D56CFCB47}

You can use [!DNL Filtering Script] to change the content of a Web document before it is indexed.

You can insert HTML tags, remove irrelevant content, and even create new HTML metadata based on a document's URL, MIME type, and existing content. The filtering script is a Perl script, which provides powerful string handling and the flexibility of regular expression matching. You use the filtering script with an initialization script, termination script, URL masks script, and test URL.

The filtering script is run each time a document is read from your website. The script runs as a standard filter, In other words, reads data from STDIN, transforms that data in some way, and writes the results to STDOUT. You can use the filtering script to print status messages from the filtering script to the index log. You either printing the messages to STDERR, or by way of the `_search_debug_log()` subroutine.

Some GNU diff options that you can use while in **[!UICONTROL Expert (diff)]** mode on the Staged Filtering Script page, include the following:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU diff option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
   <td colname="col2"> <p> Ignores changes in amount of white space. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
   <td colname="col2"> <p> Ignores changes that insert or delete blank lines. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
   <td colname="col2"> <p> Uses the context output format, showing three lines of context. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C lines </span> </p> </td> 
   <td colname="col2"> <p> Uses the context output format, showing lines (an integer) lines of context, or three if lines is not given. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> Ignores changes in case; consider upper- and lowercase letters equivalent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
   <td colname="col2"> <p> Makes output that looks similar like an ed script but has changes in the order that they appear in the file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> Outputs RCS-format diffs; like <span class="codeph"> -f </span> except that each command specifies the number of lines that are affected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Uses the unified output format, showing three lines of context. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U lines </span> </p> </td> 
   <td colname="col2"> <p> Uses the unified output format, showing lines (an integer) of context, or three if lines is not given. </p> </td> 
  </tr> 
 </tbody> 
</table>

You can use local variables, global variables, or both in these scripts. All global variables are prefaced with the namespace "main::". When the filtering script is started, its environment contains the following standard file handles:

* STDIN - nothing (immediately returns EOF when read) 
* STDOUT - replacement HTML (if data is printed to STDOUT, it is used in place of the original document) 
* STDERR - data printed to STDERR is printed to the Index Log as an error

Additionally, you can write custom messages to the index log using the `_search_debug_log()` subroutine, as in the following example:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

These messages appear with the word `DEBUG` as a preface, and are not logged as errors.

The following is an example of filtering. Web page `<title>` fields often begin with the company name. Even though this information is useful for site navigation purposes, it is not relevant when searching. If the titles of all MegaCorp web pages start with a common string, such as the following:

```
<title>MegaCorp -- meaningful title 
here</title>
```

You should remove " `MegaCorp --`" from the beginning of each document title and count each document processed with the filtering script. To do so, you can use the following script:

```
# Make sure this is an HTML document. 
if ($main::ws_content_type =~ /^text\/html/) { 
    # Read the entire document into a local scalar variable. 
    my @docarray = <>; 
    my $doc = join("", @docarray); 
 
    # Remove "MegaCorp -- " from the title. 
    $doc =~ s/(<TITLE>)MegaCorp -- /$1/gis; 
 
    # Print the resulting document. 
    print $doc; 
 
    # Count that we've filtered one more document. 
    $main::doc_count++; 
}
```

## Global Variables {#global-variables}

You can use the following variables in any filtering script:

|Variable | Description |
|--- |--- |
|`$main::search_crawl_type`|The value of `$main::search_crawl_type` indicates the type of index operation underway.  Deprecated form: `$main::ws_crawl_type`  The index operations and associated values include the following: <ul><li>Full Index: Manual - `manual`</li><li>Full Index: Scheduled - `auto`</li><li>Full Index: Remote Control - `CGI`</li><li>Incremental Index: Manual - `manual-incremental`</li><li>Incremental Index: Scheduled - `auto-incremental` </li><li>Incremental Index: Remote Control - `CGI-incremental`</li><li>Scripted Index: Manual - `manual-indexlist.txt` </li><li>Scripted Index: Scheduled - `auto-indexlist.txt`</li><li>Scripted Index: Remote Control - `CGI-indexlist.txt`</li><li>Regenerate - `manual-upgrade`</li></ul>|
|`$main::search_clear_cache`|The value indicates whether the "Clear index cache" indexing option was requested for the current index operation. If "Clear index cache" was requested, the value of `$main::search_clear_cache` is " `1`".  Deprecated form: `$main::ws_clear_cache`|
|`$main::search_fields`|The value contains a tab-separated list of the metadata fields that are defined in the account. By default, the value is:   `url title desc keys target body alt date charset language`  Deprecated form: `$main::ws_fields`|
|`$main::search_collections`|The value contains a tab-separated list of the Collections that are defined in the account.  Deprecated form: `$main::ws_collections`|
|`$main::search_url`|The value is the fully qualified URL of the document.  Deprecated form: `$main::ws_url`|
|`$main::search_content_type`|The value is the content-type of the document as fetched from the http-equiv meta tag. A typical value is "text/html; charset=iso-8859-1".  Deprecated form: `$main::ws_content_type`|
|`$main::search_content_class`|The value is the content class of the document, as derived from the content-type field.  Deprecated form: `$main::ws_content_class`|
|`$main::search_syntax_check`|The value reflects the use of the "Check Syntax" button. If clicked, the value is 1 (one); otherwise, its value is 0 (zero).  Deprecated form: `$main::ws_syntax_check`|
|`$main::search_last_mod_date`|If provided by the web server, this value contains the Epoch representation (seconds since January 1, 1970) of the document's last-modified date.  You can format this value by using the Perl localtime() library call.|

### Quick tips {#section_89A5C16911744AF98E232DF608C6A1F5}

* All global variables are prefaced with the namespace "main::": `$main::doc_count = 0;` 
* All local variables are declared with "my": `my $i = 0;` 
* Subroutines are defined in the initialization script. They do not need an explicit "main::" namespace: `sub my_sub {`  `...`

  `}` 

* Test the `$main::search_content_type` before you make changes to a file. Testing can help you avoid making careless changes to binary files, like SWF files or PDF files:

  `if ($main::search_content_type =~ /^text\/html/) { ...` 

* The `$main::search_content_type` is the full Content-Type header delivered by your server. It can sometimes contain a simple MIME type, such as "text/html". Or, it can contain a MIME type followed by other information, like the document's character set encoding, such as "text/html; charset=iso-8859-1". 
* For each type of non-HTML document, `$main::search_content_type` can take various values. Testing for each value in your script becomes cumbersome. For example, some Word documents have content type values of "application/msword", "application/vnd.ms-word" or "application/x-msword". In such cases, `$main::search_content_class` can take the following values:

    * html 
    * pdf 
    * word 
    * excel 
    * powerpoint 
    * mp3 
    * text

* In the example, testing `$main::search_content_class` for "word" would match any of the three possible content-type values. 
* If nothing is printed to STDOUT from the filtering script, then the document is used exactly as it was downloaded. That is, if you do not need to change anything in a document, then you do not need to copy STDIN to STDOUT for that document. 
* If you want to remove all text from a document, print a valid file STDOUT. For example, to completely remove all text from an HTML document, you do the following: `print "<html></html>";`

## Adding a filtering script {#task_0AB84FD1133F47F9AA069A79BEA13A22}

The filtering script is a Perl script that is run for each document that is downloaded from your website.

You use the filtering script in conjunction with an initialization script, termination script, and URL masks script.

Be sure that you rebuild your site index so that the results of your filtering script are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To add a filtering script** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Filtering Script]**.
1. (Optional) On the [!DNL Filtering Script] page, in the [!DNL Test URL] field, enter the URL of a document on your website.

   Click a testing option to see changes to the raw HTML text.

    <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Test URL field </p> </td> 
      <td colname="col2"> <p>Lets you enter the URL of a document on your website. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Tests the URL against the filtering scripts and URL masks. </p> <p>The test URL document is downloaded, which is then used as the STDIN input to the filtering script. The initialization, filtering, and termination scripts are then run. If there is any STDOUT output from the filtering script, that output is displayed in a new browser window. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test only </p> </td> 
      <td colname="col2"> <p>Tests the script's operation only. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Preview </p> </td> 
      <td colname="col2"> <p>Lets you view the page. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Full visual </p> </td> 
      <td colname="col2"> <p>Generates a full before-and-after table view of the documents. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Short visual </p> </td> 
      <td colname="col2"> <p>Shows only the differences between the before-and-after views. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Expert (diff) </p> </td> 
      <td colname="col2"> <p>Displays the raw output of the GNU diff command that is used to compare the files, using the supplied command line options. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Filtering Script </p> </td> 
      <td colname="col2"> <p>Lets you paste your filtering script in the field provided. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Save Changes </p> </td> 
      <td colname="col2"> <p>Saves the filtering script. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Check Syntax </p> </td> 
      <td colname="col2"> <p>Lets you do a quick syntax check of your script by running the initialization, filtering, and termination scripts. It does not update and save your script. </p> <p>All Perl compiler errors and warnings, and all STDERR output are printed. </p> <p>Before the effects of the script are visible to customers, you must rebuild your site index. </p> </td> 
      </tr> 
    </tbody> 
    </table>

    **GNU diff command line options**

    Some GNU diff options that you can use while in **[!UICONTROL Expert (diff)]** mode on the Staged Filtering Script page, include the following:

    <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>GNU diff command line option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
      <td colname="col2"> <p> Ignores changes in amount of white space. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
      <td colname="col2"> <p> Ignores changes that insert or delete blank lines. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
      <td colname="col2"> <p> Uses the context output format, showing three lines of context. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -C lines </span> </p> </td> 
      <td colname="col2"> <p> Uses the context output format, showing lines (an integer) lines of context, or three if lines is not given. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
      <td colname="col2"> <p> Ignores changes in case; consider upper- and lowercase letters equivalent. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
      <td colname="col2"> <p> Makes output that looks similar like an ed script but has changes in the order that they appear in the file. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
      <td colname="col2"> <p> Outputs RCS-format diffs; like <span class="codeph"> -f </span> except that each command specifies the number of lines that are affected. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>-u </p> </td> 
      <td colname="col2"> <p> Uses the unified output format, showing three lines of context. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -U lines </span> </p> </td> 
      <td colname="col2"> <p> Uses the unified output format, showing lines (an integer) of context, or three if lines is not given. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Test]** to test against the filtering scripts and URL masks.

   Clicking **[!UICONTROL Test]** does not update and save your filtering script. 
1. In the [!DNL Filtering Script] field, paste your script.
1. (Optional) Click **[!UICONTROL Check Syntax]** to perform a quick syntax check of your script by running the filtering, initialization, and termination scripts.

   **[!UICONTROL Check Syntax]** does not update and save your script. 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Filtering Script] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Initialization Script {#concept_048B4C8BC9F74BE8BB6162C490C201A3}

You can use [!DNL Initialization Script] to change the content of a Web document before it is indexed.

You can insert HTML tags, remove irrelevant content, and even create new HTML metadata based on a document's URL, MIME type, and existing content. The initialization script is a Perl script, which provides powerful string handling and the flexibility of regular expression matching. You use the initialization script with a filtering script, termination script, URL masks script, and test URL.

The initialization script is run once before indexing begins. Use this script to initialize any global variables and subroutines that are used by your filtering script. You can use the initialization script to print status messages from the filtering script to the index log. You either print the messages to STDERR, or by way of the `_search_debug_log()` subroutine.

Some GNU diff options that you can use while in **[!UICONTROL Expert (diff)]** mode on the Staged Initialization Script page, include the following:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU diff option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
   <td colname="col2"> <p> Ignores changes in amount of white space. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
   <td colname="col2"> <p> Ignores changes that insert or delete blank lines. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
   <td colname="col2"> <p> Uses the context output format, showing three lines of context. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C lines </span> </p> </td> 
   <td colname="col2"> <p> Uses the context output format, showing lines (an integer) lines of context, or three if lines is not given. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> Ignores changes in case; consider upper- and lowercase letters equivalent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
   <td colname="col2"> <p> Makes output that looks similar like an ed script but has changes in the order that they appear in the file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> Outputs RCS-format diffs; like <span class="codeph"> -f </span> except that each command specifies the number of lines that are affected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Uses the unified output format, showing three lines of context. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U lines </span> </p> </td> 
   <td colname="col2"> <p> Uses the unified output format, showing lines (an integer) of context, or three if lines is not given. </p> </td> 
  </tr> 
 </tbody> 
</table>

You can use local variables, global variables, or both in these scripts. All global variables are prefaced with the namespace "main::". When the initialization script is started, its environment contains the following standard file handles:

* STDIN - nothing (immediately returns EOF when read) 
* STDOUT - nothing (if data is printed to STDOUT, it is discarded) 
* STDERR - data printed to STDERR is printed to the Index Log as an error

Additionally, you can write custom messages to the index log using the `_search_debug_log()` subroutine, as in the following example:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

These messages appear with the word `DEBUG` as a preface, and are not logged as errors.

An example of an initialization script is the following:

```
# My subroutine to do something. 
sub my_sub_for_the_filtering_script { 
    my ($param1, $param2) = @_; 
    ... 
} 
 
# Initialize the document counter. 
$main::doc_count = 0;
```

See [Global Variables](#global-variables)

### Quick tips {#section_A2CC0302CAF14135BF8EF6171FB184F1}

* All global variables are prefaced with the namespace "main::": `$main::doc_count = 0;` 
* All local variables are declared with "my": `my $i = 0;` 
* Subroutines are defined in the initialization script. They do not need an explicit "main::" namespace: `sub my_sub {`  `...`

  `}` 

* Test the `$main::search_content_type` before you make changes to a file. Testing can help you avoid making careless changes to binary files, like SWF files or PDF files:

  `if ($main::search_content_type =~ /^text\/html/) { ...` 

* The `$main::search_content_type` is the full Content-Type header delivered by your server. It can sometimes contain a simple MIME type, such as "text/html". Or, it can contain a MIME type followed by other information, like the document's character set encoding, such as "text/html; charset=iso-8859-1". 
* For each type of non-HTML document, `$main::search_content_type` can take various values. Testing for each value in your script becomes cumbersome. For example, some Word documents have content type values of "application/msword", "application/vnd.ms-word" or "application/x-msword". In such cases, `$main::search_content_class` can take the following values:

    * html 
    * pdf 
    * word 
    * excel 
    * powerpoint 
    * mp3 
    * text

* In the example, testing `$main::search_content_class` for "word" would match any of the three possible content-type values. 
* If nothing is printed to STDOUT from the filtering script, then the document is used exactly as it was downloaded. That is, if you do not need to change anything in a document, then you do not need to copy STDIN to STDOUT for that document. 
* If you want to remove all text from a document, print a valid file STDOUT. For example, to completely remove all text from an HTML document, you do the following: `print "<html></html>";`

## Adding an initialization script {#task_5A03B8D0C46E4674B7CE88203515803B}

The initialization script is a Perl script that is run once before any documents are indexed. 

You use the initialization script in conjunction with a filtering script, termination script, and URL masks script.

Be sure that you rebuild your site index so that the results of your initialization script are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To add an initialization script** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Initialization Script]**.
1. (Optional) On the [!DNL Initialization Script] page, in the [!DNL Test URL] field, enter the URL of a document on your website.

   Click a testing option to see changes to the raw HTML text.

   See the filtering options table under **Adding a filtering script**.

   Click **[!UICONTROL Test]** to test against the filtering scripts and URL masks.

   Clicking **[!UICONTROL Test]** does not update and save your initialization script. 
1. In the [!DNL Initialization Script] field, paste your script.
1. (Optional) Click **[!UICONTROL Check Syntax]** to perform a quick syntax check of your script by running the filtering, initialization, and termination scripts.

   **[!UICONTROL Check Syntax]** does not update and save your script. 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Initialization Script] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Termination Script {#concept_AAD6B3B0E7124874AD0947096FC42F47}

You can use [!DNL Termination Script] to change the content of a Web document before it is indexed.

You can insert HTML tags, remove irrelevant content, and even create new HTML metadata based on a document's URL, MIME type, and existing content. The initialization script is a Perl script, which provides powerful string handling and the flexibility of regular expression matching. You use the termination script with an initialization script, filtering script, termination script, URL masks script, and test URL.

The termination script is run once after all the documents are indexed. You can use the termination script to print status messages from the filtering script to the index log. You either print the messages to STDERR, or by way of the `_search_debug_log()` subroutine.

Some GNU diff command line options that you can use while in **[!UICONTROL Expert (diff)]** mode on the Staged Termination Script page, include the following:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU diff command line option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
   <td colname="col2"> <p> Ignores changes in amount of white space. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
   <td colname="col2"> <p> Ignores changes that insert or delete blank lines. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
   <td colname="col2"> <p> Uses the context output format, showing three lines of context. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C lines </span> </p> </td> 
   <td colname="col2"> <p> Uses the context output format, showing lines (an integer) lines of context, or three if lines is not given. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> Ignores changes in case; consider upper- and lowercase letters equivalent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
   <td colname="col2"> <p> Makes output that looks similar like an ed script but has changes in the order that they appear in the file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> Outputs RCS-format diffs; like <span class="codeph"> -f </span> except that each command specifies the number of lines that are affected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Uses the unified output format, showing three lines of context. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U lines </span> </p> </td> 
   <td colname="col2"> <p> Uses the unified output format, showing lines (an integer) of context, or three if lines is not given. </p> </td> 
  </tr> 
 </tbody> 
</table>

You can use local variables, global variables, or both in these scripts. All global variables are prefaced with the namespace "main::". When the termination script is started, its environment contains the following standard file handles:

* STDIN - nothing (immediately returns EOF when read) 
* STDOUT - nothing (if data is printed to STDOUT, it is discarded) 
* STDERR - data printed to STDERR is printed to the index log as an error

Additionally, you can write custom messages to the index log using the `_search_debug_log()` subroutine, as in the following example:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

These messages appear with the word `DEBUG` as a preface, and are not logged as errors.

To display the number of documents that were processed by your filtering script as an error line in the index log, you can use the following termination script:

```
# Print the value of the document counter. 
print STDERR "Total docs: $main::doc_count\n"; 
# Or, using the log subroutine: 
_search_debug_log("Total docs: " . $main::doc_count);
```

See [Global Variables](#global-variables)

### Quick tips {#section_5790EA7ACAC046CBA01F759F88E2460F}

* All global variables are prefaced with the namespace "main::": `$main::doc_count = 0;` 
* All local variables are declared with "my": `my $i = 0;` 
* Subroutines are defined in the initialization script. They do not need an explicit "main::" namespace: `sub my_sub {`  `...`

  `}` 

* Test the `$main::search_content_type` before you make changes to a file. Testing can help you avoid making careless changes to binary files, like SWF files or PDF files:

  `if ($main::search_content_type =~ /^text\/html/) { ...` 

* The `$main::search_content_type` is the full Content-Type header delivered by your server. It can sometimes contain a simple MIME type, such as "text/html". Or, it can contain a MIME type followed by other information, like the document's character set encoding, such as "text/html; charset=iso-8859-1". 
* For each type of non-HTML document, `$main::search_content_type` can take various values. Testing for each value in your script becomes cumbersome. For example, some Word documents have content type values of "application/msword", "application/vnd.ms-word" or "application/x-msword". In such cases, `$main::search_content_class` can take the following values:

    * html 
    * pdf 
    * word 
    * excel 
    * powerpoint 
    * mp3 
    * text

* In the example, testing `$main::search_content_class` for "word" would match any of the three possible content-type values. 
* If nothing is printed to STDOUT from the filtering script, then the document is used exactly as it was downloaded. That is, if you do not need to change anything in a document, then you do not need to copy STDIN to STDOUT for that document. 
* If you want to remove all text from a document, print a valid file STDOUT. For example, to completely remove all text from an HTML document, you do the following: `print "<html></html>";`

## Adding a termination script {#task_F0CFB412871642CFBC88132889C5B6F9}

The termination script is a Perl script that is run once after all documents are indexed.

You use the termination script in conjunction with a filtering script, termination script, and URL masks script.

Be sure that you rebuild your site index so that the results of your initialization script are visible to your customers.

See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**To add a termination script** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Termination Script]**.
1. (Optional) On the [!DNL Termination Script] page, in the [!DNL Test URL] field, enter the URL of a document on your website.

   Click a testing option to see changes to the raw HTML text.

   See the table of filtering options under **Adding a filtering script**.

   Click **[!UICONTROL Test]** to test against the filtering scripts and URL masks.

   Clicking **[!UICONTROL Test]** does not update and save your termination script. 
1. In the [!DNL Termination Script] field, paste your script.
1. (Optional) Click **[!UICONTROL Check Syntax]** to perform a quick syntax check of your script by running the initialization, filtering, and termination scripts.

   **[!UICONTROL Check Syntax]** does not update and save your script. 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Termination Script] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About URL Masks script {#concept_384F32EA18F84853A7BA99A04009330B}

With filtering, you can change the content of a web document before it is indexed. You can insert HTML tags, remove irrelevant content, and even create new HTML metadata based on a document's URL, MIME type, and existing content. The URL masks script is a Perl script that provides powerful string handling and the flexibility of regular expression matching.

To change the contents of documents that exist only in a specific portion of your website, you can specify include URL masks, exclude URL masks, or both, to define the appropriate pages.

If you want to change only the documents under `"https://www.mysite.com/faqs/"`, you can use the following set of masks:

```
include https://www.mysite.com/faqs/ 
exclude *
```

You can also use regular expression in a URL mask script as in the following example:

```
include regexp ^https://www\.mysite\.com.*/faqs/.*$ 
exclude *
```

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Scripted URL masks are considered in the order that you entered them in the [!DNL URL Masks] field. When a document URL matches a mask, that document is included or excluded based on the type of mask. If a document's URL does not match any URL mask, the document is included only if its MIME type is "text/html". All other MIME types are excluded. 

## Adding a URL mask script {#task_D18F2A496C1C45C997B5DA650AAF5D59}

Specify URL include masks and exclude masks to change the contents of documents that exist only in a specific portion of your website.

Before the effects of the URL Masks settings are visible to visitors, rebuild your site index.

**To add a URL mask script** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL URL Masks]**.
1. (Optional) On the [!DNL URL Masks] page, in the [!DNL Test URL] field, enter a URL of a document on your website, and then click **[!UICONTROL Test]** to test the URL against the filtering scripts and masks.

   The test URL document is downloaded, which is used as the STDIN input to the filtering script. Then the filtering, initialization, and termination scripts are run. If there is any STDOUT output from the filtering script that output is displayed in a new browser window.

   Clicking **[!UICONTROL Test]** does not update and save your script. 
1. In the [!DNL URL Masks] field, enter one URL mask per line.
1. (Optional) Click **[!UICONTROL Check Syntax]** to perform a quick syntax check of your URL masks by running the filtering, initialization, and termination scripts.

   **[!UICONTROL Check Syntax]** does not update and save your script. 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL URL Masks] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Content Types in Filtering {#concept_E3EFF4A148EA4D21AFD0A5453A00427E}

Lets you select which content types that you want filtered for this account.

The text found within the selected content types is converted to HTML and then processed using the script that is specified in Filtering Script.

See [About Filtering Script](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

The Content Types that you can select from include the following:

* PDF documents 
* Text documents 
* Adobe Flash movies 
* Microsoft Word files 
* Microsoft Office files (OpenXML) 
* Microsoft Excel files 
* Microsoft Powerpoint files 
* Text in MP3 music files

Before the effects of the Content Types settings or changes to the settings are visible to customers, you must rebuild your site index. 

## Selecting the content types that are filtered {#task_C46081FA425A43EC8FDE6EA4A52A170A}

Select the content types that you want to pass to the script that is specified in Filtering Script.

See [About Filtering Script](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

**To select the content types that are filtered** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Content Types]**.
1. On the [!DNL Content Types] page, check the content types that you want pass to the filter script.
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Content Types] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
