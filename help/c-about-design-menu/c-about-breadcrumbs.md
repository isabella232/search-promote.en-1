---
description: Breadcrumbs are a navigational control that you can add to your website. The breadcrumb gives customers feedback on where they are within a search result set. It also helps them quickly back out to a previous step.
seo-description: Breadcrumbs are a navigational control that you can add to your website. The breadcrumb gives customers feedback on where they are within a search result set. It also helps them quickly back out to a previous step.
seo-title: About Breadcrumbs
solution: Target
subtopic: Navigation
title: About Breadcrumbs
topic: Design,Site search and merchandising
uuid: 3e630a72-a631-4f4f-8aa5-adf2882cdf1c
index: y
internal: n
snippet: y
---

# About Breadcrumbs{#about-breadcrumbs}

Breadcrumbs are a navigational control that you can add to your website. The breadcrumb gives customers feedback on where they are within a search result set. It also helps them quickly back out to a previous step.

## About Breadcrumbs {#concept_FB8A943C594A4A1593B118141DA61F03}

Breadcrumbs are a navigational control that you can add to your website. The breadcrumb gives customers feedback on where they are within a search result set. It also helps them quickly back out to a previous step. 

The breadcrumbs track the term searched for and the subsequent facets that were selected to narrow down the result set.

Use the Breadcrumb settings to customize the breadcrumb control of your search presentation layer. If your presentation layer has more than one set of search results, the breadcrumb control acts on the primary search on the page.

You can edit a breadcrumb to change the default behavior, max value width, and value extension, and to select whether to include the query term. 

## Adding a new breadcrumb {#task_2FFA94F82AE74F10BDDE7367CDCEAE8B}

You can add a breadcrumb bar so that a customer can track where they are on your website.

<!-- 

t_adding_a_new_breadcrumb.xml

 -->

>[!NOTE]
>
>Be sure you reference the breadcrumb in your presentation template so that it is visible on the website.

**To add a new breadcrumb** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. On the [!DNL Breadcrumbs] page, click **[!UICONTROL Add Breadcrumb]**.
1. On the [!DNL Add Breadcrumb] page, set the options that you want.

   These settings affect both the behavior and the default presentation of a breadcrumb. You can override some of these settings by way of the presentation template's settings.

   <!-- 

r_breadcrumb_options.xml

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
   <td colname="col1"> <p>Breadcrumb Name </p> </td> 
   <td colname="col2"> <p>The name of the breadcrumb. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Behavior </p> </td> 
   <td colname="col2"> <p>Sets one of the following three breadcrumb behaviors: </p> <p> 
     <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
      <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Goto </span> <p>Goto removes all the breadcrumbs after the one that is clicked, and starts a new search at that point. </p> </li> 
      <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> Remove </span> <p>Remove deletes from the path the breadcrumb that the customer clicked and then starts a new search. This behavior is useful when you want to let the customer undo steps in drilling down through the search. </p> </li> 
      <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> Drop </span> <p>Drop removes all the breadcrumbs. </p> </li> 
     </ul> </p> <p> For example, suppose you have a breadcrumb of 1 &gt; 2 &gt; 3 &gt; 4. When a customer clicks on "2", it has the following results, based on the behavior you have chosen: </p> <p> 
     <ul id="ul_96FCD8E4C3704B45B59BC18A7A1AC52A"> 
      <li id="li_B880037088DF426F880788EAA3072180">Go To - 1 &gt; 2 </li> 
      <li id="li_D0F07A15DCD043EFA4563632ED33A9E2">Remove - 1 &gt; 3 &gt; 4 </li> 
      <li id="li_D848ED44B4E44538AA92010F9F186224"> Drop - Entire breadcrumb is dropped, taking the customer back to the point before they started to drill down. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Max Value Width </p> </td> 
   <td colname="col2"> <p>Specifies the length of each value in the breadcrumb trail. You specify the setting as a number of characters. </p> <p>For example, a setting of 6 means that the breadcrumb trail can be up to 6 characters long, including spaces. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Value Extension </p> </td> 
   <td colname="col2"> <p>Specifies the ellipses to use when a breadcrumb is truncated. </p> <p>By default a "..." (ellipses) is used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Include Query Term </p> </td> 
   <td colname="col2"> <p>Controls the presence of query term in a breadcrumb. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enable User-Defined Crumbs </p> </td> 
   <td colname="col2"> <p>Check to let you use the User-Defined items in breadcrumbs using <span class="codeph"> uX=[name]&amp;[name]=[value] </span> parameters in the URL. You can use processing rules to handle this parameters the way you want. </p> <p>For example, if this feature is enabled and you have the URL, <code> https://search.host.com/?1=category&amp;q1=Clothes&amp;u2= 
      type&amp;type=Men&amp;x3=kind&amp;q3=Sweater </code> in case if you have facets <span class="codeph"> <span class="varname"> category </span> </span> and <span class="codeph"> <span class="varname"> kind </span> </span>, your breadcrumb will look like <span class="codeph"> Clothes &gt; Men &gt; Sweater </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-Defined Crumb Names </p> </td> 
   <td colname="col2"> <p>A comma-separated list of all possible names of user-defined breadcrumb items. </p> <p>This option is only available if you check <span class="uicontrol"> Enable User-Defined Crumbs </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Add]**.
1. (Optional) On the [!DNL Breadcrumbs] page, do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a breadcrumb {#task_583481D9A23E4E0F97AEB18E72CBE13F}

You can edit the settings of any breadcrumb that you have added.

<!-- 

t_editing_a_breadcrumb.xml

 -->

>[!NOTE]
>
>Be sure you reference the breadcrumb in your presentation template so that it is visible on the website.

**To edit a breadcrumb** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. On the [!DNL Breadcrumbs] page, click **[!UICONTROL Edit]** to the far right of a breadcrumb name.
1. On the [!DNL Edit Breadcrumb] page, set the options that you want.

   See the table of options under [Adding a new breadcrumb](../c-about-design-menu/c-about-breadcrumbs.md#task_2FFA94F82AE74F10BDDE7367CDCEAE8B). 
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) On the **[!UICONTROL Breadcrumb]** page, do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a breadcrumb {#task_401C6E481A744284906E15A29E04F757}

You can delete any breadcrumb that you have added.

<!-- 

t_deleting_a_breadcrumb.xml

 -->

**To delete a breadcrumb** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**
1. On the [!DNL Breadcrumbs] page, click **[!UICONTROL Delete]** to the far right of a breadcrumb name.
1. In the [!DNL Confirmation] dialog box, click **[!UICONTROL OK]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

