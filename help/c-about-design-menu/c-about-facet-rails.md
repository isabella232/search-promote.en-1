---
description: Use Facet Rail to reorder groups of facets on a web page.
seo-description: Use Facet Rail to reorder groups of facets on a web page.
seo-title: About Facet Rail
solution: Target
subtopic: Navigation
title: About Facet Rail
topic: Design,Site search and merchandising
uuid: 6da2bd67-8c20-4955-9836-bc8ba88546c5
---

# About Facet Rail{#about-facet-rail}

Use Facet Rail to reorder groups of facets on a web page.

## Using Facet Rail {#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB}

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

    | Feature/Option  | Description  |
    |--- |--- |
    |Facet Rail Name|Identifies the name of the facet rail.  You create the name of the facet rail at the time you add the facet.  See [Adding a new facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B)|
    |Facets Included|A list of possible facets that you can select to add to the facet rail.  If you choose to sort facets using `Custom`, the order that you select facets here determines the order that they appear in the `Custom Facet Order` text box.|
    |Sort Facets Method|Choose from one of the following three options in the drop-down list:<ul><li>`Alpha` The facets are sorted in alphabetical order with respect to their names, including punctuation characters.</li><li>`Alpha (not case sensitive)` The facets are sorted in alphabetical order with respect to their names, ignoring the case of alphabetic characters, and including punctuation characters. </li><li>`Alpha (alphanumeric only)` The facets are sorted in alphabetical order with respect to their names, ignoring punctuation characters. </li><li>`Alpha (not case sensitive, alphanumeric only)` The facets are sorted in alphabetical order with respect to their names, ignoring the case of alphabetic characters, and ignoring punctuation characters. </li><li>`Count` The facets are sorted base on count. </li><li>`Custom` Opens the `Custom Facet Order` text box which lets you define the order of the facets by entering the exact name of each facet. Any facet labels left out are removed from the `Custom Facet Order` list.</li></ul>|
    |Custom Facet Order|This option is only available if you selected `Custom` from the `Sort Facets Method` drop-down list.  Lets you list facet names, either one per line, or all on one line and comma-separated. If facet labels are defined they are shown in the `Facets Included` list, enclosed in parentheses.  Do not include facet labels in the `Custom Facet Order` text box.  When you select or deselect facets in the `Facets Included` list, the `Custom Facet Order` text box is automatically updated.|

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

      `<guided-facet>` 
      `<guided-facet-display-name>` 
      `<guided-facet-total-count>` 
      `<guided-facet-undo-link>` 
      `<guided-facet-undo-path>` 
      `<guided-facet-behavior>`

    * Save the presentation template and push it live.

      See [Editing a presentation or a transport template](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3). 
