---
description: Whenever your website changes, you can run a script or program requesting that the search robot run an index using Remote Control.
seo-description: Whenever your website changes, you can run a script or program requesting that the search robot run an index using Remote Control.
seo-title: About Remote Control for Indexing
solution: Target
title: About Remote Control for Indexing
topic: Index,Site search and merchandising
uuid: 20e230c6-5c1a-4bf4-bff3-b8236d14ab21
index: n
internal: n
snippet: y
---

# About Remote Control for Indexing{#about-remote-control-for-indexing}

Whenever your website changes, you can run a script or program requesting that the search robot run an index using Remote Control.

## Using Remote Control for Indexing {#concept_C79B322190E84106A434E5C6D4A4118F}

The remote control indexing request typically comes from a script or a program that is located on your server.

The robot performs the same indexing steps as though it had been started manually from the [!DNL Index] menu. To submit a remote control request, you configure the necessary password and response strings.

## How to make a remote control request {#section_42FAB2BAB25A4E24BEA69566C6D1C70F}

To make a remote control request, use the following format examples based on the location of your data center:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data center location </p> </th> 
   <th colname="col2" class="entry"> <p>Example </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>London </p> </td> 
   <td colname="col2"> <p> <code> https://center.lon5.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>North America </p> </td> 
   <td colname="col2"> <p> <code> https://center.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Singapore </p> </td> 
   <td colname="col2"> <p> <code> https://center.sin2.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

or 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>String and value </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_a= sp99999999 </span> </p> </td> 
   <td colname="col2"> <p> Your account number. </p> <p>You can find your account number under <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Account Options </span> &gt; <span class="uicontrol"> Account Settings </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_lines= N </span> </p> </td> 
   <td colname="col2"> <p>Lets you check the status of a running index crawl. </p> <p> <span class="codeph">  N </span> is either a positive integer or <span class="codeph"> all </span>. If this is a numeric value, the last <span class="codeph"> N </span> lines of the corresponding index log file are included in the JSON response. </p> <p>If the value is <span class="codeph"> all </span>, the entire file is returned. </p> <p>If the value is <span class="codeph"> 0 </span>, then no log information is returned. This value is the default for a running index status query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= op </span> </p> </td> 
   <td colname="col2"> <p>Lets you specify one of the following indexing operations that you want to run: </p> <p> 
     <ul id="ul_6CA190AC41694BC293FC7C6BABA629FE"> 
      <li id="li_EFC76E31D47E473F9A56B2EBA8A97CA1"> <span class="codeph"> full_index </span> <p>The search robot runs a full index of your website. </p> </li> 
      <li id="li_A9ACE21718804A21B3DA7B84AB6729D3"> <span class="codeph"> incremental_index </span> <p>The search robot runs an incremental index using the configuration that is set under <span class="uicontrol"> Index </span> &gt; <span class="uicontrol"> Incremental Index </span> &gt; <span class="uicontrol"> Configuration </span>. </p> </li> 
      <li id="li_722FE409AE454AD48ACE95C4CDC7A00B"> <span class="codeph"> vertical_index </span> <p>The search robot runs a vertical update using the configuration that is set under <span class="uicontrol"> Index </span> &gt; <span class="uicontrol"> Vertical Update </span> &gt; <span class="uicontrol"> Configuration </span>. </p> <p>See <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> About Vertical Update </a>. </p> </li> 
      <li id="li_A40B513CE17043A4925CE3D4DE0B48A4"> <span class="codeph"> script_index </span> <p>The search robot runs an incremental index using the text file that is specified under <span class="uicontrol"> Index </span> &gt; <span class="uicontrol"> Scripted Index </span> &gt; <span class="uicontrol"> Configuration </span>. </p> </li> 
      <li id="li_A0BC7F1373B14393997BAB7690FD3EF7"> <span class="codeph"> full_staged_index </span> <p>The search robot runs a full staged index of your website. </p> </li> 
      <li id="li_47753E358457443A95B384A278FACA83"> <span class="codeph"> incremental_staged_index </span> <p>The search robot runs an incremental staged index using the configuration that is set under <span class="uicontrol"> Index </span> &gt; <span class="uicontrol"> Incremental Index </span> &gt; <span class="uicontrol"> Configuration </span>. </p> </li> 
      <li id="li_C8B5F8F1208E438ABEFDF9129A6B14A3"> <span class="codeph"> vertical_staged_index </span> <p>The search robot runs a vertical staged update using the configuration that is set under <span class="uicontrol"> Index </span> &gt; <span class="uicontrol"> Vertical Update </span> &gt; <span class="uicontrol"> Configuration </span>. </p> </li> 
     </ul> </p> <p>Note:  To use Vertical Updates, you may need to have it enabled in your account by your Adobe account representative or by Adobe Support. </p> <p>See <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> About Vertical Update </a>. </p> <p>You can append <span class="codeph"> _saved </span> to any of the above <span class="codeph"> sp_operation </span> values to have the search robot attempt to use saved content. For example, you could specify the following: </p> <p> <code class="syntax html"> sp_operation=full_index_saved </code> </p> <p>or </p> <p> <code class="syntax html"> sp_operation=full_staged_index_saved </code> </p> <p>Or, you can append <span class="codeph"> _status </span> to any of the above <span class="codeph"> sp_operation </span> values to request a status report for the current, or most recent, operation. For example, you could specify the following: </p> <p> <code class="syntax html"> sp_operation=full_index_status </code> </p> <p>or </p> <p> <code class="syntax html"> sp_operation=full_staged_index_status </code> </p> <p>and the results are returned as a JSON object. Include <span class="codeph"> sp_lines=N </span> to include N lines of the associated log file. If N is negative, the last N lines are included. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= pushlive </span> </p> </td> 
   <td colname="col2"> <p> Lets you remotely push live a staged index. </p> <p>Any attempt to append <span class="codeph"> _saved </span> to the push live operation is ignored. </p> <p>When you run a <span class="codeph"> pushlive </span> operation an OK, Priority, or Error response text string is returned to the server. You specify these response strings on the <span class="wintitle"> Remote Control </span> page. </p> <p>See <a href="../c-about-index-menu/c-about-remote-control-for-indexing.md#task_57C296258404448DA7A5ADC9B7232391" format="dita" scope="local"> Configuring Remote Control for indexing </a>. </p> <p>If you push live when there is no staged index, nothing happens and the OK response string is returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_password= xxxxxx </span> </p> </td> 
   <td colname="col2"> <p>The remote control password. </p> </td> 
  </tr> 
 </tbody> 
</table>

Search returns data in the form of a proper HTTP response. The full response is composed of an HTTP status, HTTP response headers, a blank line, and the response string.

For example, suppose that you perform the following remote control request:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index
```

The following is the response from the server: 

```
Status: 200 OK 
Content-type: text/plain 
OK
```

Or, suppose that you perform the following remote control status request:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status
```

The response from the server might look like the following: 

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:58:58-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "status": 1, 
    "message": "ok" 
}
```

To get the first ten lines of the log listing that is associated with this index operation, along with its status, the following query is used:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=10
```

The response from the server: 

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:59:30-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "offset": 672, 
    "lines": [ 
        "07/25 16:40:07 PST   ======== Starting manual crawl of account sp99999999. ========", 
        "07/25 16:40:08 PST   Loading existing data", 
        "07/25 16:40:08 PST   Downloading entrypoint https://www.atomz.com/", 
        "07/25 16:40:08 PST   Robots.txt exclude mask: https://www.atomz.com/snap", 
        "07/25 16:40:08 PST   Exclude mask: regexp ^https://www.atomz.com/$", 
        "07/25 16:40:08 PST   Include mask: https://www.atomz.com/", 
        "07/25 16:40:08 PST   Downloading https://www.atomz.com/style.css", 
        "07/25 16:40:09 PST   Ignoring https://www.atomz.com/style.css, document type 'text/css'.", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/privacy.html", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/terms.html" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

Note the `offset` value. This value identifies the file-offset position in the log file where reading left off. To read the *next* ten lines in the file, you would include, in this example, `&sp_offset=672` in the request sent to the server.

Using `sp_offset`, you can effectively page through a log file.

To get the *last* ten lines of the log, along with the status, specify the count as a negative number. For example, specify `sp_lines=` with a value of `-10` as in the following:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=-10
```

The response from the server: 

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T11:01:14-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "lines": [ 
        "07/25 16:40:20 PST   End Time: 07/25/2017 16:40:20 PST", 
        "07/25 16:40:20 PST   Elapsed Time: 13 seconds", 
        "07/25 16:40:20 PST   Pages Crawled: 3 pages", 
        "07/25 16:40:20 PST   Pages Indexed: 3 pages", 
        "07/25 16:40:20 PST   Words/Bytes Indexed: 2373 words/ 20618 bytes", 
        "07/25 16:40:20 PST   Errors: 0", 
        "07/25 16:40:20 PST   *** Index Summary ***", 
        "07/25 16:40:20 PST   Total Pages: 3", 
        "07/25 16:40:20 PST   --------------------------------------------------------------------", 
        "07/25 16:40:20 PST   ======== Finish manual crawl of account sp99999999: Done. ========" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

Note that there is no `offset` value returned here, as this operation finished at the end of the file, and there are no more lines to read. 

## Configuring Remote Control for indexing {#task_57C296258404448DA7A5ADC9B7232391}

Whenever your website changes, you can use Remote Control to run a script or program from your server, requesting that the search robot run an index.

<!-- 

t_configuring_remote_control_for_indexing.xml

 -->

**To configure Remote Control for indexing** 

1. On the product menu, click **[!UICONTROL Index]** > **[!UICONTROL Remote Control]**.
1. On the [!DNL Remote Control] page, set each configuration field option to be able to submit an indexing request from your server automatically to index your website.

   <!-- 
   
   r_remote_control_configuration_options.xml
   
   -->

    <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>Option </p> </th> 
    <th colname="col2" class="entry"> <p>Description </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Remote Control Password </p> </td> 
    <td colname="col2"> <p>Specify the remote control password. </p> <p> Passwords are case sensitive, at least six characters long, and must include at least one letter. It is recommended that you also include at least one number. </p> <p>Do not use your site search/merchandising login password. </p> <p>Your password is used in each remote control request. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>OK Response String </p> </td> 
    <td colname="col2"> <p>Lets you specify an OK response text string if the requested index operation begins successfully. In such cases, the search robot returns your OK response string to the server. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Priority Response String </p> </td> 
    <td colname="col2"> <p>If another indexing operation is in progress when the remote request is made, the search robot cannot perform the requested index. In such cases, your Priority response text string is returned to the server. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Error Response String </p> </td> 
    <td colname="col2"> <p>Lets you specify an Error response text string If your password is incorrect, or if another error occurs. In such cases, the search robot returns your Error response string back to the server. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Save Changes]**.
