---
description: You can use Excluded Words to specify frequently used phrases and common words, such as "a" and "the", that you want to leave out of search results.
seo-description: You can use Excluded Words to specify frequently used phrases and common words, such as "a" and "the", that you want to leave out of search results.
seo-title: About Excluded Words
solution: Target
title: About Excluded Words
topic: Linguistics,Site search and merchandising
uuid: 1c879462-1b19-44f6-a3b2-20aa786b3221
index: n
internal: n
snippet: y
---

# About Excluded Words{#about-excluded-words}

You can use Excluded Words to specify frequently used phrases and common words, such as "a" and "the", that you want to leave out of search results.

## About Excluded Words {#concept_9DB67BD2F0DC43AC88741003D9F39812}

You can use Excluded Words to specify frequently used phrases and common words, such as "a" and "the", that you want to leave out of search results. 

See also [About Searches](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

Without Excluded Words, searches that contain these words may identify numerous irrelevant results. When you exclude words and phrases, search results are omitted that match only the excluded terms that you have specified. If a search query contains an excluded word, only the non-excluded words are used to find documents.

Excluded search words are not highlighted in the search results. However, the relevance score of each result is influenced by the excluded words. In other words, excluded words are ignored when finding documents, but they are still used when ranking the documents on the search results page. Before the effects of the Excluded Words settings (or changes to these settings) are available to customers, be sure you regenerate your site index.

When you enter words to exclude from the search results, you separate words or phrases from each other with commas. You can enter one or more exclude words per line. The following is an example of excluded words on separate lines and divided by commas.

![](assets/excluded_words_1.jpg)

Using the example list of excluded words above, if your customer searches for "the united states of america", the word "the" and the word "of" are excluded from the search. Instead, the search finds all pages that contain the words "united", "states", and "america". Pages that contain only the word "of" or "the" are not shown.

Some sites contain specific phrases on most, or all, pages. For example, a website about tourism in New York City could contain the words New York in the title of every page. Consider adding this phrase, and others like it, to the exclude list:

![](assets/excluded_words_2.jpg)

When a phrase is excluded, the individual words that make it up are still used as search terms. Only when a visitor searches for the exact words, in the exact order of an excluded phrase, is the phrase excluded from the search results. Using the example above, If a customer searched for the "new york ballet", the word "the" and the phrase "new york" are excluded; only pages that contain the word "ballet" are returned as a search result. On the other hand, a search for "new buildings" or "duke of york" still finds pages that contain the word "new" or "york", respectively. 

## Configuring Excluded Words {#task_60BF6BB7A66C48479D2BBB32C0F38CDE}

You can exclude frequently used phrases and common words from your search results.

<!-- 

t_configuring_excluded_words.xml

 -->

You can enter one or more words per line. Separate each word with commas as in the following example:

![](assets/excluded_words_1.jpg)

You can choose to show search results when all the words in the customer's search are excluded words. For example, if you have excluded the word "the" and a customer chooses to search only for "the", the search results show any page that contains the word "the". This result is true even though the word "the" is excluded. If you do not check this option, the customer does not get any search results. This setting has no effect if the search contains at least one non-excluded word.

**To configure excluded words** 

1. On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Excluded Words]**.
1. On the [!DNL Excluded Words] page, in the **[!UICONTROL Words and Phrases]** text field, enter the words that you want to exclude from search results.
1. (Optional) Click **[!UICONTROL Show results when all words in the query are excluded words]**.

   When all words in the customer's search are excluded words, all of the words are used together to perform the search. 
1. Click **[!UICONTROL Save Changes]**.
1. To preview the results of your changes, click **[!UICONTROL regenerate your staged site index]** to rebuild your staged website index.

   See [Running a full index of a live or staged website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   See [Running an incremental index of a live or staged website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB). 
1. (Optional) On the product menu, click **[!UICONTROL Linguistics]** > **[!UICONTROL Excluded Words]**, and then do one of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

