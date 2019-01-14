---
description: You can use Banners to manage the banner ads on your website.
seo-description: You can use Banners to manage the banner ads on your website.
seo-title: About Banners
solution: Target
title: About Banners
topic: Design,Site search and merchandising
uuid: 653b567d-5cf3-41a0-a260-a6912d0fd20d
index: y
internal: n
snippet: y
---

# About Banners{#about-banners}

You can use Banners to manage the banner ads on your website.

## About Banners {#concept_5BBE01FEC6134393B43CC917C8CC64DA}

You can use Banners to manage the banner ads on your website.

<!-- 

c_about_banners.xml

 -->

There are two methods you can use to add banner ads to your website.

The first method is to add banners by way of Target, Search&Promote. The banners are HTML code snippets that are displayed at the time that a customer searches your website. Your banner can include text or an image in GIF, JPEG, or PNG format, or a combination of both. You can select from preset sizes or define your own custom dimensions to fit your page. The HTML code that you use to display the banner can also specify such things as the font style to use, and the border. This method of adding a banner offers basic functionality and does not require additional software.

The second method is to use Adobe Scene7, a dynamic media management and publishing service. A valid Adobe Scene7 account lets you manage and deliver banner content directly to Target, Search&Promote, using Scene7. In site search/merchandising, you configure access to your Scene7 account. Then you open the Scene7 media browser and pick a dynamic media asset that you want to serve as your banner.

>[!NOTE]
>
>Before you can use dynamic media assets as banners in site search/merchandising, the assets are first uploaded and prepared for publishing in the Scene7 Publishing System. You can upload assets from within site search/merchandising and have them automatically prepared for publishing by Scene7 Publishing System. Or, you can upload and publish assets all from within Scene7 Publishing System.

## Integration of Banners with Adobe Scene7 Publishing System {#section_D4D7ADEA6A6348E68EDA138E184FE579}

You can use Scene7 asset types as banners in site search/merchandising including images, dynamic banners, and templates, such as image templates or Flash templates.

Templates are dynamically created and addressable layered image files like layered files in image-editing applications such as Adobe Photoshop®. Unlike a static image file, a template can include parameters. Through parameters, you can customize variable image properties and image content.

>[!NOTE]
>
>You can also create templates from layout-based designs by using Template Publishing in Scene7 Publishing System and files from Adobe Illustrator and Adobe InDesign.

See [Template Publishing](https://help.adobe.com/en_US/scene7/using/WSFBFBAD30-2694-4b18-B7CE-894F9FC5CDDF.html) in the Scene7 Publishing System User Guide.

A template can contain any number of image layers and text layers. You can convert a static file containing layers, such as a layered PSD file, into a template, or create templates in Scene7. You can create text layers in templates using fonts that you uploaded into Scene7 Publishing System. After you add text to a template, you can format it by changing its justification, fonts, font size, and color.

Using the Parameters screen in Scene7, you can convert any aspect of a template to an addressable parameter. In so doing, you can change which layered image to use or what text value to use in your template. Parameters are passed with the URL string, allowing you to change any parameter to dynamically customize the reply image generated from the image server.

You can learn more about how to use Scene7 to create templates and parameterize the properties on the layers so you can use them in banners.

See [Template Basics](https://help.adobe.com/en_US/scene7/using/WS60B68844-9054-4099-BF69-3DC998A04D3C.html) in the Scene7 Publishing System User Guide.

**Uploading and publishing of assets**

You must upload and publish assets in Scene7 before you can use them for banners in site search/merchandising. This prerequisite also includes any assets that an image template or a Flash template uses. Use your Scene7 account to upload and publish digital assets. Or, you can use site search/merchandising to upload a digital asset and then have Scene7 automatically publish it for you based on your upload settings. If you attempt to pick an asset that is not yet uploaded and published, you are notified in the user interface and given the option of uploading it before proceeding.

You can learn more about uploading and publishing of digital assets using Scene7 Publishing System.

See [Upload and Publish Assets](https://help.adobe.com/en_US/scene7/using/WS3673AD39-098B-4f08-8A24-CA51261B7366.html) in the Scene7 Publishing System User Guide.

>[!NOTE]
>
>To use the upload functionality in the Scene7 asset viewer, be sure that the Scene7 account you use has the role of "SPS Company Admin" already set.

See [Administration Setup](https://help.adobe.com/en_US/scene7/using/WS662101DF-D697-47a7-A7D8-B52FD8E94438.html) in the Scene7 Publishing System User Guide.

**Changing Scene7 Template Parameters in a Banner using Business Rules**

If you added a Scene7 asset as a banner, you can use [!DNL Visual Rule Builder] in [!DNL Business Rules] to add it to any banner area on your website. For example, you add the banner to your search results pages, just as you would any other banner. You can also override the default parameter values in Scene7 templates by customizing them to your specific needs. This kind of functionality lets you customize Scene7 templates with different marketing messages and hyperlinks to different endpoints.

See also [Adding a new business rule](../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7).

See also [Editing a business rule](../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087). 

## Adding a banner {#task_549D02B5F73B4158B105A94E39D937B7}

You can use [!DNL Banners] to manage the banner ads and where they are placed on your website. When you add a banner you are externally referencing the image by way of HTML code snippets that are displayed at search time.

<!-- 

t_adding_a_new_banner.xml

 -->

If you have a valid Adobe Scene7 account, you can add banner ads by way of the Scene7 Publishing System.

See [Adding a banner using Adobe Scene7](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

See [Configuring access to your Adobe Scene7 account](../c-about-settings-menu/c-about-account-options-menu.md#task_CEFF88C2033D41D0B2FE86C435EDAC6D).

**To add a banner** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Banners.]**
1. On the [!DNL Banners] page, in the **[!UICONTROL Add Banner]** drop-down list, select **[!UICONTROL HTML code]**.
1. In the [!DNL Add Banner] dialog box, set the options that you want.

   <!-- 

r_banner_options.xml

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
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2"> <p>Required. Identifies the name of your banner. The name is used to refer to the banner when you add it in the Visual Rule Builder in Business Rules. The name does not appear in the banner itself. </p> <p>See <a href="../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7" type="task" format="dita" scope="local"> Adding a new business rule </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Banner HTML </p> </td> 
   <td colname="col2"> <p> Lets you paste the HTML code that is associated with the banner. </p> <p>Any HTML code is acceptable, including CSS code that is surrounded by 
     <userinput>
       &lt;style&gt; 
     </userinput> tags, or JavaScript code that is surrounded by 
     <userinput>
       &lt;script&gt; 
     </userinput> tags. For example, the following block of code is for a text banner of the type Horizontal top : <code> &lt;div&nbsp;style="width:&nbsp;684px;&nbsp;background-image:&nbsp;url('https://www.brough.com/blackb.gif');&nbsp; 
      padding-top:&nbsp;10px;&nbsp;padding-bottom:&nbsp;10px;&nbsp;color:&nbsp;white;&nbsp;font-family:&nbsp;verdana;&nbsp; 
      text-align:&nbsp;center;&nbsp;font-size:&nbsp;20px;"&gt;&nbsp;Sound&nbsp;Study&nbsp;ships&nbsp;free!&nbsp;&lt;/div&gt; </code>In the following example, the block of code is for a full splash image: <code> &lt;img&amp;nbsp;src='https://geometrixx.com/images/GEOAds/geometrixx-beauty-home-01.jpg'&amp;nbsp;border="0"&amp;nbsp;/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type </p> </td> 
   <td colname="col2"> <p>Specifies the following types of banners: 
     <ul id="ul_6423AEDB9E664049989EB529D63C4A62"> 
      <li id="li_BF6CD60B3ED748D49CFFB9C5D607661C"> <span class="uicontrol"> [new type] </span> <p>Lets you specify the type of banner you want, including the dimensions and the name. </p> </li> 
      <li id="li_1A29AB22AD644E60A12298187B5E898E"> <span class="uicontrol"> Full splash </span> <p>The set dimension of this type of banner is 680 pixels wide, and 650 pixels high. You can optionally specify the name of the type, or accept the default name which is the name of the banner type itself. </p> </li> 
      <li id="li_2BE06D013CB54DDE851051BFC038BB57"> <span class="uicontrol"> Horizontal top </span> <p> The banner is positioned across the top area of your website. This type is useful if you intend to add hyperlinks to the left or to the right of the banner. The set dimension of this type of banner is 468 pixels wide, and 60 pixels high. You can optionally specify the name of the type, or accept the default name which is the name of the banner type itself. </p> </li> 
      <li id="li_EC35AB92234749F08AA8A9BD26D0EA8D"> <span class="uicontrol"> Horizontal top - Full width </span> <p>This type is the default when you add a new banner. The banner is positioned across the top area of your website and takes up the full width of the page. The set dimension of this type of banner is 670 pixels wide, and 150 pixels high. You can optionally specify the name of the type, or accept the default name which is the name of the banner type itself. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tags </p> </td> 
   <td colname="col2"> <p>Adds tags or "keywords" that you want to associate with the banner. If you use many banners, adding tags can help you to refine your banner search so you can quickly locate just the right banner for your needs. You can also delete any tags that you have added. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a banner {#task_D4081083BE7B40F5A003D1A2F1435AEA}

Use [!DNL Edit Banner] to change such things as the banner name, banner HTML, the banner type, and any associated tags.

<!-- 

t_editing_a_banner.xml

 -->

If you added a banner using site search/merchandising, you also edit the banner using Adobe Scene7.

See also [Editing a banner using Adobe Scene7](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9).

**To edit a banner** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Banners]**.
1. On the [!DNL Banners] page, click  ![](assets/icon_edit_16.gif)

   above a banner thumbnail that you want to edit.
1. On the [!DNL Edit Banner] page, set the options that you want.

   See the table of options under [Adding a banner](../c-about-design-menu/c-about-banners.md#task_549D02B5F73B4158B105A94E39D937B7). 
1. When you are finished editing the banner, click **[!UICONTROL Save]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Adding a banner using Adobe Scene7 {#task_AD1E0C00A9E04B1FA819EB93288786B3}

You can use [!DNL Banners] to manage the banner ads on your website. When you add a banner using Adobe Scene7, you can choose from any digital asset that you have uploaded to the Scene7 Publishing System.

<!-- 

t_adding_a_banner_using_adobe_scene7.xml

 -->

To add a banner using Adobe Scene7, be sure that you have configured access to your valid Scene7 account.

See [Configuring access to your Adobe Scene7 account](../c-about-settings-menu/c-about-account-options-menu.md#task_CEFF88C2033D41D0B2FE86C435EDAC6D).

**To add a banner using Adobe Scene7** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Banners.]**
1. On the [!DNL Banners] page, in the **[!UICONTROL Add Banner]** drop-down list, click **[!UICONTROL Adobe Scene7]**.
1. In the [!DNL Pick an Asset] dialog box, in the left pane, use the navigation options in the user interface to locate the folder that contains the digital asset that you want to use for a banner.

   <!-- 

r_pick_an_asset_options.xml

 -->

   With the exception of asset navigation options, all other options are dependent on the digital asset that you selected to add or edit.

   Use the asset navigation options to locate an asset that you want to use for a new banner in site search/merchandising. The navigation options apply to all types of selected digital assets.

   >[!NOTE]
   >
   >The asset navigation options do not appear when you edit the banner in the [!DNL Change Parameters] dialog box.

   See [Editing a banner using Adobe Scene7](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9).

   **Asset navigation options** 

<table id="table_B9173907AD514828A5865C582F6E311C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigation option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_63FE9C1D8F22498080D85A5A4D1ED487" href="assets/S7_folders.png" /> </p> </td> 
   <td colname="col2"> <p>Lets you select the Scene7 account for your particular company from the drop-down list and also navigate the digital asset folders within that account. </p> <p>When you select a folder, the right pane of the <span class="wintitle"> Pick an Asset </span> dialog box shows you all the available digital assets that are contained within that folder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_EA6AF682F0BF41229255711D83FB6F2A" href="assets/s7_folderhistory.png" /> </p> </td> 
   <td colname="col2"> <p>Lets you move forward or backward through your folder navigation history. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_8D891CE778DF49BDB286AADB50A9352F" href="assets/s7_reloadfolder.png" /> </p> </td> 
   <td colname="col2"> <p>Refreshes the list of digital assets that are displayed for a selected folder. </p> <p>You may need to click this control if you move, delete, or rename a selected asset using the <span class="uicontrol"> Actions </span> drop-down list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_11ADA8AA8D21450B9D4F98D12DEDDD1D" href="assets/s7_list_or_grid.png" /> </p> </td> 
   <td colname="col2"> <p>Displays digital assets in a list view. The list displays each asset's associated icon or thumbnail image, file name, digital asset type, dimensions, (where applicable), and the date it was last edited. </p> <p>The grid view displays digital assets in the selected folder as icons, thumbnails, or both. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_77AF34B48C804A30976CC2D70F35D1CE" href="assets/s7_actionsdropdown.png" /> </p> </td> 
   <td colname="col2"> <p>In the list view, you can move, delete, or rename a selected digital asset. </p> <p>In the grid view, you can move or delete one or more selected digital assets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_656479B4D9174AC3A5B291E66AAC7C3C" href="assets/s7_upload.png" /> </p> </td> 
   <td colname="col2"> <p>Opens the <span class="wintitle"> Upload </span> dialog box where you can upload a selected digital asset from your desktop or from an external server so that you can use it as a banner. </p> <p>After you upload the asset, a publish job is automatically schedule for you in Scene7 Publishing System. </p> <p>See the table of options in <a href="../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3" type="reference" format="dita" scope="local"> Adding a banner using Adobe Scene7 </a>. </p> <p>You can learn more about uploading and publishing of digital assets using Scene7 Publishing System. </p> <p>See <a href="https://help.adobe.com/en_US/scene7/using/WS3673AD39-098B-4f08-8A24-CA51261B7366.html" scope="external" format="html"> Upload and Publish Assets </a> in the Scene7 Publishing System User Guide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_DA7714163B3F4203ADC772DC1513B586" href="assets/s7_searchfield.png" /> </p> </td> 
   <td colname="col2"> <p>Lets you search for a digital asset by keyword or search by file location within the selected folder and its associated sub-folders. </p> <p>When you click the search field, it automatically adds an optional filter field for you. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_47F06E3A6B8548C4A155B1ECECDECE1F" href="assets/s7_addfilter.png" /> </p> </td> 
   <td colname="col2"> <p>Adds another asset filter so you can further refine the list of displayed digital assets by type or by a specific date. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_D8A0E40F356D4694A7448F307B838D7E" href="assets/s7_Kindfilter.png" /> </p> </td> 
   <td colname="col2"> <p>Refine the list of displayed digital assets to show only those by a certain type such as Flash, Image, Template, or Any. </p> <p>Click <img id="image_384234979C7B4436B0009AF1C8E28148" href="assets/s7_deletefilter.png" /> to delete the filter from the search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_FE375512F32E41DFB8FC861AC986EE39" href="assets/s7_datefilter.png" /> </p> </td> 
   <td colname="col2"> <p>Refine the list of displayed digital assets to show only those created or edit before a certain date or after a certain date. </p> <p>Click <img id="image_3B3D4C5956F741B1B342A55948C27B71" href="assets/s7_deletefilter.png" /> to delete the filter from the search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_C8AD018A3B19408F9B51D1D6B1F72846" href="assets/s7_assetzoom.png" /> </p> </td> 
   <td colname="col2"> <p>Lets you drag the slider left or right to reduce or enlarge the entire view of the digital assets pane, respectively. </p> </td> 
  </tr> 
 </tbody> 
</table>

   **Properties options**

   The Properties options appear if you chose a Flash template, image template, or an image. Depending on the digital asset you chose, not all options are available. 

<table id="table_F6CDB7DE61654840A4D3A7013119E91E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Properties option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2"> <p>The descriptive name of the template or image, without any blank spaces. You may want to optionally include the image-size specification in the name to help users further identify the asset. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Format </p> </td> 
   <td colname="col2"> <p>Identifies the format of the image, or image template. </p> <p>You can choose from the following formats: </p> 
    <ul id="ul_9A19421BCC424CF585645049DCB87F10"> 
     <li id="li_A4913D783BD547F9AFA1A259C56EC2B3">jpeg </li> 
     <li id="li_66237D7BE8754FB0B0088CE5A02C0214">png </li> 
     <li id="li_4EDDFD7C8AB04677BEC20EFC9AEBBF1F">png-alpha </li> 
     <li id="li_4FCB03C29AE647ACBAF5105016DF7579">gif </li> 
     <li id="li_B884BD7DFF1845FAA9C58EF09B888A77">gif-alpha </li> 
    </ul> <p>This option does not apply to Flash templates. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quality </p> </td> 
   <td colname="col2"> <p>Controls the compression level of JPEG or GIF format images. This setting affects both file size and image quality. The quality scale is 1-100. </p> <p>When you drag the slider left or right, the image in the preview window is updated to reflect the change in quality. </p> <p>This option does not apply to Flash templates. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Width </p> </td> 
   <td colname="col2"> <p>Specifies the width of the digital asset, in pixels. This dimension is the width at which the asset is seen by customers who visit your website. </p> <p>This option does not apply to Flash templates. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Height </p> </td> 
   <td colname="col2"> <p>Specifies the height of the digital asset, in pixels. This dimension is the height at which the asset is seen by customers who visit your website. </p> <p>This option does not apply to Flash templates. </p> </td> 
  </tr> 
 </tbody> 
</table>

   **Banner Link options**

   The Banner Link options appear only if you chose an image or an image template for your banner. 

<table id="table_18FD63F56EEB4F9A94F66DF2102A9957"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Banner Link option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Link URL </p> </td> 
   <td colname="col2"> <p>Specifies the URL address that you want the banner to link to when a customer clicks the image. </p> <p>If you do not want the banner to link to anything, leave the Link URL field blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Target </p> </td> 
   <td colname="col2"> <p>Specifies where to open the linked banner such as a new browser window or a new tab. </p> </td> 
  </tr> 
 </tbody> 
</table>

   **Modify Links option**

   The Modify Links option appears only if you chose a Flash template for your banner. 

<table id="table_24D0E07E3A8C48C18DE49401E7CB7CAB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Modify Links option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img placement="inline" id="image_EBB8159690C74D4692B5DF945B045E0B" href="assets/icon_edit_16.gif" /> </p> </td> 
   <td colname="col2"> <p>Lets you edit the URL link field that is used in the Flash template. </p> </td> 
  </tr> 
 </tbody> 
</table>

   **Replace Text options**

   The Replace Text options appear only if you chose a Flash template for your banner that has editable text layers.

   Any changes you make to text in the Flash template are reflected in the Preview window.

   >[!NOTE]
   >
   >If you add a search and replace command to replace "cow" with "apple", and then create a second command to replace "apple" with "orange", the second command does not take affect.

<table id="table_24796D7DF0634BD1A5F2263121D50519"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Replace Text option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_CA592F821E10473FA16CB1D9C74E0E70" href="assets/s7_addfilter.png" /> </p> </td> 
   <td colname="col2"> <p>Adds a search and replace field. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_3F3CD01B9F2F49398D79F8ED5BEE8021" href="assets/s7_deletefilter.png" /> </p> </td> 
   <td colname="col2"> <p>Deletes a Search and Replace field and restores the previously used text. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Search </p> </td> 
   <td colname="col2"> <p>Lets you enter a search term for non-linked text within the layers of the Flash template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Replace </p> </td> 
   <td colname="col2"> <p>Lets you specify the text that you want to insert in place of the text you are searching for. </p> <p>When you press <span class="uicontrol"> Enter </span> in this field, the preview window is updated with your replacement text. </p> </td> 
  </tr> 
 </tbody> 
</table>

   **Parameters options**

   Parameters options appear only if you chose an image template or a Flash template for your banner. The actual parameter options vary depending on how the template was created and parameterized in Scene7 Publishing System. For example, your template may parameterized fields that let you change such things as text, font style, price, special codes used for free shipping, the size of the image within the banner, or even browse for a different image to use.

   >[!NOTE]
   >
   >Be aware that any changes you make to parameters can be overridden by business rules. The parameters only serve as defaults when no business rules are created that would otherwise change the parameters.

   See [Adding a new business rule](../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7).

   See [Editing a business rule](../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087).

   **Toggle Layer Visibility options**

   The Toggle Layer Visibility option applies only if you chose a Flash template for your banner. 

<table id="table_7A6B8DF717BD43728AFEF3314D620A98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Toggle Layer Visibility option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p style="text-align: center;"> <img id="image_CAE6765313B54646BFE13EC6E4E72BCF" href="assets/s7_togglelayervisibility.png" /> </p> </td> 
   <td colname="col2"> <p>Lets you turn on or off the visibility of the various layers that make up the Flash template file. </p> <p>Each time you turn the visibility of a layer on or off, the preview window is refreshed to update the display. </p> </td> 
  </tr> 
 </tbody> 
</table>

   (Optional) If the digital asset that you want to use for a banner is not available in the selected folder, you may need to upload it. Click **[!UICONTROL Upload]**, and then select the file and options that you want. The file is uploaded to the selected folder.

   >[!NOTE]
   >
   >If you want to use the upload functionality in the Scene7 asset viewer, be sure that the Scene7 account you use has the role of "SPS Company Admin" already set.

   See [Administration Setup](https://help.adobe.com/en_US/scene7/using/WS662101DF-D697-47a7-A7D8-B52FD8E94438.html) in the Scene7 Publishing System User Guide.

   <!-- 

r_upload_options.xml

 -->

   **Basic options**

<table id="table_2C280C623EC842B8801CAC46D536F5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Browse </p> </td> 
   <td colname="col2"> <p> Lets you browse to the file that you want to upload, publish, and then select for use as a banner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Overwrite </p> </td> 
   <td colname="col2"> <p>Files that you upload replace existing files with the same filename, within the selected folder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E-mail Preference </p> </td> 
   <td colname="col2"> <p> Lets you choose what email notification you get for the upload, or you can choose to not be notified for anything related to the upload job. </p> </td> 
  </tr> 
 </tbody> 
</table>

   **Advanced options**

   When you upload PostScript (EPS) or Illustrator (AI) image files, you can format them in various ways. You can rasterize the files, convert them to FXG for Template Publishing, maintain the transparent background, choose a resolution, and choose a color space.

   PSD (Photoshop Document files) are most often used in Scene7 to create templates. When you upload a PSD file, you can create a Scene7 template automatically from the file (select the **[!UICONTROL Create Template]** option).

   Scene7 Publishing System creates multiple images from a PSD file with layers if you use the file to create a template; it creates one image for each layer. 

<table id="table_AB77A02A60444D1AAF8B9491B757A6D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option group name </p> </th> 
   <th colname="col02" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Color Profile Options </p> </td> 
   <td colname="col02"> <p>Color Profile </p> </td> 
   <td colname="col2"> <p> Lets you choose from the following options: </p> 
    <ul id="ul_6927BC08CA2647EDB2C85DAD2B82AE31"> 
     <li id="li_CA3F44FF9C0F4CE987DCB0AF9303C2E4"> <span class="uicontrol"> Convert to SRGB </span> <p>Converts to SRGB (Standard Red Green Blue). SRGB is the recommended color space for displaying images on web pages. </p> </li> 
     <li id="li_FCCEE6B14CCD4246ADA152932010ABF1"> <span class="uicontrol"> Keep Original Color Space </span> <p>Retains the original color space. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Image Editing Options </p> </td> 
   <td colname="col02"> <p>Create Mask From Clipping Path </p> </td> 
   <td colname="col2"> <p>Create a mask for the image based on its clipping path information. This option applies to images created with image-editing applications in which a clipping path was created. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PostScript Options </p> <p>Illustrator Options </p> </td> 
   <td colname="col02"> <p>Processing </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Rasterize </span> option converts vector graphics in the file to bitmap format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Postscript Options </p> <p>Illustrator Options </p> </td> 
   <td colname="col02"> <p> Resolution </p> </td> 
   <td colname="col2"> <p> Determines the resolution setting. This setting determines how many pixels are displayed per inch in the file. The default is 150. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> PostScript Options </p> <p>Illustrator Options </p> </td> 
   <td colname="col02"> <p> Color Space </p> </td> 
   <td colname="col2"> <p>Lets you choose a color space for the Illustrator file. The RGB color space is preferable for online viewing. </p> <p>You can choose from the following color space options: </p> 
    <ul id="ul_0E83E2762A574480B243F963A7FB2ACD"> 
     <li id="li_B9FEC7D220D04CCABACD30839051DAE4"> <span class="uicontrol"> Detect Automatically </span> <p> Retains the color space of the PDF file. </p> </li> 
     <li id="li_ED0EB3B12BCF41C7AFC435447010B6FF"> <span class="uicontrol"> Force as RGB </span> <p> Converts to the RGB color space. </p> </li> 
     <li id="li_3FB5DD8887C540BC97148A4D63B38F72"> <span class="uicontrol"> Force as CMYK </span> <p> Converts to the CMYK color space. </p> </li> 
     <li id="li_6C018D3A4B254880AD41896E9F4AF3D9"> <span class="uicontrol"> Force as Grayscale </span> <p> Converts to the Grayscale color space. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> PostScript Options </p> <p>Illustrator Options </p> </td> 
   <td colname="col02"> <p> Maintain transparent background </p> </td> 
   <td colname="col2"> <p>Maintains the background transparency of the file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Photoshop Options </p> </td> 
   <td colname="col02"> <p> Maintain layers </p> </td> 
   <td colname="col2"> <p>Rips the layers in the PSD, if any, into individual assets. The asset layers remain associated with the PSD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Photoshop Options </p> </td> 
   <td colname="col02"> <p>Create Template </p> </td> 
   <td colname="col2"> <p> Creates a template from the layers in the PSD file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Photoshop Options </p> </td> 
   <td colname="col02"> <p> Extract Text </p> </td> 
   <td colname="col2"> <p> Extracts the text so that customers can search for keywords within a banner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Photoshop Options </p> </td> 
   <td colname="col02"> <p> Extend Layers </p> </td> 
   <td colname="col2"> <p>Extends the size of ripped image layers to the size of the background layer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Photoshop Options </p> </td> 
   <td colname="col02"> <p> Layer Naming </p> </td> 
   <td colname="col2"> <p>Layers in the PSD file are uploaded as separate images. You can select from the following options to decide how you want to name these images in the Scene7 Publishing System: </p> 
    <ul id="ul_C2A25177A07740CA90B32C638304D39F"> 
     <li id="li_477D5BFF7238454BBF0E04B22DE378F7"> <span class="uicontrol"> Use layer name from PSD file </span> <p>Names the images after their layer names in the PSD file. For example, a layer named <span class="codeph"> Price Tag </span> in the original PSD file becomes an image named <span class="codeph"> Price Tag </span>. However, if the layer names in the PSD file are default Photoshop layer names (Background, Layer 1, Layer 2, and so on), the images are named after their layer numbers in the PSD file, not their default layer names. </p> </li> 
     <li id="li_EB4173B884FC41328CFBDE27DA6D43AA"> <span class="uicontrol"> Use PSD file name and append number </span> <p>Names the images after their layer numbers in the PSD file, ignoring original layer names. Images are named with the Photoshop filename and an appended layer number. For example, the second layer of a file called <span class="codeph"> Spring Ad.psd </span> is named <span class="codeph"> Spring Ad_2 </span> even if it had a non-default name in Photoshop. </p> </li> 
     <li id="li_10B2D2DE2FD24BD08DB56D1D95ABA53D"> <span class="uicontrol"> Use PSD filename and layer name or number </span> <p>Names the images after the PSD file followed by the layer name or layer number. The layer number is used if the layer names in the PSD file are default Photoshop layer names. For example, a layer named <span class="codeph"> Price Tag </span> in a PSD file named <span class="codeph"> SpringAd </span> is named <span class="codeph"> Spring Ad_Price Tag </span>. A layer with the default name <span class="codeph"> Layer 2 </span> is named <span class="codeph"> Spring Ad_2 </span>. </p> </li> 
     <li id="li_5E57AC0719D4484B9C9BD14DB42B4455"> <span class="uicontrol"> Create folder based on the PSD filename </span> <p>Creates a folder for the layer images using the filename of the PSD. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Photoshop Options </p> </td> 
   <td colname="col02"> <p>Anchor </p> </td> 
   <td colname="col2"> <p>Specify how images are anchored in templates that are generated from the layered composition produced from the PSD file. </p> <p>By default, the anchor is the center. A center anchor allows replacement images to best fill the same space, no matter the aspect ratio of the replacement image. Images with a different aspect that replace this image, when referencing the template and using parameter substitution, effectively occupy the same space. Change to a different setting if your application requires the replacement images to fill the allocated space in the template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PDF Options </p> </td> 
   <td colname="col02"> <p>Processing </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Rasterize </span> option rips the pages in the PDF file and converts vector graphics to bitmap images. 
     <!--Choose this option to create an eCatalog. (This option is thedefault.)--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PDF Options </p> </td> 
   <td colname="col02"> <p> Resolution </p> </td> 
   <td colname="col2"> <p>Determines the resolution setting. This setting determines how many pixels are displayed per inch in the PDF file. The default is 150. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PDF Options </p> </td> 
   <td colname="col02"> <p> Color Space </p> </td> 
   <td colname="col2"> <p>Lets you choose a color space for the PDF file. Most PDF files have both RGB and CMYK color images. The RGB color space is preferable for online viewing. </p> <p>You can choose from the following color space options: </p> 
    <ul id="ul_44A8C39DEB21473F9375E3962F14D3C6"> 
     <li id="li_1046FA0017934C5EB7C0100F8F78507D"> <span class="uicontrol"> Detect Automatically </span> <p> Retains the color space of the PDF file. </p> </li> 
     <li id="li_561CCF705EDD451993D2DA2EB33F05F7"> <span class="uicontrol"> Force as RGB </span> <p> Converts to the RGB color space. </p> </li> 
     <li id="li_D9E8CF61C40140979484EDEF7DAD2C44"> <span class="uicontrol"> Force as CMYK </span> <p> Converts to the CMYK color space. </p> </li> 
     <li id="li_F3606B45C0F84BA594263EA12243F67A"> <span class="uicontrol"> Force as Grayscale </span> <p> Converts to the Grayscale color space. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PDF Options </p> </td> 
   <td colname="col02"> <p>Auto-Generate eCatalog from multiple page PDF </p> </td> 
   <td colname="col2"> <p> Automatically creates an eCatalog from the PDF file. The eCatalog is named after the PDF file you uploaded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> PDF Options </p> </td> 
   <td colname="col02"> <p>Extract keywords </p> </td> 
   <td colname="col2"> <p>Extracts words from the PDF file so that the file is searchable by keywords. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. In the right pane, click the image, template, or Flash file that you want.

   The [!DNL Pick An Asset] pop-up window appears. 
1. (Optional) In the [!DNL Pick An Asset] pop-up window, in [!DNL Actions] drop-down list, do any one of the following:

* Click **[!UICONTROL Move]**. In the [!DNL Select a folder to move to] dialog box, select the folder where you want to move the digital asset. Click **[!UICONTROL Move]**.

  You can also select multiple digital assets that you want to move to another folder. 

* Click **[!UICONTROL Delete]**. In the [!DNL Delete Selected Assets] dialog box, click **[!UICONTROL Delete]**.

  You can also select multiple digital assets that you want to delete from the folder. 

* Click **[!UICONTROL Rename]**. In the [!DNL Enter a new name for] dialog box, in the text field, type a new name for the digital asset. Click **[!UICONTROL Rename]**.

1. (Optional) Depending on the digital asset that you selected, in the left pane of the [!DNL Pick an Asset] pop-up window, set the options that you want.
1. Click the asset to select it for use as a banner.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Editing a banner using Adobe Scene7 {#task_C3E782477FBF428ABEA220751781ACA9}

Use [!DNL Edit Banner] to change the properties and parameters of a banner that you have added using Adobe Scene7.

<!-- 

t_editing_a_banner_using_adobe_scene7.xml

 -->

If you added a banner by adding HTML code, you edit the banner using site search/merchandisng instead.

See also [Editing a banner](../c-about-design-menu/c-about-banners.md#task_D4081083BE7B40F5A003D1A2F1435AEA).

**To edit a banner using Adobe Scene7** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Banners]**.
1. On the [!DNL Banners] page, click  ![](assets/icon_edit_16.gif)

   above a banner thumbnail that has a S7 icon in the lower-left corner of the banner window.
1. On the [!DNL Change Parameter] page, set the options that you want.
1. When you are finished editing the banner, click **[!UICONTROL Save]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Deleting banners {#task_32F3BADC481E4E8984B2AA04B96052EB}

You can delete staged banners that you no longer need or want to use either one at a time, or as a group.

<!-- 

t_deleting_banners.xml

 -->

**To delete banners** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Banners]**.
1. (Optional) Do one or more of the following:

    * On the [!DNL Banners] page, select the banner type you want to find from the **[!UICONTROL Find banner of type]** drop-down list. If desired, specify a tag name in the **[!UICONTROL with tag]** text field, or a banner type name in the **[!UICONTROL with name]** text field. Click **[!UICONTROL Find.]** 
    
    * On the **[!UICONTROL Sort]** drop-down list, select how you want the list of banners ordered. 
    * On the **[!UICONTROL Show]** drop-down list, select the number of banners that you want to load into the current page that you are viewing.

1. Do one of the following:

    * In the upper-left corner of any banner box, click the checkbox of each banner that you want to delete. 
    * On the upper-bar of the [!DNL Banners] page, check **[!UICONTROL Select all]** to select every banner that is loaded on the currently displayed page.

1. On the **[!UICONTROL Bulk Actions]** drop-down list, click **[!UICONTROL Delete]**.
1. In the [!DNL Confirmation Action] dialog box, click **[!UICONTROL OK]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Previewing banners {#task_6AB1F81A984A4DC2ACACD1FE030545E2}

You can browse banners that you have added to the [!DNL Banners] page to view their full-size. Any CSS in the template that affects the banner is not shown.

<!-- 

t_previewing_banners.xml

 -->

**To preview banners** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Banners]**.
1. (Optional) Do one or more of the following:

    * On the [!DNL Banners] page, select the banner type you want to find from the **[!UICONTROL Find banner of type]** drop-down list. If desired, specify a tag name in the **[!UICONTROL with tag]** text field, or a banner type name in the **[!UICONTROL with name]** text field. Click **[!UICONTROL Find.]** 
    
    * On the **[!UICONTROL Sort]** drop-down list, select how you want the list of banners ordered. 
    * On the **[!UICONTROL Show]** drop-down list, select the number of banners that you want to load into the current page that you are viewing.

1. On the [!DNL Banners] page, click a banner thumbnail to view its full size.
1. Do one of the following:

    * In the banner preview dialog box, click the left or right arrow to navigate and view the full-size banners that you have added. 
    * Click the close button to dismiss the banner preview dialog box, and return to the [!DNL Banners] page.

## Pushing banners live {#task_161F4FEC8362474296A566E64BF05B97}

You can push one or more selected banners live to your website.

<!-- 

t_pushing_banners_live.xml

 -->

Or, if you prefer, you can push live all changes to any banner, using the **[!UICONTROL Push Live]** option near the bottom of the [!DNL Banners] page.

See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

**To push banners live** 

1. On the product menu, click **[!UICONTROL Design]** > **[!UICONTROL Banners]**.
1. (Optional) Do one or more of the following:

    * On the [!DNL Banners] page, select the banner type you want to find from the **[!UICONTROL Find banner of type]** drop-down list. If desired, specify a tag name in the **[!UICONTROL with tag]** text field, or a banner type name in the **[!UICONTROL with name]** text field. Click **[!UICONTROL Find]**. 
    
    * On the **[!UICONTROL Sort]** drop-down list, select how you want the list of banners ordered. 
    * On the **[!UICONTROL Show]** drop-down list, select the number of banners that you want to load into the current page that you are viewing.

1. Do one of the following:

    * In the upper-left corner of any banner box, click the checkbox of each banner that you want to delete. 
    * On the upper-bar of the [!DNL Banner] page, check **[!UICONTROL Select all]** to select every banner that is loaded on the currently displayed page.

1. On the **[!UICONTROL Bulk Actions]** drop-down list, click **[!UICONTROL Push live]**.
1. In the [!DNL Confirmation Action] dialog box, click **[!UICONTROL OK]**.
1. (Optional) On the [!DNL Banners] page, click **[!UICONTROL History]** to revert any changes you have made.

   See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
