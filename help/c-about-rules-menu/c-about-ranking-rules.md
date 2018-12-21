---
description: You can use Ranking Rules to control the relative positioning or ranking of a customer's search results based on contained meta tag content and related Adobe Analytics metrics.
seo-description: You can use Ranking Rules to control the relative positioning or ranking of a customer's search results based on contained meta tag content and related Adobe Analytics metrics.
seo-title: About Ranking Rules
solution: Target
subtopic: Ranking Rules
title: About Ranking Rules
topic: Rules,Site search and merchandising
uuid: 440c12d7-4b7d-493b-95ac-3e415ee1a648

---

# About Ranking Rules{#about-ranking-rules}

You can use Ranking Rules to control the relative positioning or ranking of a customer's search results based on contained meta tag content and related Adobe Analytics metrics.

## About Ranking Rules {#concept_F555C076759B4E81B925441CFE707397}

You can use Ranking Rules to control the relative positioning or ranking of a customer's search results based on contained meta tag content and related Adobe Analytics metrics. 

You define ranking rules to affect the relative placement of the documents within your search results, based on the contents of each document. You can base ranking rules either on meta tag content, Adobe Analytics metrics (if your account is configured to work with Adobe Analytics), or Adobe Analytics HBX metrics (if your account is configured to work with Adobe Analytics HBX).

You can set web pages that contain meta tags with desired characteristics, such as a certain brand name or price, or web pages that have desirable Adobe Analytics key performance indicators, such as unique viewers, to receive a higher ranking than web pages that do not. The "desirable" characteristics are easily updated by adding or editing Ranking Rules and then re-indexing your website.

If you have more than one meta tag of type "rank" defined, you can create separate collections of rules to use in calculating the various rank fields. You can add a ranking rule group, which you can then assign to one of your defined Rank fields. Rule groups normally contain one or more rule definitions, but can also refer to other Rule groups, so you can create one or more groups of commonly used rules that are shared during the calculation of your multiple ranks.

See [Adding a ranking rule group](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

A positive rank value promotes search results towards the top; a negative rank value demotes search results towards the bottom of the search results. The normal range for ranking values is 1.0 which is the maximum promotion within the search results, while -1.0 is the maximum demotion. While you can customize this range by editing the Rank field in metadata definitions, this type of customization is usually unnecessary.

See [About Definitions](../c-about-settings-menu/c-about-metadata-menu.md#concept_AE48035C210145169BE067D396975620).

If you have defined more than one rank field under Settings > Metadata > Definitions, you have the option to create additional sets of ranking rules, one for each rank field. You can defined additional sets of ranking rules without being directly associated with a rank field. This flexibility lets you create sets of common Rules that can be shared in the calculation of one or more rank value.

**Important**: Before you can use Ranking Rules, there are several account configuration steps that you must complete.

See [Configuring ranking](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5) 

## Configuring ranking {#task_4CEBC13925B047FC95BDC217B48089C5}

Before you can use ranking rules, there are several account configuration steps that you must complete.

<!-- 

t_configuring_ranking.xml

 -->

**To configure ranking** 

1. Choose from the following:

    <table id="table_8C6D8A8DFD2B4DFDAA5DB9FCF2B94A5E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Task </p> </th> 
   <th colname="col2" class="entry"> <p>Configuration </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>To create ranking rules that are based on meta tags </p> </td> 
   <td colname="col2"> <p> 
     <ol id="ol_28ABB980143948DFA79AC4360AAB7556"> 
      <li id="li_544075CFA0964C6F8FAF7941AAA9ECCC"> On the product menu, click <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span>. </li> 
      <li id="li_F237F13B89E8425080C15D3BD697652C"> On the Definitions page, click <span class="uicontrol"> Add New Field </span>. </li> 
      <li id="li_2A839874D71D45FEA661B3D3B8BE2A86"> On the Add Field page, in the <span class="uicontrol"> Field Name </span> text field, type 
       <userinput>
         rank 
       </userinput>; in the <span class="uicontrol"> Meta Tag Name </span> text field, type 
       <userinput>
         rank 
       </userinput>; in the <span class="uicontrol"> Data Type </span> drop-down list, select <span class="uicontrol"> Rank </span>. Leave all other field options as-is. <p>See the query parameter <span class="codeph"> sp_sr </span> in <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </li> 
      <li id="li_8E91AF4BE51A4A41ABBF9680DDE0B7CE">Click <span class="uicontrol"> Add </span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>To create ranking rules that are based on Adobe Analytics metrics </p> </td> 
   <td colname="col2"> <p> 
     <ol id="ol_BE57CBC303D941778B10D855ADC93C68"> 
      <li id="li_8DF5D8F924B24ECBBD2D93C76C69D00C"> Make sure you have set up Adobe Analytics authentication from within site search/merchandising. <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42" type="task" format="dita" scope="local"> Setting up Adobe Analytics metrics authentication </a>. </p> </li> 
      <li id="li_CF7DD073FC5A432DADBD282AA8BB9920"> Select and add an available report suite. <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0" type="task" format="dita" scope="local"> Adding an Adobe Analytics Report Suite </a>. </p> </li> 
      <li id="li_9A63448577D04E028DF211D8715F943A"> Configure the list of Adobe Analytics metrics that you want to be available for the creation of new Ranking Rules. <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Editing the Adobe Analytics metrics of a Report Suite </a>. </p> </li> 
      <li id="li_1ACA3611D9B44AC394604CD89209C966"> Load the initial Adobe Analytics metrics for your website pages. <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181" type="task" format="dita" scope="local"> Loading Adobe Analytics data </a>. </p> </li> 
     </ol> </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Add one or more Ranking Rules.

   See [Adding a ranking rule](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

1. Click **[!UICONTROL regenerate your staged site index]** to perform a full-reindex of your website (from **[!UICONTROL Index]** > **[!UICONTROL Full Index]**).

   See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. Check the values in the Rank column in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** to verify that your Ranking Rules were applied correctly.

## About ranking documents by age {#topic_770815CF1B2A491F83FF765871B6F1B8}

You can rank an HTML document by its age with an exponential decay function. The rate of decay is specified with a chosen half-life constant, the amount of time that must pass before the value drops to one half of its initial value.

<!-- 

c_about_ranking_documents_by_age.xml

 -->

Age ranking is based on the following two equations:

`K = -ln(2) / H`

`RANK = e^(K * T)`

Variables `H` and `T` are inputs to this function: `H` is the desired half-life period and `T` is the document's age, expressed in seconds. `K` is the calculated half-life, and `RANK` is the exponential decay of the specified age value. The resulting value is from 0 through 1. A more recent document has a rank value closer to 1 compared to an older document. In theory, documents should never reach the value of 0, but rounding errors can cause a result to become 0.

## Requirements for using age ranking {#section_D716507D589442C6B7848892BD28F966}

* Your account should already be configured correctly for ranking. If it is not configured, see [Configuring ranking](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5). 
* The HTML document must have an HTML meta tag field that represents its birth date, or inception as a time stamp, or some other meaningful date value. 
* The special built-in function, `search_get_age_rank()`, as specified in the Add or Edit Ranking Rule pages, is used to calculate a document's age rank. The next sections describe in detail the general use of the age-ranking function. An example is also presented that demonstrates the age-ranking feature.

## Using search_get_age_rank () on the Add Ranking Rule page or the Edit Ranking Rule page {#section_34BC5276F2AB4419AD92872A397CA0AF}

Specify `search_get_age_rank()` as follows:

`search_get_age_rank( Birthdate, Half_Life, Default_Rank )`

* Birthdate - The birth date or inception date of the file must be a date formatted string in accordance to the field's date formats. This date formatted string is usually a field reference, as in `{field_name}`. 
* Half_Life - The half life is the amount of time that must pass before the value drops to one half of its initial value. This value is expressed in the number of days and it is an integer or a floating point number. 
* Default_Rank - The default rank is used as a safety net in case the birth date is invalid or the date is in the future. You cannot use this default value if its associated metadata field has a valid default value too. The value here is a floating point number or an integer. See below for suggestions if you run into problems with which default value is being used.

See [Adding a ranking rule](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

See [Editing a ranking rule](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275).

**Example**

In the following example,

`search_get_age_rank({birthdate},28,0.20)`

the date contained in the document's `birthdate` field is passed in as the time-stamp. The half life is 28 days. The default ranking value is 0.20 if the date is invalid.

See the options table in [Adding a ranking rule](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

In the Values/Ranks section of the Add Ranking Rule page or the Edit Ranking Rule page, you can only use `search_get_age_rank` with custom-made rules. Therefore, be sure that you choose **Custom** from the Values/Ranks drop-down list. When the rule uses the age-ranking function, no spaces are allowed in the values part of the rule. Be sure that there are no spaces in the function arguments or in between them. And, there are no spaces between any mathematical or conditional operators.

The following is an example of a values/ranks rule—a rule associated with a text field:

`regexp .* search_get_age_rank({other_field},365,0.20)`

This example assumes that `other_field` contains a date value. If this field is not itself a date-type field, this value is interpreted using the date formats associated with the pre-defined Date field. Otherwise, this field's date formats are used. This values/ranks entry is used whenever the document's field, that the Rule's Data Source identifies, is non-empty, and the function's return value (from 0 through 1) is the assigned rank.

For a Rule associated with a Numeric field, specifically a Date field:

`9999999999 search_get_age_rank({other_field},365,0.20)`

As each document is processed, the value in `other_field` is converted to the Unix "epoch" form, using the field's date format definitions. This value is used in the `search_get_age_rank()` call. As every "epoch" value is less than 9999999999 (for now at least), the Rule simply supplies the function's return value (from 0 through 1) as the rank.

In both of the preceding examples, it is typical that the Rule's Data Source is the same field that is used in the `search_get_age_rank()` function - `other_field` in this case.

## An example of integrating age ranking into ranking rules {#section_A86D909687CC45E19D4EA7A4A9283F28}

The following is an example of how you can integrate age ranking into ranking rules. The example also shows you the raw results from the age-ranking function and the results from the ranking rules. The example assumes the following:

* The web pages that are crawled have HTML meta tag named "birthdate". The content of this tag is a time-stamp related to the document. 
* The metadata definitions have a defined metatag field for the birthdate tag. This field is set to type "date."

**Ranking rules**

See [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

Now you add a new ranking rule. The rule is defined to use the "birthdate" field on the document. A new ranking rule is added with the following properties set:

* Data Source Type: Meta Tag 
* Data Source Name: birthdate 
* Weights/Conditions: 10 - Maximum Importance 
* Values/Ranks: 9999999999 search_get_age_rank({birthdate},14,0.10) 
* Default Rank: -1

The rule does several things. The weight of the rule is set to 10. The rank value is simply the result of the age-rank function, a value from 0 through 1. You cannot use spaces with `search_get_age_rank()`. Also, notice that the field "birthdate" is enclosed in braces. Finally, when you save this rule, the commas in the Values/Ranks definition are replaced with `#` characters; this behavior is normal.

**Viewing the results**

Use the Data View feature to quickly see the results of the age-rank function. Add the appropriate Metadata fields. In the example, `age_val` and `myrank` are the two Metadata fields that should be added to the Data View. The `myrank` field shows how age ranking affects the ranking values. The `age_val` field shows the raw output of the exponential-decay function for that document.

## Default values {#section_CB109EF78F914E92955D512ACFC3310E}

The following are three default values involved with the function `search_get_age_rank()`:

* The default value that you can enter into the `search_get_age_rank()` function itself. 
* The default rank value from the Ranking rule. 
* The default value from the Metadata definition.

Depending on where the failure occurs, you may get different default values.

For example, the default value from the Metadata definition should never happen if Ranking and Filtering is properly implemented. This default value is the last resort value when no valid or known content for that Metadata field exists. The default value from the ranking rules may appear when `search_get_age_rank()` is referencing its own associated tag and the tag is missing in the document. In this case, this rule goes straight to the rule's default value. If the age-ranking function references another ranking rule's tag, it is possible that the default value passed into that age-ranking function is used if the referenced tag is missing or invalid. 

## Adding a ranking rule {#task_A132789FD4E5423DAD090DCDA7311E8A}

You can add [!DNL Ranking Rules] to affect the relative placement of the web pages within your Search results, based on the contents of each web page.

<!-- 

t_adding_a_ranking_rule.xml

 -->

See [Configuring ranking](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**To add a ranking rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Optional) If you have created a rules group and added rules to the group, on the [!DNL Define Ranking Rules] page, in the **[!UICONTROL Select Rule Group]** drop-down list, select a rule group that contains the rules you want to edit.

   See [Adding a ranking rule group](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8). 
1. On the [!DNL Define Ranking Rules] page, click **[!UICONTROL Add Rule]** to add a new Ranking Rule, or to add a reference to a Rule set.
1. On the [!DNL Add Ranking Rule] page, set the options you want. Fields that are marked with an asterisk (&#42;) are required.

   <!-- 

r_ranking_rule_options.xml

 -->

   The Data Source Type that you select affects the choices that are available on the [!DNL Data Source Name] drop-down list. For example, if you selected **[!UICONTROL Meta Tag]** as the Data Source Type, the Data Source Name refers to the name of a meta tag on your website pages. If you selected **[!UICONTROL Adobe Analytics Metric (Number)]**, the Data Source Name refers to one of the Adobe Analytics metric names that you selected in a Report Suite as found on the **[!UICONTROL Edit Adobe Analytics Metrics]** page in site search/merchandising.

   See [Editing the Adobe Analytics metrics of a Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

<table id="table_F3D9BB18266B4976B687069D371D1E25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Data Source Type </p> </td> 
   <td colname="col2"> <p>Determines the characteristics of the data source that is used as the input to this ranking rule. </p> <p>Data source types that you can select from include the following: 
     <!--removed Rule Group option from bullet list below --> 
     <ul id="ul_B0A97BF0E314495985F44A642C86918D"> 
      <li id="li_4D8BDE32853540809AE78FF5FF5677A1"> <span class="uicontrol"> Meta Tag </span> <p> Bases this rule on numeric data or textual data that is stored within a named meta tag on your website pages. </p> </li> 
      <li id="li_4976C31D67254C7F81D554EC49DDBB40"> <span class="uicontrol"> Adobe Analytics Metric (Number) </span> <p>Bases this rule on a numeric Adobe Analytics metric that is associated with your site pages. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data Source Name </p> </td> 
   <td colname="col2"> <p>If you chose <span class="uicontrol"> Meta Tag </span> as the Data Source Type, this is the name of a meta tag that is found within the pages of your website. The names in the drop-down menu come from the list of defined metadata values that were configured in Settings &gt; Metadata &gt; Definitions. </p> <p>See <a scope="local" href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita"> Adding a new meta tag field </a>. </p> <p>If you chose Adobe Analytics Metric (Number) as the Data Source Type, this is the name of a Adobe Analytics metric. The names in the drop-down menu, come from the list defined available Adobe Analytics metrics that were configured in Settings &gt; Adobe Analytics &gt; Metrics &gt; Edit. </p> <p>See <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Editing the Adobe Analytics metrics of a Report Suite </a>. </p> <p>If the Adobe Analytics metric name that you selected is not already defined in <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span>, a text field and an Add button are displayed. Enter the name of the Metadata Field Name (the metadata field name cannot exceed 20 characters), and then click <span class="uicontrol"> Add </span>. </p> <p>When pages are encountered with multiple Adobe Analytics keys, as with a product page displaying multiple products, Composite Scheme specifies how to deal with the multiple Adobe Analytics metric values associated with that page. Select one of the following: </p> <p> 
     <ul id="ul_D6E51748BB3949048A37C1895F2C0A58"> 
      <li id="li_04F00F382A264C96A519B0D975E25E94"> <span class="uicontrol"> Sum </span> <p>Returns the sum of the metric values. </p> </li> 
      <li id="li_FA44219B663F4CC197BD3A094EB84396"> <span class="uicontrol"> Average </span> <p>Returns the average of the values (the sum divided by the number of values). </p> </li> 
      <li id="li_F0EAAE1EA1754FFEB30F611E5550097B"> <span class="uicontrol"> Maximum </span> <p>Returns the largest of the values. </p> </li> 
      <li id="li_38E3E3F3D9AF4C57803B84B60223FB9D"> <span class="uicontrol"> First </span> <p>Returns the value corresponding to the first key. </p> </li> 
      <li id="li_4AEE470CE6BB4D899E975915EC226624"> <span class="uicontrol"> Last </span> <p>Return the value corresponding to the last key. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Weights/Conditions </p> </td> 
   <td colname="col2"> <p>Contains either a simple, single rule weight number, or a paired list of rules weight numbers and test conditions. </p> <p>A rule weight number is a value from 1-10 that indicates how important this ranking rule is relative to the other ranking rules in determining the overall rank of a document. A higher rule weight indicates higher importance. A weight of zero (0) ignores the rule. </p> <p>Choose <span class="uicontrol"> Custom </span> from the drop-down list to customize the rule weight for various pages by defining a list of rule weight/test conditions pairs. Test conditions are fragments of Perl that are used to test Data Source Values, or global variables that are defined within your custom filter script (for example, price, brand, season, or page views as in the following example). If a test condition evaluates to "true," the associated rule weight value is applied. If a test condition evaluates to "false,", the next condition in the list is evaluated. 
     <codeblock>
       0&nbsp;({price}&nbsp;&gt;&nbsp;50.00)&nbsp;&amp;&amp;&nbsp;({brand}=~/Kuhl/) 
      5&nbsp;{season}&nbsp;=~&nbsp;/Fall/ 
      10&nbsp;{pageviews}&nbsp;&gt;&nbsp;100000 
      5 
     </codeblock>In the custom created weight/condition example above, the rule weight 0 is applied if the first test condition evaluates to "true." That is, the price contains a value greater than 50 and the brand contains "Kuhl"). If the first test condition evaluates to "false," the next condition is evaluated. If none of the previous conditions are met, the rule weight 5 is assigned. </p> <p>You should always provide a rule weight with no condition at the end of the list. If you do not do this, the rule gets a weight of 0 in the case where none of the condition tests evaluate to "true." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Values/Ranks </p> </td> 
   <td colname="col2"> <p>Consists of either one of the built-in ranking functions, or possible Data Source content along with desired ranks. </p> <p>If you chose <span class="uicontrol"> Adobe Analytics Metric (Number) </span> as the Data Source Type, you are presented with a drop-down list with the following options: 
     <ul id="ul_104906B6AA8547BAB6979AA37C4FAB90"> 
      <li id="li_7656A2855A054DB8B64E90FE501517AA"> <span class="uicontrol"> Auto-Rank by Order (default) </span> <p>Calculates a rank that is based on the document's relative position, according to its Adobe Analytics Metric. For example, the closer the document's position to the top-ranked document, the higher its rank. </p> </li> 
      <li id="li_1A7D60EA6965434AA6D39B215C158306"> <span class="uicontrol"> Auto-Rank by Value </span> <p>Calculates a rank based on the document's relative value, according to its Adobe Analytics Metric. For example, the closer the document's value to the top-ranked document's value, the higher its rank. </p> </li> 
      <li id="li_457DE44D6ADA40619DC77220BF12318E"> <span class="uicontrol"> Custom </span> <p>Specifies custom settings. For example, a Data Source with the name of "brand" might contain the brand name for a particular product. You can specify the relative importance of each brand by listing it along with its rank. </p> </li> 
     </ul> </p> <p>The rank values returned from the Auto-Rank calculations are in the range 0.0 (lowest) to 1.0 (highest). They are not adjusted according to the ranges that are defined for the Rank field under Settings &gt; Metadata &gt; Definitions. </p> <p>In the following example, if the brand Data Source for a particular search result exactly matches "DKNY," the applied rank for that result is 0.5. Otherwise, if the brand is "Levis," the applied rank is 0.1. The Data Source content must match the set value. In other words, If the Data Source content is "Levis Corp.", it will not match the value "Levis". Case is ignored, so "DKNY" matches "dkny" and "Dkny". 
     <codeblock>
       DKNY&nbsp;0.5 
      Levis&nbsp;0.1 
      Lee&nbsp;0.2 
     </codeblock> </p> <p>As a more advanced option, you can specify values as regular expressions. For example, suppose some of your site pages contain a brand value of "Levis" and other site pages contain a brand value of "Levis jeans." You can use a regular expression specified with the keyword 
     <userinput>
       regexp 
     </userinput>. </p> <p>See <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Regular Expressions </a>. </p> <p>In the following example, a search result document containing brand content "Levis jeans" is assigned a rank of 0.1. As with standard comparison, case is ignored for regular expressions. 
     <codeblock>
       DKNY&nbsp;0.5 
      regexp&nbsp;Levis.*&nbsp;0.1 
      Lee&nbsp;0.2 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default Rank </p> </td> 
   <td colname="col2"> <p> Specifies the rank to apply for search result documents that do not match any of the specified values. In the above example, a search results document with a "brand" Data Source containing "the gap" is assigned the default rank value because "the gap" does not match any of the defined values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Notes </p> </td> 
   <td colname="col2"> <p>Add information that pertains to the ranking rule definition or the rule group definition that you created. </p> </td> 
  </tr> 
 </tbody> 
</table>

   The range of valid rank values is normally -1.0 to 1.0 as in the following:

* -1.0 is "Minimum Rank (display lower in the search results)." 
* 0.0 is "Neutral rank (do not change search results order)." 
* 1.0 is "Maximum rank (display higher in the search results."

   Defined ranks should be within the same range for every rule. The rank ranges must also match the ranges that are defined for the Rank field under **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   See [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

   See also [Editing a ranking rule](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275). 
1. Click **[!UICONTROL Add]**.
1. To preview the results of the rule addition, click **[!UICONTROL regenerate your staged site index]** to rebuild your staged website index.

   See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB). 
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a ranking rule {#task_5EBF55A43D6545FEA46BAE5E586FA275}

You can edit an existing ranking rule that you have already added.

<!-- 

t_editing_a_ranking_rule.xml

 -->

See [Configuring ranking](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**To edit a ranking rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Optional) If you have created a rules group and added any rules to the group, on the **[!UICONTROL Define Ranking Rules]** page, in the **[!UICONTROL Select Rule Group]** drop-down list, select a rule group that contains the rules you want to edit.

   See [Adding a ranking rule group](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8). 
1. In the table, under the **[!UICONTROL Actions]** column header, click **[!UICONTROL Edit]** for the data source name you want to change.
1. On the [!DNL Edit Ranking Rule] page, set the options that you want. Fields that are marked with an asterisk (&#42;) are required.

   See the table of options under [Adding a ranking rule](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A). 
1. Click **[!UICONTROL Save Changes]**.
1. Rebuild your staged website index to preview the results of the rule edit.

   See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB). 
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a ranking rule {#task_742A3BCC2A6E4164BE84CC7408807EBB}

You can delete ranking rules that you no longer need to use.

<!-- 

t_deleting_a_ranking_rule.xml

 -->

See [Configuring ranking](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

See [Adding a ranking rule group](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**To delete a ranking rule** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Optional) If you have created a rules group and added any rules to the group, on the [!DNL Define Ranking Rules] page, in the **[!UICONTROL Select Rule Group]** drop-down list, select a rule group that contains rules that you want to delete.
1. In the table, under the **[!UICONTROL Actions]** column header, click **[!UICONTROL Delete]** for the data source name you want to change.
1. On the [!DNL Delete Ranking Rule] page, click **[!UICONTROL Delete]**.

   You are returned to the [!DNL Define Ranking Rules] page. 
1. Rebuild your staged website index to preview the results of the rule deletion.

   See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB). 
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Adding a ranking rule group {#task_B65081B3CC9E4330A7FEE77B7BCD36C8}

If you have defined more than one meta tag of type "rank", you can create separate collections of rules to use in calculating the various rank fields. You can add a ranking rule group, which you can then assign to one of your defined Rank fields.

<!-- 

t_adding_a_ranking_rule_group.xml

 -->

Rule groups usually contain one or more rules that you have added. However, Rule groups can also refer to other Rule groups. For example, you can create one or more rules groups and then add commonly used rules to each one. Those rules are then shared during the calculation of your multiple ranks.

See [Editing a ranking rule group](../c-about-rules-menu/c-about-ranking-rules.md#task_D3EC0437E47144BC9E754FEF99C725E5).

See [Deleting a ranking rule group](../c-about-rules-menu/c-about-ranking-rules.md#task_BE5BE01F377843BEA9846E094A07F2EA).

See [Reviewing ranking rule groups](../c-about-rules-menu/c-about-ranking-rules.md#task_5694459D050C4254A25186038CD66B6E).

**To add a ranking rule group** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. On the [!DNL Define Ranking Rules] page, to the right of the **[!UICONTROL Select Rule Group]** drop-down list, click **[!UICONTROL Add]**.
1. On the [!DNL Add Ranking Rule Group] page, in the **[!UICONTROL Rule Group Name]** field, type a unique name for the new rule group.
1. In the **[!UICONTROL Rank Field Name]** drop-down list, select a rank metadata field name that you want to associate with the new rule group. Select **[!UICONTROL None]** if you do not want to assign a rank.

   The list of rank field names comes from metadata definitions that were added in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   See the table of options in [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5). 
1. Click **[!UICONTROL Add]**.
1. Rebuild your staged website index to preview the results of the rule addition.

   See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB). 
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a ranking rule group {#task_D3EC0437E47144BC9E754FEF99C725E5}

You can edit the settings of an existing ranking rule group.

<!-- 

t_editing_a_ranking_rule_group.xml

 -->

See [Adding a ranking rule group](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**To edit a ranking rule group** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. On the [!DNL Define Ranking Rules] page, to the right of the **[!UICONTROL Select Rule Group]** drop-down list, click **[!UICONTROL Edit]**.
1. On the [!DNL Edit Ranking Rule Group] page, in the **[!UICONTROL Rule Group Name]** field, type a unique name for the rule group.
1. In the **[!UICONTROL Rank Field Name]** drop-down list, select a rank metadata field name that you want to associate with the rule group. Select **[!UICONTROL None]** if you do not want to assign a rank.

   The list of rank field names comes from metadata definitions that were added in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   See the table of options in [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5). 
1. Click **[!UICONTROL Save Changes]**.
1. Rebuild your staged website index to preview the results of the rule addition.

   See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB). 
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a ranking rule group {#task_BE5BE01F377843BEA9846E094A07F2EA}

You can delete a Ranking Rule Group that you no longer need or use. When you delete a group, any Rules that were added to the group, are also deleted. You cannot delete the default "Ranking Rules" group.

<!-- 

t_deleting_a_ranking_rule_group.xml

 -->

The contents of any Rule Groups that are contained in the delete group are not deleted; only the references to these groups are removed.

Be sure you reindex your website so that the change is properly reflected in the search results.

See [Adding a ranking rule group](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**To delete a ranking rule group** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. On the [!DNL Define Ranking Rules] page, in the **[!UICONTROL Select Rule Group]** drop-down list, select a group that you want to delete.
1. To the right of the **[!UICONTROL Select Rule Group]** drop-down list, click **[!UICONTROL Delete]**.
1. On the [!DNL Delete Ranking Rule Group] page, click **[!UICONTROL Delete]**.
1. Rebuild your staged website index to preview the results of the rule addition.

   See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB). 
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Reviewing ranking rule groups {#task_5694459D050C4254A25186038CD66B6E}

You can use Ranking Rule Groups Overview to see each groups Rank Field name, and associated data source and weighting.

<!-- 

t_reviewing_ranking_rule_groups.xml

 -->

See [Adding a ranking rule group](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**To review ranking rule groups** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. On the [!DNL Define Ranking Rules] page, to the right of the **[!UICONTROL Select Rule Group]** drop-down list, click **[!UICONTROL Overview]**.
1. On the [!DNL Ranking Rule Groups Overview] page, click **[!UICONTROL Close]** to return to the [!DNL Define Ranking Rules] page.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testing ranking rules {#task_56F64EE7ED5B42E481F0990A9DD98ADB}

You can provide a suitable URL test the Ranking Rule definitions that you have set up. The metrics used in the calculations are displayed, along with the calculated Rank value.

<!-- 

t_testing_ranking_rules.xml

 -->

See [About Ranking Rules](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

**To test ranking rules** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. On the [!DNL Define Ranking Rules] page, in the **[!UICONTROL Test URL]** area, type the URL to a web page that is on your website.
1. Click **[!UICONTROL Test]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Adjusting the weight associated with ranking rules {#task_3CB6FC92A66F4D99874A42D55825DB64}

You can change the relative contributions of your individual Ranking Rules, and the contribution of Ranking to the final search results.

<!-- 

t_adjusting_the_weight_associated_with_ranking_rules.xml

 -->

When Ranking is not defined, the search results are 100% on the **[!UICONTROL Natural Relevance]** side of the Rules & Relevance slider bar on the **[!UICONTROL Adjust Ranking Weights]** page. This balance simply means that the search results are ordered based solely on search terms.

When Ranking is defined, the associated Rank metadata field is assigned a Relevance value, ranging from 1-10. A value of 1 means that the calculated Rank makes up 10% of the search result ordering, and Natural Relevance the remaining 90%.

If you have more than one Rule defined in a Rule group, each Rule's Weight value determines how much that Rule's result contributes to the total calculated Rank. For example, suppose you have a Natural Relevance of 80%, meaning that the associated Rank field's relevance is 2. You also have defined two Rules: one with a weight of 3, and the second with a weight of 7. In such case, the first Rule's contribution to the final result is 6% ((3 / (3+7)) &#42; 20%). The second Rule's contribution to the final result is 14% ((7 / (3+7)) &#42; 20%).

**To adjust the weight associated with ranking rules** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Adjust Weights]**.
1. On the [!DNL Adjust Ranking Weights] page, in the **[!UICONTROL Select Rule Group]** drop-down list, select a group whose ranking weights you want to adjust.
1. Drag the sliders to change the corresponding contribution values.

   The pie chart reflects your changes graphically. 
1. Click **[!UICONTROL Save Changes]**.
1. Rebuild your staged website index to preview the results of the rule addition.

   See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB). 
1. (Optional) Do one of the following:

    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

