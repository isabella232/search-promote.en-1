---
description: Staging lets you test and preview changes to your settings and configurations without impacting your live index.
seo-description: Staging lets you test and preview changes to your settings and configurations without impacting your live index.
seo-title: About Staging
solution: Target
title: About Staging
topic: Staging,Site search and merchandising
uuid: 2e5889a6-2e9c-4ac7-9d6e-d35e7cafda5b
index: n
internal: n
snippet: y
---

# About Staging{#about-staging}

Staging lets you test and preview changes to your settings and configurations without impacting your live index.

## About Staging {#concept_08B8F3CA1F4241108F14BA7FC7806CA7}

Staging lets you test and preview changes to your settings and configurations without impacting your live index. 

See also [Element ID :context_A5783D07C72042EC8886F300FFF62C50](c-about-simulator.md#context_A5783D07C72042EC8886F300FFF62C50).

Any page that has the staging options **[!UICONTROL Push All Live]** or **[!UICONTROL View Live Settings]** means that all the settings on that page can be staged. The exceptions are the web pages in Index. The pages in this area are either explicitly for the staged index or the live index to let you directly control the two indexes independently.

You can stage almost anything including your index. Some exceptions include account specific settings that impact both your staged and live environment simultaneously and the scheduling of indexing operations. By default when you save any changes to a setting that can be staged, it is automatically staged.

When the **[!UICONTROL Push All Live]** or the **[!UICONTROL View Lives Settings]** options are not enabled (dimmed) it means that the staged settings on that page are the same as the live settings.

For an item that is staged, note that the live version of the settings is read-only; it can only be manipulated by pushing the staged settings live.

## About History on Staged pages {#section_5BE780AFF26A450A9EFF4000DE53531B}

Most staged settings have a [!DNL History] option in the upper-right area of the page. When you click **[!UICONTROL History]**, it lets you revert any changes that you have recently made to the particular staged page that you have open.

You can also view the Change Log for an alternate view of History. Every time a change is applied, a backup version of the underlying data file is created. The Change Log shows each such revision, showing the version number, the e-mail address of the user who performed the changes, and the date on which the backup was made. The entry with a bold version value represents the current version.

See [Viewing the Change Log](c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

## The Manage Stage-Live Settings page {#section_E72B8CAF516345A5B6B6783CF6E512EE}

Besides offering the **[!UICONTROL Push All Live]** and **[!UICONTROL View Live Settings]** options directly from within a given page, you can also use the **[!UICONTROL Manage Stage-Live Settings]** page to do the same thing. The **[!UICONTROL Manage Stage-Live Settings]** page, available from the main product menu, is a central location that shows you all the settings in your account that are currently staged. You can push all settings live, push only selected settings live, or you can delete settings. As a best practice, however, always push all staged items live to avoid any interdependency issues.

The settings on the page are grouped into categories. You can expand each category to show which page's settings are staged. Currently, dependencies are not tracked within the stage manager. Therefore, it is recommended that you push everything live at once except for the index.

You can push a staged index live. Be sure that you first check that your staged index is not stale or corrupted. If you make a mistake and push the staged index live you can roll back an old live index. Pushing a staged index live usually takes less than 30 seconds.

## Testing a staged setting or index {#section_6800E52D20854A779946EAB600801F12}

On pages that support a test control, you can test against the staged or live settings. When you view the staged settings, the staged setting is used for the test. Similarly, when you are viewing the live setting the test uses the live settings. In the templates section, all tests are done against the staged version of the index. To search a staged index, set the `sp_staged` CGI parameter equal to 1. In turn, this indicates that you want to use the staged index. If a staged index does not exist, your live index is searched and any staged search-time settings are applied as appropriate.

See also [Backend search CGI parameters](c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). 

## Viewing live settings {#task_401A0EBDB5DB4D4CA933CBA7BECDC10F}

You can review the live version of the settings from any staged page.

<!-- 

t_viewing_live_settings.xml

 -->

If the **[!UICONTROL View Live Settings]** option is not enable (dimmed), it means that the stage settings for that page and the live settings are already in synch.

**To view live settings** 

1. On any page that has staged settings, click **[!UICONTROL View Live Settings]** to see the live version of the settings.
1. Optionally, do one of the following:

    * Click **[!UICONTROL View]** to see the current options that are selected for the staged setting. 
    * Click **[!UICONTROL View Stage Settings]** to return to the staged setting where you can edit or delete the setting.

## Pushing stage settings live {#task_44306783B4C0408AAA58B471DAF2D9A4}

You can push settings live from any staged page view or from the central **[!UICONTROL Manage Stage-Live Settings]** page .

<!-- 

t_pushing_live_settings_live.xml

 -->

When the **[!UICONTROL Push Live]** option is enabled (undimmed) on a page it means that there is a setting that is staged. Or, it means that a setting has edits and when you save, the setting becomes staged. When you click this option any unsaved edits are saved to the staged area. If there are no pending edits, the page's settings are immediately pushed live.

**To push staged settings live** 

1. Do one of the following:

    * On any page that has "Staged" selected as the View, click **[!UICONTROL Push Live]**. 
    * On the product menu, click **[!UICONTROL Staging]**. On the **[!UICONTROL Manage Stage-Live Settings]** page, do one of the following:

    * Use the settings tree to check only those settings that you want to push live, and then click **[!UICONTROL Push Selected Live]**. 
    * Click **[!UICONTROL Push All Live]**.

## Deleting stage-live settings from a central location {#task_B72BEA9269704B1399600A9CA273369B}

If you have many settings to delete, you can use the **[!UICONTROL Manage Stage-Live Settings]** page to delete settings from one, central location.

<!-- 

t_deleting_staged_settings_from_a_central_location.xml

 -->

**Warning**: When you click **[!UICONTROL Delete Selected]**, all checked settings are immediately deleted; there is no confirmation dialog box to verify that you really want to delete the selected settings. Also, there is no History feature associated with the page. Therefore, you cannot undo your deletion.

**To delete stage-live settings from a central location** 

1. On the product menu, click **[!UICONTROL Staging]**.
1. On the **[!UICONTROL Manage Stage-Live Settings]** page, use the settings tree to check only those settings that you want to delete.
1. Click **[!UICONTROL Delete Selected]**.
