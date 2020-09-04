---
description: Use the Metadata menu to customize Search definitions and index injections.
seo-description: Use the Metadata menu to customize Search definitions and index injections.
seo-title: About the Metadata menu
solution: Target
subtopic: Metadata
title: About the Metadata menu
topic: Settings,Site search and merchandising
uuid: f12fc863-a140-45e8-b219-3dbfdef099cd
---

# About the Metadata menu{#about-the-metadata-menu}

Use the Metadata menu to customize Search definitions and index injections.

## About Definitions {#concept_AE48035C210145169BE067D396975620}

You can use [!DNL Definitions] to customize the content and relevance of the HTML and metadata fields that are considered when a customer submits a search query.

You can edit the fields that are already pre-defined. Or, you can also create new user-defined fields based on metadata tag content. Each definition is displayed on a single line on the [!DNL Staged Definitions] page.

See also [About Data Views](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3). 

## Adding a new meta tag field {#task_6DF188C0FC7F4831A4444CA9AFA615E5}

You can define and add your own metadata tag fields.

Before the effects of the new meta tag definition is visible to customers, you must rebuild your site index.

**To add a new meta tag field** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. On the [!DNL Definitions] page, click **[!UICONTROL Add New Field]**.
1. On the [!DNL Add Field] page, set the options that you want.

    <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Field Name </p> </td> 
      <td colname="col2"> <p>Specifies a name that is used to reference the field. </p> <p>The field name must adhere to the following rules: </p> <p> 
      <ul id="ul_D39D09CD7E7D41A59ECB6C5A6F4F263D"> 
      <li id="li_11CE852BE3C64CEF90FEC7A6E1079E13"> The name must contain only alphanumeric characters. </li> 
      <li id="li_7FC340E7C58545C88CE9AF4AF09AD7AD"> Dashes are allowed in the name, but no spaces. </li> 
      <li id="li_996FF38457AB4C6DB22B15850A0830CC"> You can enter a name up to 20 characters long. </li> 
      <li id="li_C1019E587995444D9587D5EA495D719E"> The name is not case-sensitive, but is displayed and stored exactly as you type it. </li> 
      <li id="li_E55404D6CE354EC89CFFEB1048A11F44"> You cannot use the names that exist in the pre-defined fields as seen in the table on the <span class="wintitle"> Staged Definitions </span> page. </li> 
      <li id="li_7CE328AE3B5F45A8A09E2DA7ECB62551"> You cannot use the word "any" as the value of a user-defined field name. </li> 
      <li id="li_9B8287EED1784E79BFCBBBA956705CD2"> You cannot edit the names of pre-defined fields. </li> 
      </ul> </p> <p> Field name examples: </p> <p> 
      <ul id="ul_5881669913D04E35A6D4A6D31BEE7DF3"> 
        <li id="li_0AFFB8B516FE40F8A615C2F578F2CEA3"> author </li> 
        <li id="li_7F0ADFBFB21E4B84ACA8A1CEBFE344D1"> PublishDate </li> 
        <li id="li_6D1BEB3D19AC499E9227EC115AEB6296"> something-wild </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Meta Tag Name(s) </p> </td> 
      <td colname="col2"> <p>Determines the content that is associated with the defined field. </p> <p>The list of names can be up to 255 characters long. And, name can contain any characters that are allowed in the name attribute of an HTML meta tag. </p> <p>You can specify multiple meta tags in a single field definition. </p> <p>Multiple values must be comma-separated, and the leftmost meta tag name found on any given web page takes precedence. </p> <p>For example, suppose that you have defined a field named "auth". The field name has the associated meta tags "author, dc.author". In this case, the content from the "author" meta tag is indexed and searched over that of the "dc.author" if both meta tags appear on a web page. </p> <p>User-defined fields must have at least one meta tag name in their definition. Pre-defined fields do not need to have an associated meta tag. However, if one or more meta tags are specified, the content of the meta tags override the current data source for each tag. </p> <p>For example, if the meta tag "dc.title" is associated with the pre-defined "title" field, the content from the "dc.title" meta tag is indexed over that of the 
      <code>
        &lt;title&gt; 
      </code> tag for any particular document. </p> <p>Examples include the following: </p> <p> 
      <ul id="ul_0132E15FC19E4C0CA13CD5A12EA3BBEC"> 
      <li id="li_ECD3B194FECB4C2090CAEC8449320D3F"> dc.date </li> 
      <li id="li_09C76BC7AC7348859D01989697212E31"> description </li> 
      <li id="li_9230C0450F9D424087D1F127048DA311"> proprietarytag </li> 
      </ul> </p> </td> 
    </tr> 
      <tr> 
      <td colname="col1"> <p>Data Type </p> </td> 
      <td colname="col2"> <p>Every field has an associated data type such as text, number, date, version, rank, or location. This data type determines how the field's content is indexed, searched and optionally, sorted. </p> <p>You cannot change the data type after you create the field definition. </p> <p>Use the following information to help you select the data type that is relevant to the information that the field contains. </p> <p> 
      <ul id="ul_A3AD5A0CF354410F836311F39151B8A6"> 
      <li id="li_9F412DA7D9EF497BA6E65F9CE10F3046"> <span class="uicontrol"> Text </span> data type fields are treated as character strings. </li> 
      <li id="li_AD78B75644AE40208F0239311015611F"> <span class="uicontrol"> Number </span> data type fields are treated as integer or floating-point numeric values. </li> 
      <li id="li_0B46975C589148E9A7C32A8D250487B7"> <span class="uicontrol"> Date </span> data type fields are treated as date/time specifiers. You can customize the allowed date/time formats when you add or edit the new field. </li> 
      <li id="li_BB68CB1DBE0543AC9000B3DEDFB28E7E"> <span class="uicontrol"> Version </span> data type fields are treated as free-form numeric data. For example, 1.2.3 sorts before 1.2.2. </li> 
      <li id="li_0BA895B4DADA46528A7A4161EEB1521E"> <span class="uicontrol"> Rank </span> data type fields are treated the same as "Number" type fields, except that they additionally influence the ranking / relevance calculations in the search results. <p>See <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" type="concept" format="dita" scope="local"> About Ranking Rules </a>. </p> </li> 
      <li id="li_459405DA437049AD88AA1FAC28F04720"> <span class="uicontrol"> Location </span> data type fields are treated as a physical location anywhere in the world. The allowed location formats include the following: <p> 
      <ul id="ul_D2CEBFA1A5504AA996BA2F7641AFB7F3"> 
      <li id="li_5283A2F2D5D84840B3D920C08D43654C"> 5- or 9-digit ZIP codes in the form of DDDDD or DDDDD-DDDD, where each "D" is a 0-9 digit. </li> 
      <li id="li_A5CD4DFC90164BC68183DB7D10603B7C"> Three-digit area-codes in the form of DDD. </li> 
      <li id="li_9DAEAE64BC7F4902B25043D998C8F56D"> Latitude/longitude pairs in the form ±DD.DDDD±DDD.DDDD, where the first number specifies the latitude and the second number specifies the longitude. </li> 
      </ul> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Allow Lists </p> </td> 
      <td colname="col2"> <p>Available only if the data type <span class="uicontrol"> Text </span>, or <span class="uicontrol"> Number </span> is selected. </p> <p>Separately index delimited values in the metadata content of this field. </p> <p>For example, the content "Red, Yellow, Green, Blue" is treated as four separate values instead of one when "Allow Lists" is selected. This treatment is most useful with range searching (using 
      <code>
        sp_q_min 
      </code>, 
      <code>
        sp_q_max 
      </code>, or 
      <code>
        sp_q_exact 
      </code>) and with the 
      <code>
        &lt;search-field-value-list&gt; 
      </code>, 
      <code>
        &lt;search-field-values&gt; 
      </code>, and 
      <code>
        &lt;search-display-field-values&gt; 
      </code>. </p> <p>Not available if Version data type is selected. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Dynamic Facet </p> </td> 
      <td colname="col2"> <p> 
        <!--NEW 2/2/2014--> <p>Note:  This feature is not enabled by default. Contact Technical Support to activate it for your use. After it is activated, it appears in the user interface. </p> </p> <p>Sets the identified facet to be dynamic. </p> <p>Facets are built on top of meta tag fields. A meta tag field is a low-level, core search layer of Adobe Search&amp;Promote. Facets, on the other hand are part of GS (Guided Search)-the high-level, presentation layer of Adobe Search&amp;Promote. Facets own meta tag fields, however, meta tag fields know nothing about facets. </p> <p>See <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> About Dynamic Facets </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Allow Dedupe </p> </td> 
      <td colname="col2"> <p>Check this option to enable deduplication for this field. That is, allow this field to be specified at search-time by way of the 
        <code>
          sp_dedupe_field 
        </code> Search CGI parameter. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Search CGI parameters </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Table Name </p> </td> 
      <td colname="col2"> <p>Permanently associates the given field with the given table name. </p> <p>Any time such a field is mentioned within a core search CGI parameter or a template tag, the table name is provided automatically. This feature allows the selection of dynamic facets through table matches, but you can also use it for non-dynamic facet fields, if desired. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>List Delimiters </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Allow Lists </span> is selected. </p> <p>Specifies which characters separate individual list values. You can specify multiple characters, each of which are treated as a value separator. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Search By Default </p> </td> 
      <td colname="col2"> <p>When selected, the field content is searched even when the field is not explicitly specified in a given search query. If you deselect this option, the field is only searched when requested. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vertical Update Field </p> </td> 
      <td colname="col2"> <p> <p>Note:  This feature is not enabled by default. Contact Technical Support to activate it for your use. After it is activated, it appears in the user interface. </p> </p> <p>Sets the identified field to be a Vertical Update field. </p> <p>Vertical Update fields are candidates to be updated by way of the Vertical Update process ( <span class="uicontrol"> Index </span> &gt; <span class="uicontrol"> Vertical Update </span>.) Due to the way that Vertical Updates are made, content from these fields cannot be searched in free-text searches. Checking this option results in this field's content not being added to the "word" index during any kind of index operation. It also enables the update of this field during a Vertical Update operation. </p> <p>To learn more about Vertical Updates, see <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> About Vertical Update </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Relevance </p> </td> 
      <td colname="col2"> <p>You can edit the relevance of pre-defined and user-defined fields. </p> <p>Relevance is specified on a scale 1-10. A setting of 1 means that it is the least relevant and 10 being the most relevant. These values are taken into account when the software considers the query matches in each field. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sorting </p> </td> 
      <td colname="col2"> <p>Specifies when results are sorted by the named field, by way of the 
        <code>
          sp_s 
        </code> Search CGI parameter. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Search CGI parameters </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Language </p> </td> 
      <td colname="col2"> <p>Available only if the data type <span class="uicontrol"> Rank </span>, <span class="uicontrol"> Number </span>, or <span class="uicontrol"> Date </span> is selected. </p> <p>Controls the language and locale conventions that are applied when indexing the date, number, and rank values for this field. </p> <p>You can choose to apply the account language (Linguistics &gt; Words &amp; Languages). Or, you can apply the language that is associated with the document that contains each number or date value, or a specific language. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Date Format(s) </p> </td> 
      <td colname="col2"> <p>Available only if the data type <span class="uicontrol"> Date </span> is selected. </p> <p>Controls the date formats that are recognized when indexing date values for this field. </p> <p>A default list of date format strings is provided for each date field. You can add to the list or edit the list to suit your own site's needs. </p> <p>See <a href="../c-appendices/r-date-formats.md#reference_4D1FC1F6B9F44857967188496D8D335B" type="reference" format="dita" scope="local"> Date Formats </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test Date Formats </p> </td> 
      <td colname="col2"> <p>Available only if the data type <span class="uicontrol"> Date </span> is selected as the Data Type. </p> <p>Lets you preview the date formats that you have specified to ensure that they are formatted correctly. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Time Zone </p> </td> 
      <td colname="col2"> <p>Available only if the data type <span class="uicontrol"> Date </span> is selected as the Data Type. </p> <p>Controls the assumed time zone that is applied when indexing date values for this field that do not specify a time zone. </p> <p>For example, if your account time zone is set to "America/Los Angeles" and you select <span class="uicontrol"> Use Account Time Zone </span>, the following meta date value, which does not have a specified time zone, is treated as if it were Pacific Time, accounting for daylight savings: </p> <p>&lt;meta name="dc.date" content="Mon, 05 Sep 201213:12:00"&gt; </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Least Important Rank Value </p> </td> 
      <td colname="col2"> <p>Available only if the data type <span class="uicontrol"> Rank </span> is selected as the Data Type. </p> <p>Controls the rank value that represents the minimum rank of any document. </p> <p>If your document rankings range from 0 for the lowest rank to 10 for the highest rank, then you set this value to 0. </p> <p>If your document rankings range from 1 for the highest rank to 10 for the lowest rank, then you set this value to 10. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Default Rank Value </p> </td> 
      <td colname="col2"> <p>Available only if the data type <span class="uicontrol"> Rank </span> is selected as the Data Type. </p> <p>Controls the rank value that is used if a document does not contain any of the meta tags that are defined for this rank field. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Most Important Rank Value </p> </td> 
      <td colname="col2"> <p>Available only if the data type <span class="uicontrol"> Rank </span> is selected as the Data Type. </p> <p>Controls the rank value that represents the maximum rank of any document. </p> <p>If your document rankings range from 0 for the lowest rank to 10 for the highest rank, then you set this value to 10. </p> <p>If your document rankings range from 1 for the highest rank to 10 for the lowest rank, then you set this value to 1. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Default Units </p> </td> 
      <td colname="col2"> <p>Available only if the data type <span class="uicontrol"> Location </span> is selected as the Data Type. </p> <p>Controls the treatment of distance values for proximity searches. </p> <p>If you set the default units to <span class="uicontrol"> Miles </span>, then any proximity search minimum/maximum distance criteria that is applied to this field (by way of the 
      <code>
        sp_q_min[_#] 
      </code> or the 
      <code>
        sp_q_max[_#] 
      </code> Search CGI parameters) is treated as miles, otherwise as kilometers. </p> <p>This option also controls the default distance units that are applied to the output of the 
      <code>
        &lt;Search-Display-Field&gt; 
      </code> search results template tag when applied to a proximity search output field. </p> <p>See <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> About proximity search </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Create Range Description? </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Number </span> is selected as the Data Type. </p> <p>Controls the automatic creation of Field Range descriptions, for use with <span class="uicontrol"> Design </span> &gt; <span class="uicontrol"> Navigation </span> &gt; <span class="uicontrol"> Facets </span>. </p> <p>See <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" format="dita" scope="local"> About Facets </a>. </p> <p> <p>Note:  If this field has <span class="uicontrol"> Vertical Update Field </span> checked, the generated Field Range description field is updated during a Vertical Update. However, it is recommended that the field identified in <span class="uicontrol"> Range Field </span> also have <span class="uicontrol"> Vertical Update Field </span> checked. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Range Field </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked. </p> <p>The <span class="uicontrol"> Text </span> field to be updated with range descriptions for the current field. This list contains all <span class="uicontrol"> Text </span> fields that are not already being used with other fields for Field Range generation. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Range Values </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked and a <span class="uicontrol"> Range Field </span> item is selected. </p> <p>A blank-delimited list of data points to use when creating the Field Range descriptions. For example: </p> <code> 10&amp;nbsp;20&amp;nbsp;50&amp;nbsp;100&amp;nbsp;1000 </code> <p>You can enter these values in any order. The values are sorted and duplicates removed before it is saved. You can also specify negative and non-integer values. </p> <p>For each of this field's values: 
      <ul id="ul_C4B41AF5AADF4B84B9C489CE82FF7075"> 
      <li id="li_90736394A5AE4F5CA6B47687BCB627AA">if the value is less than (&lt;) the smallest value in <span class="uicontrol"> Range Values </span>, the <span class="uicontrol"> "Less Than" Format </span> is used </li> 
      <li id="li_A5C272B2D26A468CA07EB2046B2EA8A7">if the value is greater than or equal to (&gt;=) the largest value in <span class="uicontrol"> Range Values </span>, the <span class="uicontrol"> "Greater Than" Format </span> is used. </li> 
      <li id="li_9DDFB70E1E824CF4819C57450C1A6DD2">otherwise, a "range" is found where the field value falls between two consecutive <span class="uicontrol"> Range Values </span> (greater than (&gt;) the smaller value and less than or equal to (&lt;=) the larger value), and the <span class="uicontrol"> Intermediate Format </span> is used. </li> 
    </ul> </p> <p>For example, the above example set of values will define a set of descriptions for values: 
    <ul id="ul_03ED30D5A19346AB8E6809BDD186A9A9"> 
      <li id="li_F97A6B3763954EFE9B6751F472AF7D20">less than 10 </li> 
      <li id="li_12B6F636A6444B8292E0BFE4F55032DF">greater than or equal to 10 and less than 20 </li> 
      <li id="li_545A2EAF5BD046B5AD59B77DB43DCD14">greater than or equal to 20 and less than 50 </li> 
      <li id="li_26A8CD2422524D2CBD36794C6908572A">greater than or equal to 50 and less than 100 </li> 
      <li id="li_05EBEEE68DC348E0821F1CC16D04D69C">greater than or equal to 100 and less than 10000 </li> 
      <li id="li_9513A6B519394780A6A41B80762A0370">greater than or equal to 10000 </li> 
      </ul> </p> <p>See <span class="uicontrol"> Test using Greater Than? </span> to change how these tests are performed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>"Less Than" Format </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked and a <span class="uicontrol"> Range Field </span> item is selected. </p> <p>This is the template used to specify the range description for values less than the smallest value found in <span class="uicontrol"> Range Values </span>. The smallest value will be represented using the numeric placeholder token <span class="uicontrol"> ~N~ </span>. For example: </p> <code> Less&amp;nbsp;than&amp;nbsp;~N~ </code> <p>or: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;below </code> <p>Normally, the value will be formatted "as-is" - i.e. for a <span class="uicontrol"> Range Values </span> definition of "5 10 20" and a supplied value of 1, the generated range description would simply be something like "Less than 5". If you'd instead like to have it be "4.99 and below", set <span class="uicontrol"> Precision </span> to <span class="uicontrol"> 2 </span> and use this format: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;below </code> <p>In <span class="uicontrol"> "Less Than" Format </span>, the lower-case <span class="uicontrol"> ~n~ </span> will cause the value to be rounded <i>down</i> according to the <span class="uicontrol"> Precision </span> setting. </p> <p>Note: to include any numeric placeholder in the range description, as is, specify with a backslash (\) prefix - e.g. <span class="uicontrol"> \~N~ </span> or <span class="uicontrol"> \~n~ </span>. To include a backslash character, specify it with another backslash - e.g. <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Intermediate Format </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked and a <span class="uicontrol"> Range Field </span> item is selected. </p> <p>This is the template used to specify the range description for values that fall somewhere between the smallest and largest values found in <span class="uicontrol"> Range Values </span>. For the given range, the lower range value will be represented using the numeric placeholder token <span class="uicontrol"> ~L~ </span>, and the higher range value will be represented using the token <span class="uicontrol"> ~H~ </span>. For example: </p> <code> ~L~&amp;nbsp;to&amp;nbsp;~H~ </code> <p>or: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>or: </p> <code> Less&amp;nbsp;than&amp;nbsp;~H~&amp;nbsp;and&amp;nbsp;greater&amp;nbsp;than&amp;nbsp;~L~ </code> <p>Normally, the values will be formatted "as-is" - i.e. for a <span class="uicontrol"> Range Values </span> definition of "5 10 20" and a supplied value of 8, the generated range description would simply be something like "Between 5 and 10". If you'd instead like to have it be "Between 5 and 9.99", with the higher value adjusted <i>downwards</i>, set <span class="uicontrol"> Precision </span> to <span class="uicontrol"> 2 </span> and use this format: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~h~ </code> <p>Similarly, <span class="uicontrol"> ~L~ </span> can be replaced with <span class="uicontrol"> ~l~ </span> to have the lower value adjusted <i>upwards</i>, also according to the <span class="uicontrol"> Precision </span> setting. This means that a definition like: </p> <code> Between&amp;nbsp;~l~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>with a <span class="uicontrol"> Precision </span> value of <span class="uicontrol"> 2 </span> would create "Between 5.01 and 10". </p> <p>The lower-case <span class="uicontrol"> ~l~ </span> will cause the lower value to be rounded <i>up</i> according to the <span class="uicontrol"> Precision </span> setting, and the lower-case <span class="uicontrol"> ~h~ </span> will cause the higher value to be rounded <i>down</i>. </p> <p>Note: to include any numeric placeholder in the range description, as is, specify with a backslash (\) prefix - e.g. <span class="uicontrol"> \~L~ </span> or <span class="uicontrol"> \~h~ </span>. To include a backslash character, specify it with another backslash - e.g. <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>"Greater Than" Format </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked and a <span class="uicontrol"> Range Field </span> item is selected. </p> <p>This is the template used to specify the range description for values greater than the largest value found in <span class="uicontrol"> Range Values </span>. The largest value will be represented using the numeric placeholder token <span class="uicontrol"> ~N~ </span>. For example: </p> <code> Greater&amp;nbsp;than&amp;nbsp;~N~ </code> <p>or: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;above </code> <p>Normally, the value will be formatted "as-is" - i.e. for a <span class="uicontrol"> Range Values </span> definition of "5 10 20" and a supplied value of 30, the generated range description would simply be something like "Greater than 20". If you'd instead like to have it be "20.01 and above", set <span class="uicontrol"> Precision </span> to <span class="uicontrol"> 2 </span> and use this format: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;above </code> <p>In <span class="uicontrol"> "Greater Than" Format </span>, the lower-case <span class="uicontrol"> ~n~ </span> will cause the value to be rounded <i>up</i> according to the <span class="uicontrol"> Precision </span> setting. </p> <p>Note: to include any numeric placeholder in the range description, as is, specify with a backslash (\) prefix - e.g. <span class="uicontrol"> \~N~ </span> or <span class="uicontrol"> \~n~ </span>. To include a backslash character, specify it with another backslash - e.g. <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Precision </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked and a <span class="uicontrol"> Range Field </span> item is selected. </p> <p>An integer value specifying the number of digits to the right of a decimal point. This also controls rounding operations. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Strip leading zeros? </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked, a <span class="uicontrol"> Range Field </span> item is selected and a non-zero <span class="uicontrol"> Precision </span> value has been set. </p> <p>Should we display "0.50" as ".50"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Strip trailing zeros? </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked, a <span class="uicontrol"> Range Field </span> item is selected and a non-zero <span class="uicontrol"> Precision </span> value has been set. </p> <p>Should we display "10.00" as "10"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Show thousands separators? </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked and a <span class="uicontrol"> Range Field </span> item is selected. </p> <p>Should we display "10000" as "10,000"? Locale-specific values will be used. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Adjust zero values? </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked and a <span class="uicontrol"> Range Field </span> item is selected. </p> <p>When rounded zero values are displayed, should they be rounded up or down according to the <span class="uicontrol"> Precision </span> setting? i.e. display "0.01"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test using Greater Than? </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked and a <span class="uicontrol"> Range Field </span> item is selected. </p> <p>As each value is compared against the values in <span class="uicontrol"> Range Values </span>, processed in <i><b>descending</b></i> order, it is compared, by default, using the Greater Than or Equal (&gt;=) operator, stopping once this test succeeds. This means that with a set of <span class="uicontrol"> Range Values </span> like "10 20 50 100 1000" the value 100 will fall in the range 100 to 1000, as 100 is indeed &gt;= 100. If you'd rather have it fall in the range 50 to 100, check this option, which will cause the comparisons to use the Greater Than (&gt;) operator, instead. </p> <p>For example, for each of this field's values, when this option is checked: 
      <ul id="ul_969621B1BD914FA5BD73ED21F8841010"> 
      <li id="li_157BEFDA7D0E44C481F4E4BC9046EF24">if the value is less than or equal to (&lt;=) the smallest value in <span class="uicontrol"> Range Values </span>, the <span class="uicontrol"> "Less Than" Format </span> will be used </li> 
      <li id="li_737EE666CA6243A8864E17A311CF3ACC">if the value is greater than (&gt;) the largest value in <span class="uicontrol"> Range Values </span>, the <span class="uicontrol"> "Greater Than" Format </span> will be used </li> 
      <li id="li_353A9820F7F74CCCBB3281EC4CB48734">otherwise, a range will be found where the field value falls between two consecutive <span class="uicontrol"> Range Values </span> (greater than or equal to (&gt;=) the smaller value and less than (&lt;) the larger value), and the <span class="uicontrol"> Intermediate Format </span> will be used </li> 
    </ul> </p> <p>and, when unchecked: 
    <ul id="ul_945844C33C2E4D95A598C4876E15F211"> 
      <li id="li_653B6E2934574DA3B4BCEF07D0A84527">if the value is less than (&lt;) the smallest value in <span class="uicontrol"> Range Values </span>, the <span class="uicontrol"> "Less Than" Format </span> will be used </li> 
      <li id="li_AECA6880002F40FAB1820B37237550A7">if the value is greater than or equal to (&gt;=) the largest value in <span class="uicontrol"> Range Values </span>, the <span class="uicontrol"> "Greater Than" Format </span> will be used </li> 
      <li id="li_ECB2DF7CA592497298E9ADC708220366">otherwise, a range will be found where the field value falls between two consecutive <span class="uicontrol"> Range Values </span> (greater than (&gt;) the smaller value and less than or equal to (&lt;=) the larger value), and the <span class="uicontrol"> Intermediate Format </span> will be used </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Available only if <span class="uicontrol"> Create Range Description </span> is checked and a <span class="uicontrol"> Range Field </span> item is selected. </p> <p>Supply a sample numeric value and press the <span class="uicontrol"> Test </span> button to see how the Range Field is created. The generated Range description will be displayed in the window. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   See also [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5). 
1. Click **[!UICONTROL Add]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing pre-defined or user-defined meta tag fields {#task_0A7657B63596421BB6DB3ED44F827AB3}

You can edit only certain fields in pre-defined meta tags, or edit all the fields in meta tags that are user-defined.

Before the effects of your meta tag changes are visible to customers, you must rebuild your site index.

**To edit pre-defined or user-defined meta tag fields** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. On the [!DNL Definitions] page, in the [!DNL Actions] column of the table, click **[!UICONTROL Edit]** in the row of the meta tag field name that you want to change.
1. On the [!DNL Pinned Keyword Results Manager] page, in the table, click **[!UICONTROL Edit]** in the row of the keyword that you want to change.
1. On the [!DNL Edit Field] page, set the options that you want.

   If you chose to make changes to a pre-defined meta tag field, be aware that not all fields are editable.

   See the table of options under [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a user-defined meta tag field {#task_9361EF38B5E743038B6672FA6CF70FD3}

You can delete a user-defined meta tag field that you no longer need or use.

You cannot delete pre-defined meta tag fields. However, you can edit certain fields.

See [Editing pre-defined or user-defined meta tag fields](../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3).

Before the effects of your delete meta tag are visible to customers, you must rebuild your site index.

**To delete a user-defined meta tag field** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. On the [!DNL Definitions] page, in the [!DNL User-defined fields] section of table, click **[!UICONTROL Delete]** in the row of the meta tag field name that you want to remove.
1. In the Confirmation dialog box, click **[!UICONTROL OK]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Injections {#concept_DA091920671948A0A893A26B3A2FAAE5}

You can use [!DNL Injections] to insert content into your web pages without the need to edit the pages themselves.

You can append content to specific indexed fields like "target" or "body", or replace indexed content with new values. For example, if you inserted new content into the "target" meta tag field, This information is treated just as it would hard-coded page content. You can edit the content of any pre-defined meta tag field regardless of whether your site pages have corresponding content. For example, you can edit the content of the following pre-defined meta tag field names:

* alt 
* body 
* charset 
* date 
* desc 
* keys 
* language 
* target 
* title 
* url

## Working with Test Field Injections {#section_74939EA9E6EA4D2A92E8066B3B11CF92}

You can optionally use **[!UICONTROL Test]** on the [!DNL Staged Injections] page. You enter a test field name (for example, "title" or "body"), the original field value (for example, "Home Page"), and a test URL from your website. The resulting value is displayed for your reference. The current values are not altered during the test.

## Working with Field Injection Definitions {#section_C1BBF19DE8EF4A6F8CC3ED691F3953A9}

Injection definitions have the following form:

```
append|replace field [regexp] URL value
```

The `append|replace`, `field`, `URL`. and `value` items are mandatory. You enter one injection definition per line. The following example contains six different injection definitions.

```
replace title  https://www.yoursite.com/company/contactus.html Adobe: Contact Us 
append body https://www.yoursite.com/products/* On Sale Now! 
append target https://www.yoursite.com/news/bob_white/ Regular Weekly Feature 
append target regexp https://www.yoursite.com/travel/mr_travel/.*\column.html$ Regular Weekly Feature 
replace charset https://www.yoursite.com/japanese/intro.txt shift-jis 
replace language https://www.yoursite.com/japanese/intro.txt ja_JP
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Injection definition </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> append|replace </span> </p> </td> 
   <td colname="col2"> <p>Choose "append" to add the value of the injection definition ("Adobe: Contact Us" or "On Sale Now!" in the above examples) to the content of existing fields. Choose "replace" to overwrite existing field content with the defined value. If a field does not currently have content, the defined value is added automatically, regardless of which option (append or replace) is used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> field </span> </p> </td> 
   <td colname="col2"> <p>A field name is required. The following are ten pre-defined field names that you can use: </p> <p> 
     <ul id="ul_B9336FA53023474EAEE399116E7FC972"> 
      <li id="li_C621203DCD2B4875A54A1DD19F0B5B90"> <span class="codeph"> alt </span> </li> 
      <li id="li_9217E6A037254BEDBB8D006B70D7670D"> <span class="codeph"> body </span> </li> 
      <li id="li_DCDC50F93F224F02897419B745E09399"> <span class="codeph"> charset </span> </li> 
      <li id="li_D95668236B6547B99966668C82B302AB"> <span class="codeph"> date </span> </li> 
      <li id="li_D2071681274345C3B97E9ADA6D223271"> <span class="codeph"> desc </span> </li> 
      <li id="li_26683A9209454A438D811187FB929482"> <span class="codeph"> keys </span> </li> 
      <li id="li_A5E19F81B872402CA62B5AB9497E030D"> <span class="codeph"> language </span> </li> 
      <li id="li_FD0B1CD9E6304B18B9D7F57E61015107"> <span class="codeph"> target </span> </li> 
      <li id="li_400D7E3F3E9B47EFB2FF5C0D278DB573"> <span class="codeph"> title </span> </li> 
      <li id="li_449BCBEE4F64424BB69F780C10F5956C"> <span class="codeph"> url </span> </li> 
     </ul> </p> <p>Each field name corresponds to elements on your site pages. If you specify the field name <span class="codeph"> desc </span> for example, you can add the injection definition value to the field that corresponds to the description Meta tags on your site pages. </p> <p>If no description Meta tag exists on your pages, the defined content creates the tag for you. The content specified in a <span class="codeph"> desc </span> injection displays on your results page just as hard-coded Meta-description content would. </p> <p>You can also create multiple definitions with the same field name. For example, supposed you have the following injections: </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/&nbsp;Welcome&nbsp;to&nbsp;My&nbsp;Site </code> </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/company/*.html&nbsp;My&nbsp;Site:&nbsp;Contact </code> </p> <p>All site pages in the above example receive an injected title "Welcome to My Site". Pages in the "/company/" folder are injected with a new title "My Site: Contact Us" that replaces the previous one. </p> <p>Notice that injections are applied in the order in which they appear in the <span class="wintitle"> Field Injection Definitions </span> text box. If the same field ("title" in this example) is defined more than once for pages at the same location, the later definition takes precedence. </p> <p> <span class="codeph"> [regexp] </span> - optional. If you choose to use the <span class="codeph"> regexp </span> option, the defined URL is treated as a regular expression. </p> <p>See <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Regular Expressions </a>. </p> <p>In the following definition: </p> <p> <code> replace&nbsp;target&nbsp; <b>regexp&amp;nbsp;^.*/products/.*\.html$</b>&nbsp;Important&nbsp;information </code> </p> <p> "Important information" is injected into the "target" field on all pages that match the regular expression <span class="codeph"> ^.*/products/.*\.html$ </span>. </p> <p>Therefore, you have the following: </p> <p> <code> https://www.mydomain.com/products/page1.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p> <code> https://www.mydomain.com/product/oldstuff.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;not&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p>In the following example: </p> <p> <code> append&amp;nbsp;title&amp;nbsp;regexp&amp;nbsp;^.*\.pdf$&amp;nbsp;Millennium&amp;nbsp;Science </code> </p> <p>The injection appends "Millennium Science" to the "title" content of all pages that end with a ".pdf" filename extension. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> URL </span> </p> </td> 
   <td colname="col2"> <p>A URL is required and specifies which documents are injected. </p> <p>The URL is any one of the following: </p> <p> 
     <ul id="ul_C5C74F6D5EA943B293742989EB822751"> 
      <li id="li_382392DB778D4E14BFFC96D35A861951"> A full path, as in https://www.mydomain.com/products.html </li> 
      <li id="li_EA2BD0FB66A44CD0844613316F6174D4"> A partial path, as in https://www.mydomain.com/products </li> 
      <li id="li_D5E0D6D897C8493ABBFC65517CD4A7DB"> A URL that uses wild cards, as in https://www.mydomain.com/*.html </li> 
     </ul> </p> <p>The URL value must not have any space characters in it. If the <span class="codeph"> regexp </span> option is used, the URL is treated like a regular expression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> value </span> </p> </td> 
   <td colname="col2"> <p>A value is required and is used to either replace or add to existing field content. You can specify multiple values for the same field name. For example: </p> <p>append <b>keys</b> https://www.mysite.com/travel/ <b>summer</b>, <b>beach</b>, <b>sand</b> </p> <p>append <b>keys</b> https://www.mysite.com/travel/fare/*.html <b>cheap tickets</b> </p> <p>In the above example, the words "summer, beach, sand" is appended to the "keys" field on all pages in the "/travel/" directory. The words "cheap tickets" is also appended to the "keys" field on all pages in the "/travel/fare/" directory. </p> </td> 
  </tr> 
 </tbody> 
</table>

See also [Selecting content types to crawl and index](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8). 

## Adding field injection definitions {#task_E86566FA1FF74CF68115C0ADA05172AE}

You can use [!DNL Injections] to insert content into your web pages without the need to edit the pages themselves.

You can optionally use **[!UICONTROL Test]** on the [!DNL Injections] page. You enter a test field name (for example, "title" or "body"), the original field value (for example, "Home Page"), and a test URL from your website. The resulting value is displayed for your reference. The current values are not altered during the test.

**To add field injection definitions** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**.
1. (Optional) On the [!DNL Injections] page, in the [!DNL Test Field Injections] area, enter the test field, the test original value, and test URL, and then click **[!UICONTROL Test]**.
1. In the [!DNL Field Injection Definitions] field, enter one injection definition per line.
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Attribute Loader {#concept_9EF38E98811B42CDA41996432B9AD209}

Use [!DNL Attribute Loader] to define additional input sources to augment data crawled from a website.

>[!NOTE]
>
>To use Attribute Loader, you may need to have it enabled in your account by your Adobe account representative or by Adobe Support.

You can use a data feed input source to access content that is stored in a form that is different from what is typically discovered on a website. You do this using one of the available crawl methods. Data from these sources can then be injected into data from crawled content.

After you add an Attribute Loader definition to the [!DNL Staged Attribute Loader Definitions] page, you can change any configuration setting except the Name values and Type values

The [!DNL Attribute Loader] page shows you the following information:

* The name of defined Attribute Loader configuration that you have configured and added. 
* One of the following data source types for each connector that you have added:

    * **Text** - Simple "flat" files, comma-delimited, tab-delimited, or other consistently delimited formats. 
    * **Feed** - XML feeds.

* Whether the configuration is enabled or not for the next crawl and indexing. 
* The address of the data source.

See also [How the attribute injection process works for Text and Feed...](../c-about-settings-menu/c-about-metadata-menu.md#section_E059A33D61EE4DB0972A37B8A35E9E16)

See also [About configuring multiple Attribute Loaders](../c-about-settings-menu/c-about-metadata-menu.md#section_4CC49C74EF294608A184E233F215ADFF)

See also [About the use of Preview when you add an Attribute...](../c-about-settings-menu/c-about-metadata-menu.md#section_E9CAB000A94C4D9189786C1EDB1CDB46)

## How the attribute injection process works for Text and Feed configurations in Attribute Loader {#section_E059A33D61EE4DB0972A37B8A35E9E16}

<table> 
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
   <td colname="col3"> <p>For <span class="uicontrol"> Text </span>, each newline-delimited line of text corresponds to an individual document, and is parsed using the specified delimiter, such as a comma or tab. </p> <p>For <span class="uicontrol"> Feed </span>, each document's data is extracted using a regular expression pattern in the following form: </p> <p> <code class="syntax js"> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Using <span class="uicontrol"> Map </span> on the <span class="wintitle"> Attribute Loader Add </span> page, create a cached copy of the data and then create a list of links for the crawler. The data is stored in a local cache and is populated with the configured fields. </p> <p>The parsed data is written to the local cache. </p> <p>This cache is read later to create the simple HTML documents needed by the crawler. For example, </p> <p> <code class="syntax html"> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>The <span class="codeph"> &lt;title&gt; </span> element is only generated when a mapping exists to the Title metadata field. Similarly, the <span class="codeph"> &lt;body&gt; </span> element is only generated when a mapping exists to the Body metadata field. </p> <p> <b>Important</b>: The assignment of values to the pre-defined URL meta tag is not supported. </p> <p>For all other mappings, <span class="codeph"> &lt;meta&gt; </span> tags are generated for each field that has data found in the original document. </p> <p>The fields for each document are added to the cache. For each document that is written to the cache, a link is also generated as in the following examples: </p> <p> <code class="syntax html"> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>The configuration's mapping must have one field identified as the Primary Key. This mapping forms the key that is used when data is fetched from the cache. </p> <p>The crawler recognizes the URL <span class="codeph"> index: </span> scheme prefix, which can then access the locally cached data. </p> </td> 
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

## About configuring multiple Attribute Loaders {#section_4CC49C74EF294608A184E233F215ADFF}

You can define multiple Attribute Loader configurations for any account.

When you add an Attribute Loader, you can optionally use the feature **[!UICONTROL Setup Maps]** to download a sample of your data source. The data is examined for suitability.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Attribute Loader type </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Text </p> </td> 
   <td colname="col2"> <p>Determines the delimiter value by trying tabs first, then vertical-bars ( <span class="codeph"> | </span>), and finally commas ( <span class="codeph"> , </span>). If you already specified a delimiter value before you clicked <span class="uicontrol"> Setup Maps </span>, that value is used instead. </p> <p>The best-fit scheme results in the Map fields being filled out with guesses at the appropriate Tag and Field values. Additionally, a sampling of the parsed data is displayed. Be sure to select <span class="uicontrol"> Headers in First Row </span> if you know that the file includes a header row. The setup function uses this information to better identify the resulting map entries. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Downloads the data source and performs simple XML parsing. </p> <p>The resulting XPath identifiers are displayed in the Tag rows of the Map table, and similar values in Fields. These rows only identify the available data, and do not generate the more complicated XPath definitions. However, it is still helpful because it describes the XML data and identifies Itemtag. </p> <p> <p>Note:  The Setup Maps function downloads the entire XML source to perform its analysis. If the file is large, this operation could time out. </p> </p> <p>When successful, this function identifies all possible XPath items, many of which are not desirable to use. Be sure that you examine the resulting Map definitions and remove the ones that you do not need or want. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The Setup Maps feature may not work for large XML data sets because its file parser attempts to read the entire file into memory. As a result, you could experience an out-of-memory condition. However, when the same document is processed at the time of indexing, it is not read into memory. Instead, large documents are processed “on the go,” and are not read entirely into memory first.

## About the use of Preview when you add an Attribute Loader {#section_E9CAB000A94C4D9189786C1EDB1CDB46}

Attribute Loader data is loaded prior to an Index operation.

At the time you add an Attribute Loader, you can optionally use the feature **[!UICONTROL Preview]** to validate the data, as though you were saving it. It runs a test against the configuration, but without saving the configuration to the account. The test accesses the configured data source. However, it writes the download cache to a temporary location; it does not conflict with the main cache folder that the indexing crawler uses.

Preview only processes a default of five documents as controlled by **Acct:IndexConnector-Preview-Max-Documents**. The previewed documents are displayed in source form, as they are presented to the indexing crawler. The display is similar to a “View Source" feature in a Web browser. You can navigate the documents in the preview set using standard navigation links.

Preview does not support XML configurations because such documents are processed directly and not downloaded to the cache. 

## Adding an Attribute Loader definition {#task_A735E5EF763343A9B675E1A3B09AFDBC}

Each Attribute Loader configuration defines a data source and mappings to relate the data items defined for that source to metadata fields in the index.

>[!NOTE]
>
>To use Attribute Loader, you may need to have it enabled in your account by your Adobe account representative or by Adobe Support.

Before the effects of the new and enabled definition are visible to customers, rebuild your site index.

**To add an Attribute Loader definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. On the [!DNL Stage Attribute Loader Definitions] page, click **[!UICONTROL Add New Attribute Loader]**.
1. On the [!DNL Attribute Loader Add] page, set the configuration options that you want. The options that are available depend on the **[!UICONTROL Type]** that you selected.

    <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Name </p> </td> 
      <td colname="col2"> <p>The unique name of the Attribute Loader configuration. You can use alphanumeric characters. The characters "_" and "-" are also allowed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Type </p> </td> 
      <td colname="col2"> <p>The source of your data. The data source type that you select affects the resulting options that are available on the <span class="wintitle"> Attribute Loader Add </span> page. You can choose from the following: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Text </span> <p>Simple flat text files, comma-delimited, tab-delimited, or other consistently delimited formats. Each newline-delimited line of text corresponds to an individual document, and is parsed using the specified delimiter. </p> <p>You can map each value, or column, to a metadata field, referenced by the column number, starting at 1 (one). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Downloads a primary XML document that contains multiple "rows" of information. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Data source type: Text</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Enabled </p> </td> 
      <td colname="col2"> <p>Turns the configuration "on" for use. Or, you can turn "off" the configuration to prevent if from being used. </p> <p> <b>Note</b>: Disabled Attribute Loader configurations are ignored. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Host Address </p> </td> 
      <td colname="col2"> <p>Specifies the address of the server host where your data is located. </p> <p>If desired, you can specify a full URI (Uniform Resource Identifier) path to the data source document as in the following examples: </p> <p> <code otherprops="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>or </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>The URI is broken down into the appropriate entries for the Host Address, File Path, Protocol, and, optionally, Username, and Password fields </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>File Path </p> </td> 
      <td colname="col2"> <p>Specifies the path to the simple flat text file, comma-delimited, tab-delimited, or other consistently delimited format file. </p> <p>The path is relative to the root of the host address. </p> </td> 
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
      <td colname="col1"> <p>Stale Days </p> </td> 
      <td colname="col2"> <p>Sets the minimum interval between downloads of Attribute Loader data. Index-triggered downloads that occur within the download refresh frequency interval are ignored. When you set this value to the default of 1, Attribute Loader data does not download more than once within a 24 hour period. All Search indexes that occur within the download refresh frequency interval use the last data set that was downloaded. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Map </p> </td> 
      <td colname="col2"> <p>Specifies column-to-metadata mappings, using column numbers. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Column </span> <p> Specifies a column number, with the first column being 1 (one). To add new map rows for each column, under <span class="wintitle"> Action </span>, click <span class="uicontrol"> + </span>. </p> <p>You do not need to reference each column in the data source. Instead, you can choose to skip values. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Field </span> <p>Defines the name attribute value that is used for each generated &lt;meta&gt; tag. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadata? </span> <p>Causes <span class="uicontrol"> Field </span> to become a drop-down list from which you can select defined metadata fields for the current account. </p> <p>The <span class="uicontrol"> Field </span> value can be an undefined metadata field, if desired. An undefined metadata field is sometimes useful to create content used by a <span class="wintitle"> Filtering Script </span>. </p> <p>See <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> About Filtering Script </a>. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Primary Key? </span> <p>Only one field is identified as the primary key. This field will be used as the "foreign key" to match the Attribute Loader data with the corresponding document in the index. </p> </li> 
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
      <td colname="col2"> <p>Turns the configuration "on" for use. Or, you can turn "off" the configuration to prevent if from being used. </p> <p> <b>Note</b>: Disabled Attribute Loader configurations are ignored. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Host Address </p> </td> 
      <td colname="col2"> <p>Specifies the address of the server host where your data is located. </p> <p>If desired, you can specify a full URI (Uniform Resource Identifier) path to the data source document as in the following examples: </p> <p> <code class="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>or </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>The URI is broken down into the appropriate entries for the Host Address, File Path, Protocol, and, optionally, Username, and Password fields. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>File Path </p> </td> 
      <td colname="col2"> <p>Specifies the path to the primary XML document that contains multiple "rows" of information. </p> <p>The path is relative to the root of the host address. </p> </td> 
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
      <td colname="col2"> <p>Identifies the XML element that you can use to identify individual XML lines in the data source file that you specified. </p> <p>For example, in the following Feed fragment of an Adobe XML document, the Itemtag value is <span class="codeph"> record </span>: </p> <p> <code class="syntax xml"> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; 
        &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
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
        </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Cross-Reference Field Name </p> </td> 
      <td colname="col2"> <p>Specifies a metadata field whose values are used as look-up "keys" into the Attribute Loader configuration's data. If no value is selected (<b>--None--</b>), this configuration's data is not available for use in Ranking calculations (<b>Rules</b> &gt; <b>Ranking Rules</b> &gt; <b>Edit Rules</b>). When you select a value, this field's values are used to cross-reference site search/merchandising documents with this configuration's data. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Stale Days </p> </td> 
      <td colname="col2"> <p>Sets the minimum interval between downloads of Attribute Loader data. Index-triggered downloads that occur within the download refresh frequency interval are ignored. When you set this value to the default of 1, Attribute Loader data does not download more than once within a 24 hour period. All Search indexes that occur within the download refresh frequency interval use the last data set that was downloaded. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Map </p> </td> 
      <td colname="col2"> <p>Lets you specify XML-element-to-metadata mappings, using XPath expressions. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tag </span> <p>Specifies an XPath representation of the parsed XML data. Using the example Adobe XML document above, under the option Itemtag, it could be mapped using the following syntax: </p> <p> <code class="syntax xml"> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>The above syntax translates as the following: </p> <p> 
        <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
        <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code class="syntax xml"> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>The <span class="codeph"> displayurl </span> attribute of the <span class="codeph"> record </span> element maps to the metadata field <span class="codeph"> page-url </span>. </p> </li> 
        <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code class="syntax xml"> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>The <span class="codeph"> content </span> attribute of any <span class="codeph"> meta </span> element that is contained inside a <span class="codeph"> metadata </span> element, that is contained inside a <span class="codeph"> record </span> element, whose name attribute is <span class="codeph"> title </span>, maps to the metadata field <span class="codeph"> title </span>. </p> </li> 
        <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>The <span class="codeph"> content </span> attribute of any <span class="codeph"> meta </span> element that is contained inside a <span class="codeph"> metadata </span> element, that is contained inside the <span class="codeph"> record </span> element, whose name attribute is <span class="codeph"> description </span>, maps to the metadata field <span class="codeph"> desc </span>. </p> </li> 
        <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>The <span class="codeph"> content </span> attribute of any <span class="codeph"> meta </span> element that is contained within a <span class="codeph"> metadata </span> element, that is contained within the <span class="codeph"> record </span> element, whose name attribute is <span class="codeph"> description </span>, maps to the metadata field <span class="codeph"> body </span>. </p> </li> 
        </ul> </p> <p>XPath is a relatively complicated notation. More information is available at the following location: </p> <p>See <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Field </span> <p>Defines the name attribute value that is used for each generated <span class="codeph"> &lt;meta&gt; </span> tag. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadata? </span> <p>Causes <span class="uicontrol"> Field </span> to become a drop-down list from which you can select defined metadata fields for the current account. </p> <p>The <span class="uicontrol"> Field </span> value can be an undefined metadata field, if desired. An undefined metadata field is sometimes useful to create content used by <span class="wintitle"> Filtering Script </span>. </p> <p>See <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> About Filtering Script </a>. </p> <p>When Attribute Loader processes XML documents with multiple hits on any map field, the multiple values are concatenated into a single value in the resulting cached document. By default, these values are combined using a comma delimiter. However, suppose that the corresponding <span class="wintitle"> Field </span> value is a defined metadata field. In addition, that field has the <span class="wintitle"> Allow Lists </span> attribute set. In this case, the field's List Delimiters value, which is the first delimiter defined, is used in the concatenation. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Primary Key? </span> <p>Only one field is identified as the primary key. This field will be used as the "foreign key" to match the Attribute Loader data with the corresponding document in the index. </p> </li> 
      <li id="li_80D6AF130FCE40AC972FE4B605B86BF6"> <span class="uicontrol"> Strip HTML? </span> <p>When this option is checked, any HTML tags found in this field's data is removed. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Action </span> <p>Lets you add rows to the map or remove rows from the map. The order of the rows is not important. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Optional) Click **[!UICONTROL Setup Maps]** to download a sample of your data source. The data is examined for suitability.
1. Click **[!UICONTROL Add]** to add the configuration to the [!DNL Attribute Loader Definitions] page.
1. On the [!DNL Attribute Loader Definitions] page, click **[!UICONTROL rebuild your staged site index]**.
1. (Optional) On the [!DNL Attribute Loader Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing an Attribute Loader definition {#task_AA2D1B2BCAFA44A6A0C59A0318274E80}

You can edit an existing Attribute Loader that you have defined.

>[!NOTE]
>
>To use Attribute Loader, you may need to have it enabled in your account by your Adobe account representative or by Adobe Support.

Not all Attribute Loader options are available for you to change, such as the Attribute Loader Name or Type from the [!DNL Type] drop-down list.

**To edit an Attribute Loader definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. On the [!DNL Attribute Loader] page, under the [!DNL Actions] column heading, click **[!UICONTROL Edit]** for an Attribute Loader definition name whose settings you want to change.
1. On the [!DNL Attribute Loader Edit] page, set the options you want.

   See the table of options under [Adding an Attribute Loader definition](../c-about-settings-menu/c-about-metadata-menu.md#task_A735E5EF763343A9B675E1A3B09AFDBC). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) On the [!DNL Attribute Loader Definitions] page, click **[!UICONTROL rebuild your staged site index]**.
1. (Optional) On the [!DNL Attribute Loader Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Copying an Attribute Loader definition {#task_9B40D5ECFC81411E9480F62A0FD5F2E0}

You can copy an existing Attribute Loader definition to use as the basis for a new Attribute Loader that you want to create.

>[!NOTE]
>
>To use Attribute Loader, you may need to have it enabled in your account by your Adobe account representative or by Adobe Support.

When copying an Attribute Loader definition, the copied definition is disabled by default. To enable or "turn on" the definition, you must edit it from the [!DNL Attribute Loader Edit] page, and select **[!UICONTROL Enable]**.

See [Editing an Attribute Loader definition](../c-about-settings-menu/c-about-metadata-menu.md#task_AA2D1B2BCAFA44A6A0C59A0318274E80).

**To copy an Attribute Loader definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. On the [!DNL Attribute Loader] page, under the [!DNL Actions] column heading, click **[!UICONTROL Copy]** for an Attribute Loader definition name whose settings you want to duplicate.
1. On the [!DNL Attribute Loader Copy] page, enter the new name of the definition.
1. Click **[!UICONTROL Copy]**.
1. (Optional) On the [!DNL Attribute Loader Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Renaming an Attribute Loader definition {#task_58D5DFD7EBC04111BCB91118E4440DB4}

You can change the name of an existing Attribute Loader definition.

>[!NOTE]
>
>To use Attribute Loader, you may need to have it enabled in your account by your Adobe account representative or by Adobe Support.

**To rename an Attribute Loader definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. On the [!DNL Attribute Loader] page, under the [!DNL Actions] column heading, click **[!UICONTROL Rename]** for Attribute Loader definition name that you want to change.
1. On the [!DNL Attribute Loader Rename] page, enter the new name of the definition in the [!DNL Name] field.
1. Click **[!UICONTROL Rename]**.
1. (Optional) On the [!DNL Attribute Loader Definitions] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Loading Attribute Loader data {#task_2F3C55189B0A4049AB2113F2291CC181}

You can download the configured Attribute Loader data into site search/merchandising.

The [!DNL Data Load] page shows the following information about the status of your last Attribute Loader Data Load operation:  

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Status field </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Indicates the success or failure of the last data load attempt. Or, it displays the status of a data load operation that is already in progress. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Start Time </p> </td> 
   <td colname="col2"> <p>Displays the date and time that the last data load operation started. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stop Time </p> </td> 
   <td colname="col2"> <p>Displays the completion date and time of the last data load operation. Or, it indicates the current data load operation is still in progress. </p> </td> 
  </tr> 
 </tbody> 
</table>

**To load Attribute Loader data** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. On the [!DNL Attribute Loader Definitions] page, click **[!UICONTROL Load Attribute Loader Data]**.
1. On the **[!UICONTROL Attribute Loader Data Load]** page, do one of the following:

    * Click **[!UICONTROL Start Load]** to start the load operation.

      During a data load operation, the**Progress** row provides information on its progress.

    * Click **[!UICONTROL Stop Load]** to stop the load operation.

1. Click **[!UICONTROL Close]** to return to the [!DNL Attribute Loader Definitions] page.

## Previewing Attribute Loader data {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

You can use Preview to view your most recently loaded Attribute Loader data.

The Row column in the table shows the number for each row of data, indicating the original order that the Attribute Loader values were loaded.

The remaining columns show the values that are associated with each entry.

If the table is empty, it means that you have not loaded any Attribute Loader data yet. You can close the [!DNL Attribute Loader Data Preview] page, and then load Attribute Loader data.

See [Loading Attribute Loader data](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**To preview Attribute Loader data** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. On the [!DNL Attribute Loader Definitions] page, under the [!DNL Actions] column, click **[!UICONTROL Preview]** for the configuration whose downloaded data you want to view.
1. On the [!DNL Attribute Loader Data Preview] page, use the navigation and viewing options at the top and bottom of the page to view the data.

   Click any column heading in the table to sort the data in ascending or descending order. 
1. Do any of the following:

    * Click **[!UICONTROL Download to Desktop]** to download and save the table as a .xlt file. 
    * Close the page when you are finish previewing the Attribute Loader data and return to the previously viewed page.

## Viewing the settings of an Attribute Loader definition {#task_EA99A9694FE948ADA82C1DBA0667851B}

You can review the configuration settings of an existing Attribute Loader definition.

After an Attribute Loader definition is added to the [!DNL Attribute Loader Definitions] page, you cannot change its Type setting. Instead, you must delete the definition and then add a new one.

>[!NOTE]
>
>To use Attribute Loader, you may need to have it enabled in your account by your Adobe account representative or by Adobe Support.

**To view the settings of an Attribute Loader definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. On the [!DNL Attribute Loader] page, under the [!DNL Actions] column heading, click **[!UICONTROL Edit]** for an Attribute Loader definition name whose settings you want to review or edit.

## Viewing the log from the most recent Attribute Loader data load {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

You can use [!DNL View Log] to examine the Attribute Loader data log file of the most recent download process. You can also use the log view to monitor a running download.

See [Loading Attribute Loader data](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**To view the log from the most recent Attribute Loader data load** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. On the [!DNL Attribute Loader Definitions] page, click **[!UICONTROL View Log]**. Log page,
1. On the [!DNL Attribute Loader Data Log] page, use the navigation and viewing options at the top and bottom of the page to view the log information.
1. When you are finished, close the page to return to the [!DNL Attribute Loader Definitions] page.

## Deleting an Attribute Loader definition {#task_E8980F66888B476E98C228C1D307EDF8}

You can delete an existing Attribute Loader definition that you no longer need or use.

>[!NOTE]
>
>To use Attribute Loader, you may need to have it enabled in your account by your Adobe account representative or by Adobe Support.

**To delete an Attribute Loader definition** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. On the [!DNL Attribute Loader Definitions] page, under the [!DNL Actions] column heading, click **[!UICONTROL Delete]** for the Attribute Loader definition name you want to remove.
1. On the [!DNL Attribute Loader Delete] page, click **[!UICONTROL Delete]**.
