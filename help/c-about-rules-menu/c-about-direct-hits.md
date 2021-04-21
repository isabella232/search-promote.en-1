---
description: Direct hits let you redirect a customer to a specified URL when the customer searches for a matching term. This kind of functionality lets you improve the navigation of the search of your website.
solution: Target
title: About Direct Hits
topic-legacy: Rules,Site search and merchandising
uuid: 374d63c8-2b82-4165-b543-05b587757baa
exl-id: 251dfa47-f55a-469c-8fca-e187877b7759
---
# About Direct Hits{#about-direct-hits}

Direct hits let you redirect a customer to a specified URL when the customer searches for a matching term. This kind of functionality lets you improve the navigation of the search of your website.

## Using Direct Hits {#concept_C5EE074A19FD4D5B8DD21DB575E35565} 

Direct hits consist of two main elements: the URL of your website, and one or more comma-delimited search terms. Direct hits are specified as follows:

```
    website_URL: term
    website_URL: term, term, term
```

For example, suppose that you have a corporate website with a page that specifies all of your terms and conditions. When a customer searches for your terms and conditions, rather than showing the results, you can redirect the customer to your terms and conditions page.

```
    https://www.mycompany.com/policies.asp?article=terms: terms and conditions, terms, conditions, security
    https://www.mycompany.com/press/news.asp: press releases, press
```

If the query term does not match any direct hits, search results are returned in the usual manner. 

## Configuring direct hits {#task_64DFB8C554874C699FCC0C2F26C3669F}

You can specify search terms that redirect a web browser to a URI instead of returning search results.

<!-- 

t_configuring_direct_hits.xml

 -->

Blank lines and comment lines beginning with a '#' (hash) character are permitted.

**To configure direct hits** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]**.
1. In the [!DNL Direct Hits] field, enter the URL of your website, and one or more comma-delimited search terms.
1. Click **[!UICONTROL Save Changes]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testing direct hits {#task_1E2EA833BF90423AA0DD8C5BBFE77445}

Before you push direct hit rules live, you can test direct hits by entering a term.

<!-- 

t_testing_direct_hits.xml

 -->

If you test a term that is not covered by a direct hit rule, a message is displayed letting you know. Under such a scenario, if the direct hit rule was live on your website, search results would be returned as usual. If you test a term that is covered by a direct hit rule, a message is displayed letting you know that a redirect to the specified URL has occurred.

**To test direct hits** 

1. On the product menu, click **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]**.
1. In the [!DNL Test Direct Hits] field, enter a search term, and then click **[!UICONTROL Test]**.
1. (Optional) Do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
