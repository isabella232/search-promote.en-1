---
description: You can configure various areas of Auto-Complete to control the generation of the auto-complete enabled search form, and the file autocomplete_data.js, which is included as a part of the auto-complete enabled search form.
seo-description: You can configure various areas of Auto-Complete to control the generation of the auto-complete enabled search form, and the file autocomplete_data.js, which is included as a part of the auto-complete enabled search form.
seo-title: About Auto-Complete
solution: Target
subtopic: Auto-Complete
title: About Auto-Complete
topic: Design,Site search and merchandising
uuid: 3dfdd14d-2044-4f01-a5bc-fcb2eb0d5068
---

# About Auto-Complete{#about-auto-complete}

You can configure various areas of Auto-Complete to control the generation of the auto-complete enabled search form, and the file autocomplete_data.js, which is included as a part of the auto-complete enabled search form.

## About Auto-Complete {#concept_093A9CD754864BA79B456FE4BEB64578}

You can configure various areas of Auto-Complete to control the generation of the auto-complete enabled search form, and the file , which is included as a part of the auto-complete enabled search form. 

The file [!DNL autocomplete_data.js] is regenerated and published to the search content network each time there are changes that the Auto-Complete Setup page has saved. 

## Configuring Auto-Complete {#task_F491F2BFC4D24A61BBDC48B9059C11BB}

You can configure and setup the options that control the generation of the auto-complete enabled search form, and the file.

<!-- 

t_configuring_auto-complete.xml

 -->

After you configure auto-complete, you can view the resulting HTML source for review. The HTML source is what you copy and paste into the pages of your website.

See [Previewing the search form as it would appear on your...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

See [Configuring Auto-Complete Word List](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4).

See [Configuring Auto-Complete CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**To configure Auto-Complete** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Setup]**.
1. On the [!DNL Auto-Complete Setup] page, set the options that you want.

<!-- 

r_auto-complete_setup_options.xml

-->

   See also [Previewing the search form as it would appear on your...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Maximum suggestions </p> </td> 
      <td colname="col2"> <p>Specifies the maximum number of items to display in the auto-complete suggestions list. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Minimum input characters </p> </td> 
      <td colname="col2"> <p>Specifies the number of characters that a customer must type into the auto-complete search form before it displays suggestions. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximum cache entries </p> </td> 
      <td colname="col2"> <p>Specifies the maximum number of previously requested auto-complete suggestions to cache in the customer's browser. Generally, you should leave this setting at the default of 1000. </p> <p>While you can completely disable browser caching by setting this option to 0, it is not recommended. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Display shadow </p> </td> 
      <td colname="col2"> <p>Adds a cosmetic drop-shadow to the auto-complete suggestions list. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Form name </p> </td> 
      <td colname="col2"> <p>Specifies the "name" attribute of the auto-complete enabled search form's "form" tag. For example, </p> <p> <span class="filepath"> &lt;form name="SiteSearch" method="get" action="https://sp1004337c.guided.t1.atomz.com" target="_blank"&gt; </span> </p> <p>where <span class="filepath"> SiteSearch </span> is the name attribute of the form tag. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Div tag ID </p> </td> 
      <td colname="col2"> <p>Specifies the ID attribute of the auto-complete enabled search form's "div" tag. For example, </p> <p> <span class="filepath"> &lt;div id="autocomplete"&gt; </span> </p> <p>where <span class="filepath"> autocomplete </span> is the attribute of the div tag. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Input tag ID </p> </td> 
      <td colname="col2"> <p>Specifies the ID attribute of the auto-complete enabled search form's "input" tag. For example, </p> <p> <span class="filepath"> &lt;input type="text" id="q" name="q" /&gt; </span> </p> <p>where <span class="filepath"> q </span> is the id attribute of the input tag. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configuring Auto-Complete Word List {#task_1F8E0F346263443383F8CFD2C7AB35D4}

Configure the list of words and phrases that Auto-Complete displays to a customer as suggestions.

<!-- 

t_configuring_auto-complete_word_list.xml

 -->

See [Configuring Auto-Complete](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

See [Configuring Auto-Complete CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**To configure Auto-Complete Word List** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Word List]**.
1. On the [!DNL Auto-Complete Word List] page, set the options that you want.

<!-- 

r_auto-complete_word_list_options.xml

 -->

   See [Previewing the search form as it would appear on your...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Popular Searches Period </p> </td> 
      <td colname="col2"> <p> Controls the time period for the inclusion of words and phrases from a customer's recent searches. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Maximum Search Count </p> </td> 
      <td colname="col2"> <p>Controls the maximum number of searched words and phrases to include in the auto-complete word list. The top words and phrases, which are also the most popular, are included. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Field Name </p> </td> 
      <td colname="col2"> <p>Each field name defines the name of one field for which to include indexed values. Use + and - to add or remove field names. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximum Value Count </p> </td> 
      <td colname="col2"> <p>Defines the maximum count of field values that are allowed for the selected field name. The top values, which are also the most referenced, are included. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Add these words and phrases </p> </td> 
      <td colname="col2"> <p> The auto-complete word list is populated with the words and phrases that are listed in this area. </p> <p> Click <span class="uicontrol"> Edit </span> to see the list or to add word and phrases to the list. When you are finished, click <span class="uicontrol"> Save Changes </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Remove these words and phrases </p> </td> 
      <td colname="col2"> <p> Entries in this area are not displayed in the auto-complete word list. </p> <p> Click <span class="uicontrol"> Edit </span> to see the list or to add word and phrases to the list. When you are finished, click <span class="uicontrol"> Save Changes </span>. </p> <p> Regular expressions are allowed in this list. To specify a regular expression in this list, start the line with 
        <userinput>
          regexp 
        </userinput> followed by a single space, followed by the regular expression. Any lines in the word list that match the regular expression are removed. </p> <p> <b>Important</b>: You should only use regular expressions only if you have previously worked with them in other applications. </p> <p>See <a href="c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Regular Expressions </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignore Case </p> </td> 
      <td colname="col2"> <p>Duplicate entries in the auto-complete word list that differ only by alphabetic uppercase/lowercase are removed; all word list entries are forced to lowercase. </p> <p>If you want the Auto-Complete suggestions to appear "first letter capitalized" or "all caps", add the 
        <userinput>
          text-transform : capitalize; 
        </userinput> or 
        <userinput>
          text-transform : uppercase; 
        </userinput> CSS text properties to the Auto-Complete CSS content, under "/* styles for result item */". </p> <p>See <a href="c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96" type="task" format="dita" scope="local"> Configuring Auto-Complete CSS </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Update on Re-Index </p> </td> 
      <td colname="col2"> <p>Auto-complete word list is automatically regenerated after each successful account re-index. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made. 
    * Click **[!UICONTROL Preview Word List]** to save any changes you have made, and then open [!DNL Auto-Complete Word List Preview] page where you can review the auto-complete suggestions list. Use the navigation options near the top of the page to review and refine the displayed list. When you are done, click **[!UICONTROL Close]** to return to the [!DNL Auto-Complete Word List] page.

      See [Using the History option](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configuring Auto-Complete CSS {#task_EECE35DEB6C94F4A8A5B42B4DED76D96}

Use Auto-Complete CSS to configure the auto-complete cascading style sheet that you want to use.

<!-- 

t_configuring_auto-complete_css.xml

 -->

Auto-Complete CSS controls the content of [!DNL autocomplete_styles.css], which is included as a part of the auto-complete enabled search form. The CSS you specify here controls the visual presentation of the auto-complete suggestion list. For an example of the visual presentation ideas that are possible, see the following:

[https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html](https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html).

[Configuring Auto-Complete Word List](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4).

[Configuring Auto-Complete](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

When you are finished configuring Auto-Complete CSS, you can preview the search form to see if the CSS that you specified is acceptable in appearance and layout.

See [Previewing the search form as it would appear on your...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

**Important**: To apply your custom auto-complete CSS, you need to remove the comment tags from the second line that appears in the HTML code. Then you move the same line to within the head section of the page that contains the search form.

See [Copying the HTML code of the search form into the...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

**To configure Auto-Complete CSS** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete CSS]**.
1. In the [!DNL Auto-Complete CSS] text field, paste or type the cascading style sheet information that you want to associate with the auto-complete suggestion list.
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Previewing the search form as it would appear on your website {#task_437B35EFA5424603A08AF8E79E6B4714}

Based on your configuration of Auto-Complete and Auto-Complete CSS, you can preview how the search form appears if you were to add the HTML code to your website.

<!-- 

t_previewing_the_search_form_as_it_would_appear_on_your_website.xml

 -->

See [Configuring Auto-Complete](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

See [Configuring Auto-Complete CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

See [Copying the HTML code of the search form into the...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

See [Using collections in search forms](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

See [Using frames with forms](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

See [Sample advanced search form](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).

See [Advanced search form HTML code](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9).

See [Advanced search form template code](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579).

**To preview the search form as it would appear on your website** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Search Form]**.
1. (Optional) Click **[!UICONTROL HTML code]** to see the HTML that you copy and paste into the pages of your website.

## Copying the HTML code of the search form into the pages of your website {#task_A3A01EA800F24C0AA33902387E0362C7}

Based on your configuration of Auto-Complete and Auto-Complete CSS, you can preview how the search form appears if you were to add the HTML code to your website.

<!-- 

t_copying_the_html_code_of_the_search_form_into_the_pages_of_your_website.xml

 -->

See [Configuring Auto-Complete](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

See [Configuring Auto-Complete CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

See [Copying the HTML code of the search form into the...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

See [Using collections in search forms](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

See [Using frames with forms](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

See [Sample advanced search form](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).

See [Advanced search form HTML code](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9).

See [Advanced search form template code](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579).

**To copy the HTML code of the search form into the pages of your website** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**.

   >[!NOTE]
   >
   >Do not change the `form name=` value in the form source.

1. (Optional) Do any of the following:

    * If you configured auto-complete CSS and want the styles applied to the search form, remove the comment tags from the second line that appears in the HTML code. Next, move the same line to within the head section of the page that contains the search form. 
    * For maximum performance, move the tags that are listed at the bottom of the HTML code and place them at the bottom of the body section of each page that contains the search form.

1. Copy the code and paste it in the web pages of your website where you want the search form to appear.
