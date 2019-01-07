---
description: null
seo-description: null
seo-title: CGI parameters
solution: Target
title: CGI parameters
topic: Appendices,Site search and merchandising
uuid: c5c951fc-4e7b-430d-a77c-49ef4d3a2c67
index: y
internal: n
snippet: y
---

# CGI parameters{#cgi-parameters}

## CGI parameters {#concept_F395999090FE4926B38BC73D5E612800}

## Search CGI parameters {#reference_DA27A8B0728246DA94994885E1353890}

Search form code is provided that you can copy and paste into the HTML of your site ( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**).

<!-- 

r_search_cgi_parameters.xml

 -->

See [Copying the HTML code of the search form into the...](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

You can also set the parameters that are listed either in the search form itself, or from a script. In addition to the parameters that are listed below you can also use the backend search parameters to control search.

See [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

Search requests consist of a base URL. The base URL indicates what account the customer is searching, and a set of CGI parameters (key-value pairs) that indicate how to return the desired search results for the associated account.

The base URL is associated with a specific account and a staged or live environment. You can request multiple aliases for the base URL from your account manager. For example, a company called Megacorp may have two base URLs associated with their account: http://search.megacorp.com and http://stage.megacorp.com. The former URL searches their live index and the latter URL searches their staged index.

Three formats of CGI Parameters are supported. By default your account is configured to separate CGI Parameters with a semi-colon as in the following example:

`http://search.megacorp.com?q=shoes;page=2`

If you prefer, you can have your account manager configure your account to use ampersands to separate the CGI parameters as in the following example:

`http://search.megacorp.com?q=shoes&page=2`

A third format, called the SEO format, is also supported where a forward slash "/" is used in place of the separator and equal sign as in the following example:

`http://search.megacorp.com/q/shoes/page/2`

Any time the SEO format is used to send a request, all output links are returned in the same format.

<table id="table_89D371BD757F4BFEAD124AEC52EA8E6E"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> <p>Guided Search parameter </p> </th> 
   <th colname="col3" class="entry"> <p>Example </p> </th> 
   <th colname="col4" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p>q </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> q=string </span> </p> </td> 
   <td colname="col4"> <p>Specifies the query string for the search. This parameter maps to the <span class="codeph"> sp_q </span> backend search parameter. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>q# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> q#=string </span> </p> </td> 
   <td colname="col4"> <p>Faceting (searching within a given field) is done by way of numbered q and x parameters. </p> <p>The q parameter defines the term you are searching for in the facet as denoted by the corresponding numbered x parameter. </p> <p>For example, if you have two facets that are named size and color, you can have something like q1=small;x1=size;q2=red;x2=color. </p> <p>This parameter maps to the <span class="codeph"> sp_q_exact_# </span> backend search parameters. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>x# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> q#=string </span> </p> </td> 
   <td colname="col4"> <p>Faceting (searching within a given field) is done by way of numbered q and x parameters. </p> <p>The q parameter defines the term you are searching for in the facet as denoted by the corresponding numbered x parameter. </p> <p>For example, if you have two facets that are named size and color, you can have something like q1=small;x1=size;q2=red;x2=color. </p> <p>This parameter maps to the <span class="codeph"> sp_x_# </span> backend search parameters. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>collection </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> collection=string </span> </p> </td> 
   <td colname="col4"> <p>Specifies the collection to use for the search. </p> <p>This parameter maps to the <span class="codeph"> sp_k </span> backend search parameter. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>count </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> count=number </span> </p> </td> 
   <td colname="col4"> <p>Specifies the total count of results that are shown. </p> <p>The default is defined in <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Searching </span> &gt; <span class="uicontrol"> Searches </span>. . </p> <p>This parameter maps to the <span class="codeph"> sp_c </span> backend search parameter. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>page </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> page=number </span> </p> </td> 
   <td colname="col4"> <p>Specifies the page of results that are returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>rank </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> rank=field </span> </p> </td> 
   <td colname="col4"> <p>Specifies the rank field to use for static ranking. </p> <p>The field must be a field of type Rank with relevance greater than 0. </p> <p>This parameter maps to the <span class="codeph"> sp_sr </span> backend parameter. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>sort </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sort=number </span> </p> </td> 
   <td colname="col4"> <p>Specifies the sort order. </p> <p> "0" is the default and sorts by relevance score; "1" sorts by date; "-1" does not sort. </p> <p>Users can specify a field name for the value of the <span class="codeph"> sp_s </span> parameter. </p> <p>For example, <span class="codeph"> sp_s=title </span> sorts results according to the values that are contained in the title field. When a field name is used for the value of an <span class="codeph"> sp_s </span> parameter, results are sorted by that field and then sub-sorted by relevance. </p> <p>To enable this feature, click <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span>. On the Definitions page, click <span class="uicontrol"> Add New Field </span> or click <span class="uicontrol"> Edit </span> for a particular field name. In the <span class="uicontrol"> Sorting </span> drop-down list, select either <span class="uicontrol"> Ascending </span> or <span class="uicontrol"> Descending </span>. This parameter maps to the <span class="codeph"> sp_s </span> backend search parameter. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Backend search CGI parameters {#reference_582E85C3886740C98FE88CA9DF7918E8}

Typically customers interact with a presentation layer called Guided Search. However, it is theoretically possible to skip the Guided Search layer and interact with the backend core search directly using the CGI parameters that are described on this page.

<!-- 

r_backend_search_cgi_parameters.xml

 -->

You can select backend search CGI parameters from the following table:

<table id="table_802D1D13EA6F4DAAA45291B5DA90D2AC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Single query support </p> </th> 
   <th colname="col03" class="entry"> <p>Multiple query support </p> </th> 
   <th colname="col3" class="entry"> <p>Examples </p> </th> 
   <th colname="col4" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>sp_a </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_a= string </span> </p> </td> 
   <td colname="col4"> <p>Specifies the account number string. This parameter is required, and must be a valid account number string. You can find your account number string under <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Account Options </span> &gt; <span class="uicontrol"> Account Settings </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_advanced= 0 or 1 </span> </p> </td> 
   <td colname="col4"> <p>If <span class="codeph"> sp_advanced=1 </span> is submitted with a query, then all code between the <span class="codeph"> &lt;search-if-advanced&gt; </span> tag and the <span class="codeph"> &lt;/search-if-advanced&gt; </span> tag in the search template is used for the search form. All code between the <span class="codeph"> &lt;search-if-not-advanced&gt; </span> tag and the <span class="codeph"> &lt;/search-if-not-advanced&gt; </span> tag is be ignored. If <span class="codeph"> sp_advanced=0 </span> (or any other value) is submitted, then the &lt;search-if-advanced&gt; template block is ignored and the &lt;search-if-not-advanced&gt; template block is used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_c= number </span> </p> </td> 
   <td colname="col4"> <p>Specifies the total count of results to show. The default is 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_context_ 
      field= 
      <i>field</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>Collects contextual information for the given field. Collected information is output in the search results by way of the <span class="codeph"> &lt;search-context&gt; </span> template tag. The default value is <span class="codeph"> body </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d= type </span> </p> </td> 
   <td colname="col4"> <p>Specifies the type of date range searching to perform. Possible values for type are any, which means do not perform date range searching, custom, which indicates that the value of <span class="codeph"> sp_date_range </span> should be used to determine the dates to search, and specific, which indicates that the values in <span class="codeph"> sp_start_day </span>, <span class="codeph"> sp_start_month </span>, <span class="codeph"> sp_start_year </span>, <span class="codeph"> sp_end_day </span>, <span class="codeph"> sp_end_month </span>, and <span class="codeph"> sp_end_year </span> is used to determine the date range to search. <span class="codeph"> sp_d </span> is only required if your search form contains the option to search either by a custom range (by way of <span class="codeph"> sp_date_range </span>), or by a specific start and end date range. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d_#= type </span> </p> </td> 
   <td colname="col4"> <p>Specifies the type of date range searching to perform for the corresponding <span class="codeph"> sp_q_# </span> query. The "#" is replaced with a number between 1 and 16 (for example, <span class="codeph"> sp_d_8 </span>, applies to the numbered query <span class="codeph"> sp_q_8 </span>). </p> <p>You can set <span class="codeph"> type </span> to any, which means do not perform date range searching, custom, which indicates that the value of <span class="codeph"> sp_date_range_# </span> is used to determine the dates to search, and specific, which indicates that the values in <span class="codeph"> sp_q_min_day_# </span>, <span class="codeph"> sp_q_min_month_# </span>, <span class="codeph"> sp_q_min_year_# </span>, <span class="codeph"> sp_q_max_day_# </span>, <span class="codeph"> sp_q_max_month_# </span>, and <span class="codeph"> sp_q_max_year_# </span> should be used to determine the date range. The use of <span class="codeph"> sp_d_# </span> is only required if your search form contains the option to search either by a custom range (by way of <span class="codeph"> sp_date_range_# </span>), or by a specific start and end date range. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>sp_date_range </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_date_ 
      range= 
      <i>number</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>Specifies a pre-defined date range to apply to the search. Values greater than or equal to zero specify the number of days to search prior to today — for example, a value of "0" specifies "today," a value of "1" specifies "today and yesterday," a value of "30" specifies "within the last 30 days," and so forth. </p> <p>Values below zero specify a custom range as follows: </p> <p>-1 = "None," the same as specifying no date range. </p> <p>-2 = "This week," which searches from Sunday to Saturday of the current week. </p> <p>-3 = "Last week," which searches from Sunday to Saturday of the week prior to the current week. </p> <p>-4 = "This month," which searches dates within the current month. </p> <p>-5 = "Last month," which searches dates within the month prior to the current month. </p> <p>-6 = "This year," which searches dates within the current year. </p> <p>-7 = "Last year," which searches dates within the year prior to the current year. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_date_ 
     range_# </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_date_ 
      range_#= 
      <i>number</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>Specifies a pre-defined date range to apply to the corresponding <span class="codeph"> sp_q_# </span> query. The "#" is replaced with a number between 1 and 16 (for example, <span class="codeph"> sp_date_range_8 </span>, applies to the numbered query <span class="codeph"> sp_q_8 </span>). </p> <p>Values greater than or equal to zero specify the number of days to search prior to today. For example, a value of 0 specifies today; a value of 1 specifies today and yesterday; a value of 30 specifies within the last 30 days, and so forth. </p> <p>Values below zero specify a custom range as follows: </p> <p>-1 = "None," the same as specifying no date range. </p> <p>-2 = "This week," which searches from Sunday to Saturday of the current week. </p> <p>-3 = "Last week," which searches from Sunday to Saturday of the week prior to the current week. </p> <p>-4 = "This month," which searches dates within the current month. </p> <p>-5 = "Last month," which searches dates within the month prior to the current month. </p> <p>-6 = "This year," which searches dates within the current year. </p> <p>-7 = "Last year," which searches dates within the year prior to the current year. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_ 
     field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_dedupe_ 
      field= 
      <i>fieldname</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>Specifies a single field to dedupe search results on. All duplicate results on that field are removed from the search results. For example, if for <span class="codeph"> sp_dedupe_field=title </span>, only the top result for a given title is displayed in the search results (no two results will have identical title field content). For multi-value (allow list) type fields, the entire field contents are used for comparison. Only one field may be specified. A "table-qualifier" is not allowed in the field name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e= number </span> </p> </td> 
   <td colname="col4"> <p>Specifies that automatic wildcard expansion should take place for any word from the query string with more than number characters. In other words, <span class="codeph"> sp_e=5 </span> specifies that words with 5 or more characters, like "query" or "number", should be expanded with the wildcard character '*', making the search equivalent to a search for "query*" or "number*". Words with fewer characters are not expanded, so a search for "word" would not have automatic wildcard expansion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e_#= number </span> </p> </td> 
   <td colname="col4"> <p>Specifies that automatic wildcard expansion takes place for any word from the corresponding <span class="codeph"> sp_q_# </span> query string with more than number characters. In other words, <span class="codeph"> sp_e_2=5 </span> specifies that words with five or more characters in the <span class="codeph"> sp_q_2 </span> query string, like "query" or "number", should be expanded with the wildcard character ' <span class="codeph"> * </span>', making the search equivalent to a search for "query*" or "number*". Words with fewer characters are not expanded, so a search for "word" in <span class="codeph"> sp_q_2 </span> would not have automatic wildcard expansion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>sp_end_day, sp_end_month, sp_end_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_end_day= 
      <i>number</i>, 
      sp_end_month= 
      <i>number</i>, 
       sp_end_year= 
      <i>number</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>This triplet of values specifies the end date range for the search and must be provided as a set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>sp_f </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_f= string </span> </p> </td> 
   <td colname="col4"> <p>Specifies the character set of the query parameter strings (such as <span class="codeph"> sp_q </span>). This string must always match the character set of the page that contains the search form. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_field_ 
      table=table: 
      field,field... 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>Defines a logical data table consisting of the given fields. For example, a table named "items" consisting of the fields "color," "size," and "price" would be defined as the following: </p> <p> <span class="codeph"> sp_field_table=items:color,size,price </span> </p> <p>Logical tables are most useful in conjunction with fields that have "Allow Lists" checked (under <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span>). All CGI parameters and template tags that take a field name as a value may optionally specify a table name followed by a "." prior to the field name (for example, <span class="codeph"> sp_x_1=tablename.fieldname </span>). </p> <p>For example, to perform a search for documents that contain one or more "red" items in size "large" (where items are represented as parallel rows of metadata), you could use the following: </p> <p> 
     <codeblock>
       sp_q_exact_1=red&amp;sp_x_1=items.color&amp; 
      sp_q_exact_2=large&amp;sp_x_2=items.size&amp; 
      sp_field_table=items:color,size,price 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_i= <span class="varname"> value </span> </span> </p> </td> 
   <td colname="col4"> <p>Ignores the search when you generate reports. </p> <p>Use this query to mask certain backend searches, such as searches that Did You Mean generates, or searches that an Administrator generates in the member center. Because an end user does not generate these types of searches, they do not show up in various Adobe Search&amp;Promote reports. </p> <p>Valid values are <span class="codeph"> sp_i=1 </span> and <span class="codeph"> sp_i=2 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>16 </p> </td> 
   <td colname="col2"> <p>sp_k </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_k= string </span> </p> </td> 
   <td colname="col4"> <p> Specifies the collection to use for the search. The default is no collection, meaning that the search should include the whole site. </p> <p>See <a href="../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3" type="reference" format="dita" scope="local"> Using collections in search forms </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>17 </p> </td> 
   <td colname="col2"> <p>sp_l </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_l= string </span> </p> </td> 
   <td colname="col4"> <p>Specifies the language of the query parameter strings (such as <span class="codeph"> sp_q </span>). The <i> <span class="codeph"> string </span></i> should be a standard locale ID containing an ISO-639 language code optionally followed by an ISO-3166 country code. For example, "en" or "en_US" for English or "ja" or "ja_JP" for Japanese. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>18 </p> </td> 
   <td colname="col2"> <p>sp_literal </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_literal= 0 or 1 </span> </p> </td> 
   <td colname="col4"> <p> Setting <span class="codeph"> sp_literal=1 </span> temporarily disables all features that might interpret the words in the query. With this parameter, only the literal words of the query match documents, regardless of synonyms, alternate word forms, and sound-alike matching. </p> <p>Note that <span class="codeph"> sp_literal=0 </span> has no meaning, and is ignored if used. </p> <p>See <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> About Dictionaries </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>19 </p> </td> 
   <td colname="col2"> <p>sp_m </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_m= number </span> </p> </td> 
   <td colname="col4"> <p> Specifies whether summaries are displayed. 1 is yes, 0 is no. The default is 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>20 </p> </td> 
   <td colname="col2"> <p>sp_n </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_n= number </span> </p> </td> 
   <td colname="col4"> <p> Specifies the number of the result that starts the search results. The default is 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>21 </p> </td> 
   <td colname="col2"> <p>sp_not_ 
     found_page </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_not_found_page= url </span> </p> </td> 
   <td colname="col4"> <p> Specifies whether to redirect to the specified URL if there are no search results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>22 </p> </td> 
   <td colname="col2"> <p>sp_p </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p> Specifies the default type of searching to perform. The use of <span class="codeph"> any </span> means search for documents that contain any word from the query string. The use of <span class="codeph"> all </span> means search for documents that contain all of the words in the query string. The use of <span class="codeph"> phrase </span> means the query string is treated as if it were a quoted phrase and all user-typed quotes are ignored. </p> <p>For <span class="codeph"> phrase </span> and <span class="codeph"> all </span>, the specification of "+" and "-" before search words is disabled and those characters are ignored. If <span class="codeph"> sp_p </span> is not present, or if it is set to an empty string or any, standard "+" and "-" word prefixes are allowed. </p> <p>See the Search Tips description for more information about using plus ("+") and minus ("-") in searches. </p> <p>See <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> About Searches </a>. </p> <p>See the sample advanced search form for examples on using the <span class="codeph"> sp_p </span> parameter. </p> <p>See <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Sample advanced search form </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>23 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_p_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p_#= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p>Specifies the default type of searching to be performed with the corresponding <span class="codeph"> sp_q_# </span> query. The "#" is replaced with a number between 1 and 16 (for example, <span class="codeph"> sp_p_8 </span> applies to the numbered query <span class="codeph"> sp_q_8 </span>). The use of <span class="codeph"> any </span> means return documents that contain any word from the query string. The use of <span class="codeph"> all </span> means return documents that contain all of the words in the query string. The use of <span class="codeph"> phrase </span> means to treat the query string as if it was a complete phrase (and all user-typed quotes are ignored). </p> <p>If you specify either <span class="codeph"> all </span> or <span class="codeph"> phrase </span>, any plus and minus signs before search words are ignored. If <span class="codeph"> sp_p_# </span> is omitted, or if it is set to an empty string or <span class="codeph"> any </span>, standard "+" and "-" prefixes are allowed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>24 </p> </td> 
   <td colname="col2"> <p>sp_pt </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_pt= 
      <i>exact/ 
       equivalent/compatible</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p> Specifies the type of target matching to apply. The use of <span class="codeph"> exact </span> means yield target matches only in documents that exactly match the query string within target content. The use of <span class="codeph"> equivalent </span> is like exact, except that the order of the words is not important. The use of <span class="codeph"> compatible </span> automatically sets the target matching type based on the value of the <span class="codeph"> sp_p </span> parameter. The use of <span class="codeph"> exact </span> is used if <span class="codeph"> sp_p </span> is <span class="codeph"> all </span> or <span class="codeph"> phrase </span>, otherwise <span class="codeph"> equivalent </span> is used. The default value of <span class="codeph"> sp_pt </span> is <span class="codeph"> compatible </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>25 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_pt_# </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_pt_#= 
      <i>exact/ 
       equivalent/compatible</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>Specifies the type of target matching to apply with the corresponding <span class="codeph"> sp_q_# </span> query. The "#" is replaced with a number between 1 and 16 (for example, <span class="codeph"> sp_p_8 </span> applies to the numbered query <span class="codeph"> sp_q_8 </span>). The use of <span class="codeph"> exact </span> means yield target matches only in documents that exactly match the query string within target content. The use of <span class="codeph"> equivalent </span> is like <span class="codeph"> exact </span>, except that the order of the words is not important. The use of <span class="codeph"> compatible </span> automatically sets the target matching type based on the value of the corresponding <span class="codeph"> sp_p_# </span> parameter: <span class="codeph"> exact </span> is used if <span class="codeph"> sp_p_# </span> is all or phrase, otherwise <span class="codeph"> equivalent </span> is used. The default value of <span class="codeph"> sp_pt_# </span> is <span class="codeph"> compatible </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>26 </p> </td> 
   <td colname="col2"> <p>sp_q </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q= string </span> </p> </td> 
   <td colname="col4"> <p> Specifies the query string for the search. An empty string leads to no results being shown. </p> <p> 
     <!--See also <xref href="c_about_common_phrases.xml#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">About Common Phrases</xref>--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>27 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_q_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_#= text </span> </p> </td> 
   <td colname="col4"> <p>This parameter allows for the creation of multiple queries on search forms. The <span class="codeph"> sp_q_# </span> parameter contains the query string to use in the given numbered query. A search request may reference up to 16 different numbered queries ( <span class="codeph"> sp_q_1 </span> to <span class="codeph"> sp_q_16 </span>). </p> <p>For example, submitting the following form returns all documents that contain the words "great" and "books". </p> <p> 
     <codeblock class="syntax html">
       Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; 
     </codeblock> </p> <p> 
     <!--See also <xref href="c_about_common_phrases.xml#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">About Common Phrases</xref>--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>28 </p> </td> 
   <td colname="col2"> <p>sp_q_day, sp_q_month, sp_q_year </p> </td> 
   <td colname="col03"> <p> sp_q _day_#, sp_q _month_#, sp_q _year_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_day= integer value </span> </p> <p> <span class="codeph"> sp_q_month= integer value </span> </p> <p> <span class="codeph"> sp_q_year= integer value </span> </p> <p> <span class="codeph"> sp_q_day_#= integer value </span> </p> <p> <span class="codeph"> sp_q_month_#= integer value </span> </p> <p> <span class="codeph"> sp_q_year_#= integer value </span> </p> </td> 
   <td colname="col4"> <p>These parameters are used to specify an exact date for a particular query. The <span class="codeph"> sp_q_day </span>, <span class="codeph"> sp_q_month </span>, and <span class="codeph"> sp_q_year </span> parameters apply to the main query ( <span class="codeph"> sp_q </span>). </p> <p>The <span class="codeph"> # </span>parameter is replaced with a number between 1 and 16 (for example, <span class="codeph"> sp_q_day_6 </span>, which applies to the numbered query <span class="codeph"> sp_q_6 </span>). By default, all dates are searched relative to Greenwich Mean Time. </p> <p>The following section of code lets a user to search for the word "orange" in documents dated "Jan. 1st, 2000" in a user-defined field named <span class="codeph"> PublishDate </span>: </p> <p> 
     <codeblock class="syntax html">
       &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt; 
      On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>29 </p> </td> 
   <td colname="col2"> <p>sp_q_location </p> </td> 
   <td colname="col03"> <p>sp_q_ 
     location_# </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_q_location= 
       
      <i>latitude/longitude</i> OR 
      <i>areacode</i> OR 
      <i>zipcode</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_location_#= 
       
      <i>latitude/longitude</i> OR 
      <i>areacode</i> OR 
      <i>zipcode</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>These parameters associate a location with the main or numbered query. The use of <span class="codeph"> sp_q_location </span> affects the main query, <span class="codeph"> sp_q_location_# </span> (where the <span class="codeph"> # </span> is replaced by a number from 1 to 16), affects the given numbered query. These parameters are used to perform minimum and/or maximum distance proximity searches against the location data indexed for each site page. The format of the value determines its interpretation. </p> <p>A value in the form DDD (three digits) is interpreted as a US telephone areacode; a value in the form DDDDD or DDDDD-DDDD is interpreted as a US zipcode; and a value in the form ±DD.DDDD±DDD.DDDD is interpreted as a latitude/longitude pair. The signs are required for each value. For example, +38.6317+120.5509 specifies latitude 38.6317, longitude 120.5509. </p> <p>See <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> About proximity search </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>30 </p> </td> 
   <td colname="col2"> <p>sp_q_max_ 
     relevant_distance </p> </td> 
   <td colname="col03"> <p>sp_q_max _relevant _distance _# </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_q_max_relevant_ 
      distance= 
      <i>value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_max_relevant_ 
      distance_#= 
      <i>value</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>These parameters control the relevance calculation applied to proximity searches. The use of <span class="codeph"> sp_q_max_relevant_distance </span> affects the main query, <span class="codeph"> sp_q_max_relevant_distance_# </span> (where the <span class="codeph"> # </span> is replaced by a number from 1 to 16), affects the given numbered query. </p> <p>The default value of <span class="codeph"> sp_q_max_relevant_distance </span> is 100. </p> <p>A perfect relevance score for the proximity component would represent a distance of 0. A minimum relevance score for the proximity component would represent a distance just over the specified <span class="codeph"> sp_q_max_relevant_distance_# </span> value. </p> <p>See <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> About proximity search </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>31 </p> </td> 
   <td colname="col2"> <p>sp_q_min_day, sp_q_min_month, sp_q_min_year </p> <p>sp_q_max_day, sp_q_max_month, sp_q_max_year </p> </td> 
   <td colname="col03"> <p>sp_q_min_ 
     day_#, sp_q_min_ 
     month_#, sp_q_min_ 
     year_# </p> <p> sp_q_max_ 
     day_#, sp_q_max_ 
     month_#, sp_q_max_ 
     year_# </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_q_min_day= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_min_month= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_min_year= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_max_day= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_max_month= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_max_year= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_min_day_#= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_min_month_#= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_min_year_#= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_max_day_#= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_max_month_#= 
       
      <i>integer value</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_q_max_year_#= 
       
      <i>integer value</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>These parameters are used to set minimum and maximum date ranges for a particular query. The <span class="codeph"> sp_q_min_day </span>, <span class="codeph"> sp_q_min_month </span>, <span class="codeph"> sp_q_min_year </span>, <span class="codeph"> sp_q_max_day </span>, <span class="codeph"> sp_q_max_month </span>, and <i>sp_q_max_year</i> parameters apply to the main query ( <span class="codeph"> sp_q </span>). </p> <p>The <span class="codeph"> # </span>in the parameter name is replaced with a number between 1 and 16 (for example, <span class="codeph"> sp_q_min_day_6 </span> applies to the numbered query <span class="codeph"> sp_q_6 </span>). </p> <p>It is legal to specify only a minimum date, only a maximum date, or both minimum and maximum date. However, for a given minimum or maximum set, all three date parameters must be specified (day, month and year). By default, all dates are searched relative to Greenwich Mean Time. </p> <p>The following section of code lets a user search for the word "orange" in documents with a date between Jan. 1st, 2000 and Dec. 31st, 2000 in a user-defined field named <span class="codeph"> PublishDate </span>: </p> <p> 
     <codeblock class="syntax html">
       &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt; 
      Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>32 </p> </td> 
   <td colname="col2"> <p>sp_q_min, sp_q_max </p> </td> 
   <td colname="col03"> <p>sp_q _min_#, sp_q _max_#, sp_q _exact_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_min= value </span> </p> <p> <span class="codeph"> sp_q_max= value </span> </p> <p> <span class="codeph"> sp_q_min_#= value </span> </p> <p> <span class="codeph"> sp_q_max_#= value </span> </p> <p> <span class="codeph"> sp_q_exact_#=value </span> </p> </td> 
   <td colname="col4"> <p>These parameters specify a minimum (and/or maximum) value to apply to the main or numbered query. The use of <span class="codeph"> sp_q_min </span>, <span class="codeph"> sp_q_max </span>, and <span class="codeph"> sp_q_exact </span> affect the main query ( <span class="codeph"> sp_q </span>). </p> <p>Replace <span class="codeph"> # </span>in the parameter name with a number between 1 and 16 (for example, <span class="codeph"> sp_q_min_8 </span> applies to the numbered query <span class="codeph"> sp_q_8 </span>). </p> <p>The use of <span class="codeph"> sp_q_exact_# </span> is shorthand for specifying both <span class="codeph"> sp_q_min_# </span> and <span class="codeph"> sp_q_max_# </span> with the same value. If <span class="codeph"> sp_q_exact_# </span> is specified, any corresponding <span class="codeph"> sp_q_min_# </span> or <span class="codeph"> sp_q_max_# </span> parameters are ignored. </p> <p>The <span class="codeph"> sp_q_min_# </span>, <span class="codeph"> sp_q_max_# </span> and <span class="codeph"> sp_q_exact_# </span> parameters may optionally specify multiple "|" separated values. For example, to search for documents that contain the value green or red within the "color" field: <span class="codeph"> ...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>33 </p> </td> 
   <td colname="col2"> <p>sp_q_nocp </p> </td> 
   <td colname="col03"> <p>sp_q _nocp _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_nocp= 1 or 0 </span> </p> <p> <span class="codeph"> sp_q_nocp_#= 1 or 0 </span> </p> </td> 
   <td colname="col4"> <p>The default parameter value is <span class="codeph"> 0 </span> meaning that Common Phrase expansions are performed. </p> <p>When set to <span class="codeph"> 1 </span> for the corresponding search query, Common Phrases expansions are not performed. </p> <p>Using <span class="codeph"> sp_q_nocp </span> affects the main search query parameter <span class="codeph"> sp_q </span>. To apply this parameter to a numbered search query, replace <span class="codeph"> # </span> in the parameter name with the corresponding number. For example, <span class="codeph"> sp_q_nocp_8 </span> applies to the numbered search query <span class="codeph"> sp_q_8 </span>. </p> <p> 
     <!--See also <xref href="c_about_common_phrases.xml#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">About Common Phrases</xref>--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>34 </p> </td> 
   <td colname="col2"> <p>sp_q_required </p> </td> 
   <td colname="col03"> <p>sp_q _required _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_required= 1 or 0 or -1 </span> </p> <p> <span class="codeph"> sp_q_required_#= 1 or 0 or -1 </span> </p> </td> 
   <td colname="col4"> <p>This parameter determines whether a match must (1), may (0), or must not (-1) occur in the corresponding query in order for a document to be returned on the result page. </p> <p>The use of <span class="codeph"> sp_q_required </span> affects the main query ( <span class="codeph"> sp_q </span>). </p> <p>To apply to a numbered query, replace the <span class="codeph"> # </span> in the parameter name with the corresponding number (for example, <span class="codeph"> sp_q_required_8 </span> applies to the numbered query <span class="codeph"> sp_q_8 </span>). The default value of the parameter is 1 (must match). </p> <p>To search for documents that contain the word "calc" but do NOT contain "mac", "win" or "all" in the user-defined "platform" field, your HTML search form could contain the following lines: </p> <p> 
     <codeblock class="syntax html">
       &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>35 </p> </td> 
   <td colname="col2"> <p>sp_redirect_ 
     if_one_result </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_redirect_ 
      if_one_result= 
      <i>0 or 1</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>Specifies whether to redirect to the search result URL if there is only one search result. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>36 </p> </td> 
   <td colname="col2"> <p>sp_referrer </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_referrer= url </span> </p> </td> 
   <td colname="col4"> <p>Specifies the referrer URL for the search. Useful for search rewrite rules where the search results link back to the same site as the search form. </p> <p>The default value is the standard CGI HTTP_REFERRER value delivered by the browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>37 </p> </td> 
   <td colname="col2"> <p>sp_ro </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_ro= <span class="varname"> field </span>: <span class="varname"> relevance </span> </span> </p> </td> 
   <td colname="col4"> <p>Allows optional search time, per field name, relevance control. The <span class="codeph"> ro </span> in the parameter name stands for "relevance override". The parameter accepts one or more field names, followed by a colon character, followed by a relevance value from 0-10. </p> <p>For example, to set the relevance value for the field name "body" to 10, at the time a customer performs a search, the parameter would appears as follows: </p> <p> <span class="codeph"> sp_ro=body:10 </span> </p> <p>Or, to specify multiple field relevance overrides in the parameter string, you can use a pipe delimiter. For example, to set the relevance value for the field names "body" and "title" to 9, at the time a customer performs a search, the parameter would appear as follows: </p> <p> <span class="codeph"> sp_ro=body:9|title:9 </span> </p> <p> <p>Note:  Specifying a field that is not involved in the associated search has no effect. For example, if you set <span class="codeph"> sp_ro=title:10 </span>, but the <span class="codeph"> title </span> field name is not searched, the <span class="codeph"> sp_ro </span> parameter has no effect. In other words, specifying a field name using the <span class="codeph"> sp_ro </span> parameter does not automatically search that field; instead, it only overrides that field's associated relevance setting. </p> </p> <p>See <a href="../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3" type="task" format="dita" scope="local"> Editing pre-defined or user-defined meta tag fields </a>. </p> <p>See <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" type="concept" format="dita" scope="local"> About Query Cleaning Rules </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>38 </p> </td> 
   <td colname="col2"> <p>sp_s </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_s= number </span> </p> </td> 
   <td colname="col4"> <p>Specifies the sort order. Zero (0) is the default and means to sort by relevance score. One (1) means to sort by date and -1 means to not sort. </p> <p>You can specify a field name for the value of the <span class="codeph"> sp_s </span> parameter. For example, <span class="codeph"> sp_s=title </span> sorts results according to the values that are contained in the title field. When a field name is used for the value of an <span class="codeph"> sp_s </span> parameter, results are sorted by that field and then sub-sorted by relevance. </p> <p>Set Sorting for the referenced field to either <span class="uicontrol"> Ascending </span> or <span class="uicontrol"> Descending </span> in <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span> to enable this feature. </p> <p>You can also assign several sort fields to a single query by setting the <span class="codeph"> sp_s </span> parameter several times in the search form. The following template lines sets the search results to be sorted first by artist name, then by album name, and then by track name. </p> <p> 
     <codeblock class="syntax html">
       &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; 
     </codeblock> </p> <p>It is also possible to sort on table matched field data by specifying a table name qualifier prior to the field name, for example, items.price. See the <span class="codeph"> sp_field_table </span> parameter for more information on table matching. </p> <p>If searching by proximity, you may sort results according to proximity by specifying a "proximity output field". </p> <p>See <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> About proximity search </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>39 </p> </td> 
   <td colname="col2"> <p>sp_sr </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sr= field </span> </p> </td> 
   <td colname="col4"> <p>Specifies the rank field to use for static ranking. The field must be a field of type Rank with relevance greater than 0. If no <span class="codeph"> sp_sr </span> parameter is provided for the query, a field of type Rank is automatically selected. </p> <p>To disable static ranking for a particular query, include a NULL value for <span class="codeph"> sp_sr </span> (for example, <span class="codeph"> &lt;input type="hidden" name="sp_sr" value=""&gt; </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>40 </p> </td> 
   <td colname="col2"> <p>sp_sfvl_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_field= string </span> </p> </td> 
   <td colname="col4"> <p>Specifies the name of a field to use in conjunction with the <span class="codeph"> &lt;search-field-value-list&gt; </span> tag in the search template. </p> <p>You can specify multiple <span class="codeph"> sp_sfvl_field </span> parameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>41 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_count </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_df_count= <span class="varname"> &lt;integer_value&gt; </span> </span> </p> </td> 
   <td colname="col4"> <p> 
     <!--NEW 2/2/2014-->Requests up to <span class="codeph"> <span class="varname"> &lt;integer_value&gt; </span> </span> <span class="codeph"> search-field-value-list </span> dynamic-facet fields for this search. </p> <p>The default value is 0. The maximum allowed value is the current number of dynamic-facet fields, dynamic-facet-field-count defined for a given index. Integer values that are below 0 are treated as 0. Integer values specified above <span class="codeph"> dynamic-facet-field-count </span> are capped at <span class="codeph"> dynamic-facet-field-count </span>. Non-integer values are ignored; they are treated as the default value. </p> <p>A given slice's search is capped with a maximum allowed <span class="codeph"> sp_sfvl_df_count </span> value of this slice's <span class="codeph"> dynamic-facet-field-count </span> value. When merging slice results, the effective maximum value of <span class="codeph"> sp_sfvl_df_count </span> is the maximum actual <span class="codeph"> sp_sfvl_df_count </span> across all slices. </p> <p>See <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Configuring dynamic facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>42 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_exclude </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_exclude= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span> </span>&gt;|... </p> </td> 
   <td colname="col4"> <p> Specifies a list of specific dynamic facet fields to exclude from consideration for this search. </p> <p>By default, all dynamic facet fields are considered. </p> <p>See <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Configuring dynamic facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>43 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_include </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_include= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span> </span>&gt;|... </p> </td> 
   <td colname="col4"> <p> Specifies a list of specific dynamic facet fields to include in the search results. </p> <p> <p>Note:  The <span class="codeph"> sp_sfvl_df_count </span> parameter determines the total number of dynamic facet fields to return, including any specified by way of <span class="codeph"> sp_sfvl_df_include </span>. That is, using <span class="codeph"> sp_sfvl_df_include </span> does not allow the total count of returned dynamic facet fields to exceed <span class="codeph"> sp_sfvl_df_count </span>. </p> </p> <p>See <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Configuring dynamic facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>44 </p> </td> 
   <td colname="col2"> <p>sp_staged </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_staged= 0 or 1 </span> </p> </td> 
   <td colname="col4"> <p>If <span class="codeph"> sp_staged=1 </span> is submitted with a query, the query that is run is a staged search. </p> <p>A staged search uses all the components that are currently staged including the index and templates. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>45 </p> </td> 
   <td colname="col2"> <p>sp_start_day, sp_start_month, sp_start_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_start_day= number </span> </p> <p> <span class="codeph"> sp_start_month= number </span> </p> <p> <span class="codeph"> sp_start_year= number </span> </p> </td> 
   <td colname="col4"> <p>This triplet of values specifies the starting date range for the search and you provide it as a set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>46 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_ suggest _q </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_suggest_q= number </span> </p> </td> 
   <td colname="col4"> <p>The <span class="codeph"> sp_suggest_q </span> parameter determines which <span class="codeph"> sp_q[_#] </span> parameter to use with the Suggest service. </p> <p>The default value of <span class="codeph"> sp_suggest_q </span> is 0, which means that the search engine uses the value of <span class="codeph"> sp_q </span> to determine the suggestions. </p> <p>Set <span class="codeph"> sp_suggest_q=1 </span> to use the value of <span class="codeph"> sp_q_1 </span> to determine the suggestions, and so on. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>47 </p> </td> 
   <td colname="col2"> <p>sp_t </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_t= string </span> </p> </td> 
   <td colname="col4"> <p>Specifies the transport template to use. </p> <p>This parameter is useful if you want to control the appearance of core search results across your website by using different search transport templates for each area in your Search account. </p> <p>The default transport template is "search". </p> <p>See <a href="../c-appendices/c-templates.md#reference_12AAB3B9F4C74C11956F1DBA95714C2F" type="reference" format="dita" scope="local"> Managing multiple transport templates for your website </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>48 </p> </td> 
   <td colname="col2"> <p>sp_trace </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_trace= 0 or 1 </span> </p> </td> 
   <td colname="col4"> <p>When set as <span class="codeph"> sp_stage=1 </span>, enables the core search trace capability in Simulator. </p> <p>See <a href="../c-about-simulator.md#concept_020AA6751E32421A96A3455508364C7E" format="dita" scope="local"> About Simulator </a>. </p> <p> <p>Note:  If this parameter is not specified, core search does not gather the tracing information and the related core search template tags have no output. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>49 </p> </td> 
   <td colname="col2"> <p>sp_w, sp_w_control </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> 
     <codeblock>
       sp_w= 
      <i>sound- 
       alike-enable</i> 
     </codeblock> </p> <p> 
     <codeblock>
       sp_w_control= 
       
      <i>sound-alike-control</i> 
     </codeblock> </p> </td> 
   <td colname="col4"> <p>Specifies that sound-alike matching should be enabled or disabled for this particular query. </p> <p> 
     <table id="table_CB36D47EE3124B01966D106A090BE63D">  
     </table> </p> <p>The <span class="codeph"> sp_w_control </span> parameter lets you create a negatively or positively worded checkbox for end-user control of sound-alike matching. </p> <p>If <span class="codeph"> sp_w_control=0 </span> is used, then a negatively worded checkbox is used to set the <span class="codeph"> sp_w </span> parameter as in the following example: </p> <p> 
     <codeblock class="syntax html">
       &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt; 
      &lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching 
     </codeblock> </p> <p>If <span class="codeph"> sp_w_control=1 </span> is used, then a positively worded checkbox is used to set the <span class="codeph"> sp_w </span> parameter as in the following: </p> <p> 
     <codeblock class="syntax html">
       &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt; 
      &lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching 
     </codeblock> </p> <p>See the sample advanced search form for more examples on using <span class="codeph"> sp_w_control </span> and <span class="codeph"> sp_w </span> parameters. </p> <p>See <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Sample advanced search form </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>50 </p> </td> 
   <td colname="col2"> <p>sp_x </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x= field </span> </p> </td> 
   <td colname="col4"> <p>Specifies the fields to search for the query string. any means search all fields. title means search only title fields. desc means search only document description fields. keys means search only document keywords. body means search only body text. alt means search only alternate text. url means search only the URL values. target means search only target keywords. In any of these cases, user specification of "text:", "desc:", "keys:", "body:", "alt:", "url:", and "target:" field prefixes within the corresponding <span class="codeph"> sp_q </span> parameter are ignored. If <span class="codeph"> sp_x </span> is not present or if it is set to an empty string or any, then the standard user field prefixes are allowed. See the Search Tips description for more information about the field prefixes. </p> <p>See <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> About Searches </a>. </p> <p>See the sample Advanced Search Form description for examples using the <span class="codeph"> sp_x </span> parameter. </p> <p>See <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Sample advanced search form </a>. </p> <p>You can create queries that search all fields set to <span class="uicontrol"> Search By Default </span> under <span class="uicontrol"> Options </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span> by setting <span class="codeph"> sp_x=any </span>. Both pre- and user-defined fields may be used as the value of the <span class="codeph"> sp_x </span> parameter. </p> <p>You can also assign several fields to a single query by setting the <span class="codeph"> sp_x </span> parameter several times. The following template lines let users query both the "title" and "author" fields for "Great Books". </p> <p> 
     <codeblock class="syntax html">
       &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>51 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_x_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x_#= field-name </span> </p> </td> 
   <td colname="col4"> <p>This parameter specifies which field to search in the corresponding <span class="codeph"> sp_q_# </span> query. The <span class="codeph"> <span class="codeph"> # </span> </span> is replaced with a number between 1 and 16 (for example, <span class="codeph"> sp_x_8 </span>). The field-name is any pre- or user-defined field. </p> <p>If no <span class="codeph"> sp_x_# </span> parameter is provided for a particular numbered query, all fields defined as <span class="uicontrol"> Search By Default </span> as set under <span class="uicontrol"> Setting </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span> are searched by that query. </p> <p>For example, submitting the following form returns all documents that contain the word "great" that also contain the word "Fitzgerald" in the "author" field: </p> <p> 
     <codeblock class="syntax html">
       Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt; 
      Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; 
     </codeblock> </p> <p>You can associate multiple field names with a particular query or numbered query by providing more than one instance of the same <span class="codeph"> sp_x </span> or <span class="codeph"> sp_x_# </span> parameter in a single search request. </p> <p>For example, to search for the word "flower" within both the "body" and "keys" fields, you could create a search form with the following information: </p> <p> 
     <codeblock class="syntax html">
       &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; 
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

## A typical example of using backend search CGI parameters {#section_260012BBC2514CC9A8E02E53DE8B41EE}

The following link queries start a search using "Music" as the search query, and uses all the default parameters. Note that the URL is split across two lines for readability. In your HTML, this link should all be on one line.

```
<a href="http://search.atomz.com/search/?sp_q=Music&sp_a=sp99999999"> 
Testing...</a>
```

The same functionality is more typically defined with a form:

```
<form action="http://search.atomz.com/search/"> 
<input size=12 name="sp_q" value="Music"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
</form>
```

You should typically use default parameters when initiating a search. That way, the first page is shown, sorted by relevance, and allows the customer to choose other pages and other options. If the search form on your site includes options for collections, pass in the collection name as a parameter.

## A detailed example of using backend search CGI parameters {#section_5FA3C620D5124FB2AB28857F8D8473F6}

The following form queries display `25` results starting at result `10`. Summaries are not shown, the sort order is by date, and the collection named `support` is used. Only documents dated within the last 30 days are returned.

```
<form action="http://search.atomz.com/search/"> 
<input size=12 name="sp_q"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
<input type=hidden name=sp_n value=10> 
<input type=hidden name=sp_c value=25> 
<input type=hidden name=sp_m value=0> 
<input type=hidden name=sp_s value=1> 
<input type=hidden name=sp_k value="support"> 
<input type=hidden name=sp_date_range value=30> 
</form>
```

