---
description: Data Views displays the search results with the meta fields. Each column is a meta field and each row is result from a search query. Customize Data Views by choosing and rearranging columns. Data Views can also have custom titles and descriptions.
solution: Target
title: About Data Views
topic: Reports,Site search and merchandising
uuid: 18930551-960d-40c2-b5b7-0807a2e11134
---

# About Data Views{#about-data-views}

Data Views displays the search results with the meta fields. Each column is a meta field and each row is result from a search query. Customize Data Views by choosing and rearranging columns. Data Views can also have custom titles and descriptions.

## Using Data Views {#concept_DCA897D074464BC1861AA47B40CC86C3}

Each account has the convenience of creating multiple data views. Use the Data Views page to create and edit these data views.

After you add a data view, you must edit it to configure and customize the view.

See [Editing a data view](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

You can copy an existing data view to use as the basis for creating a new data view.

See [Copying a data view](../c-about-reports-menu/c-about-data-views.md#task_78D4C2799BC84677843ED4CA1CD205AF). 

## Adding a data view {#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D}

You can add a data view to the [!DNL Data Views] page to display the values of each meta field with a search query.

After you add a data view, you must edit it to configure and customize the view.

See [Editing a data view](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

**To add a data view** 

1. On the product menu, click **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. On the [!DNL Data Views] page, click **[!UICONTROL Add New Data View]**.
1. In the [!DNL Add New Data View] dialog box, in the [!DNL Title] field, enter the name of the data view you want to create.
1. Click **[!UICONTROL Add]**.

## Editing a data view {#task_258A367896C24DD498C755925EA8F516}

When you add a data view to the [!DNL Data Views] page, you use Edit to change the data view's name and description or to move, reveal, or hide the display of each meta field.

You can also lock or unlock a selected data view.

See [Adding a data view](../c-about-reports-menu/c-about-data-views.md#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D).

**To edit a data view** 

1. On the product menu, click **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. On the [!DNL Data Views] page, in the [!DNL Actions] column of the table, click **[!UICONTROL Edit]** in the row with the data view that you want to change.
1. On the [!DNL Data Views Editor] page, set the options you want.

   The Data View Editor has all the controls for hiding, showing, and moving field columns on the Data View page.

   When you view a data view, the resulting table also shows the following additional column fields which are not editable: Ranking, Relevance, and Score (overall). These three special fields represent the relevance scores, rank scores, and overall scores for each result.

    <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Description </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Title </p> </td> 
      <td colname="col2"> <p>The name of the data view. The name is displayed at the top right when you view the data view. </p> <p>See <a href="../c-about-reports-menu/c-about-data-views.md#task_FD0D2CE53DF84CBD9220AD7CA920011F" type="task" format="dita" scope="local"> Viewing a data view</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Description </p> </td> 
      <td colname="col2"> <p>(Optional) Contains a description of the data view. The description is displayed between the title name of the data view and the <span class="wintitle"> New Search</span> text field. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Search Parameters </p> </td> 
      <td colname="col2"> <p>Lets you specify default search parameters. When the data view is displayed for the first time, these CGI parameters are automatically appended. </p> <p>Do not change or delete <span class="codeph"> sp_cs</span> or <span class="codeph"> sp_f</span>. These parameters are essential to Data View regardless of the account's preferred character set. </p> <p>See <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend search CGI parameters</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lock Status </p> </td> 
      <td colname="col2"> <p>Lets you lock or unlock the data view. </p> <p>You can view a locked data view only with a password and user name. The user must be a current member of the account. </p> <p>An unlocked data view is accessed without a password or user account. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Order </p> </td> 
      <td colname="col2"> <p> Lets you change the column order by editing the number in the <span class="wintitle"> Order</span> text box. You can also drag-and-drop a row to change the column order. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Include </p> </td> 
      <td colname="col2"> <p> Lets you turn on or off the display of the column. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Display URL as image </p> </td> 
      <td colname="col2"> <p>Display thumbnails and images in this column if the search result for this column returns a URL. </p> <p>The URL is stripped of its scheme name or protocol before becoming a value of the <span class="codeph"> src</span> attribute of an image tag. </p> <p>If the returning search result does not look like a URL to an image, then an is displayed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Field Length </p> </td> 
      <td colname="col2"> <p>Sets the number of characters that are displayed as a result on the data view. </p> <p>The default is 100 characters. </p> <p>Some fields, such as the ranking score and the date field, do not have adjustable field lengths. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Copying a data view {#task_78D4C2799BC84677843ED4CA1CD205AF}

You can copy an existing data view on the [!DNL Data Views] page to use as the basis for creating a new data view.

After you copy a data view, you can further customize it by editing the view.

See [Editing a data view](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

**To copy a data view** 

1. On the product menu, click **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. On the [!DNL Data Views] page, in the [!DNL Actions] column of the table, click **[!UICONTROL Copy]** in the row with the data view that you want to copy.
1. On the [!DNL Copy Data View] page, in the [!DNL New Title] text field, enter the new name that you want to assign the data view.
1. Click **[!UICONTROL Copy]**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting a data view {#task_61C32F8F00A549A5A3E7EDDA6F537098}

You can delete a data view on the [!DNL Data Views] page that you no longer need or use.

**To delete a data view** 

1. On the product menu, click **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. On the [!DNL Data Views] page, in the [!DNL Actions] column of the table, click **[!UICONTROL Delete]** in the row with the data view that you want to remove.
1. On the [!DNL Delete Data View] page, click **Delete**.
1. (Optional) Do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Viewing a data view {#task_FD0D2CE53DF84CBD9220AD7CA920011F}

You can use [!DNL View] on the [!DNL Data Views] page to display a selected data view.

The data view that you select is opened in a separate browser window.

**To view a data view** 

1. On the product menu, click **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. Do any one of the following:

    * On the [!DNL Data Views] page, in the [!DNL Title] column of the table, click the name of a data view that you want to open. 

    * On the [!DNL Data Views] page, in the [!DNL Actions] column of the table, click **[!UICONTROL View]** in the row with the data view that you want to open.

