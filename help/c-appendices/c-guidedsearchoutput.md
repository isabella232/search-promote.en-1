---
description: You can customize output in any text-based format, including XML or JSON.
seo-description: You can customize output in any text-based format, including XML or JSON.
seo-title: Guided Search output
solution: Target
title: Guided Search output
topic: Appendices,Site search and merchandising
uuid: cf8565b9-9c0e-4db3-82d3-09a15d2cdd67
index: y
internal: n
snippet: y
---

# Guided Search output{#guided-search-output}

You can customize output in any text-based format, including XML or JSON.

## Guided Search output {#concept_2A1BA3AD413848A1AC2A3ABC4FFE481F}

You can customize output in any text-based format, including XML or JSON.

<!-- 

c_aboutgsxmloutputforsp.xml

 -->

The output format is customizable to support the faceting, sorting, and other implementation-specific decisions that are made during the design process. You can adapt the format itself to simplify the development of the customer’s front end, if necessary.

The entire output is contained within `<result>` tags, and most of the dynamic data is enclosed within `<![CDATA[ ]]>` tags. Such organization allows the results to contain HTML and other non-XML entities.

Where links to other pages are provided, they are presented in the form of a relative URL. This result also includes the query string parameters that are passed to generate the desired result.

## Understanding a Guided Search implementation {#section_95483980930C4325BAB50A40BD47245A}

When you begin a Guided Search implementation remember that [!DNL Adobe Search&Promote] is responsible for the Business Layer. That is, the logic that surrounds what results and facets are shown to a customer at any given time.

When you implement the Web application front end that parses and displays the results as HTML, restrict the functionality to display only. In other words, any server-side logic that you use to create the Presentation Layer does not make the decisions about what to present to a customer, unless it is necessary. The Business Rules will not work as you expect if the front-end script is altering the search results.

[!DNL Adobe Search&Promote] maintains user state of selected search refinement options by way of the URL parameters. All `<link>` nodes contain the relevant parameters of the customer’s selections. These parameters can include breadcrumb, pagination, sort, and facet selections. Where applicable, `<undolink>` nodes are returned to allow a customer to “back out” of a selection. Facets and breadcrumbs offer these types of links.

## Working with the Search Server {#section_8DBEACDECD714E59BDED6315E6041B8D}

A REST-like API is used that you can interact with to perform searches and receive results. The most common formats used for the results are XML or JSON.

The base URI is associated with a specific account and a staged or live environment. You can request multiple aliases for the base URI from your account manager. For example, a fictional company called Megacorp has the following two base URLs associated with their account:

* http://search.megacorp.com 
* http://stage.megacorp.com

The former URI performs searches against their live index and the latter URI against their staged index.

Search requests consist of the base URI and a set of CGI parameters or key-value pairs that indicate the desired search for the account that is associated with the base URI.

Three formats of CGI parameters are supported. By default your account is configured to separate CGI parameters with a semi-colon ( `;`), as in the following example:

* `http://search.megacorp.com?q=shoes ;page=2`

If you prefer, you can have your account manager configure your account to use ampersands ( `&`) to separate the CGI parameters, as in the following example:

* `http://search.megacorp.com?q=shoes &page=2`

A third format, called the SEO format, is also supported where a forward slash ( `/`) is used in place of the separator and equal sign to generate “clean” links, as in the following example:

* `http://search.megacorp.com/q/shoes/page/2`

Any time the SEO format is used to send a request, all output links are returned in the same format.

## Search query parameters {#section_7ADA5E130E3040C9BE85D0D68EDD3223}

The following table describes the standard “out-of-the-box” search query parameters that you can use. Processing rules and business rules can be built based off user-defined query parameters to implement custom business logic that is relevant to your company. You can work with the consulting team to obtain documentation on those parameters.

<table id="table_C447B58F3B5C4E99A4E6DF70CF175337"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Search query parameter </p> </th> 
   <th colname="col2" class="entry"> <p>Example </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q= string </span> </p> </td> 
   <td colname="col3"> <p> Specifies the query string for the search. This parameter maps to the <span class="codeph"> sp_q </span> backend search parameter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q# </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q#= string </span> </p> </td> 
   <td colname="col3"> <p>Numbered <span class="codeph"> q </span> and <span class="codeph"> x </span> parameters accomplish faceting, or searching within a given field. </p> <p>The <span class="codeph"> q </span> parameter defines the term you are searching for in the facet as the corresponding numbered <span class="codeph"> x </span> parameter denotes. For example, if you have two facets that are named size and color, you could have something like the following: </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color </span> </p> <p>This parameter maps to the <span class="codeph"> sp_q_exact_# </span> backend search parameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> x# </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> x#= string </span> </p> </td> 
   <td colname="col3"> <p> Numbered <span class="codeph"> q </span> and <span class="codeph"> x </span> parameters accomplish faceting, or searching within a given field. </p> <p>The <span class="codeph"> q </span> parameter defines the term you are searching for in the facet as the corresponding numbered <span class="codeph"> x </span> parameter denotes. For example, if you have two facets that are named size and color, you could have something like the following: </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color </span> </p> <p>This parameter maps to the <span class="codeph"> sp_x_# </span> backend search parameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> collection </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> collection= string </span> </p> </td> 
   <td colname="col3"> <p> Specifies the collection to use for the search. This parameter maps to the <span class="codeph"> sp_k </span> backend search parameter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> count </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> count= number </span> </p> </td> 
   <td colname="col3"> <p> Specifies the total count of results that are shown. The default is defined in <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Searching </span> &gt; <span class="uicontrol"> Searches </span>. This parameter maps to the <span class="codeph"> sp_c </span> backend search parameter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> page </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> page= number </span> </p> </td> 
   <td colname="col3"> <p> Specifies the page of results that are returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> rank </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> rank= field </span> </p> </td> 
   <td colname="col3"> <p> Specifies the rank field to use for static ranking. The field must be a field of type Rank with relevance greater than 0. This parameter maps to the <span class="codeph"> sp_sr </span> backend parameter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> gs_store </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> gs_store= string </span> </p> </td> 
   <td colname="col3"> <p> Specifies the store to search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sort </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> sort= number </span> </p> </td> 
   <td colname="col3"> <p> Specifies the sort order. "0" is the default and sorts by relevance score; "1" sorts by date; "-1" does not sort. </p> <p>Users can specify a field name for the value of the <span class="codeph"> sp_s </span> parameter. For example, <span class="codeph"> sp_s=title </span> sorts results according to the values that are contained in the title field. When a field name is used for the value of an <span class="codeph"> sp_s </span> parameter, results are sorted by that field and then subsorted by relevance. </p> <p>To enable this feature, do the following: </p> 
    <ol id="ol_3894F81EA7BF4827A84DE8662111ABEF"> 
     <li id="li_C040C0B88F174A4885E1A8E721FD032A">On the product menu, click <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span>. </li> 
     <li id="li_2E83C3A46D1B4BF991EABAD9D3E52B7D">On the <span class="wintitle"> Staged Definitions </span> page, do one of the following: 
      <ul id="ul_8018FEE10E0A4C96A74F84A897080580"> 
       <li id="li_E9A7CE43E2734F4D9522A1283CA111FB">Click <span class="uicontrol"> Add New Field </span>. </li> 
       <li id="li_9D2434A321924FBD874569CA9AD2EEF7">Click <span class="uicontrol"> Edit </span> for a particular field name. </li> 
      </ul> </li> 
     <li id="li_90D5E3F4AC0A4A6189934A5589F69903">In the <span class="wintitle"> Sorting </span> drop-down list, click either <span class="uicontrol"> Ascending </span> or <span class="uicontrol"> Descending </span>. <p>This parameter maps to the <span class="codeph"> sp_s </span> backend search parameter. </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Integrating with your system {#section_91261B19A44A4E579B3FC9FAB9AD3665}

The following are recommendations for integration with your system.

* Communicating with the search server.

  You can communicate with the [!DNL Adobe Search&Promote] web servers using http GET requests. Your servers generate these requests or on the client side doing an Ajax request. 
* Saving the search history.

[!DNL Adobe Search&Promote] is stateless where the entire state is passed over in the http request. 
* Parsing the returned results.

  It is recommended that you use a SAX-based XML parser to parse the XML response. If you are generating Ajax request, configure [!DNL Adobe Search&Promote] to return JSON responses for those requests to make it easier to parse the response.

## Guided Search JSON Output {#reference_EB8182A564DE4374BB84158F2AABEF74}

Tables that describe the standard JSON response output.

<!-- 

r_gsjsonoutputforsp.xml

 -->

See also [Guided Search JSON Output](../c-appendices/c-guidedsearchoutput.md#reference_EB8182A564DE4374BB84158F2AABEF74).

You can review JSON response for the following:

* [Banners](../c-appendices/c-guidedsearchoutput.md#section_88519CAAD25F4BD49D5E517077745B0E) 
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_A7DB0F1DA9ED4CBCAE18395122F3E01E) 
* [Facets](../c-appendices/c-guidedsearchoutput.md#section_65932C95931743A1BFAF1DF16D7E6D92) 
* [Header and Query](../c-appendices/c-guidedsearchoutput.md#section_1D57062259CA46E0B4F598FA4EB37065) 
* [Pagination](../c-appendices/c-guidedsearchoutput.md#section_504E7AB570BD49AF9839530DC438EE96) 
* [Recent Searches](../c-appendices/c-guidedsearchoutput.md#section_525816A0355C48F8970D89B8FC3F1FFF) 
* [Results](../c-appendices/c-guidedsearchoutput.md#section_41AC56BB0A084BF59379B06C8BEF2157) 
* [Search Form](../c-appendices/c-guidedsearchoutput.md#section_434DA13EA295474C99FFE9F14801CD0E) 
* [Sort](../c-appendices/c-guidedsearchoutput.md#section_558853CD376F4D71BACF211D53085D55) 
* [Suggestions](../c-appendices/c-guidedsearchoutput.md#section_6EC104E1DDD94AC799B65E6E61A2FB3C) 
* [Zones](../c-appendices/c-guidedsearchoutput.md#section_AE53A498B440465EAF2286F2AE87D548)

## Banners {#section_88519CAAD25F4BD49D5E517077745B0E}

Example:

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="http://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table id="table_8C0D271824BD469794ADF113FA0E5524"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Banners </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> An individual banner node. You can have multiple banner nodes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> The area on the web page where the banner is displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;content&gt; </span> </p> </td> 
   <td colname="col2"> <p> The HTML content for the banner area. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_A7DB0F1DA9ED4CBCAE18395122F3E01E}

In the following example, each time the customer narrows down further through the facets, the selection is added to the breadcrumb. Each item is represented as a `<breadcrumb-item>`.

Example:

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 

```

<table id="table_7823C08B6D34409FA0919330F0B82C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Breadcrumb </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> A relative link to search results that shows the desired view. Clicking a breadcrumb link takes the customer to a view where all the subsequent refinements are removed. Other options are also available. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Customer-facing text for the breadcrumb item. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_65932C95931743A1BFAF1DF16D7E6D92}

Facets are refinement options that give customers the ability to filter on the results. Facets are commonly used for categorization, price ranges, color selections, and other attribute refinement. The metadata in the index is what drives facets.

It is common to hide or show categorization facets' as a customer moves down through the categorization. The highest level of categorization (category) is known as Tier 1. When a customer clicks a Tier 1 option, the Tier 2 (subcategory) refinement options to appear and the Tier 1 options disappear. When a customer clicks a Tier 2 option, the Tier 3 (subsubcategory) refinement options appear, and the Tier 2 options disappear. As noted above, these options are hidden and shown-your web application is not impacted by them.

Each facet is contained within `<facet-item>` tags. In the following example, it shows one facet that allows the customer to refine the search results by "holiday".

Example:

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item> 
 
 </facets> 

```

<table id="table_D71BB0860ECD4BB5964937613DDA480B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Facets </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Customer-facing title for the facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Customer-facing label for the facet option. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Relative link to results that the option refines down. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> The number of results in that refined result set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> When a facet value is selected the node returns an “undo link” that lets a customer back out of the results. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header and Query {#section_1D57062259CA46E0B4F598FA4EB37065}

Example:

```xml
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 

```

Used together, these tags present a message such as the following: "Showing results 1-16 of 621 for 'new year'."

<table id="table_CE5F16F3E1C2484889A08352F80F4AE1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in header and query </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> The keyword query that is submitted with the request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> The item number of the first result on this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> The item number of the last result on this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> The total number of results that match the user query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> An optional field that applies globally to the search results. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pagination {#section_504E7AB570BD49AF9839530DC438EE96}

Example:

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 

```

<table id="table_EA9D4071110E4378B3773BCB8E201008"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Pagination </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> Total number of pages of results, based on the number of results divided by the number of results per page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to the first page in the result set, unless the customer is already viewing page 1. In such case, it is blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to the last page in the result set, unless the customer is viewing the last page. In such case, it is blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to the previous page in the result set, unless the customer is viewing page 1; in such case, it is blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to the last page in the result set, unless the customer is viewing the last page. In such case, it is blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x" </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to a particular page number. Ten contiguous page numbers are shown. On page 1, it would be pages 1-10. At the end of the result set (in this case, 39), it would be pages 30-39. For example, in the center of the result set, page 15, it would be pages 11-20. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Applied as an attribute to the currently selected page. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recent Searches {#section_525816A0355C48F8970D89B8FC3F1FFF}

Recent Searches is a cookie-based feature that only works if you relay the cookie information to the servers.

Example:

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 

```

<table id="table_56F85EA20C754ECEB147A6787E4DA7F2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Recent Searches </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> An individual recent-search node. You can have multiple recent-search nodes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> The term that the customer searched for previously. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Links to the previous search. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Results {#section_41AC56BB0A084BF59379B06C8BEF2157}

The Results set is a customizable area of the JSON response. Each index is unique in the field naming mechanisms of metadata. There are common fields that are returned for each result such as title, description, and URL. But, any metadata that is defined for a page in the index can become available to use in each result node. Categorization, prices, colors, and thumbnails are just a few of the options that you can apply to a result to produce more compelling search results.

The Results format is customized based on the metadata that is specific to your implementation. Any per-result data for display in the results, including thumbnail image URLs, is contained here.

In addition, it is possible to configure multiple result zones within the page, such as “Featured Results”, or separate “Products” and “Content” results sections. In these cases, multiple result zones are provided within the HTML, although facets are only associated with the primary result set.

Example:

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[http://mysite.com/assets/cms/parties/new-years-eve-​​​​​slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[http://mysite.com/assets/cms/parties/new-years-eve-​slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[http://mysite.com/assets/cms/parties/10-holiday-​traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[http://mysite.com/assets/cms/parties/10-holiday-​traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[http://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[http://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[http://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[http://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 

```

<table id="table_6B0CCC8ADAE14355A08E6DAA02C7F0CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Results </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> The serial number of the result within this result set. In this example, where ten results are shown per page, on page 2 of the results, the first item would have an index of 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> The customer-facing title for this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> The URL for this page. It is used to create a hyperlink that lets the customer click through the results. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Search Form {#section_434DA13EA295474C99FFE9F14801CD0E}

Example:

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table id="table_5262D0D26B0F4B808F5CAAD123E8EC41"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Search Form </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> Optional. When present in the JSON, a value of 1 it indicates that your account is linked to <span class="keyword"> Test&amp;Target </span> and has at least one business rule that is in an A:B test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> Optional. When using auto-complete, this node is present to indicate that the CSS and JavaScript is present on the page along with the content that is in the form. These fields typically do not change unless someone has changed an autocomplete setting. In such cases, the xxx_cache_ver field is incremented to force an invalidation of the cached content on your customer’s browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> The CSS that is associated with autocomplete. It is recommended that you place this tag high in the page to improve page rendering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> Content that is required inside your search-from for the autocomplete utility to hook-up to the correct control. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> Custom JavaScript that is required for Autocomplete. It is recommended that you place this tag low in the page to improve page rendering. The YUI JavaScript is also required for autocomplete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains all the hidden parameters (name and value) to include in the search form. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sort {#section_558853CD376F4D71BACF211D53085D55}

The following example shows the data for a three-option sort menu. The menu allows the customer to sort by relevance, title, or rating. The currently selected item includes an attribute "selected=true". ". Always offer a relevance option to allow a customer to return to the default search results that were originally displayed.

Example:

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>

```

<table id="table_D4093615A2234A6D9BAC93E0C914417B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Sort Menu </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> The customer-facing text for the option. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Represents the value of the “sort” query string parameter for this option. This tag is not needed if the <span class="codeph"> &lt;link&gt; </span> value is used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> For the non-selected options, the <span class="codeph"> &lt;link&gt; </span> parameter contains the relative link that returns the same result set, sorted by the new sort parameter. This field is blank for the currently selected sort option. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suggestions {#section_6EC104E1DDD94AC799B65E6E61A2FB3C}

Suggestions are returned when there are only a few result or no results. This node contains terms that do yield successful queries and can be displayed on a "No Results" page. The link is also returned so a customer can jump to the new query.

Example:

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 

```

<table id="table_AC393E215BAD4421B0506E80A6C41DCA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Suggestions </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>A relative link that is used to create a hyperlink to search results for the suggestion term. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>The suggested term. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zones {#section_AE53A498B440465EAF2286F2AE87D548}

Example:

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 

```

<table id="table_05E9648A282B49CCB014CBA93ECC1001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Zones </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> An individual zone node. You can have multiple zone nodes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> The name of the zone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1 or 0 to indicate if the zone is or is not displayed. The actual zone content can be a static area on your web page or in your search results, such as best sellers or related products. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Guided Search XML Output {#reference_D93E859A277643068B10AE7A61C973EA}

Tables that describe the standard XML response output.

<!-- 

r_gsxmloutputforsp.xml

 -->

You can review XML response for the following:

* [Banners](../c-appendices/c-guidedsearchoutput.md#section_6A19EC26DD3B494194AAA788151B78B5) 
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_E48A71B0EBDB4EDDA7587009AD865488) 
* [Facets](../c-appendices/c-guidedsearchoutput.md#section_5CEB1F966C004FFEA3CF675638966E25) 
* [Header and Query](../c-appendices/c-guidedsearchoutput.md#section_802835E19BCB48239C6770A1B72DFFF8) 
* [Pagination](../c-appendices/c-guidedsearchoutput.md#section_72DB86DDE1284B1EA295CFFBC16A3150) 
* [Recent Searches](../c-appendices/c-guidedsearchoutput.md#section_BCA2DDD17F264CF6BA11634E1A514E28) 
* [Results](../c-appendices/c-guidedsearchoutput.md#section_EC496F5CA2634158891455E2F6DF6833) 
* [Search Form](../c-appendices/c-guidedsearchoutput.md#section_F92D8C3D37174A10A4E26CAFF3F3DF89) 
* [Sort](../c-appendices/c-guidedsearchoutput.md#section_32DC50A103BF491BA3665A5CADCCAADE) 
* [Suggestions](../c-appendices/c-guidedsearchoutput.md#section_D81BCE46F0AF443695DF9C4BA084B716) 
* [Zones](../c-appendices/c-guidedsearchoutput.md#section_15D8AA585F3246799968BA88EE2C9FC2)

## Banners {#section_6A19EC26DD3B494194AAA788151B78B5}

Example:

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="http://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table id="table_9CE30BB1CFFE47A69868EEEAE9F5CD99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Banners </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> An individual banner node. You can have multiple banner nodes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> The area on the web page where the banner is displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;content&gt; </span> </p> </td> 
   <td colname="col2"> <p> The HTML content for the banner area. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_E48A71B0EBDB4EDDA7587009AD865488}

In the following example, each time the customer narrows down further through the facets, the selection is added to the breadcrumb. Each item is represented as a `<breadcrumb-item>`.

Example:

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 

```

<table id="table_1A0CA8A62FAD4D83A50F84FD4113D9DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Breadcrumb </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> A relative link to search results that shows the desired view. Clicking a breadcrumb link takes the customer to a view where all the subsequent refinements are removed. Other options are also available. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Customer-facing text for the breadcrumb item. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_5CEB1F966C004FFEA3CF675638966E25}

Facets are refinement options that give customers the ability to filter on the results. Facets are commonly used for categorization, price ranges, color selections, and other attribute refinement. The metadata in the index is what drives facets.

It is common to hide or show categorization facets' as a customer moves down through the categorization. The highest level of categorization (category) is known as Tier 1. When a customer clicks a Tier 1 option, the Tier 2 (subcategory) refinement options to appear and the Tier 1 options disappear. When a customer clicks a Tier 2 option, the Tier 3 (subsubcategory) refinement options appear, and the Tier 2 options disappear. As noted above, these options are hidden and shown-your web application is not impacted by them.

Each facet is contained within `<facet-item>` tags. In the following example, it shows one facet that allows the customer to refine the search results by "holiday".

Example:

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item> 
 
 </facets> 

```

<table id="table_0B30EB2D155146CFA93F102516F2E5FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Facets </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Customer-facing title for the facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Customer-facing label for the facet option. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Relative link to results that the option refines down. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> The number of results in that refined result set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> When a facet value is selected the node returns an “undo link” that lets a customer back out of the results. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header and Query {#section_802835E19BCB48239C6770A1B72DFFF8}

Example:

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 

```

Used together, these tags present a message such as the following: "Showing results 1-16 of 621 for 'new year'."

<table id="table_E566D26FECEF4CE4AB3B46EDA1CAF8EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Header and Query </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> The keyword query that is submitted with the request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> The item number of the first result on this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> The item number of the last result on this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> The total number of results that match the user query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> An optional field that applies globally to the search results. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pagination {#section_72DB86DDE1284B1EA295CFFBC16A3150}

Example:

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 

```

<table id="table_0E4D4903A2A243109FB878E90B8A046E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Pagination </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> Total number of pages of results, based on the number of results divided by the number of results per page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to the first page in the result set, unless the customer is already viewing page 1. In such case, it is blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to the last page in the result set, unless the customer is viewing the last page. In such case, it is blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to the previous page in the result set, unless the customer is viewing page 1; in such case, it is blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to the last page in the result set, unless the customer is viewing the last page. In such case, it is blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x" </span> </p> </td> 
   <td colname="col2"> <p> Contains a relative link to a particular page number. Ten contiguous page numbers are shown. On page 1, it would be pages 1-10. At the end of the result set (in this case, 39), it would be pages 30-39. For example, in the center of the result set, page 15, it would be pages 11-20. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Applied as an attribute to the currently selected page. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recent Searches {#section_BCA2DDD17F264CF6BA11634E1A514E28}

Recent Searches is a cookie-based feature that only works if you relay the cookie information to the servers.

Example:

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 

```

<table id="table_B2E55ECBF4FF46AF8AFE06D083836F3E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Recent Searches </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> An individual recent-search node. You can have multiple recent-search nodes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> The term that the customer searched for previously. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Links to the previous search. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Results {#section_EC496F5CA2634158891455E2F6DF6833}

The Results set is a customizable area of the XML response. Each index is unique in the field naming mechanisms of metadata. There are common fields that are returned for each result such as title, description, and URL. But, any metadata that is defined for a page in the index can become available to use in each result node. Categorization, prices, colors, and thumbnails are just a few of the options that you can apply to a result to produce more compelling search results.

The Results format is customized based on the metadata that is specific to your implementation. Any per-result data for display in the results, including thumbnail image URLs, is contained here.

In addition, it is possible to configure multiple result zones within the page, such as “Featured Results”, or separate “Products” and “Content” results sections. In these cases, multiple result zones are provided within the HTML, although facets are only associated with the primary result set.

Example:

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[http://mysite.com/assets/cms/parties/new-years-eve-​​​​​slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[http://mysite.com/assets/cms/parties/new-years-eve-​slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[http://mysite.com/assets/cms/parties/10-holiday-​traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[http://mysite.com/assets/cms/parties/10-holiday-​traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[http://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[http://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[http://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[http://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[http://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 

```

<table id="table_0F8EF727ADFC483BB4BEBAD02803F65C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Results </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> The serial number of the result within this result set. In this example, where ten results are shown per page, on page 2 of the results, the first item would have an index of 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> The customer-facing title for this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> The URL for this page. It is used to create a hyperlink that lets the customer click through the results. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Search Form {#section_F92D8C3D37174A10A4E26CAFF3F3DF89}

Example:

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table id="table_6161E740EC9B4F05AFB2036B019C57F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Search Form </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> Optional. When present in the XML, a value of 1 it indicates that your account is linked to <span class="keyword"> Test&amp;Target </span> and has at least one business rule that is in an A:B test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> Optional. When using auto-complete, this node is present to indicate that the CSS and JavaScript is present on the page along with the content that is in the form. These fields typically do not change unless someone has changed an autocomplete setting. In such cases, the xxx_cache_ver field is incremented to force an invalidation of the cached content on your customer’s browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> The CSS that is associated with autocomplete. It is recommended that you place this tag high in the page to improve page rendering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> Content that is required inside your search-from for the autocomplete utility to hook-up to the correct control. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> Custom JavaScript that is required for Autocomplete. It is recommended that you place this tag low in the page to improve page rendering. The YUI JavaScript is also required for autocomplete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> Contains all the hidden parameters (name and value) to include in the search form. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sort {#section_32DC50A103BF491BA3665A5CADCCAADE}

The following example shows the data for a three-option sort menu. The menu allows the customer to sort by relevance, title, or rating. The currently selected item includes an attribute "selected=true". ". Always offer a relevance option to allow a customer to return to the default search results that were originally displayed.

Example:

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>

```

<table id="table_8517E21402104B8AA415BA0AF9CD5E28"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Sort Menu </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> The customer-facing text for the option. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Represents the value of the “sort” query string parameter for this option. This tag is not needed if the <span class="codeph"> &lt;link&gt; </span> value is used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> For the non-selected options, the <span class="codeph"> &lt;link&gt; </span> parameter contains the relative link that returns the same result set, sorted by the new sort parameter. This field is blank for the currently selected sort option. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suggestions {#section_D81BCE46F0AF443695DF9C4BA084B716}

Suggestions are returned when there are only a few result or no results. This node contains terms that do yield successful queries and can be displayed on a "No Results" page. The link is also returned so a customer can jump to the new query.

Example:

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 

```

<table id="table_D7CF50B4BF2D4D9EBC386649A1BA89C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Suggestions </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>A relative link that is used to create a hyperlink to search results for the suggestion term. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>The suggested term. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zones {#section_15D8AA585F3246799968BA88EE2C9FC2}

Example:

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 

```

<table id="table_4789E01C699E4D2C90A5ED7596D2041B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Zones </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> An individual zone node. You can have multiple zone nodes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> The name of the zone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1 or 0 to indicate if the zone is or is not displayed. The actual zone content can be a static area on your web page or in your search results, such as best sellers or related products. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Guided Search XML Output for Adobe Experience Manager {#reference_DBE13C606C3A4BB185DE53F88D0D3048}

Tables that describe the standard XML response output for AEM (Adobe Experience Manager).

<!-- 

r_gsxmloutputforwem.xml

 -->

See also . [Guided Search XML Output](../c-appendices/c-guidedsearchoutput.md#reference_D93E859A277643068B10AE7A61C973EA)

You can review XML response for the following:

* [Banners](../c-appendices/c-guidedsearchoutput.md#section_B16EDC5533FA4494AC9983AA7357CBE3) 
* [Breadcrumbs](../c-appendices/c-guidedsearchoutput.md#section_49EA7043FBE44315A79A4E738BE30114) 
* [Custom Fields](../c-appendices/c-guidedsearchoutput.md#section_38DD31AFE5DD4263A63644AFF484E0F4) 
* [Facets](../c-appendices/c-guidedsearchoutput.md#section_BE98990E3DD748A1BD4E0CA322314B79) 
* [Header](../c-appendices/c-guidedsearchoutput.md#section_5305B1DC5774439485CA0665DB683F9C) 
* [Menus and Sorting](../c-appendices/c-guidedsearchoutput.md#section_A34CBB645DBF4C70A12A5B7E81211295) 
* [Pagination](../c-appendices/c-guidedsearchoutput.md#section_E52F81C6A6EB4B8F996157B657EC540F) 
* [Query](../c-appendices/c-guidedsearchoutput.md#section_3DAA1013F09742869B80F6A361816E6C) 
* [Recent Searches](../c-appendices/c-guidedsearchoutput.md#section_17F942F6EC07456DABED7A483AC08446) 
* [Results](../c-appendices/c-guidedsearchoutput.md#section_155A80B8C4F641678DD9C8F257108412) 
* [Search Form](../c-appendices/c-guidedsearchoutput.md#section_9E4B99D4FEDC49629F6C7E866F3A7493) 
* [Suggestions](../c-appendices/c-guidedsearchoutput.md#section_2899FACB9AD84F60B3687C1B4EF09E15) 
* [Template](../c-appendices/c-guidedsearchoutput.md#section_1E2BB2F274B04F5491A4CCCC38F507BD) 
* [Zones](../c-appendices/c-guidedsearchoutput.md#section_26C4A947E7B1474A8E37D86D9579B93E)

## Banners {#section_B16EDC5533FA4494AC9983AA7357CBE3}

Site search/merchandising can manage a customer's banners, plugging the banners into various parts on a web page.

Example banner:

The following is an example of a banner that is placed in the area of the pages called "top".

```xml
   <banners> 
       <banner> 
           <area><![CDATA[top]]></area> 
           <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
       </banner> 
    </banners> 

```

<table id="table_36C4AA40C4D041F8BD174E12651DE0DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>banners </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p>Contains 0-n banner nodes denoting each banner area and the content that is plugged into that area. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>banner </p> </td> 
   <td colname="col2"> <p>banners </p> </td> 
   <td colname="col3"> <p>An individual banner node. You can have multiple banner nodes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>area </p> </td> 
   <td colname="col2"> <p>banner </p> </td> 
   <td colname="col3"> <p>The area on the web page where the banner is displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>content </p> </td> 
   <td colname="col2"> <p>banner </p> </td> 
   <td colname="col3"> <p>The banner content. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumbs {#section_49EA7043FBE44315A79A4E738BE30114}

Multiple breadcrumbs are supported. You can define breadcrumbs and their corresponding behavior in **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**. Also, you need to assign a unique name for each breadcrumb that you define. The breadcrumbs XML node iterates over all of your defined breadcrumbs. It is recommended that you only display one breadcrumb in your search-results.

In the following example, each time the customer narrows down further through the facets, the selection is added to the breadcrumb. Each item is represented as a `<breadcrumb-item>`.

Example breadcrumb node:

```xml
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;sp_cs=UTF-8;view=xml]]></link> 
   <value><![CDATA[mens]]></value> 
                <label><![CDATA[]]></label> 
      </breadcrumb-item> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;q1=Channel;sp_cs=UTF-8;view=xml;x1=brand]]></link> 
   <value><![CDATA[Channel]]></value> 
                <label><![CDATA[brand]]></label> 
      </breadcrumb-item> 
   </breadcrumb> 
    </breadcrumbs> 

```

<table id="table_66079AAA77534D36B6CE64B09BE446AC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>breadcrumbs </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p> Contains 0-n breadcrumb nodes that define each breadcrumb. Most customers only have one breadcrumb. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>breadcrumb </p> </td> 
   <td colname="col2"> <p>breadcrumbs </p> </td> 
   <td colname="col3"> <p> Contains the children nodes defining the definition of a breadcrumb. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>breadcrumb </p> </td> 
   <td colname="col3"> <p> The name of the breadcrumb. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>breadcrumb-item </p> </td> 
   <td colname="col2"> <p>An individual item within the breadcrumb. Each item denotes a step in the trail as the user narrows down the results set. </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> A relative link to search results that shows the desired view. Clicking a breadcrumb link takes the customer to a view where all the subsequent refinements are removed. Other options are also available such as drop and remove. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> Customer-facing text for the breadcrumb item. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> The label tag outputs a label for a breadcrumb value detailing which facet was selected to generate that breadcrumb item. It is only used in the context of a guided-breadcrumb block. For the query term step this is blank. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Custom Fields {#section_38DD31AFE5DD4263A63644AFF484E0F4}

Custom fields is a miscellaneous collection of variables with a global context. It is typically used to pass over variables for SEO purposes that are set in the search results page's metadata.

Example custom fields node:

```xml
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 

```

<table id="table_8BA1810900D54C35A0F7CABA2BE0EEE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>custom-fields </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p> Can contain 0-n children nodes that define custom fields. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>custom-field </p> </td> 
   <td colname="col2"> <p>custom-fields </p> </td> 
   <td colname="col3"> <p> Optional. Contains a value for a given custom field indicated by the name attribute. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_BE98990E3DD748A1BD4E0CA322314B79}

Facets are refinement options that give customers the ability to filter on the results. Facets are commonly used for categorization, price ranges, color selections, and other attribute refinement. Facets are built on top of the metadata in the index.

It is common to hide or show categorization facets' as a customer moves down through the categorization. The highest level of categorization (category) is known as Tier 1. When a customer clicks a Tier 1 option, the Tier 2 (subcategory) refinement options to appear and the Tier 1 options disappear. When a customer clicks a Tier 2 option, the Tier 3 (sub-subcategory) refinement options appear, and the Tier 2 options disappear. As noted above, these options are hidden and displayed; your web application does not impact them.

Each facet is contained within `<facet-item>` tags. In the following example, it shows one facet that lets the customer refine the search results by "holiday".

Example of facet block:

```xml
<facets>  
         
     <facet> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undo-link> 
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;q2=Mens;sp_staged=1;view=xml;x1=brand;x2=leveli]]></link> 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undolink> 
      </facet-value> 
      </facet> 
     <facet> 
         <facet-title><![CDATA[Sub-Category]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>0</selected> 
      <facet-value>           
              <label><![CDATA[Apparel]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans;q3=Apparel;sp_staged=1;view=xml;x1=leveli;x2=brand;x3=levelii]]></link> 
       <count><![CDATA[3]]></count>                         
      </facet-value>   
      </facet>         
     <facet> 
         <facet-title><![CDATA[Brand]]></facet-title> 
                <behavior><![CDATA[multi-select]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undo-link> 
      <facet-value>        
              <label><![CDATA[Amoura]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Amoura;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[9]]></count>                         
      </facet-value>   
      <facet-value>         
              <label><![CDATA[Armora]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[12]]></count>                        
      </facet-value>   
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Armora Jeans]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora+Jeans;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undolink> 
      </facet-value>   
      <facet-value>           
              <label><![CDATA[Art of Grooming]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Art+of+Grooming;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count>                         
      </facet-value>   
      <facet-value>          
              <label><![CDATA[Bear Co.]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Bear+Co.;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[1]]></count> 
      </facet-value> 
      <facet-value>      
              <label><![CDATA[Citizens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Citizens;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[D&amp;B]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|D%26B;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[17]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[David Yuri]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|David+Yuri;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[2]]></count>    
      </facet-value>   
      </facet> 
    </facets> 

```

<table id="table_63EDBBC84A1B46A5B24A5BD30069C997"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>facets </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p>The container facets node that has 0-n children nodes representing each facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet </p> </td> 
   <td colname="col2"> <p>facets </p> </td> 
   <td colname="col3"> <p> A single facet instance. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-title </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Customer-facing title for the facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>behavior </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>The facet's behavior. For example, normal, sticky, or multi-select. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>selected </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>1 if the facet has a selected value otherwise 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>undo-link </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p> Only present when the facet selected. Undo link reverts the whole facet. For example, when it is a multi-select facet, it deselects all selected options for the facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-value </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Contains all the individual facet items belonging to the facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>selected </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>If the current item with the facet is selected, this node is present and set to "true". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Customer-facing label for the facet option. By default this should already by HTML-escaped. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p> Relative link to results that the option further refines. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>count </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>The number of results in that refined result set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>undo-link </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>When a facet value is selected the node returns an “undo link” that lets a customer back out selecting that individual facet selection. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header {#section_5305B1DC5774439485CA0665DB683F9C}

Example:

```xml
xml version="1.0" encoding="utf-8" standalone="yes" 
```

## Menus and Sorting {#section_A34CBB645DBF4C70A12A5B7E81211295}

Menus for sorting the results are supported, and changing the number of results to return per page. It also supports a navigation menu that is useful for using "search as navigation". An account can define multiple menus of the same type and use any of the menus for their presentation.

Example menus node:

The following example shows the data for a three-option sort menu and navigation menu. The sort menu allows the customer to sort by relevance, title, or rating. The currently selected item includes an attribute "selected=true". ". Always offer a relevance option to allow a customer to return to the default search results that were originally displayed.

```xml
<menus> 
        <menu> 
           <name><![CDATA[sort]]></name>         
             <item selected="true"> 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>   
                    <item> 
                        <label><![CDATA[WOMEN'S]]></label> 
          <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[MEN'S]]></label> 
          <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
          <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
          <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
          <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
          <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[GIFTS & HOME]]></label> 
          <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[CHILDREN & TOYS]]></label> 
          <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[ELECTRONICS]]></label> 
          <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link> 
                    </item> 
        </menu> 
    </menus> 

```

<table id="table_62C463D195E94557B2C32E91F5E92C04"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>menus </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p>Contains 0-n children nodes defining each menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>menu </p> </td> 
   <td colname="col2"> <p>menus </p> </td> 
   <td colname="col3"> <p>Single instance of a menu (corresponds to a menu that is defined in <span class="uicontrol"> Design </span> &gt; <span class="uicontrol"> Navigation </span> &gt; <span class="uicontrol"> Menus </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>menu </p> </td> 
   <td colname="col3"> <p>Name of the menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>item </p> </td> 
   <td colname="col2"> <p>menu </p> </td> 
   <td colname="col3"> <p>Defines each item in the menu. The optional attribute selected is set to true if the given menu item is currently selected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>item </p> </td> 
   <td colname="col3"> <p>The customer-facing text for the menu item. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>item </p> </td> 
   <td colname="col3"> <p>Represents the value of the menu item (the query parameter value that the menu is set too) . This tag is not needed if the &lt;link&gt; value is used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>item </p> </td> 
   <td colname="col3"> <p>For the non-selected options, the &lt;link&gt; parameter contains the relative link that returns the same result set, but with the menu option applied. This field is blank for the currently selected sort option. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pagination {#section_E52F81C6A6EB4B8F996157B657EC540F}

Results sets are split over several pages. Typically customers display 10 - 20 results on a single page. Subsequent results are displayed on the next page. The pagination XML lets you build a set of navigation links so that your customers can browse, page by page, through the result sets. There are four available navigation links: first, last, next, and previous. Each type of link lets customers quickly move through the pages so they can review and refine what they are looking for, easily.

The following example shows the pagination for a search that is on the first page with the pagination configured to show links to five pages.

Example pagination:

```xml
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
        </pages> 
    </pagination> 

```

<table id="table_8996E1EEA70E4023A93C55F6CCA716AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>pagination </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p> Total number of pages of results, based on the number of results divided by the number of results per page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total-pages </p> </td> 
   <td colname="col2"> <p>pagination </p> </td> 
   <td colname="col3"> <p>The total number of pages that the search results are spread out over. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pages </p> </td> 
   <td colname="col2"> <p>pagination </p> </td> 
   <td colname="col3"> <p>Contains 0-n page nodes defining each page in the pagination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>page </p> </td> 
   <td colname="col2"> <p>pages </p> </td> 
   <td colname="col3"> <p>Four special page nodes exists: first, last, previous, and next. These four pages are optional and appear in the result set only if they make sense. For example, if you are on page 1, there is no "previous" link. All other pages indicate a position. The number of pages that are listed depends on the "number of links to pages" that is configured in the pagination user interface. The "selected" attribute indicates the page that the customer is currently on. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Query {#section_3DAA1013F09742869B80F6A361816E6C}

Example query node:

```xml
    <query> 
        <user-query><![CDATA[mens]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[265]]></total-results> 
    </query> 

```

<table id="table_70E0F1CB76E24892AB054669C255E291"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>query </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p> A global node that provides an overview of the query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>user-query </p> </td> 
   <td colname="col2"> <p>query </p> </td> 
   <td colname="col3"> <p> The keyword that was searched for. If <span class="uicontrol"> Did You Mean </span> automatically searched for a suggested term due to the original term yielding no results, it is reflected in the new keyword that was searched for (see the suggestions node to get the original keyword). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>lower-results </p> </td> 
   <td colname="col2"> <p>query </p> </td> 
   <td colname="col3"> <p> The item number of the first result on this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>upper-results </p> </td> 
   <td colname="col2"> <p>query </p> </td> 
   <td colname="col3"> <p> The item number of the last result on this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total-results </p> </td> 
   <td colname="col2"> <p>query </p> </td> 
   <td colname="col3"> <p> The total number of results that match the user query. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recent Searches {#section_17F942F6EC07456DABED7A483AC08446}

Recent Searches is a cookie-based feature that only works if you relay the cookie information to site search/merchandising servers.

Example of recent searches:

```xml
    <recent-searches> 
        <clear-link><![?q=womens&gscr=clear]]></clear-link> 
        <recent-search> 
            <link><![?q=mens]]></link> 
            <label><![CDATA[mens]]></label> 
        <recent-search> 
    </recent-searches> 

```

<table id="table_04D61364303D42399A467E83A96DD7C1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>recent-searches </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p>Node is only present if search has recent searches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clear-link </p> </td> 
   <td colname="col2"> <p>recent-searches </p> </td> 
   <td colname="col3"> <p>The relative path that clears all the customer's recent searches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>recent-search </p> </td> 
   <td colname="col2"> <p>recent-searches </p> </td> 
   <td colname="col3"> <p>Defines n recent searches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>recent-search </p> </td> 
   <td colname="col3"> <p>The path to create a link that performs a search that the user recently performed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>recent-search </p> </td> 
   <td colname="col3"> <p>Customer facing display label for the recent search. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Results {#section_155A80B8C4F641678DD9C8F257108412}

The Results set is a customizable area of the XML response. Each index is unique in the field naming mechanisms of metadata. There are common fields that are returned for each result such as title, description, and URL. But, any metadata that is defined for a page in the index can become available to use in each result node. Categorization, prices, colors, and thumbnails are just a few of the options that you can apply to a result to produce more compelling search results.

The results format is customized based on the metadata that is specific to your implementation. Any per-result data for display in the results, including thumbnail image URLs, is contained here.

In addition, it is possible to configure multiple result zones within the page, such as "Featured Results", or separate "Products" and "Content" results sections. In these cases, multiple result zones are provided within the HTML, although facets are only associated with the primary result set.

Example results node:

```xml
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
                    <field name="sku"><![CDATA[200190]]></field> 
                    <field name="pagename"><![CDATA[Relaxed Paint Splattered]]></field> 
 
                    <field name="img_sm_url"><![CDATA[http://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>   
         <result> 
                    <field name="index"><![CDATA[2]]></field> 
                    <field name="sku"><![CDATA[200195]]></field> 
                    <field name="pagename"><![CDATA[Tumbled Jeans]]></field> 
 
                    <field name="img_sm_url"><![CDATA[http://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[235]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>    
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
                    <field name="sku"><![CDATA[200196]]></field> 
                    <field name="pagename"><![CDATA[Montana Relaxed]]></field> 
 
                    <field name="img_sm_url"><![CDATA[http://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[220]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>   
      
        </result-set>   
    </results> 

```

<table id="table_44C1078F413B483284855B52E8E0AC2C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>results </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p>The container node for 0-n results sets. Zero result sets means that you are on a special no-results landing page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>result-set </p> </td> 
   <td colname="col2"> <p>results </p> </td> 
   <td colname="col3"> <p>An incoming search can fire multiple searches. Each result-set contains the results for a specific named search that was performed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>result-set </p> </td> 
   <td colname="col3"> <p>The name of the search that the result set belongs to. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>result </p> </td> 
   <td colname="col2"> <p>result-set </p> </td> 
   <td colname="col3"> <p>Contains all the fields that are associated with an individual result for the result set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>field </p> </td> 
   <td colname="col2"> <p>result </p> </td> 
   <td colname="col3"> <p>The name attribute defines the name of the field within the index that is displayed. The value is the actual value for that field. Some results can have missing fields that are not relevant for that individual result. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Search Form {#section_9E4B99D4FEDC49629F6C7E866F3A7493}

Search Form is included in the result set to let customers build their search form dynamically. This step is optional. Most customers have a fixed search form. However, it does allow customers to determine if the search form needs a Test&Target mbox, based on having at least one business rule that does an A:B test. Similarly it allows customers to automatically pick-up the latest autocomplete CSS and JavaScript.

Example of search form XML:

```xml
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="http://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="http://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 

```

<table id="table_EAB9976D5433486EB3D45B512EE96E5B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>search-form </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p>Contains data for driving the search form. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>include-tnt-mbox </p> </td> 
   <td colname="col2"> <p> search-form </p> </td> 
   <td colname="col3"> <p>Technically you only require an mbox in the search form when you have at least one business rule doing a Test&amp;Target A:B test. This node indicates if you need an mbox or not allowing you to reduce the number hits on the Test&amp;Target servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>autocomplete </p> </td> 
   <td colname="col2"> <p>search-form </p> </td> 
   <td colname="col3"> <p>Houses children node related to auto-complete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>enabled </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>Set to 1 when the search account is using autocomplete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>css </p> </td> 
   <td colname="col2"> <p> autocomplete </p> </td> 
   <td colname="col3"> <p> CSS for autocomplete. Place this node as high up on the page as possible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> form-content </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>Content that is injected into the search form. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javascript </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>JavaScript for autocomplete. Place this node as low as possible on the page. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suggestions {#section_2899FACB9AD84F60B3687C1B4EF09E15}

Customers can configure **[!UICONTROL Did You Mean]** functionality in three ways: make suggestions due to no results, automatically search against the first suggestion when we have no results, or make suggestions due to low results (where the suggestions have a higher result count). All the suggestions yield results.

This suggestions node contains the terms that do yield successful queries. The link is also returned so a customer can jump to the new query.

Example output for making suggestion due to 0 results:

```xml
    <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>0</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=arcade;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[arcade]]></word> 
 </suggestion-item>    
    </suggestions>

```

Example output for automatically searching against a suggestion:

```xml
    <suggestions> 
        <auto-searched>1</auto-searched> 
        <orig-query><![CDATA[arcace]]></orig-query> 
        <suggestions-low-results>0</suggestions-low-results>         
    </suggestions> 

```

Example output for making suggestion due to low results:

```xml
   <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>1</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=coffee;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[coffee]]></word> 
 </suggestion-item>  
    </suggestions> 

```

<table id="table_7ABB4F1B979F4645AEB36FCA735B49C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>suggestion </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p> Contains children nodes that define suggestion, if any exist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>auto-searched </p> </td> 
   <td colname="col2"> <p>suggestions </p> </td> 
   <td colname="col3"> <p> If present, indicates if site search/merchandising automatically searched against a new term due to no results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>orig-query </p> </td> 
   <td colname="col2"> <p>suggestions </p> </td> 
   <td colname="col3"> <p> When site search/merchandising automatically searches against the first suggestion, the user-query in the query node shows the keyword that is searched against. This node shows the original query term. Combining the two lets customers create structures such as "Searching for arcade instead of arcace". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>suggestions-low-results </p> </td> 
   <td colname="col2"> <p>suggestions </p> </td> 
   <td colname="col3"> <p>If present, indicates if site search/merchandising is making suggestions due to the current search term yielding low results and a suggestion yielding considerably higher results. The two thresholds are configurable in <span class="uicontrol"> Did You Mean </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>suggestion-item </p> </td> 
   <td colname="col2"> <p>suggestions </p> </td> 
   <td colname="col3"> <p>Contains 0-n nodes denoting the various suggestions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>suggestion-item </p> </td> 
   <td colname="col3"> <p>Contains the path for creating a link to the suggested term. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>word </p> </td> 
   <td colname="col2"> <p>suggestion-item </p> </td> 
   <td colname="col3"> <p> Contains the suggested word. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Template {#section_1E2BB2F274B04F5491A4CCCC38F507BD}

The ability to switch a customers search experience based on the results is supported. Part of this involves switching between different templates with a different layout of search results. For example, you may have a template with a grid view of products for when you have lots of products. Or, you may have a "spotlight" template when displaying a single result that has more details. You may also have a "no results" template when a search does not yield any results. The template node indicates which template is used to display the search results.

Example template:

```xml
<template><![CDATA[grid]]></template>
```

<table id="table_5AF5CE3898B64CDCB7F0AC473EB381E6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>template </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p>Indicates the name of the template that is used to display the search results. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zones {#section_26C4A947E7B1474A8E37D86D9579B93E}

Zones are sections of the pages that can be turned on or turned off by business rules. A zone can contain any content including, but not limited too, facets, searches, breadcrumbs, static content. The zones on the customers web page should map to the same areas as site search/merchandising.

Example of zone nodes:

```xml
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 

```

<table id="table_F7F7CEB652AC4C01A55377287E3B7741"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Node </p> </th> 
   <th colname="col2" class="entry"> <p>Parent Node </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>zones </p> </td> 
   <td colname="col2"> <p>customer-results </p> </td> 
   <td colname="col3"> <p>Contains 0-n zones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zone </p> </td> 
   <td colname="col2"> <p>zones </p> </td> 
   <td colname="col3"> <p> An individual zone node. You can have multiple zone nodes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>zone </p> </td> 
   <td colname="col3"> <p>The name of the zone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>display </p> </td> 
   <td colname="col2"> <p>1 or 0, indicating if the zone corresponding to the zone name is displayed or hidden. </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Examples {#reference_64B7D8D228AF4B8D90EDF4DE507B0F84}

Example output for a &#42; search on a fictional website called Geometrixx and an example presentation template that is used to produce the example output.

<!-- 

r_examples.xml

 -->

* [Example Output](../c-appendices/c-guidedsearchoutput.md#section_515C000A18B847D59097D0A9CCC02636) 
* [Example Presentation Template](../c-appendices/c-guidedsearchoutput.md#section_AD42571DFB88491AA7F0FDF0929EBE97)

## Example Output {#section_515C000A18B847D59097D0A9CCC02636}

Example output for a &#42; search on a fictional website called Geometrixx.

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[*]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[1337]]></total-results> 
    </query> 
 
    <custom-fields> 
 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name>

             <item selected="true"> 
 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item>

             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=*;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>

                    <label><![CDATA[WOMEN'S]]></label> 
      <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link>

                    <label><![CDATA[MEN'S]]></label> 
      <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
      <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link>

                    <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
      <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
      <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link>

                    <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
      <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link>

                    <label><![CDATA[GIFTS & HOME]]></label> 
      <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link>

                    <label><![CDATA[CHILDREN & TOYS]]></label> 
      <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link>

                    <label><![CDATA[ELECTRONICS]]></label> 
      <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link>

        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
       
  <breadcrumb-item> 
    <link><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></link> 
    <value><![CDATA[*]]></value> 
                        <label><![CDATA[]]></label> 
   </breadcrumb-item> 
          
   </breadcrumb> 
 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched>0</auto-searched> 
         
        <suggestions-low-results>0</suggestions-low-results> 
         
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
      
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

        </pages> 
    </pagination> 
 
    <facets>  
         
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected>0</selected>

      <facet-value> 
           
              <label><![CDATA[Womens]]></label> 
 
       <link><![CDATA[?i=1;q=*;q1=Womens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[219]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Mens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[202]]></count> 
                         
      </facet-value> 
   
      <facet-value>

              <label><![CDATA[Beauty &amp; Fragrance]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Beauty+%26+Fragrance;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[169]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Children &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Children+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[209]]></count> 
                         
      </facet-value>

      <facet-value> 
           
              <label><![CDATA[Electronics &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Electronics+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[200]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Gifts &amp; Home]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Gifts+%26+Home;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[156]]></count>

      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Jewelry &amp; Accessories]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Jewelry+%26+Accessories;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[182]]></count> 
                         
      </facet-value> 
   
      </facet-item> 
  
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
               
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[2]]></field> 
      <field name="brand"><![CDATA[One For All]]></field> 
      <field name="price"><![CDATA[145]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[208]]></field> 
 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[4]]></field> 
      <field name="brand"><![CDATA[Vera Watson]]></field> 
      <field name="price"><![CDATA[850]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Dresses,  
          Day]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[5]]></field> 
 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[6]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[80]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[7]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[85]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[8]]></field> 
      <field name="brand"><![CDATA[Woolberry]]></field> 
 
      <field name="price"><![CDATA[280]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[9]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[10]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[55]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[11]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[45]]></field> 
 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[12]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[47]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
      
        </result-set>   
    </results>

    <banners> 
         
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
            </banner>

    </banners> 
 
    <zones> 
        <zone> 
 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="http://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="http://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 

```

## Example Presentation Template {#section_AD42571DFB88491AA7F0FDF0929EBE97}

The following is an example presentation template that is used to produce the example output above.

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[<guided-query-param gsname="q" />]]></user-query> 
 <lower-results><![CDATA[<guided-results-lower>]]></lower-results> 
 <upper-results><![CDATA[<guided-results-upper>]]></upper-results> 
 <total-results><![CDATA[<guided-results-total>]]></total-results> 
    </query> 
 
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[<guided-general-field gsname="default" field="seo_search_keywords"/>]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name> 
     <guided-menu gsname="sort"> 
         <guided-if-menu-item-selected> 
             <item selected="true"> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
        <guided-else-menu-item-selected> 
             <item> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[<guided-menu-item-path />]]></link>     
             </item> 
        </guided-if-menu-item-selected> 
    </guided-menu> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name> 
            <guided-menu gsname="ss_head_nav"> 
                <guided-if-menu-item-selected> 
                    <item selected="true"> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                <guided-else-menu-item-selected> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                </guided-if-menu-item-selected> 
            </guided-menu>  
        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
      <guided-breadcrumb gsname="default"> 
  <breadcrumb-item> 
    <link><![CDATA[<guided-breadcrumb-path gsname="goto">]]></link> 
    <value><![CDATA[<guided-breadcrumb-value />]]></value> 
                        <label><![CDATA[<guided-breadcrumb-label>]]></label> 
   </breadcrumb-item> 
         </guided-breadcrumb> 
   </breadcrumb> 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched><guided-if-suggestion-autosearch>1<guided-else-suggestion-autosearch>0</guided-if-suggestion-autosearch></auto-searched> 
        <guided-if-suggestion-autosearch><orig-query><![CDATA[<guided-suggestion-original-query/>]]></orig-query></guided-if-suggestion-autosearch> 
        <suggestions-low-results><guided-if-suggestion-low-results>1<guided-else-suggestion-low-results>0</guided-if-suggestion-low-results></suggestions-low-results> 
        <guided-suggestions> 
     <suggestion-item> 
         <link><![CDATA[<guided-suggestion-path />]]></link> 
  <word><![CDATA[<guided-suggestion />]]></word> 
     </suggestion-item> 
 </guided-suggestions> 
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[<guided-page-total />]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[<guided-page-path gsname="first" />]]></page> 
     <page position="last"><![CDATA[<guided-page-path gsname="last" />]]></page> 
     <guided-if-page-prev><page position="prev"><![CDATA[<guided-page-path gsname="prev" />]]></page></guided-if-page-prev> 
     <guided-if-page-next><page position="next"><![CDATA[<guided-page-path gsname="next" />]]></page></guided-if-page-next> 
     <guided-if-page-viewall><page position="viewall"><![CDATA[<guided-page-path gsname="viewall" />]]></page></guided-if-page-viewall> 
     <guided-if-page-viewpages><page position="viewall"><![CDATA[<guided-page-path gsname="viewpages" />]]></page></guided-if-page-viewpages> 
 
     <guided-pages> 
                <guided-if-page-selected><page position="<guided-page-number />" selected="true"><![CDATA[<guided-page-path />]]></page> 
  <guided-else-page-selected><page position="<guided-page-number />"><![CDATA[<guided-page-path />]]></page> 
  </guided-if-page-selected> 
     </guided-pages> 
        </pages> 
    </pagination> 
 
    <facets>  
        <guided-facet gsname="leveli"> 
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected><guided-if-facet-selected>1<guided-else-facet-selected>0</guided-if-facet-selected></selected> 
                <guided-if-facet-selected><undo-link><![CDATA[<guided-facet-undo-path gsname="leveli">]]></undo-link></guided-if-facet-selected> 
  <guided-facet-values> 
      <facet-value> 
          <guided-if-facet-value-selected><selected><![CDATA[true]]></selected></guided-if-facet-value-selected> 
              <label><![CDATA[<guided-facet-value>]]></label> 
       <link><![CDATA[<guided-facet-value-path />]]></link> 
       <count><![CDATA[<guided-facet-count>]]></count> 
                        <guided-if-facet-value-selected><undolink><![CDATA[<guided-facet-value-undo-path />]]></undolink></guided-if-facet-value-selected> 
      </facet-value> 
  </guided-facet-values> 
      </facet-item> 
 </guided-facet> 
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
            <guided-results gsname="default">   
         <result> 
                    <field name="index"><![CDATA[<guided-result-index />]]></field> 
      <field name="brand"><![CDATA[<guided-result-field gsname="brand" />]]></field> 
      <field name="price"><![CDATA[<guided-result-field gsname="price" />]]></field> 
      <field name="foundIn"><![CDATA[<guided-if-result-field gsname="leveli"><!--tmpl_var name='leveli'-->, </guided-if-result-field> 
            <guided-if-result-field gsname="levelii"><!--tmpl_var name='levelii'-->, </guided-if-result-field> 
          <guided-if-result-field gsname="leveliii"><!--tmpl_var name='leveliii'--></guided-if-result-field>]]></field> 
         </result>   
     </guided-results> 
        </result-set>   
    </results> 
 
    <guided-if-recent-searches> 
    <recent-searches> 
        <clear-link><guided-recent-searches-clear-path/></clear-link> 
        <guided-recent-searches> 
            <recent-search> 
                <link><guided-recent-searches-path></link> 
                <label><guided-recent-searches-value></label> 
            <recent-search> 
        </guided-recent-searches> 
    </recent-searches> 
    </guided-if-recent-searches> 
 
    <banners> 
        <guided-if-banner-set gsname="top"> 
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<guided-banner gsname="top">]]></content> 
            </banner> 
        </guided-if-banner-set> 
        <guided-if-banner-set gsname="bottom"> 
            <banner> 
                <area><![CDATA[bottom]]></area> 
                <content><![CDATA[<guided-banner gsname="bottom">]]></content> 
            </banner> 
        </guided-if-banner-set> 
    </banners> 
 
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display><guided-if-zone gsname="brand-facet">1<guided-else-zone>0</guided-if-zone></display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox><guided-if-tnt-business-rules>1<guided-else-tnt-business-rules>0</guided-if-tnt-business-rules></include-tnt-mbox> 
        <autocomplete> 
            <enabled><guided-if-autocomplete>1<guided-else-autocomplete>0</guided-if-autocomplete></enabled> 
            <css><![CDATA[<guided-ac-css/>]]></css> 
            <form-content><![CDATA[<guided-ac-form-content/>]]></form-content> 
            <javascript><![CDATA[<guided-ac-javascript/>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 

```

