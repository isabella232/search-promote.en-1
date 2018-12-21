---
description: Use the Account Options menu to update your account settings, set merchandising preferences, or remove your own Search&Promote account.
seo-description: Use the Account Options menu to update your account settings, set merchandising preferences, or remove your own Search&Promote account.
seo-title: About the Account Options menu
solution: Target
subtopic: Account Options
title: About the Account Options menu
topic: Settings,Site search and merchandising
uuid: db3f9977-7355-4974-8027-52702efd2d4d
index: y
internal: n
snippet: y
---

# About the Account Options menu{#about-the-account-options-menu}

Use the Account Options menu to update your account settings, set merchandising preferences, or remove your own Search&Promote account.

## Configuring your account settings {#task_80A38D0C8E4F453395BD67B81E4B45D9}

Manage account settings such as the website name and address, time zone, and more. Or, view your account number.

<!-- 

t_configuring_your_searchpromote_account_settings.xml

 -->

**To configure your account settings** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Account Settings]**.
1. On the [!DNL Account Settings] page, set the options that you want.

   <!-- 

r_account_settings_options.xml

 -->

<table id="table_7660BFC618684030A510776F542A6904"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Web Site Name </p> </td> 
   <td colname="col2"> <p>Required. </p> <p>A short name that is used to describe your website/account. This option is useful if you have multiple websites. </p> <p> <p>Note:  You must contact Technical Support to select one or more names that you want to use. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Web Site Address </p> </td> 
   <td colname="col2"> <p>Required. </p> <p>The URL address of your website. The address specified here is used as the main website entry point. </p> <p>See also <a href="../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45" type="task" format="dita" scope="local"> Adding multiple URL entry points that you want indexed </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Time Zone (for reports and scheduling) </p> </td> 
   <td colname="col2"> <p>The time zone that is used for reports and publish operations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Validate Template Tag Attributes on Save </p> </td> 
   <td colname="col2"> <p>Validates all attributes in <span class="codeph"> &lt;guided-*&gt; </span> and <span class="codeph"> &lt;search-*&gt; </span> when you save a template in the Staged Template Editor. </p> <p>See <a href="../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3" type="task" format="dita" scope="local"> Editing a presentation or a transport template </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Validate Template References to GS Objects on Save </p> </td> 
   <td colname="col2"> <p> Checks the existence of Guided Search objects, such as menus, facets, breadcrumbs, custom vars, and templates, that are referred to in <span class="codeph"> &lt;guided-*&gt; </span> tags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enforce stringent template syntax checking </p> </td> 
   <td colname="col2"> <p>Makes the template validator more strict and enables the checking of things such as unbalanced quotes and &lt;&gt; symbols. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Account Number </p> </td> 
   <td colname="col2"> <p>You cannot edit the account number. It is for display purposes only. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.

## Configuring integration with Adobe CQ5 {#task_EA2FC2C24960498DAE01A1AB769D2F14}

You can configure the integration of site search/merchandising with Adobe CQ5.

<!-- 

t_configuring_integration_with_adobe_cq.xml

 -->

**To configure integration with Adobe CQ5** 

1. Obtain your Member ID and Account ID by doing the following:

* Login to your site search/merchandising account. 
* In the URL path, copy the member ID and the account ID.

  For example, if the URL path to your account were `http://searchandpromote.mycompany.com/px/home/?sp_id=00123a4b-sp1234a5b6`, the member ID would be `00123a4b` and the account ID would be `sp1234a5b6`.

1. In Adobe CQ5, use the Cloud Services tab to create your site search/merchandising configuration.

   Use the copied Member ID and Account ID for the respective settings. 
## Configuring Merchandising preferences {#task_7AC7B9F5D9F44E10AB5BC0B8CB31C37A}

Manage Merchandising preferences such as the default rule builder and default search term.

<!-- 

t_configuring_merchandising_preferences.xml

 -->

**To configure Merchandising preferences** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Merchandising Preferences]**.
1. On the [!DNL Merchandising Preferences] page, set the options that you want.

   <!-- 

r_merchandising_preferences_options.xml

 -->

<table id="table_C566C46F6A4A47EF9D892CF6186E89B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Trigger Group Dominant Threshold </p> </td> 
   <td colname="col2"> <p> The threshold percentage to apply to "group dominant" results-based triggers that specify "use account default". </p> <p>Changing this setting can immediately effect live searches, therefore use with caution. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Group Definition </p> </td> 
   <td colname="col2"> <p>The number of results in a group for the merchandising console. The maximum is 50,000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'Merchandising Document ID' (MDI) field </p> </td> 
   <td colname="col2"> <p> The field you specify must "uniquify" the search results that you want to manipulate by way of 'single result' results-based triggers and actions. </p> <p>Using the pre-defined URL field works in some cases, but is not recommended. A user-defined meta field with a unique ID for every page (like SKU or product_id for example) would be much more efficient than using the URL field. Specifying 'none' disables 'single result' results-based triggers &amp; actions in the rules manager. Changing this option only applies to rules that are saved going forward; existing rules continue to use the MDI with which they were originally saved. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default VRB (Visual Rule Builder) search term </p> </td> 
   <td colname="col2"> <p> Lets you customize the initial search term that is used in Visual Rule Builder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>VRB Default Search </p> </td> 
   <td colname="col2"> <p>This setting lets you set what default search is initially selected in Visual Rule Builder. </p> <p> This setting is only relevant for implementation with multiple searches. The VRB lets you select what search the trigger or action that the defined group applies to. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>VRB / Simulator Timeout </p> </td> 
   <td colname="col2"> <p>The VRB and Simulator sends searches through a proxy server which are slower than your production search. Under certain circumstances, such as slow loading assets, the VRB or simulator can timeout. You can increase, or decrease, the number of seconds that the user interface must wait before it stops. You seldom need to increase this setting from the default of 60. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.

## Configuring access to your Adobe Scene7 account {#task_CEFF88C2033D41D0B2FE86C435EDAC6D}

Link your site search/merchandising account to Adobe Scene7 so you can easily add banner ads to your website using uploaded digital assets from Adobe Scene7.

<!-- 

t_configuring_your_scene7_account.xml

 -->

See [About Banners](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA).

See [Adding a banner using Adobe Scene7](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

**To configure access to your Adobe Scene7 account** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Scene7 Configuration]**.
1. On the [!DNL Scene7 Configuration] page, set the options that you want.

   <!-- 

r_scene7_configuration_options.xml

 -->

<table id="table_C6C322C0DF0F4113B7D5729EC6A2EA9D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Region </p> </td> 
   <td colname="col2"> <p>Required. Identifies the region of the world where your Scene7 account accesses the various Scene7 servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default Company </p> </td> 
   <td colname="col2"> <p>Identifies the name of the company that is associated with your Scene7 account. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Email </p> </td> 
   <td colname="col2"> <p>Required. Identifies your email address that is used for Scene7 sign-in and communications. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Password </p> </td> 
   <td colname="col2"> <p>Required. Your Scene7 sign-in password. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enabled </p> </td> 
   <td colname="col2"> <p>Enables all the Scene7 controls within site search/merchandising. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Test </p> </td> 
   <td colname="col2"> <p>Verifies that your Scene7 region name, email address, and password details are correct. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Optional) Click **[!UICONTROL Test]** to verify that your Scene7 region name, email address, and password details are correct.
1. Click **[!UICONTROL Save Changes]**.

## Configuring Adobe Analytics Redirector {#task_2C9DE333FD7246E4A460FC0F55204160}

If you use [!DNL Adobe Analytics] for tracking site visitors, you can use [!DNL Adobe Analytics Redirector] in site search/merchandising to track all HTTP redirects with [!DNL Adobe Analytics].

<!-- 

t_configuring_adobe_analytics_redirector.xml

 -->

**To configure Adobe Analytics Redirector** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Adobe Analytics Redirector]**.
1. On the [!DNL Adobe Analytics Redirector] page, set the options that you want.

   <!-- 

r_adobe_analytics_redirector_options.xml

 -->

<table id="table_5AFDBEF161A94707BA1AB847BBD62A62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Option </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Turn on Adobe Analytics Redirector feature </p> </td> 
   <td colname="col2"> <p>Turns on tracking HTTP redirects with Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tracking Server </p> </td> 
   <td colname="col2"> <p> Identifies your Adobe Analytics tracking server name. </p> <p>To find out the tracking server name, </p> <p> 
     <ol id="ol_D17B77E81F8D40D0948415CD60839BE3"> 
      <li id="li_BE58DBA104D44F0DB6C64AD3F12CEA97"> In Adobe Analytics, click <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Admin Console </span> &gt; <span class="uicontrol"> Code Manager </span>. </li> 
      <li id="li_67A93D17C3A14874928C6DC4FF2D4784"> In the <span class="wintitle"> Options </span> group box, select a report suite from the respective drop-down list. </li> 
      <li id="li_5AAB004AC58441DBB0F813BDE30EFFD4"> Click <span class="uicontrol"> Generate Code </span>. </li> 
      <li id="li_E80368993F4D4DD69E37509FF4348B36"> On the <span class="wintitle"> Code Manager </span> page, click the <span class="uicontrol"> Core Javascript File tab </span>. </li> 
      <li id="li_991BDCDDA41A445F85CEEAAE9A46A304"> In <span class="wintitle"> Config Section </span>, find line the looks like the following: <p> 
        <codeblock>
          s.trackingServer="yourcompany.122.2o7.net" 
          
        </codeblock> </p> <p>The tracking server name, in this case, is <span class="codeph"> "yourcompany.122.2o7.net" </span> </p> </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Suite ID </p> </td> 
   <td colname="col2"> <p> Identifies your report suite ID. </p> <p>To find out your report suite ID, </p> <p> 
     <ol id="ol_4FD7B2459358486DBDB130426131D16A"> 
      <li id="li_9AF624CEB128453C808892EEE385D5D1"> In Adobe Analytics, click <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Admin Console </span> &gt; <span class="uicontrol"> Report Suites </span>. </li> 
      <li id="li_AAC47EAA04144A67BDCB5C7B8D8098E9"> Look at <span class="wintitle"> Report Suite Id </span> column in the table to find the ID. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom Parameters </p> </td> 
   <td colname="col2"> <p>Lets you add custom parameters to the Adobe Analytics redirect URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Set the case of all custom values to </p> </td> 
   <td colname="col2"> <p>Lets you standardize on the casing that is used for any custom parameter values that you specified above. Adobe Analytics is case-sensitive so there is a reason to unify the case of values. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Adobe Analytics Redirector] page, do any of the following:

    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Configuring root files {#task_5F175C8743FB49A2A003813CBF7C56BF}

Manage root files in the root folder of your website.

<!-- 

t_configuring_root_files.xml

 -->

**To configure root files** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Root Files]**.
1. On the [!DNL Root Files] page, browse to the root files you want to upload.

   <!-- 

r_root_file_options.xml

 -->

<table id="table_B51AD4F407894E44B70F44D58BE67C3B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Root file </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>favicon.ico </p> </td> 
   <td colname="col2"> <p> The icon of the site. Usually it is shown in the address bar of the customer's browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>robots.txt </p> </td> 
   <td colname="col2"> <p>Allows or disallows bots to access certain parts of the website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sitemap.xml </p> </td> 
   <td colname="col2"> <p>The XML file with a list of all pages that are available on the website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>crossdomain.xml </p> </td> 
   <td colname="col2"> <p>Allows or disallows Flash Player to access files across domains. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Root Files] page, do any of the following:

    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Transferring account ownership to another account user {#task_47E3C66CC6374274830DA10171E0CF17}

As an account owner, if you intend to cancel your login, you have to first transfer ownership to another active account user. You can use [!DNL Transfer Ownership] to accomplish this task.

<!-- 

t_transferring_account_ownership_to_another_account_user.xml

 -->

You can transfer ownership to any existing site search/merchandising account user.

When transfer of ownership is complete, the new account owner receives an e-mail notification, and the former owner is relieved of the restrictions and responsibilities of that position.

There can only be one owner per account. If you transfer your ownership to another user, you no longer have ownership privileges.

See [Canceling your login](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

See [Removing an account](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32).

See [Removing yourself from an account](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F).

**To transfer account ownership to another account** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Transfer Ownership]**.
1. On the [!DNL Transfer Ownership] page, click the user whom you want to take ownership of your account.
1. Click **[!UICONTROL Transfer]**.

## Removing an account {#task_975178D5B9444BF8B52D72B897A49C32}

You can remove an account entirely from site search/merchandising. When you do so, you and any other users of your account no longer have access to it.

<!-- 

t_removing_an_account.xml

 -->

When you remove your account, it can no longer be used to index or search your live site. Also,

To allow others users to continue using this account, you can transfer ownership to a different user and then remove yourself as a user of the account.

See [Transferring account ownership to another account user](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17).

If you have other accounts, after you remove the current account, you are taken to the first account that is listed in your login.

See [Removing yourself from an account](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F).

See [Canceling your login](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

**To remove an account** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Account]**.
1. (Optional) In the [!DNL Reason for Removal] field, enter a reason for the account removal.
1. Click **[!UICONTROL Remove Account]**.

## Removing yourself from an account {#task_C56F5AB87B664BAAAC2FD2F15003E73F}

You can remove yourself from a site search/merchandising account.

<!-- 

t_removing_yourself_from_an_account.xml

 -->

When you remove yourself from an account, you can no longer access it and you cannot edit account settings or index your site with it.

To regain access to the account, ask a current account user to reinstate you.

See [Canceling your login](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

See [Removing an account](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32).

See [Transferring account ownership to another account user](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17).

**To remove yourself from an account** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Yourself]**.
1. Click **[!UICONTROL Remove Yourself]**.
