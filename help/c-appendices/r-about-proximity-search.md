---
description: Proximity Search lets you associate a unique location with any page on your website, and then search and sort results by proximity (distance) from a given location.
seo-description: Proximity Search lets you associate a unique location with any page on your website, and then search and sort results by proximity (distance) from a given location.
seo-title: About proximity search
solution: Target
title: About proximity search
topic: Appendices,Site search and merchandising
uuid: 88b2af15-b0c9-4756-b6f0-b71148a8278d
index: y
internal: n
snippet: y
---

# About proximity search{#about-proximity-search}

Proximity Search lets you associate a unique location with any page on your website, and then search and sort results by proximity (distance) from a given location.

For example, suppose you have populated pages on your website with United States postal ZIP code metadata such as the following:

```
<meta name="zipcode" content="84057">
```

Then you configure your account to index your ZIP code metadata. In **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** > **[!UICONTROL Add New Field]**, on the [!DNL Add Field] page, you set the following options:

* Field name: `zip` 
* Meta Tag Name(s): `zipcode` 
* Data Type: **[!UICONTROL Location]** 
* Sorting: **[!UICONTROL Ascending]** 
* Default Units: **[!UICONTROL Miles]**

After indexing your site, you perform the following search:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_s=zip_proximity
```

The result set contains any documents located within 100 miles of ZIP code 84057, sorted in ascending order of distance from this ZIP code.

You can also use telephone area codes for United States locations. Or, you can use latitude/longitude pairs to specify locations in your site metadata and in your search criteria. The location type is automatically determined from the form of the data that is provided.

Three-digit location values ("DDD", where each "D" represents a decimal digit from 0-9) are treated as a United States telephone area code.

Five or five-dash-four digit location values ("DDDDD" or "DDDDD-DDDD") are treated as a United States postal ZIP code.

Location values in the exact form of "±DD.DDDD±DDD.DDDD" are treated as a latitude/longitude pair. The first signed numeric value specifies latitude and the second signed numeric value represents longitude.

**Important**: If you specify a positive latitude value, or a positive longitude value, or both, the "+" character in the URL must be encoded as `%2b`. Otherwise, the "+" is interpreted as a space, and the value is not recognized as a valid location. For example, suppose you had a latitude value of +49.2394 and longitude value of -123.1892. The location portion of the URL, with "+" encoded, would look like the following:

```
...&sp_q_location_1=%2b49.2394-123.1892...
```

* Positive latitude values represent degrees North of the equator. 
* Negative latitude values represent degrees South of the equator. 
* Positive longitude values represent degrees East of Prime Meridian. 
* Negative longitude values represent degrees West of Prime Meridian.

For example, the value "+48.8577+002.2950" represents 48.8577 degrees North of the equator, 2.295 degrees East of the Prime Meridian, the exact location of the Eiffel Tower in Paris, France. The numeric signs and each digit are required, even the leading and trailing zeros. For example, the three values "48.8577+2.2950", "+48.8577+2.2950", and "+48.8577+02.295" are not locations. The first value is missing the leading sign on the latitude. The second value is missing the two leading zeros on the longitude. The third value is missing the trailing zero on the longitude. Be sure that you examine your index log carefully for any location-related problems.

When you search by proximity there is a special "proximity output field" created for that search. The field is populated with the relative distance between the location that is specified in the search criteria, and the location that is associated with each search result. This special field is named for the location-type field that is used in the search criteria with "_proximity" added to the end.

In the example search above, the results are sorted in ascending order of "zip_proximity." That is, the distance between the specified ZIP code (84057) and each result's "zip" field location. You can also use this special "proximity output field" to display the relative distance for each search result, in either kilometers or miles, using the `<Search-Display-Field>` Search template tag.

See [Search template tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

You can also search without the sp_s option. In such case, the results are sorted by score (sp_s=0, which is the default).The score is influenced by the relative distance of each result from the proximity search location that is specified by way of the sp_q_location[_#] parameter. A new cgi parameter sp_q_max_relevant_distance[#] is added, to optionally control the relevance calculation applied to proximity searches.

The following is a proximity-relevance search example:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_q_2=shirt&sp_x_2=title&sp_q_max_relevant_distance_2=50
```

The result set contains any documents located within 100 miles of ZIP code 84057 and contain the word "shirt" in title field, sorted by scoring that influenced by proximity-relevance scoring. A perfect relevance score for the proximity component would represent a distance of 0. A minimum relevance score for the proximity component would represent a distance just over 50 miles.

You can learn more information about proximity search by reviewing `sp_location`, `sp_location_#`, `sp_q_min`, `sp_q_min_#`, `sp_q_max`, `sp_q_max_#`, and `sp_s` in the Search CGI Parameters reference topic.

See [Search CGI parameters](../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890).

See [Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5). 
