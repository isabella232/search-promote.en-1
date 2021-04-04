---
description: Learn about how to use various CGI parameters.
solution: Target
title: CGI parameters
topic: Appendices,Site search and merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
exl-id: 9f24aebf-5fa3-433e-b66d-4129bdd3f7f6
---
# CGI parameters{#cgi-parameters}

## CGI parameters {#concept_F395999090FE4926B38BC73D5E612800}

## Search CGI parameters {#reference_DA27A8B0728246DA94994885E1353890}

Search form code is provided that you can copy and paste into the HTML of your site ( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**).

See [Copying the HTML code of the search form into the...](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

You can also set the parameters that are listed either in the search form itself, or from a script. In addition to the parameters that are listed below you can also use the backend search parameters to control search.

See [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

Search requests consist of a base URL. The base URL indicates what account the customer is searching, and a set of CGI parameters (key-value pairs) that indicate how to return the desired search results for the associated account.

The base URL is associated with a specific account and a staged or live environment. You can request multiple aliases for the base URL from your account manager. For example, a company called Megacorp may have two base URLs associated with their account: `https://search.megacorp.com` and `https://stage.megacorp.com`. The former URL searches their live index and the latter URL searches their staged index.

Three formats of CGI Parameters are supported. By default your account is configured to separate CGI Parameters with a semi-colon as in the following example:

`https://search.megacorp.com?q=shoes;page=2`

If you prefer, you can have your account manager configure your account to use ampersands to separate the CGI parameters as in the following example:

`https://search.megacorp.com?q=shoes&page=2`

A third format, called the SEO format, is also supported where a forward slash `/` is used in place of the separator and equal sign as in the following example:

`https://search.megacorp.com/q/shoes/page/2`

Any time the SEO format is used to send a request, all output links are returned in the same format.

| Guided Search parameter  | Example  | Description  |
|--- |--- |--- |
|q|`q=string`|Specifies the query string for the search. This parameter maps to the `sp_q` backend search parameter.  See [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).|
|q#|`q#=string`|Faceting (searching within a given field) is done by way of numbered q and x parameters.  The q parameter defines the term you are searching for in the facet as denoted by the corresponding numbered x parameter.<br>For example, if you have two facets that are named size and color, you can have something like q1=small;x1=size;q2=red;x2=color.  This parameter maps to the `sp_q_exact_#` backend search parameters.  <br>See [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).|
|x#|`q#=string`|Faceting (searching within a given field) is done by way of numbered q and x parameters.  The q parameter defines the term you are searching for in the facet as denoted by the corresponding numbered x parameter. <br>For example, if you have two facets that are named size and color, you can have something like q1=small;x1=size;q2=red;x2=color.  This parameter maps to the `sp_x_#` backend search parameters.  <br>See [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).|
|collection|`collection=string`|Specifies the collection to use for the search.  This parameter maps to the `sp_k` backend search parameter.  See [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).|
|count|`count=number`|Specifies the total count of results that are shown.  The default is defined in [!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ]. .  This parameter maps to the `sp_c` backend search parameter.  See [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).|
|page|`page=number`|Specifies the page of results that are returned.|
|rank|`rank=field`|Specifies the rank field to use for static ranking.  The field must be a field of type Rank with relevance greater than 0.  This parameter maps to the `sp_sr` backend parameter.  See [Backend search CGI parameters](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).|
|sort|`sort=number`|Specifies the sort order.<br>"0" is the default and sorts by relevance score; "1" sorts by date; "-1" does not sort.  Users can specify a field name for the value of the `sp_s` parameter.  For example, `sp_s=title` sorts results according to the values that are contained in the title field. When a field name is used for the value of an ` sp_s ` parameter, results are sorted by that field and then sub-sorted by relevance.  To enable this feature, click [!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]. On the Definitions page, click [!UICONTROL Add New Field ] or click [!UICONTROL Edit ] for a particular field name. In the [!UICONTROL Sorting ] drop-down list, select either [!UICONTROL Ascending ] or [!UICONTROL Descending ]. This parameter maps to the `sp_s` backend search parameter. <br>See [Backend search CGI parameters].(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).|

## Backend search CGI parameters {#reference_582E85C3886740C98FE88CA9DF7918E8}

Typically customers interact with a presentation layer called Guided Search. However, it is theoretically possible to skip the Guided Search layer and interact with the backend core search directly using the CGI parameters that are described on this page.

You can select backend search CGI parameters from the following table:
<table> 
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
   <td colname="col3"> <p> <code>sp_a= string </code> </p> </td> 
   <td colname="col4"> <p>Specifies the account number string. This parameter is required, and must be a valid account number string. You can find your account number string under <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Account Options </span> &gt; <span class="uicontrol"> Account Settings </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_advanced= 0 or 1 </code> </p> </td> 
   <td colname="col4"> <p>If <code>sp_advanced=1 </code> is submitted with a query, then all code between the <code>&lt;search-if-advanced&gt; </code> tag and the <code>&lt;/search-if-advanced&gt; </code> tag in the search template is used for the search form. All code between the <code>&lt;search-if-not-advanced&gt; </code> tag and the <code>&lt;/search-if-not-advanced&gt; </code> tag is be ignored. If <code>sp_advanced=0 </code> (or any other value) is submitted, then the &lt;search-if-advanced&gt; template block is ignored and the &lt;search-if-not-advanced&gt; template block is used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_c= number </code> </p> </td> 
   <td colname="col4"> <p>Specifies the total count of results to show. The default is 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>Collects contextual information for the given field. Collected information is output in the search results by way of the <code>&lt;search-context&gt; </code> template tag. The default value is <code>body </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_d= type </code> </p> </td> 
   <td colname="col4"> <p>Specifies the type of date range searching to perform. Possible values for type are any, which means do not perform date range searching, custom, which indicates that the value of <code>sp_date_range </code> should be used to determine the dates to search, and specific, which indicates that the values in <code>sp_start_day </code>, <code>sp_start_month </code>, <code>sp_start_year </code>, <code>sp_end_day </code>, <code>sp_end_month </code>, and <code>sp_end_year </code> is used to determine the date range to search. <code>sp_d </code> is only required if your search form contains the option to search either by a custom range (by way of <code>sp_date_range </code>), or by a specific start and end date range. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <code>sp_d_#= type </code> </p> </td> 
   <td colname="col4"> <p>Specifies the type of date range searching to perform for the corresponding <code>sp_q_# </code> query. The "#" is replaced with a number between 1 and 16 (for example, <code>sp_d_8 </code>, applies to the numbered query <code>sp_q_8 </code>). </p> <p>You can set <code>type </code> to any, which means do not perform date range searching, custom, which indicates that the value of <code>sp_date_range_# </code> is used to determine the dates to search, and specific, which indicates that the values in <code>sp_q_min_day_# </code>, <code>sp_q_min_month_# </code>, <code>sp_q_min_year_# </code>, <code>sp_q_max_day_# </code>, <code>sp_q_max_month_# </code>, and <code>sp_q_max_year_# </code> should be used to determine the date range. The use of <code>sp_d_# </code> is only required if your search form contains the option to search either by a custom range (by way of <code>sp_date_range_# </code>), or by a specific start and end date range. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>sp_date_range </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifies a pre-defined date range to apply to the search. Values greater than or equal to zero specify the number of days to search prior to today — for example, a value of "0" specifies "today," a value of "1" specifies "today and yesterday," a value of "30" specifies "within the last 30 days," and so forth. </p> <p>Values below zero specify a custom range as follows: </p> <p>-1 = "None," the same as specifying no date range. </p> <p>-2 = "This week," which searches from Sunday to Saturday of the current week. </p> <p>-3 = "Last week," which searches from Sunday to Saturday of the week prior to the current week. </p> <p>-4 = "This month," which searches dates within the current month. </p> <p>-5 = "Last month," which searches dates within the month prior to the current month. </p> <p>-6 = "This year," which searches dates within the current year. </p> <p>-7 = "Last year," which searches dates within the year prior to the current year. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_date_range_# </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range_#= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifies a pre-defined date range to apply to the corresponding <code>sp_q_# </code> query. The "#" is replaced with a number between 1 and 16 (for example, <code>sp_date_range_8 </code>, applies to the numbered query <code>sp_q_8 </code>). </p> <p>Values greater than or equal to zero specify the number of days to search prior to today. For example, a value of 0 specifies today; a value of 1 specifies today and yesterday; a value of 30 specifies within the last 30 days, and so forth. </p> <p>Values below zero specify a custom range as follows: </p> <p>-1 = "None," the same as specifying no date range. </p> <p>-2 = "This week," which searches from Sunday to Saturday of the current week. </p> <p>-3 = "Last week," which searches from Sunday to Saturday of the week prior to the current week. </p> <p>-4 = "This month," which searches dates within the current month. </p> <p>-5 = "Last month," which searches dates within the month prior to the current month. </p> <p>-6 = "This year," which searches dates within the current year. </p> <p>-7 = "Last year," which searches dates within the year prior to the current year. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifies a single field to dedupe search results on. All duplicate results on that field are removed from the search results. For example, if for <code>sp_dedupe_field=title </code>, only the top result for a given title is displayed in the search results (no two results will have identical title field content). For multi-value (allow list) type fields, the entire field contents are used for comparison. Only one field may be specified. A "table-qualifier" is not allowed in the field name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_e= number </code> </p> </td> 
   <td colname="col4"> <p>Specifies that automatic wildcard expansion should take place for any word from the query string with more than number characters. In other words, <code>sp_e=5 </code> specifies that words with 5 or more characters, like "query" or "number", should be expanded with the wildcard character '*', making the search equivalent to a search for "query*" or "number*". Words with fewer characters are not expanded, so a search for "word" would not have automatic wildcard expansion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <code>sp_e_#= number </code> </p> </td> 
   <td colname="col4"> <p>Specifies that automatic wildcard expansion takes place for any word from the corresponding <code>sp_q_# </code> query string with more than number characters. In other words, <code>sp_e_2=5 </code> specifies that words with five or more characters in the <code>sp_q_2 </code> query string, like "query" or "number", should be expanded with the wildcard character ' <code>* </code>', making the search equivalent to a search for "query*" or "number*". Words with fewer characters are not expanded, so a search for "word" in <code>sp_q_2 </code> would not have automatic wildcard expansion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>sp_end_day, sp_end_month, sp_end_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_end_day= <i>number</i>,sp_end_month= <i>number</i>, sp_end_year= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>This triplet of values specifies the end date range for the search and must be provided as a set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>sp_f </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_f= string </code> </p> </td> 
   <td colname="col4"> <p>Specifies the character set of the query parameter strings (such as <code>sp_q </code>). This string must always match the character set of the page that contains the search form. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>Defines a logical data table consisting of the given fields. For example, a table named "items" consisting of the fields "color," "size," and "price" would be defined as the following: </p> <p> <code>sp_field_table=items:color,size,price </code> </p> <p>Logical tables are most useful in conjunction with fields that have "Allow Lists" checked (under <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span>). All CGI parameters and template tags that take a field name as a value may optionally specify a table name followed by a "." prior to the field name (for example, <code>sp_x_1=tablename.fieldname </code>). </p> <p>For example, to perform a search for documents that contain one or more "red" items in size "large" (where items are represented as parallel rows of metadata), you could use the following: </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_i= <span class="varname"> value </code> </span> </p> </td> 
   <td colname="col4"> <p>Ignores the search when you generate reports. </p> <p>Use this query to mask certain backend searches, such as searches that Did You Mean generates, or searches that an Administrator generates in the member center. Because an end user does not generate these types of searches, they do not show up in various Adobe Search&amp;Promote reports. </p> <p>Valid values are <code>sp_i=1 </code> and <code>sp_i=2 </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>16 </p> </td> 
   <td colname="col2"> <p>sp_k </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_k= string </code> </p> </td> 
   <td colname="col4"> <p> Specifies the collection to use for the search. The default is no collection, meaning that the search should include the whole site. </p> <p>See <a href="../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3" type="reference" format="dita" scope="local"> Using collections in search forms </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>17 </p> </td> 
   <td colname="col2"> <p>sp_l </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_l= string </code> </p> </td> 
   <td colname="col4"> <p>Specifies the language of the query parameter strings (such as <code>sp_q </code>). The <i> <code>string </code></i> should be a standard locale ID containing an ISO-639 language code optionally followed by an ISO-3166 country code. For example, "en" or "en_US" for English or "ja" or "ja_JP" for Japanese. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>18 </p> </td> 
   <td colname="col2"> <p>sp_literal </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_literal= 0 or 1 </code> </p> </td> 
   <td colname="col4"> <p> Setting <code>sp_literal=1 </code> temporarily disables all features that might interpret the words in the query. With this parameter, only the literal words of the query match documents, regardless of synonyms, alternate word forms, and sound-alike matching. </p> <p>Note that <code>sp_literal=0 </code> has no meaning, and is ignored if used. </p> <p>See <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> About Dictionaries </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>19 </p> </td> 
   <td colname="col2"> <p>sp_m </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_m= number </code> </p> </td> 
   <td colname="col4"> <p> Specifies whether summaries are displayed. 1 is yes, 0 is no. The default is 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>20 </p> </td> 
   <td colname="col2"> <p>sp_n </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_n= number </code> </p> </td> 
   <td colname="col4"> <p> Specifies the number of the result that starts the search results. The default is 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>21 </p> </td> 
   <td colname="col2"> <p>sp_not_found_page </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_not_found_page= url </code> </p> </td> 
   <td colname="col4"> <p> Specifies whether to redirect to the specified URL if there are no search results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>22 </p> </td> 
   <td colname="col2"> <p>sp_p </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_p= any/all/phrase </code> </p> </td> 
   <td colname="col4"> <p> Specifies the default type of searching to perform. The use of <code>any </code> means search for documents that contain any word from the query string. The use of <code>all </code> means search for documents that contain all of the words in the query string. The use of <code>phrase </code> means the query string is treated as if it were a quoted phrase and all user-typed quotes are ignored. </p> <p>For <code>phrase </code> and <code>all </code>, the specification of "+" and "-" before search words is disabled and those characters are ignored. If <code>sp_p </code> is not present, or if it is set to an empty string or any, standard "+" and "-" word prefixes are allowed. </p> <p>See the Search Tips description for more information about using plus ("+") and minus ("-") in searches. </p> <p>See <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> About Searches </a>. </p> <p>See the sample advanced search form for examples on using the <code>sp_p </code> parameter. </p> <p>See <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Sample advanced search form </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>23 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_p_# </p> </td> 
   <td colname="col3"> <p> <code>sp_p_#= any/all/phrase </code> </p> </td> 
   <td colname="col4"> <p>Specifies the default type of searching to be performed with the corresponding <code>sp_q_# </code> query. The "#" is replaced with a number between 1 and 16 (for example, <code>sp_p_8 </code> applies to the numbered query <code>sp_q_8 </code>). The use of <code>any </code> means return documents that contain any word from the query string. The use of <code>all </code> means return documents that contain all of the words in the query string. The use of <code>phrase </code> means to treat the query string as if it was a complete phrase (and all user-typed quotes are ignored). </p> <p>If you specify either <code>all </code> or <code>phrase </code>, any plus and minus signs before search words are ignored. If <code>sp_p_# </code> is omitted, or if it is set to an empty string or <code>any </code>, standard "+" and "-" prefixes are allowed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>24 </p> </td> 
   <td colname="col2"> <p>sp_pt </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_pt= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p> Specifies the type of target matching to apply. The use of <code>exact </code> means yield target matches only in documents that exactly match the query string within target content. The use of <code>equivalent </code> is like exact, except that the order of the words is not important. The use of <code>compatible </code> automatically sets the target matching type based on the value of the <code>sp_p </code> parameter. The use of <code>exact </code> is used if <code>sp_p </code> is <code>all </code> or <code>phrase </code>, otherwise <code>equivalent </code> is used. The default value of <code>sp_pt </code> is <code>compatible </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>25 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_pt_# </p> </td> 
   <td colname="col3"> <p> <code> sp_pt_#= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifies the type of target matching to apply with the corresponding <code>sp_q_# </code> query. The "#" is replaced with a number between 1 and 16 (for example, <code>sp_p_8 </code> applies to the numbered query <code>sp_q_8 </code>). The use of <code>exact </code> means yield target matches only in documents that exactly match the query string within target content. The use of <code>equivalent </code> is like <code>exact </code>, except that the order of the words is not important. The use of <code>compatible </code> automatically sets the target matching type based on the value of the corresponding <code>sp_p_# </code> parameter: <code>exact </code> is used if <code>sp_p_# </code> is all or phrase, otherwise <code>equivalent </code> is used. The default value of <code>sp_pt_# </code> is <code>compatible </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>26 </p> </td> 
   <td colname="col2"> <p>sp_q </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_q= string </code> </p> </td> 
   <td colname="col4"> <p> Specifies the query string for the search. An empty string leads to no results being shown. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>27 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_q_# </p> </td> 
   <td colname="col3"> <p> <code>sp_q_#= text </code> </p> </td> 
   <td colname="col4"> <p>This parameter allows for the creation of multiple queries on search forms. The <code>sp_q_# </code> parameter contains the query string to use in the given numbered query. A search request may reference up to 16 different numbered queries ( <code>sp_q_1 </code> to <code>sp_q_16 </code>). </p> <p>For example, submitting the following form returns all documents that contain the words "great" and "books". </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>28 </p> </td> 
   <td colname="col2"> <p>sp_q_day, sp_q_month, sp_q_year </p> </td> 
   <td colname="col03"> <p> sp_q _day_#, sp_q _month_#, sp_q _year_# </p> </td> 
   <td colname="col3"> <p> <code>sp_q_day= integer value </code> </p> <p> <code>sp_q_month= integer value </code> </p> <p> <code>sp_q_year= integer value </code> </p> <p> <code>sp_q_day_#= integer value </code> </p> <p> <code>sp_q_month_#= integer value </code> </p> <p> <code>sp_q_year_#= integer value </code> </p> </td> 
   <td colname="col4"> <p>These parameters are used to specify an exact date for a particular query. The <code>sp_q_day </code>, <code>sp_q_month </code>, and <code>sp_q_year </code> parameters apply to the main query ( <code>sp_q </code>). </p> <p>The <code># </code>parameter is replaced with a number between 1 and 16 (for example, <code>sp_q_day_6 </code>, which applies to the numbered query <code>sp_q_6 </code>). By default, all dates are searched relative to Greenwich Mean Time. </p> <p>The following section of code lets a user to search for the word "orange" in documents dated "Jan. 1st, 2000" in a user-defined field named <code>PublishDate </code>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>29 </p> </td> 
   <td colname="col2"> <p>sp_q_location </p> </td> 
   <td colname="col03"> <p>sp_q_location_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> <p> <code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> </td> 
   <td colname="col4"> <p>These parameters associate a location with the main or numbered query. The use of <code>sp_q_location </code> affects the main query, <code>sp_q_location_# </code> (where the <code># </code> is replaced by a number from 1 to 16), affects the given numbered query. These parameters are used to perform minimum and/or maximum distance proximity searches against the location data indexed for each site page. The format of the value determines its interpretation. </p> <p>A value in the form DDD (three digits) is interpreted as a US telephone areacode; a value in the form DDDDD or DDDDD-DDDD is interpreted as a US zipcode; and a value in the form ±DD.DDDD±DDD.DDDD is interpreted as a latitude/longitude pair. The signs are required for each value. For example, +38.6317+120.5509 specifies latitude 38.6317, longitude 120.5509. </p> <p>See <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> About proximity search </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>30 </p> </td> 
   <td colname="col2"> <p>sp_q_max_relevant_distance </p> </td> 
   <td colname="col03"> <p>sp_q_max _relevant _distance _# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_max_relevant_distance= <i>value</i> </code> </p> <p> <code> sp_q_max_relevant_distance_#= <i>value</i> </code> </p> </td> 
   <td colname="col4"> <p>These parameters control the relevance calculation applied to proximity searches. The use of <code>sp_q_max_relevant_distance </code> affects the main query, <code>sp_q_max_relevant_distance_# </code> (where the <code># </code> is replaced by a number from 1 to 16), affects the given numbered query. </p> <p>The default value of <code>sp_q_max_relevant_distance </code> is 100. </p> <p>A perfect relevance score for the proximity component would represent a distance of 0. A minimum relevance score for the proximity component would represent a distance just over the specified <code>sp_q_max_relevant_distance_# </code> value. </p> <p>See <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> About proximity search </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>31 </p> </td> 
   <td colname="col2"> <p>sp_q_min_day, sp_q_min_month, sp_q_min_year </p> <p>sp_q_max_day, sp_q_max_month, sp_q_max_year </p> </td> 
   <td colname="col03"> <p>sp_q_min_day_#, sp_q_min_month_#, sp_q_min_year_# </p> <p> sp_q_max_day_#, sp_q_max_month_#, sp_q_max_year_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_min_day=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year=<i>integer value</i> </code> </p> <p> <code> sp_q_min_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year_#=<i>integer value</i> </code> </p> </td> 
   <td colname="col4"> <p>These parameters are used to set minimum and maximum date ranges for a particular query. The <code>sp_q_min_day </code>, <code>sp_q_min_month </code>, <code>sp_q_min_year </code>, <code>sp_q_max_day </code>, <code>sp_q_max_month </code>, and <i>sp_q_max_year</i> parameters apply to the main query ( <code>sp_q </code>). </p> <p>The <code># </code>in the parameter name is replaced with a number between 1 and 16 (for example, <code>sp_q_min_day_6 </code> applies to the numbered query <code>sp_q_6 </code>). </p> <p>It is legal to specify only a minimum date, only a maximum date, or both minimum and maximum date. However, for a given minimum or maximum set, all three date parameters must be specified (day, month and year). By default, all dates are searched relative to Greenwich Mean Time. </p> <p>The following section of code lets a user search for the word "orange" in documents with a date between Jan. 1st, 2000 and Dec. 31st, 2000 in a user-defined field named <code>PublishDate </code>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>32 </p> </td> 
   <td colname="col2"> <p>sp_q_min, sp_q_max </p> </td> 
   <td colname="col03"> <p>sp_q _min_#, sp_q _max_#, sp_q _exact_# </p> </td> 
   <td colname="col3"> <p> <code>sp_q_min= value </code> </p> <p> <code>sp_q_max= value </code> </p> <p> <code>sp_q_min_#= value </code> </p> <p> <code>sp_q_max_#= value </code> </p> <p> <code>sp_q_exact_#=value </code> </p> </td> 
   <td colname="col4"> <p>These parameters specify a minimum (and/or maximum) value to apply to the main or numbered query. The use of <code>sp_q_min </code>, <code>sp_q_max </code>, and <code>sp_q_exact </code> affect the main query ( <code>sp_q </code>). </p> <p>Replace <code># </code>in the parameter name with a number between 1 and 16 (for example, <code>sp_q_min_8 </code> applies to the numbered query <code>sp_q_8 </code>). </p> <p>The use of <code>sp_q_exact_# </code> is shorthand for specifying both <code>sp_q_min_# </code> and <code>sp_q_max_# </code> with the same value. If <code>sp_q_exact_# </code> is specified, any corresponding <code>sp_q_min_# </code> or <code>sp_q_max_# </code> parameters are ignored. </p> <p>The <code>sp_q_min_# </code>, <code>sp_q_max_# </code> and <code>sp_q_exact_# </code> parameters may optionally specify multiple "|" separated values. For example, to search for documents that contain the value green or red within the "color" field: <code>...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>33 </p> </td> 
   <td colname="col2"> <p>sp_q_nocp </p> </td> 
   <td colname="col03"> <p>sp_q _nocp _# </p> </td> 
   <td colname="col3"> <p> <code>sp_q_nocp= 1 or 0 </code> </p> <p> <code>sp_q_nocp_#= 1 or 0 </code> </p> </td> 
   <td colname="col4"> <p>The default parameter value is <code>0 </code> meaning that Common Phrase expansions are performed. </p> <p>When set to <code>1 </code> for the corresponding search query, Common Phrases expansions are not performed. </p> <p>Using <code>sp_q_nocp </code> affects the main search query parameter <code>sp_q </code>. To apply this parameter to a numbered search query, replace <code># </code> in the parameter name with the corresponding number. For example, <code>sp_q_nocp_8 </code> applies to the numbered search query <code>sp_q_8 </code>. </p> <p> 
     <!--See also <xref href="c_about_common_phrases.xml#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">About Common Phrases</xref>--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>34 </p> </td> 
   <td colname="col2"> <p>sp_q_required </p> </td> 
   <td colname="col03"> <p>sp_q _required _# </p> </td> 
   <td colname="col3"> <p> <code>sp_q_required= 1 or 0 or -1 </code> </p> <p> <code>sp_q_required_#= 1 or 0 or -1 </code> </p> </td> 
   <td colname="col4"> <p>This parameter determines whether a match must (1), may (0), or must not (-1) occur in the corresponding query in order for a document to be returned on the result page. </p> <p>The use of <code>sp_q_required </code> affects the main query ( <code>sp_q </code>). </p> <p>To apply to a numbered query, replace the <code># </code> in the parameter name with the corresponding number (for example, <code>sp_q_required_8 </code> applies to the numbered query <code>sp_q_8 </code>). The default value of the parameter is 1 (must match). </p> <p>To search for documents that contain the word "calc" but do NOT contain "mac", "win" or "all" in the user-defined "platform" field, your HTML search form could contain the following lines: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>35 </p> </td> 
   <td colname="col2"> <p>sp_redirect_ 
     if_one_result </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifies whether to redirect to the search result URL if there is only one search result. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>36 </p> </td> 
   <td colname="col2"> <p>sp_referrer </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_referrer= url </code> </p> </td> 
   <td colname="col4"> <p>Specifies the referrer URL for the search. Useful for search rewrite rules where the search results link back to the same site as the search form. </p> <p>The default value is the standard CGI HTTP_REFERRER value delivered by the browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>37 </p> </td> 
   <td colname="col2"> <p>sp_ro </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_ro= <span class="varname"> field </code>: <span class="varname"> relevance </span> </span> </p> </td> 
   <td colname="col4"> <p>Allows optional search time, per field name, relevance control. The <code>ro </code> in the parameter name stands for "relevance override". The parameter accepts one or more field names, followed by a colon character, followed by a relevance value from 0-10. </p> <p>For example, to set the relevance value for the field name "body" to 10, at the time a customer performs a search, the parameter would appears as follows: </p> <p> <code>sp_ro=body:10 </code> </p> <p>Or, to specify multiple field relevance overrides in the parameter string, you can use a pipe delimiter. For example, to set the relevance value for the field names "body" and "title" to 9, at the time a customer performs a search, the parameter would appear as follows: </p> <p> <code>sp_ro=body:9|title:9 </code> </p> <p> <p>Note:  Specifying a field that is not involved in the associated search has no effect. For example, if you set <code>sp_ro=title:10 </code>, but the <code>title </code> field name is not searched, the <code>sp_ro </code> parameter has no effect. In other words, specifying a field name using the <code>sp_ro </code> parameter does not automatically search that field; instead, it only overrides that field's associated relevance setting. </p> </p> <p>See <a href="../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3" type="task" format="dita" scope="local"> Editing pre-defined or user-defined meta tag fields </a>. </p> <p>See <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" type="concept" format="dita" scope="local"> About Query Cleaning Rules </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>38 </p> </td> 
   <td colname="col2"> <p>sp_s </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_s= number </code> </p> </td> 
   <td colname="col4"> <p>Specifies the sort order. Zero (0) is the default and means to sort by relevance score. One (1) means to sort by date and -1 means to not sort. </p> <p>You can specify a field name for the value of the <code>sp_s </code> parameter. For example, <code>sp_s=title </code> sorts results according to the values that are contained in the title field. When a field name is used for the value of an <code>sp_s </code> parameter, results are sorted by that field and then sub-sorted by relevance. </p> <p>Set Sorting for the referenced field to either <span class="uicontrol"> Ascending </span> or <span class="uicontrol"> Descending </span> in <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span> to enable this feature. </p> <p>You can also assign several sort fields to a single query by setting the <code>sp_s </code> parameter several times in the search form. The following template lines sets the search results to be sorted first by artist name, then by album name, and then by track name. </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code> </p> <p>It is also possible to sort on table matched field data by specifying a table name qualifier prior to the field name, for example, items.price. See the <code>sp_field_table </code> parameter for more information on table matching. </p> <p>If searching by proximity, you may sort results according to proximity by specifying a "proximity output field". </p> <p>See <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> About proximity search </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>39 </p> </td> 
   <td colname="col2"> <p>sp_sr </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_sr= field </code> </p> </td> 
   <td colname="col4"> <p>Specifies the rank field to use for static ranking. The field must be a field of type Rank with relevance greater than 0. If no <code>sp_sr </code> parameter is provided for the query, a field of type Rank is automatically selected. </p> <p>To disable static ranking for a particular query, include a NULL value for <code>sp_sr </code> (for example, <code>&lt;input type="hidden" name="sp_sr" value=""&gt; </code>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>40 </p> </td> 
   <td colname="col2"> <p>sp_sfvl_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_sfvl_field= string </code> </p> </td> 
   <td colname="col4"> <p>Specifies the name of a field to use in conjunction with the <code>search-field-value-list</code> tag in the search template. </p> <p>You can specify multiple <code>sp_sfvl_field </code> parameters. </p> </td> 
  </tr> 
  <tr>
   <td colname="col1"> <p>41 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_count </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_sfvl_df_count= <span class="varname"> &lt;integer_value&gt; </code> </span> </p> </td> 
   <td colname="col4"> <p> Requests up to <code><span class="varname"> &lt;integer_value&gt; </code> </span> <code>search-field-value-list </code> dynamic-facet fields for this search. </p> <p>The default value is 0. The maximum allowed value is the current number of dynamic-facet fields, dynamic-facet-field-count defined for a given index. Integer values that are below 0 are treated as 0. Integer values specified above <code>dynamic-facet-field-count </code> are capped at <code>dynamic-facet-field-count </code>. Non-integer values are ignored; they are treated as the default value. </p> <p>A given slice's search is capped with a maximum allowed <code>sp_sfvl_df_count </code> value of this slice's <code>dynamic-facet-field-count </code> value. When merging slice results, the effective maximum value of <code>sp_sfvl_df_count </code> is the maximum actual <code>sp_sfvl_df_count </code> across all slices. </p> <p>See <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Configuring dynamic facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>42 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_exclude </p> </td> 
   <td colname="col03"> <p> </p> </td>
   <td colname="col3"> <p> </p> <p> <code>sp_sfvl_df_exclude= &lt; <span class="varname"> field_name </code>&gt;&lbrack;|&lt; <span class="varname"> field_name </span> </span>&gt;|... </p> </td> 
   <td colname="col4"> <p> Specifies a list of specific dynamic facet fields to exclude from consideration for this search. </p> <p>By default, all dynamic facet fields are considered. </p> <p>See <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Configuring dynamic facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>43 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_include </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <code>sp_sfvl_df_include= &lt; <span class="varname"> field_name </code>&gt;&lbrack;|&lt; <span class="varname"> field_name </span> </span>&gt;|... </p> </td> 
   <td colname="col4"> <p> Specifies a list of specific dynamic facet fields to include in the search results. </p> <p> <p>Note:  The <code>sp_sfvl_df_count </code> parameter determines the total number of dynamic facet fields to return, including any specified by way of <code>sp_sfvl_df_include </code>. That is, using <code>sp_sfvl_df_include </code> does not allow the total count of returned dynamic facet fields to exceed <code>sp_sfvl_df_count </code>. </p> </p> <p>See <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Configuring dynamic facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>44 </p> </td> 
   <td colname="col2"> <p>sp_staged </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_staged= 0 or 1 </code> </p> </td> 
   <td colname="col4"> <p>If <code>sp_staged=1 </code> is submitted with a query, the query that is run is a staged search. </p> <p>A staged search uses all the components that are currently staged including the index and templates. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>45 </p> </td> 
   <td colname="col2"> <p>sp_start_day, sp_start_month, sp_start_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_start_day= number </code> </p> <p> <code>sp_start_month= number </code> </p> <p> <code>sp_start_year= number </code> </p> </td> 
   <td colname="col4"> <p>This triplet of values specifies the starting date range for the search and you provide it as a set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>46 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_ suggest _q </p> </td> 
   <td colname="col3"> <p> <code>sp_suggest_q= number </code> </p> </td> 
   <td colname="col4"> <p>The <code>sp_suggest_q </code> parameter determines which <code>sp_q[_#] </code> parameter to use with the Suggest service. </p> <p>The default value of <code>sp_suggest_q </code> is 0, which means that the search engine uses the value of <code>sp_q </code> to determine the suggestions. </p> <p>Set <code>sp_suggest_q=1 </code> to use the value of <code>sp_q_1 </code> to determine the suggestions, and so on. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>47 </p> </td> 
   <td colname="col2"> <p>sp_t </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_t= string </code> </p> </td> 
   <td colname="col4"> <p>Specifies the transport template to use. </p> <p>This parameter is useful if you want to control the appearance of core search results across your website by using different search transport templates for each area in your Search account. </p> <p>The default transport template is "search". </p> <p>See <a href="../c-appendices/c-templates.md#reference_12AAB3B9F4C74C11956F1DBA95714C2F" type="reference" format="dita" scope="local"> Managing multiple transport templates for your website </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>48 </p> </td> 
   <td colname="col2"> <p>sp_trace </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_trace= 0 or 1 </code> </p> </td> 
   <td colname="col4"> <p>When set as <code>sp_stage=1 </code>, enables the core search trace capability in Simulator. </p> <p>See <a href="../c-about-simulator.md#concept_020AA6751E32421A96A3455508364C7E" format="dita" scope="local"> About Simulator </a>. </p> <p> <p>Note:  If this parameter is not specified, core search does not gather the tracing information and the related core search template tags have no output. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>49 </p> </td> 
   <td colname="col2"> <p>sp_w, sp_w_control </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_w= <i>sound-alike-enable</i> </code> </p> <p> <code> sp_w_control=<i>sound-alike-control</i> </code> </p> </td> 
   <td colname="col4"> <p>Specifies that sound-alike matching should be enabled or disabled for this particular query. </p> <p>The sp_w_control for `Exact` is Ignored. Sound-alike matching is Disabled. </p><p>The sp_w_control for `Alike` is Ignored. Sound-alike matching is Enabled</p><p>The sp_w_control for Anything else is 1. Sound-alike matching is Disabled. </p><p>The sp_w_control for Anything else is anything else. Sound-alike matching is Enabled. </p>The <code>sp_w_control </code> parameter lets you create a negatively or positively worded checkbox for end-user control of sound-alike matching. </p> <p>If <code>sp_w_control=0 </code> is used, then a negatively worded checkbox is used to set the <code>sp_w </code> parameter as in the following example: </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code> </p> <p>If <code>sp_w_control=1 </code> is used, then a positively worded checkbox is used to set the <code>sp_w </code> parameter as in the following: </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code> </p> <p>See the sample advanced search form for more examples on using <code>sp_w_control </code> and <code>sp_w </code> parameters. </p> <p>See <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Sample advanced search form </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>50 </p> </td> 
   <td colname="col2"> <p>sp_x </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_x= field </code> </p> </td> 
   <td colname="col4"> <p>Specifies the fields to search for the query string. any means search all fields. title means search only title fields. desc means search only document description fields. keys means search only document keywords. body means search only body text. alt means search only alternate text. url means search only the URL values. target means search only target keywords. In any of these cases, user specification of "text:", "desc:", "keys:", "body:", "alt:", "url:", and "target:" field prefixes within the corresponding <code>sp_q </code> parameter are ignored. If <code>sp_x </code> is not present or if it is set to an empty string or any, then the standard user field prefixes are allowed. See the Search Tips description for more information about the field prefixes. </p> <p>See <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> About Searches </a>. </p> <p>See the sample Advanced Search Form description for examples using the <code>sp_x </code> parameter. </p> <p>See <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Sample advanced search form </a>. </p> <p>You can create queries that search all fields set to <span class="uicontrol"> Search By Default </span> under <span class="uicontrol"> Options </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span> by setting <code>sp_x=any </code>. Both pre- and user-defined fields may be used as the value of the <code>sp_x </code> parameter. </p> <p>You can also assign several fields to a single query by setting the <code>sp_x </code> parameter several times. The following template lines let users query both the "title" and "author" fields for "Great Books". </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>51 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_x_# </p> </td> 
   <td colname="col3"> <p> <code>sp_x_#= field-name </code> </p> </td> 
   <td colname="col4"> <p>This parameter specifies which field to search in the corresponding <code>sp_q_# </code> query. The <code> # </code> is replaced with a number between 1 and 16 (for example, <code>sp_x_8 </code>). The field-name is any pre- or user-defined field. </p> <p>If no <code>sp_x_# </code> parameter is provided for a particular numbered query, all fields defined as <span class="uicontrol"> Search By Default </span> as set under <span class="uicontrol"> Setting </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span> are searched by that query. </p> <p>For example, submitting the following form returns all documents that contain the word "great" that also contain the word "Fitzgerald" in the "author" field: </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code> </p> <p>You can associate multiple field names with a particular query or numbered query by providing more than one instance of the same <code>sp_x </code> or <code>sp_x_# </code> parameter in a single search request. </p> <p>For example, to search for the word "flower" within both the "body" and "keys" fields, you could create a search form with the following information: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## A typical example of using backend search CGI parameters {#section_260012BBC2514CC9A8E02E53DE8B41EE}

The following link queries start a search using "Music" as the search query, and uses all the default parameters. Note that the URL is split across two lines for readability. In your HTML, this link should all be on one line.

```
<a href="https://search.atomz.com/search/?sp_q=Music&sp_a=sp99999999"> 
Testing...</a>
```

The same functionality is more typically defined with a form:

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q" value="Music"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
</form>
```

You should typically use default parameters when initiating a search. That way, the first page is shown, sorted by relevance, and allows the customer to choose other pages and other options. If the search form on your site includes options for collections, pass in the collection name as a parameter.

## A detailed example of using backend search CGI parameters {#section_5FA3C620D5124FB2AB28857F8D8473F6}

The following form queries display `25` results starting at result `10`. Summaries are not shown, the sort order is by date, and the collection named `support` is used. Only documents dated within the last 30 days are returned.

```
<form action="https://search.atomz.com/search/"> 
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
