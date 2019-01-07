---
description: You can use menus to customize your presentation layer.
seo-description: You can use menus to customize your presentation layer.
seo-title: About Menus
solution: Target
subtopic: Navigation
title: About Menus
topic: Design,Site search and merchandising
uuid: c8522c6e-c9d7-41e3-aba8-7eff3c23cfbc
index: y
internal: n
snippet: y
---

# About Menus{#about-menus}

You can use menus to customize your presentation layer.

## About Menus {#concept_68123CE5CF4447B59217B5D721424E32}

You can use menus to customize your presentation layer. 

Add menus that map to settings within your search. Each item within a menu specifies the value for the setting of the menu. You can also customize the menu labels.

In your presentation template, you can reference the menus that are defined. You can then put them in any HTML component that you want, such as a select control. This combination enables users to customize their search results. Three menu types are supported: sort, count, and navigation. 

## Adding a new menu {#task_EE171532D3AE477FAFE8C2F4077A6D73}

You can add menus that map to settings within your search results.

<!-- 

t_adding_a_new_menu.xml

 -->

>[!NOTE]
>
>Be sure you reference the menu in your presentation template so that it is visible on the website.

**To add a new menu** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**.
1. On the [!DNL Menus] page, click **[!UICONTROL Add New Menu]**.
1. On the [!DNL Add Menu] page, set the options that you want.

   These settings affect both the behavior and the default presentation of a breadcrumb. You can override some of these settings by way of the presentation template's settings.

   See [About Menus](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32).

   <!-- 

r_add_menu_options.xml

 -->

<table id="table_C5641613476D4B0B8A4916C84FB4ACD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Menu Name </p> </td> 
   <td colname="col2"> <p>Name of the menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Menu type </p> </td> 
   <td colname="col2"> <p>Sets one of the following three menu types: </p> <p> 
     <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
      <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Sort </span> <p>Organizes your search by any of your defined metadata types. </p> <p>For example, you might define a sort menu with the following metadata types: three items of relevance; a custom metadata field such as an availability code; and price. The three items can be given the labels "Sort by Relevance", "Sort by Availability", and "Sort by Price", respectively. When you include this in your presentation template, the customer can use this control to sort their search results. </p> </li> 
      <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> Count </span> <p>Defines the number of search results to show. This menu type maps to the cgi parameter <span class="varname"> sp_c </span>. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </li> 
      <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> Navigation </span> <p>Specifies a set of static URLs that are associated with menu items. Typically, a navigation menu is used to create a top-level navigation bar on your search results page. </p> <p>For example, you could create a menu that has women, men, boys, and girls where the menu items would be something like the following: 
        <userinput>
          /?q1=womens;x1=gender 
        </userinput>, 
        <userinput>
          /?q1=mens;x1=gender 
        </userinput> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Merchandising </p> 
    <!--DONT' KNOW WHAT THIS DOES--> </td> 
   <td colname="col2"> <p>This option is only available if you chose the menu type <span class="uicontrol"> Sort. </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Number of items in menu </p> </td> 
   <td colname="col2"> <p>Specifies the number of items in a menu. Changing this setting adds or deletes fields from the form. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default item </p> </td> 
   <td colname="col2"> <p>Lets you select which menu item is displayed by default. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Item value </p> </td> 
   <td colname="col2"> <p>The item value depends on the menu type you have set. </p> 
    <ul id="ul_2F14E6AA673640578A2D5161FD9D13EF"> 
     <li id="li_5017EC6E4ACB4B8E99E0AA61CBAAFFAE"> Sort menu type <p>Identifies what the selected item in the menu should sort by. The select items are populated with sortable metadata fields. </p> <p>For a single item you can sort by three metadata fields. The sort is done in the order that is specified. </p> </li> 
     <li id="li_CC6BAFBF969C4367A71B55F08E0758D1"> Count menu type <p>Lets you specify the number of results that you want to return when the customer selects this menu item. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Item label </p> </td> 
   <td colname="col2"> <p>The item label depends on the menu type you have set. </p> 
    <ul id="ul_957BF01235F84748B5EB7062D6AEAC41"> 
     <li id="li_03FB2E2C96134A2B8E08154F87F0CD55"> Sort menu type <p>Identifies the custom label that you want your customer to see when they view this item in the menu. </p> </li> 
     <li id="li_C9FE2BC46D9443FB85FEB837C7CA45E1"> Count menu type <p>Identifies the custom label that you want to have displayed for this menu item. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Add]**.
1. (Optional) On the [!DNL Menus] page, do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a menu {#task_0770DBFD0C7046169097FB6F771B9114}

You can edit the settings of any menu that you have added.

<!-- 

t_editing_a_menu.xml

 -->

>[!NOTE]
>
>Be sure you reference the menu in your presentation template so that it is visible on the website.

**To edit a menu** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**.
1. On the [!DNL Menus] page, click **[!UICONTROL Edit]** to the far right of a menu name.
1. On the [!DNL Edit Menu] page, set the options that you want.

   See the table of options under [Adding a new menu](../c-about-design-menu/c-about-menus.md#task_EE171532D3AE477FAFE8C2F4077A6D73). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) On the [!DNL Menus] page, do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a menu {#task_645E212311A045CD8D9D906878165F47}

You can delete any menu that you have added.

<!-- 

t_deleting_a_menu.xml

 -->

**To delete a menu** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**
1. On the [!DNL Menus] page, click **[!UICONTROL Delete]** to the far right of a menu name.
1. In the [!DNL Confirmation] dialog box, click **[!UICONTROL OK]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

