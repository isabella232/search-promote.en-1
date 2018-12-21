---
description: Use Facet Rail to reorder groups of facets on a web page.
seo-description: Use Facet Rail to reorder groups of facets on a web page.
seo-title: About Facet Rail
solution: Target
subtopic: Navigation
title: About Facet Rail
topic: Design,Site search and merchandising
uuid: c37051bc-40bf-4425-bc46-28c9c2bca3fb

---

# About Facet Rail{#about-facet-rail}

Use Facet Rail to reorder groups of facets on a web page.

## About Facet Rail {#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB}

Use Facet Rail to reorder groups of facets on a web page. 

A facet is a property or characteristic, It is a way to generally categorize the search results. For example, manufacturer, price, and color could be considered a group of facets. Each facet can have multiple constraints or values. For example, if you had color as a facet, the "facet values" could be red, orange, yellow, green, blue, indigo, and violet.

See [About Facets](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

You use Facet Rail to reorder these groups of facets on a web page. For example, suppose that you had a search results section on the left side of a web page. The section listed, top to bottom, a Category facet, a Brand facet, a Price facet, and a Most Popular facet. Using a facet rail, you can, for example, have the Most Popular facet appear above or below the Category facet.

The group of facets that you want to reorder together belong to a facet rail tag. A facet can only belong to one facet rail. The facet rail is a Presentation template tag and encloses a single representation of a facet. All facets that belong to this rail share that single facet representation.

See [About Templates](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5) and Facet in [Presentation template tags](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64). 

## Configuring a facet rail {#task_561A8FF1CAD1402B9DD33E276BBC6A0E}

You can add a facet rail to customize your presentation layer. Facet rails provide your customers with a Guided Search that lets them drill down into their search results based on the order of the facets on your web page.

<!-- 

t_configuring_facet_rail.xml

 -->

Any changes you make to facet rails can be reverted using the History feature.

**To configure a facet rail** 

1. Before you can configure a facet rail, make sure that you have already added a facet and, as part of that task, specified a facet rail name.

   See [Adding a new facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B). 
1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facet Rail.]**
1. On the [!DNL Facet Rail] page, select the facets that you want to include in the facet rail, and then set the **[!UICONTROL Sort Facets Method]** option from the drop-down list.

   <!-- 

r_facet_rail_options.xml

 -->

<table id="table_F1912CBB3ACE418B9763DF7A480AF4E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Feature/Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Facet Rail Name </p> </td> 
   <td colname="col2"> <p>Identifies the name of the facet rail. </p> <p>You create the name of the facet rail at the time you add the facet. </p> <p>See <a href="../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B" format="dita" scope="local"> Adding a new facet</a> </p> 
    <!--<p>To change the name of a facet rail, edit the facet. </p> <p>See <xref href="t_Editing_a_facet.xml#task_457EDC49983F4F7781873703AF574DA5" format="dita" scope="local">Editing a facet</xref>. </p>--> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Facets Included </p> </td> 
   <td colname="col2"> <p>A list of possible facets that you can select to add to the facet rail. </p> <p>If you choose to sort facets using <span class="uicontrol"> Custom</span>, the order that you select facets here determines the order that they appear in the <span class="uicontrol"> Custom Facet Order</span> text box. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sort Facets Method </p> </td> 
   <td colname="col2"> <p>Choose from one of the following three options in the drop-down list: </p> <p> 
     <ul id="ul_DD398ADCE9814CC0B4FDDDEED580F038"> 
      <li id="li_3BEA6E7D8BA247BCB5624EEBF78851EB"> <span class="uicontrol"> Alpha</span> <p>The facets are sorted in alphabetical order with respect to their names, including punctuation characters. </p> </li> 
      <li id="li_3BEA6E7D8BA247BCB5624EEBF78851EC"> <span class="uicontrol"> Alpha (not case sensitive)</span> <p>The facets are sorted in alphabetical order with respect to their names, ignoring the case of alphabetic characters, and including punctuation characters. </p> </li> 
      <li id="li_3BEA6E7D8BA247BCB5624EEBF78851ED"> <span class="uicontrol"> Alpha (alphanumeric only)</span> <p>The facets are sorted in alphabetical order with respect to their names, ignoring punctuation characters. </p> </li> 
      <li id="li_3BEA6E7D8BA247BCB5624EEBF78851EE"> <span class="uicontrol"> Alpha (not case sensitive, alphanumeric only)</span> <p>The facets are sorted in alphabetical order with respect to their names, ignoring the case of alphabetic characters, and ignoring punctuation characters. </p> </li> 
      <li id="li_6B71E95A671A4BEC8C701E6E63ED44DE"> <span class="uicontrol"> Count</span> <p>The facets are sorted base on count. </p> </li> 
      <li id="li_A8DBEB6D9D4B40799A606ACE8AE63A03"> <span class="uicontrol"> Custom</span> <p>Opens the <span class="uicontrol"> Custom Facet Order</span> text box which lets you define the order of the facets by entering the exact name of each facet. Any facet labels left out are removed from the <span class="uicontrol"> Custom Facet Order</span> list. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom Facet Order </p> </td> 
   <td colname="col2"> <p>This option is only available if you selected <span class="uicontrol"> Custom</span> from the <span class="uicontrol"> Sort Facets Method</span> drop-down list. </p> <p>Lets you list facet names, either one per line, or all on one line and comma-separated. If facet labels are defined they are shown in the <span class="uicontrol"> Facets Included</span> list, enclosed in parentheses. </p> <p>Do not include facet labels in the <span class="uicontrol"> Custom Facet Order</span> text box. </p> <p>When you select or deselect facets in the <span class="uicontrol"> Facets Included</span> list, the <span class="uicontrol"> Custom Facet Order</span> text box is automatically updated. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) On the [!DNL Facet Rail] page, do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

1. Edit the Presentation template by doing the following:.

* Create a "facet template" on the presentation template. 
* Surround the "facet template" with the `<guided-facet-rail>` tags.

  See Facets in [Presentation template tags](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

  Example:

  ```
  <guided-facet-rail>
    <guided-facet>
      <guided-facet-display-name/>
      ...
      </guided-facet>
    </guided-facet-rail>
  ```

  These tags carve out a section of the presentation template to become a repeatable pattern for each facet in the facet rail. Each facet that belongs to the facet rail uses this carved out section to evaluate its output. Only one `<guided-facet-rail>` tag can appear on the final presentation template.

  The following tags do not need the `gsname` attribute inside `<guided-facet-rail>` because the value is dynamically determined at search time and is properly substituted:

    * `<guided-facet>` 
    * `<guided-facet-display-name>` 
    * `<guided-facet-total-count>` 
    * `<guided-facet-undo-link>` 
    * `<guided-facet-undo-path>` 
    * `<guided-facet-behavior>`

* Save the presentation template and push it live.

   See [Editing a presentation or a transport template](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3). 
