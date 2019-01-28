---
description: Use the Rewrite Rules menu to set crawl and search URL and title rules.
seo-description: Use the Rewrite Rules menu to set crawl and search URL and title rules.
seo-title: About the Rewrite Rules menu
solution: Target
subtopic: Rewrite Rules
title: About the Rewrite Rules menu
topic: Settings,Site search and merchandising
uuid: 77ee84dd-fdba-4d34-ae8e-2fe786599800
index: n
internal: n
snippet: y
---

# About the Rewrite Rules menu {#about-the-rewrite-rules-menu}

Use the Rewrite Rules menu to set crawl and search URL and title rules.

## About Crawl List Store URL Rules {#concept_B71CF4C8030A4A74A22C3BFE4DE3B865}

Crawl URL Rules specify how the URLs it encounters within web content are rewritten. You can specify an unlimited number of rules and conditions, and you can manipulate any portion of the encountered URLs.

<!-- 

c_about_crawl_list_store_url_rules.xml

 -->

Crawl rules are most useful for rewriting dynamic parts of a URL, such as a session identifier which is unique for each customer who visits your website. You can also use rewrite rules to hide portions of a URL, such as query parameters, from the search robot. By default, no rules are specified and no URL rewriting is performed.

As a website is crawled, embedded content URLs are stored in a temporary list of additional web pages to crawl. Before a URL is added to this list, the Store rewrite rules are applied to it. Typically, Store rewrite rules are used to remove a session id from a URL or to enforce a specific session id for crawling. When the search robot retrieves a URL from the list, the Retrieve rewrite rules are used to again manipulate portions of that URL. Typically, the retrieve rules are used for inserting time-sensitive data back into the URL. It is this final URL that is used to actually retrieve the page from your website.

See [About Crawl List Retrieve URL Rules](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA).

Typically, you use Store URL Rules exclusively. Retrieve URL Rules are only necessary if URLs contain dynamic data, like a session ID, and if that dynamic data changes over time to remain valid. In this case, you use Store URL Rules to get the most recent state of the data from the encountered URLs. Then you use the Retrieve URL Rules to add that data to each URL when the search robot tries to retrieve the page.

Each rule is specified with a rewrite rule (RewriteRule) directive and one or more optional rewrite conditions (RewriteCond). The order of the rules is important. The rule set is looped through rule by rule. When a rule matches, it loops through any corresponding rewrite conditions. A crawl URL rule is specified in the following manner:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

When an embedded URL is encountered, the search robot tries to match the URL to the Pattern of each crawl rule. If the pattern matches, the rewrite engine looks for corresponding RewriteCond directives. If no conditions are present, the URL is substituted with a new value constructed from the Substitution string and continues with the next rule in the rule set. If conditions exist, they are processed in the order that they are listed. The rewrite engine tries to match a condition pattern (CondPattern) against a test string (TestString). If the two match, then the next condition is processed until no more conditions are available. If all conditions match, the URL is replaced with the Substitution that is specified in the rule. If the condition is not met, the complete set of conditions and the corresponding rule fails.

## About RewriteRule directives {#section_162122340BB34F12BB9A36DC9349092B}

A RewriteRule directive has the following form:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` can be a POSIX regular expression, which is applied to the current URL. The "current URL" can differ from the original requested URL, because earlier rules may have already matched and altered the URL.

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

You cannot use the "not" character ('!') to prefix the pattern. The "not" character lets you negate a pattern, that is, to be true only if the current URL does NOT match this pattern. The "not" character can be used when it is better to match a negative pattern, or as a final default rule.

>[!NOTE]
>
>You cannot use both the "not" character and grouped wildcards in a pattern. In addition, you cannot use a negated pattern when the substitution string contains $N.

You can use parentheses to create a backreference in the pattern, which can be referenced by the Substitution and CondPattern.

**Substitution** The URL is replaced by the substitution string, that contains the following:

Plain Text: Text that is passed through unchanged.

Backreferences provide access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. The following are the two types of backreferences:

* **RewriteRule Backreferences** These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.` 

* **RewriteCond Backreferences** These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0 <= N <= 9).

Variables: These are variables of the form %{NAME_OF_VARIABLE} where NAME_OF_VARIABLE is a string for the name of a defined variable. See the `*[E]*` flag for more information on setting environment variables.

Functions: These are functions of the form ${NAME_OF_FUNCTION:key} where NAME_OF_FUNCTION is the following:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase. 
* escape URL-encodes all characters in *key*. 
* The characters 'a'..'z', 'A'..'Z', '0'..'9', '*', '-', '.', '/', '@', and '_' are left unchanged; spaces are translated to '+', and all other characters are transformed to their %xx URL-encoded equivalent. 
* unescape transforms '+' back to space and all %xx URL- encoded characters back into single characters.

>[!NOTE]
>
>There is a special substitution string: `'-'` that means "NO substitution." The `'-'` string is often used with the C (chain) flag, letting you match a URL to several patterns before a substitution occurs.

**Flags**  

(optional) Enclose flags in brackets `[]`. Multiple flags are comma-separated. 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Last rule. </p> <p>Stops the rewriting process and does not apply any additional rewriting rules. Use this flag to prevent any further processing to the current URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Next round. </p> <p> Reruns the rewriting process (starting again with the first rewriting rule) using the URL from the last rewriting rule (not the original URL). Be careful not to create a deadloop! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Chained with next rule. </p> <p>Chains the current rule to the next rule (which can also be chained to its following rule, and so on). If a rule matches, then the substitution process continues as usual. If the rule does not match, then all subsequent chained rules are skipped. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>No case. </p> <p> Makes the Pattern not case sensitive (that is, there is no difference between 'A-Z' and 'a-z') when the pattern is matched against the current URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Skip the next rule or rules. </p> <p> If the current rule matches, this flag forces the rewrite engine to skip the next num rules in the rule set. Use this flag to make pseudo if-then-else constructs. The last rule of the then-clause becomes a skip=N where N is the number of rules in the else-clause. </p> <p> <p>Note:  This flag is not the same as the 'chain|C' flag!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Sets the environmental variable. </p> <p>Creates an environmental variable "VAR" set to the value VAL, where VAL can contain regular expressions backreferences, $N and %N, which are expanded. You can use this flag more than once to set multiple variables. The variables can be later de-referenced in a following RewriteCond pattern via %{VAR}. </p> <p>Use this flag to strip and remember information from URLs. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The Store Rewrite Rules and the Retrieve Rewrite Rules share variable values. Because of this behavior, you can set a variable to a time-sensitive sessionid value when an embedded URL is encountered and stored. When the next URL is retrieved from the temporary storage list, the latest sessionid value can be added to it before that page is retrieved.

**Example of a RewriteRule with a function**

Assume that you have a case-sensitive server, which handles the strings `"www.mydomain.com"` and `"www.MyDomain.com"` differently. In order for your server to work correctly, ensure that the domain is always `"www.mydomain.com"` even though some documents contain links referencing `"www.MyDomain.com."` To do this, you could use the following rule:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

This rewrite rule uses the function `tolower` to rewrite the domain portion of a URL to ensure that it is always lowercase as in the following:

1. The Pattern `(^https://([^/]*)(.*)$)` contains a backreference `([^/]*)` that matches all characters between `https://` and the first `/` in the URL. The pattern also contains a second backreference `(.*)` that matches all remaining characters in the URL. 

1. The Substitution `(https://${tolower:$1}$2)` tells the search engine to rewrite the URL by using the `tolower` function on the first backreference `(https:// ${tolower:$1}$2)` leaving the rest of the URL untouched `(https://${tolower:$1} $2)`.

Thus, a URL of the form `https://www.MyDomain.com/INTRO/index.Html` is rewritten as `https://www.mydomain.com/INTRO/index.Html`.

## About RewriteCond directives {#section_CD5A19B2D3204F73B645411931FC34A1}

The RewriteCond directive defines a rule condition. When a RewriteCond precedes a RewriteRule, the rule is only used if its pattern matches the current title and the additional conditions apply. Rewrite conditions take the following form:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` is a string which can contain the following constructs:

Plain text: Text that is passed through unchanged.

Backreferences provide access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. The following are the two types of backreferences:

* **RewriteRule Backreferences** These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`. 

* ** RewriteCond Backreferences** These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0<= N <= 9).

Variables: These are variables of the form %{NAME_OF_VARIABLE} where NAME_OF_VARIABLE can be a string for the name of a defined variable. See the RewriteRule *`[E]`* flag for more information on setting variables.

Functions: These are functions of the form ${NAME_OF_FUNCTION:key} where NAME_OF_FUNCTION is the following:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase. 
* escape URL-encodes all characters in key. The characters 'a'..'z', 'A'..'Z', '0'..'9', '*', '-', '.', '/', '@', and '_' are left unchanged, spaces are translated to '+', and all other characters are transformed to their `%xx` URL-encoded equivalent. 
* unescape transforms '+' back to space and all `%xx` URL encode characters back into single characters.

**CondPattern** is a standard Extended Regular Expression with some additions. The pattern string can be prefixed with a `!` character (exclamation mark) to specify a non-matching pattern. Instead of real regular expression strings, you can use one of the following special variants:

>[!NOTE]
>
>You can also prefix all of these tests with an exclamation mark ('!') to negate their meaning.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern string </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexically less. </p> <p> Treats the CondPattern as a plain string and compares it lexically to TestString. True if TestString is lexically less than CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexically greater. </p> <p> Treats the CondPattern as a plain string and compares it lexically to TestString. True if TestString is lexically greater than CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexically equal. </p> <p> Treats the CondPattern as a plain string and compares it lexically to TestString. True if TestString is lexically equal to CondPattern, that is, the two strings are exactly equal (character by character). If CondPattern is just "" (two quotation marks), this compares TestString to the empty string. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags** 
(optional) Enclose flags in brackets `[]`. Multiple flags are comma-separated. 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> No case. </p> <p>This flag makes the test not case sensitive, that is, there is no difference between 'A-Z' and 'a-z' both in the expanded TestString and in the CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>Or next condition. </p> <p>Use this flag to combine rule conditions with a local OR instead of the implicit AND. Without this flag, you would have to write the cond/rule multiple times. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Example**

Some web pages assign a "sessionid" CGI variable the first time a visitor arrives at a site. This variable is used to identify the visitor and, as the visitor browses through the site, the variable is passed along. Because the search robot looks like a visitor to your site, it is assigned a "sessionid"number. The search robot maintains this single "sessionid" value, even if a second site page tries to assign a new value. To ensure this, you need two rewrite rules.

The first rule is used to identify and store the sessionid variable:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

The RewriteRule uses an E-flag `([E=sessionid:$1])` to assign the current value of the sessionid CGI parameter to the variable `sessionid`. The `$1` refers to the first backreference, which is contained between the first set of parentheses in the RewriteRule's Pattern `([^&#]+)`.

The regular expression `^&#]+` matches the portion of a URL between the word `sessionid` and the next `**&**or**#**` character. Since this RewriteRule is used only to create the initial value for the sessionid variable, it does no rewriting. Note that the rule's Substitution field is set to `-` to indicate that no rewriting is required.

The RewriteCond examines the variable `sessionid` ( `%{sessionid}`). If it does not have even a single character (!.+), then the RewriteRule matches.

Using this rule, the URL is read as `https://www.domain.com/home/?sessionid=1234&function=start` and assign the value `1234` to the variable `sessionid`.

The second rule is used to rewrite all URLs that match the following RewriteRule Pattern:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

The RewriteRule Pattern contains two backreferences: `(.+)` and `(.*)`. The first backreference matches all characters before `sessionid`. The second backreference matches all characters after the terminating `&` or `#`.

The Substitution pattern rewrites the URL using the first backreference, followed by the string "sessionid=", followed by the value of the session ID variable defined by the first rule `%{sessionid}`, followed by the second backreference. `($1sessionid=%{sessionid} $2)`

Notice that this RewriteRule does not contain a RewriteCond. As such, it causes a rewrite for all URLs that match the RewriteRule *Pattern*. Thus, if the value of the sessionid variable ( `%{sessionid}`) is `1234`, a URL of the form `https://www.domain.com/products/?sessionid=5678&function=buy` is rewritten as `https://www.domain.com/products/?sessionid=1234&function=buy`

## Acknowledgment {#section_B17088EF38244496BC1DDD4ECF75EB5B}

The rewrite engine software was originally developed by the Apache Group for use in the Apache HTTP server project (https://www.apache.org/). 

## Adding a crawl list store URL rule {#task_22DD40DF95584B12BE8E6ECFBF579BCD}

You can add crawl list store URL rules to specify how the URLs that are encountered within web content are rewritten. You can specify an unlimited number of rules and conditions, and you can manipulate any portion of the encountered URLs.

<!-- 

t_adding_a_crawl_list_store_url_rule.xml

 -->

**To add crawl list store URL rules** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Store URL Rules]**.
1. In the [!DNL Crawl List Store URL Rules] field, enter the rules that you want.

   Blank lines and comment lines beginning with a '#' (hash) character are permitted. 
1. (Optional) On the [!DNL Crawl List Store URL Rules] page, in the [!DNL Test Crawl List Store URL Rules] field, enter a test URL whose crawl rules you want to test, and then click **Test**.
1. Click **Save Changes**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Crawl List Store URL Rules] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Crawl List Retrieve URL Rules {#concept_EC8E2E48B99A458D8567B526C9827CBA}

Crawl URL Rules specify how the URLs that are encountered within web content are rewritten. You can specify an unlimited number of rules and conditions, and you can manipulate any portion of the encountered URLs.

<!-- 

c_about_crawl_list_retrieve_url_rules.xml

 -->

Before the effects of the rules are visible to customers, be sure you rebuild your site index.

Crawl rules are most useful for rewriting dynamic parts of a URL, such as a session identifier which is unique for each customer who visits your website. You can also use rewrite rules to hide portions of a URL, such as query parameters, from the search robot. By default, no rules are specified and no URL rewriting is performed.

As a website is crawled, embedded content URLs are stored in a temporary list of additional web pages to crawl. When the search robot retrieves a URL from the list, the Retrieve Rewrite Rules are used to manipulate portions of that URL. Typically, the retrieve rules are used for inserting time-sensitive data into a URL. It is this final URL that is used to actually retrieve the page from your website.

Retrieve Rewrite Rules are only necessary if URLs contain dynamic data, like a session id, and if that dynamic data changes over time to remain valid. In this case, you use Store Rewrite Rules to get the most recent state of the data from the encountered URLs. Then, you use the Retrieve Rewrite Rules to add that data to each URL when the search robots retrieves the page.

Each rule is specified with a rewrite rule (RewriteRule) directive and one or more optional rewrite conditions (RewriteCond). The order of the rules is important. The rule set is looped through rule by rule. When a rule matches, it loops through any corresponding rewrite conditions. A crawl URL rule is specified in the following manner:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

When an embedded URL is encountered, the search robot tries to match the URL to the Pattern of each crawl rule. If the pattern matches, the rewrite engine looks for corresponding RewriteCond directives. If no conditions are present, the URL is substituted with a new value constructed from the Substitution string and continues with the next rule in the rule set. If conditions exist, they are processed in the order that they are listed. The rewrite engine tries to match a condition pattern (CondPattern) against a test string (TestString). If the two match, then the next condition is processed until no more conditions are available. If all conditions match, the URL is replaced with the Substitution that is specified in the rule. If the condition is not met, the complete set of conditions and the corresponding rule fails.

## About RewriteRule directives {#section_32B24B29627946398AFBC5F869A610CB}

A RewriteRule directive has the following form:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` can be a POSIX regular expression, which is applied to the current URL. The "current URL" can differ from the original requested URL, because earlier rules may have already matched and altered the URL.

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

You cannot use the "not" character ('!') to prefix the pattern. The "not" character lets you negate a pattern, that is, to be true only if the current URL does NOT match this pattern. The "not" character can be used when it is better to match a negative pattern, or as a final default rule.

>[!NOTE]
>
>You cannot use both the "not" character and grouped wildcards in a pattern. In addition, you cannot use a negated pattern when the substitution string contains $N.

You can use parentheses to create a backreference in the pattern, which can be referenced by the Substitution and CondPattern.

**Substitution** The URL is replaced by the substitution string, that contains the following:

Plain Text: Text that is passed through unchanged.

Backreferences provide access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. The following are the two types of backreferences:

* **RewriteRule Backreferences** These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.` 

* ** RewriteCond Backreferences** These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0 <= N <= 9).

Variables: These are variables of the form %{NAME_OF_VARIABLE} where NAME_OF_VARIABLE is a string for the name of a defined variable. See the *[E]* flag for more information on setting environment variables.

Functions: These are functions of the form ${NAME_OF_FUNCTION:key} where NAME_OF_FUNCTION is the following:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase. 
* escape URL-encodes all characters in *key*. 
* The characters 'a'..'z', 'A'..'Z', '0'..'9', '*', '-', '.', '/', '@', and '_' are left unchanged; spaces are translated to '+', and all other characters are transformed to their %xx URL-encoded equivalent. 
* unescape transforms '+' back to space and all %xx URL- encoded characters back into single characters.

>[!NOTE]
>
>There is a special substitution string: '-' that means "NO substitution." The '-' string is often used with the C (chain) flag, letting you match a URL to several patterns before a substitution occurs.

**Flags** 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Last rule. </p> <p>Stops the rewriting process and does not apply any additional rewriting rules. Use this flag to prevent any further processing to the current URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Next round. </p> <p> Reruns the rewriting process (starting again with the first rewriting rule) using the URL from the last rewriting rule (not the original URL). Be careful not to create a deadloop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Chained with next rule. </p> <p>Chains the current rule to the next rule (which can also be chained to its following rule, and so on). If a rule matches, then the substitution process continues as usual. If the rule does not match, then all subsequent chained rules are skipped. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>No case. </p> <p> Makes the Pattern not case sensitive (that is, there is no difference between 'A-Z' and 'a-z') when the pattern is matched against the current URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Skip the next rule or rules. </p> <p> If the current rule matches, this flag forces the rewrite engine to skip the next num rules in the rule set. Use this flag to make pseudo if-then-else constructs. The last rule of the then-clause becomes a skip=N where N is the number of rules in the else-clause. </p> <p> <p>Note:  This flag is not the same as the 'chain|C' flag!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Sets the environmental variable. </p> <p>Creates an environmental variable "VAR" set to the value VAL, where VAL can contain regular expressions backreferences, $N and %N, which are expanded. You can use this flag more than once to set multiple variables. The variables can be later de-referenced in a following RewriteCond pattern via %{VAR}. </p> <p>Use this flag to strip and remember information from URLs. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The Store Rewrite Rules and the Retrieve Rewrite Rules share variable values. Because of this behavior, you can set a variable to a time-sensitive sessionid value when an embedded URL is encountered and stored. When the next URL is retrieved from the temporary storage list, the latest sessionid value can be added to it before that page is retrieved.

**Example of a RewriteRule with a function**

Assume that you have a case-sensitive server, which handles the strings "www.mydomain.com" and "www.MyDomain.com" differently. In order for your server to work correctly, ensure that the domain is always "www.mydomain.com" even though some documents contain links referencing "www.MyDomain.com." To do this, you could use the following rule:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

This rewrite rule uses the function `tolower` to rewrite the domain portion of a URL to ensure that it is always lowercase as in the following:

1. The Pattern `(^https://([^/]*)(.*)$)` contains a backreference ** `([^/]*)`** that matches all characters between `https://` and the first `/` in the URL. The pattern also contains a second backreference `(.*)` that matches all remaining characters in the URL. 
1. The Substitution `(https://${tolower:$1}$2)` tells the search engine to rewrite the URL by using the `tolower` function on the first backreference `(https:// ${tolower:$1}$2)` leaving the rest of the URL untouched `(https://${tolower:$1} $2)`.

Thus, a URL of the form `https://www.MyDomain.com/INTRO/index.Html` is rewritten as `https://www.mydomain.com/INTRO/index.Html`.

## About RewriteCond directives {#section_ADD642A24B68452CB98294A0BD687EC3}

The RewriteCond directive defines a rule condition. When a RewriteCond precedes a RewriteRule, the rule is only used if its pattern matches the current title and the additional conditions apply. Rewrite conditions take the following form:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` is a string which can contain the following constructs:

Plain text: Text that is passed through unchanged.

Backreferences provide access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. The following are the two types of backreferences:

* **RewriteRule Backreferences** These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`. 

* **RewriteCond Backreferences** These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0<= N <= 9).

Variables: These are variables of the form %{NAME_OF_VARIABLE} where NAME_OF_VARIABLE can be a string for the name of a defined variable. See the RewriteRule *`[E]`* flag for more information on setting variables.

Functions: These are functions of the form ${NAME_OF_FUNCTION:key} where NAME_OF_FUNCTION is the following:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase. 
* escape URL-encodes all characters in key. The characters 'a'..'z', 'A'..'Z', '0'..'9', '*', '-', '.', '/', '@', and '_' are left unchanged, spaces are translated to '+', and all other characters are transformed to their %xx URL-encoded equivalent. 
* unescape transforms '+' back to space and all %xx URL encode characters back into single characters.

**CondPattern** is a standard Extended Regular Expression with some additions. The pattern string can be prefixed with a '!' character (exclamation mark) to specify a non-matching pattern. Instead of real regular expression strings, you can use one of the following special variants:

>[!NOTE]
>
>You can also prefix all of these tests with an exclamation mark ('!') to negate their meaning.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern string </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexically less. </p> <p> Treats the CondPattern as a plain string and compares it lexically to TestString. True if TestString is lexically less than CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexically greater. </p> <p> Treats the CondPattern as a plain string and compares it lexically to TestString. True if TestString is lexically greater than CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexically equal. </p> <p> Treats the CondPattern as a plain string and compares it lexically to TestString. True if TestString is lexically equal to CondPattern, that is, the two strings are exactly equal (character by character). If CondPattern is just "" (two quotation marks), this compares TestString to the empty string. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags** 
(optional) Enclose flags in brackets `[]`. Multiple flags are comma-separated. 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> No case. </p> <p>This flag makes the test not case sensitive, that is, there is no difference between 'A-Z' and 'a-z' both in the expanded TestString and in the CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>Or next condition. </p> <p>Use this flag to combine rule conditions with a local OR instead of the implicit AND. Without this flag, you would have to write the cond/rule multiple times. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Example**

Some web pages assign a "sessionid" CGI variable the first time a visitor arrives at a site. This variable is used to identify the visitor and, as the visitor browses through the site, the variable is passed along. Because the search robot looks like a visitor to your site, it is assigned a "sessionid"number. The search robot maintains this single "sessionid" value, even if a second site page tries to assign a new value. To ensure this, you need two rewrite rules.

The first rule is used to identify and store the sessionid variable:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

The RewriteRule uses an E-flag `([E=sessionid:$1])` to assign the current value of the sessionid CGI parameter to the variable `sessionid`. The `$1` refers to the first backreference, which is contained between the first set of parentheses in the RewriteRule's Pattern `([^&#]+)`.

The regular expression `^&#]+` matches the portion of a URL between the word `sessionid` and the next**&**or**#**character. Since this RewriteRule is used only to create the initial value for the sessionid variable, it does no rewriting. Note that the rule's Substitution field is set to `-` to indicate that no rewriting is required.

The RewriteCond examines the variable `sessionid` ( `%{sessionid}`). If it does not have even a single character (!.+), then the RewriteRule matches.

Using this rule, the URL is read as `https://www.domain.com/home/?sessionid=1234&function=start` and assign the value `1234` to the variable `sessionid`.

The second rule is used to rewrite all URLs that match the following RewriteRule Pattern:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

The RewriteRule Pattern contains two backreferences: `(.+)` and `(.*)`. The first backreference matches all characters before `sessionid`. The second backreference matches all characters after the terminating `&` or `#`.

The Substitution pattern rewrites the URL using the first backreference, followed by the string "sessionid=", followed by the value of the session ID variable defined by the first rule `%{sessionid}`, followed by the second backreference. `($1sessionid=%{sessionid} $2)`

Notice that this RewriteRule does not contain a RewriteCond. As such, it causes a rewrite for all URLs that match the RewriteRule *Pattern*. Thus, if the value of the sessionid variable ( `%{sessionid}`) is `1234`, a URL of the form `https://www.domain.com/products/?sessionid=5678&function=buy` is rewritten as `https://www.domain.com/products/?sessionid=1234&function=buy`

## Acknowledgment {#section_EC3A1DAEB5A54C93A265CB119DF91E9F}

The rewrite engine software was originally developed by the Apache Group for use in the Apache HTTP server project (https://www.apache.org/). 

## Adding crawl list retrieve URL rules {#task_94A28ED7DC404BFF9767DBB5ADEE6B7A}

You can add crawl list retrieve URL rules to specify how encountered URLs within web content are rewritten. Retrieve Rewrite Rules are only necessary if URLs contain dynamic data, such as a session ID, and if that dynamic data changes over time to remain valid.

<!-- 

t_adding_crawl_list_retrieve_url_rules.xml

 -->

**To add crawl list retrieve URL rules** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**.
1. In the [!DNL Crawl List Retrieve URL Rules] field, enter the rules that you want.

   Blank lines and comment lines beginning with a '#' (hash) character are permitted. 
1. (Optional) On the [!DNL Crawl List Retrieve URL Rules] page, in the [!DNL Test Crawl List Retrieve URL Rules] field, enter a test URL whose crawl rules you want to test, and then click **Test**.
1. Click **Save Changes**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Crawl List Retrieve URL Rules] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Crawl Title Rules {#concept_BD3A576987DA4D93A998B0B9CDDC3C79}

Crawl Title Rules specify how encountered titles within Web content are rewritten before they are stored in the search index.

<!-- 

c_about_crawl_title_rules.xml

 -->

For example, you can use a rewrite rule to remove a portion of a title such as an organization name. As a website is crawled, encountered titles are stored in a temporary buffer. However, before a title is added to this buffer, the title rules are applied to it. By default, site search/merchandising has no crawl title rules and makes no title modifications.

Before the effects of the rules are visible to customers, rebuild your site index.

You can quickly revert any changes you make to Crawl Title Rules by using the History feature.

Rules can consist of two main elements: the RewriteRule and the optional RewriteCond. You can specify an unlimited number of rules and conditions. The order of these rules is important because the rule set is looped through rule by rule. When a rule matches, it loops through any (optional) corresponding rewrite conditions. Crawl URL rules are specified in the following manner:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

When a title is encountered, the search robot tries to match the title to the Pattern of each crawl rule. If the pattern matches, the rewrite engine looks for corresponding RewriteCond directives. If no conditions are present, the URL is substituted with a new value constructed from the Substitution string and continues with the next rule in the rule set. If conditions exist, they are processed in the order that they are listed. The rewrite engine tries to match a condition pattern (CondPattern) against a test string (TestString). If the two match, then the next condition is processed until no more conditions are available. If all conditions match, the URL is replaced with the Substitution that is specified in the rule. If the condition is not met, the complete set of conditions and the corresponding rule fails.

Enter the Crawl URL Rules in the text box, and then click Save Changes. Blank lines and comment lines beginning with a '#' (hash) character are permitted. To test the search rules, you can enter a test URL in the "Test Rewrite Rules" text box, and then click Test.

## RewriteRule directive {#section_669445C505754E838E14029D6583D9B6}

Each RewriteRule directive defines one rewriting rule. Rules are applied in the order in which they are listed. A rewrite rule takes the following form:

```
RewriteRule Pattern Substitution [Flags]
```

**Pattern** can be a POSIX regular expression, which is applied to the current title. The "current title" differs from the original title, because earlier rules have already matched and altered it.

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

You can use the "not" character ('!') to prefix the pattern. The "not" character allows you to negate a pattern, that is, to be true only if the current title does NOT match the pattern. The "not" character can be used when it is better to match a negative pattern, or as a final default rule. Note: You cannot use both the "not" character and grouped wildcards in a pattern. In addition, you cannot use a negated pattern when the substitution string contains $N.

You can use parentheses to create a backreference, which can be referenced by the Substitution and CondPattern.

**Substitution** The title is replaced by the substitution string. The string can contain the following:

Plain text - Text that is passed through unchanged.

Backreferences provide access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. The following are two types of backreferences:

* RewriteRule Backreferences

  These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}` 
* RewriteCond Backreferences

  These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0 <= N <= 9).

Variables These are variables of the form %{NAME_OF_VARIABLE} where NAME_OF_VARIABLE can be a string for the name of a defined variable. See the `[E]` flag for more information on setting environment variables.

Functions These are functions of the form ${NAME_OF_FUNCTION: key} where NAME_OF_FUNCTION is:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase.

>[!NOTE]
>
>There is a special substitution string: '-' that means "NO substitution." The '-' string is often useful with the C (chain) flag, allowing you to match a title to several patterns before a substitution occurs.

**Flags** (optional)

Flags are enclosed in brackets `[]`and multiple flags are comma-separated:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Last rule. </p> <p> Stops the rewrite process and does not apply any additional rewriting rules. Use this flag to prevent any further processing to the current title. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Next round. </p> <p> Reruns the rewriting process (starting again with the first rewriting rule) using the title from the last rewriting rule, not the original title. Be careful not to create a dead loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Chained with next rule. </p> <p>Chains the current rule to the next rule (which can also be chained to its following rule, and so on). If a rule matches, then the substitution process continues as usual. If the rule does not match, then all subsequent chained rules are skipped. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>No case. </p> <p>Makes the Pattern not case sensitive (that is, there is no difference between 'A-Z' and 'a-z') when the pattern is matched against the current title. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Skip next rule or rules. </p> <p> If the current rule matches, this flag forces the rewrite engine to skip the next num rules in the rule set. Use this to make pseudo if-then-else constructs. The last rule of the then-clause becomes a skip=N where N is the number of rules in the else-clause. (Note: This is not the same as the 'chain|C' flag!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Set environment variable. </p> <p> Creates an environmental variable "VAR" set to the value VAL, where VAL can contain regular expressions backreferences, $N and %N, which is expanded. You can use this flag more than once to set multiple variables. The variables can be later referenced in a following RewriteCond pattern via %{VAR}. Use this flag to strip and remember information from titles. </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond Directive (Optional) {#section_D664B71DE3884E0790531804C49A3222}

The RewriteCond directive defines a rule condition. When a RewriteCond precedes a RewriteRule, the rule is only used if its pattern matches the current title and the additional conditions apply.

Rewrite condition directives take the following form:

```
RewriteCond TestString CondPattern [Flags] 
```

**TestString** is a string that can contain the following constructs:

Plain text - Text that is passed through unchanged.

Backreferences provide access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. There are two types of backreferences:

* RewriteRule Backreferences These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}` 
* RewriteCond Backreferences These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0 <= N <= 9).

Variables These are variables of the form %{NAME_OF_VARIABLE} where NAME_OF_VARIABLE can be a string for the name of a defined variable. See the `[E]` flag for more information on setting environment variables..

Functions These are functions of the form ${NAME_OF_FUNCTION:key} where NAME_OF_FUNCTION is:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase. 
* escape URL-encodes all characters in key. 
* The characters 'a'..'z', 'A'..'Z', '0'..'9', '*', '-', '.', '/', '@', and '_' are left unchanged, spaces are translated to '+', and all other characters are transformed to their %xx URL-encoded equivalent. 
* unescape transforms '+' back to space and all %xx URL- encoded characters back into single characters.

**CondPattern** is a standard Extended Regular Expression with some additions. The pattern string can be prefixed with a '!' character (exclamation mark) to specify a non-matching pattern. Instead of real regular expression strings, you can use one of the following special variants.

>[!NOTE]
>
>You can prefix all of these tests with an exclamation mark ('!') to negate their meaning.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern string </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Is lexically less. </p> <p>Treats the <i>CondPattern</i> as a plain string and compares it lexically to <i>TestString</i>. True if <i>TestString</i> is lexically less than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Is lexically greater. </p> <p>Treats the <i>CondPattern</i> as a plain string and compares it lexically to <i>TestString</i>. True if <i>TestString</i> is lexically greater than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p> Is lexically equal. </p> <p>Treats the <i>CondPattern</i> as a plain string and compares it lexically to <i>TestString</i>. True if <i>TestString</i> is lexically equal to <i>CondPattern</i>, that is, the two strings are exactly equal (character by character). If <i>CondPattern</i> is just "" (two quotation marks), this compares <i>TestString</i> to the empty string. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags** (optional)

Flags are enclosed in brackets `[]`and multiple flags are comma-separated: 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>No case. </p> <p> Makes the test not sensitive. That is, there is no difference between 'A-Z' and 'a-z' both in the expanded <i>TestString</i> and in the <i>CondPattern.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p> Or next condition. </p> <p>Use this flag to combine rule conditions with a local OR instead of the implicit AND. Without this flag, you would have to write the cond/rule multiple times. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Example**

Assume that you have a corporate Web site with a standard title format: "My Company" followed by a hyphen and then a page-specific description ("My Company - Welcome" or "My Company - News", for example). You want to strip "My Company - " from the title and convert the whole title into uppercase letters when it indexes the site.

The following rewrite rule uses the function toupper to rewrite only the descriptive portion of a title to uppercase:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>}
```

The rule's Pattern `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` contains a backreference `(.*)` that matches the title content that follows "My Company-". Remember that surrounding a portion of a pattern with parenthesis ( ) creates a backreference that can be referenced by the Substitution. In this example, the Substitution (${toupper:**$1**}) rewrites that backreference (**$1**) using the toupper function.

Thus, a title of the form "My Company - Welcome" is rewritten as "WELCOME".

**Acknowledgment**

The rewrite engine software was originally developed by the Apache Group for use in the Apache HTTP server project (https://www.apache.org/). 

## Adding crawl title rules {#task_272BB4C603BA4C9ABDBEEB398798B101}

You can add crawl title rules to specify how the encountered titles within the web content are rewritten before they are stored in the search index.

<!-- 

t_adding_crawl_title_rules.xml

 -->

**To add crawl title rules** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl Title Rules]**.
1. In the [!DNL Crawl Title Rules] field, enter the rules that you want.

   Blank lines and comment lines beginning with a '#' (hash) character are permitted. 
1. (Optional) On the [!DNL Crawl Title Rules] page, in the [!DNL Test Crawl Title Rules] field, enter a test URL whose search rules you want to test, and then click **Test**.
1. Click **Save Changes**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Crawl Title Rules] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Search URL Rules {#concept_017EC95E68844B6C8CC9F874F0EC8D3C}

Search URL Rules specify how the URLs in your web site search results should display. The rules operate on full URLs. Any portion of the URL can be manipulated, including query arguments where session ID information is often kept.

<!-- 

c_about_search_url_rules.xml

 -->

Typically, search URL rules are used to insert a session ID into a URL. However, you can also use search URL rules to alter the domain name that is displayed with your results. By default, no rules are specified and no URL modification is performed.

Search URL rules can consist of two main elements: the RewriteRule and the optional RewriteCond. When a URL is included as part of a search result, the rules are used to manipulate it. You can specify an unlimited number of search URL rules and conditions. The order of these rules is important because the rule set is looped through rule-by-rule. When a rule matches, the software loops through any (optional) corresponding rewrite conditions. Crawl URL rules are specified in the following manner:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

When processing a URL, site search/merchandising tries to match it to the Pattern of each search rule. If the match fails, the rewrite engine immediately stops processing the rule and continues with the next rule in the set. If the pattern matches, the rewrite engine looks for corresponding RewriteCond instructions. If no conditions exist, the URL is substituted with a new value. This value is constructed from the Substitution string and continues with the next rule in the rule set. If conditions exist, the order that they are listed is how they are processed. The rewrite engine tries to match a condition pattern (CondPattern) against a test string (TestString). If the two match, then the next condition is processed until no more conditions are available. If all conditions match, the URL is replaced with the Substitution specified in the rule. If the condition is not met, the complete set of conditions and the corresponding rule fails.

## About RewriteRule directive {#section_A3473B5B90B74DA1970213113A90591E}

A rewrite rule takes the following form:

```
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

**Pattern** can be a POSIX regular expression, which gets applied to the current URL. The "current URL" may differ from the original URL, because earlier rules may have already matched and altered it.

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

You can use the "not" character ('!') to prefix the pattern. The "not" character lets you negate a pattern. In other words, it is true only if the current URL does NOT match the pattern. You can use the "not" character when it is better to match a negative pattern, or as a final default rule. Note that you cannot use both the "not" character and grouped wildcards in a pattern. In addition, you cannot use a negated pattern when the substitution string contains $N.

You can use parentheses to create a backreference, which can be referenced by the Substitution and CondPattern.

**Substitution** The URL is completely replaced by the substitution string, which can contain the following:

Plain Text - Text that is passed through unchanged.

Backreferences Provides access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. There are two types of backreferences:

RewriteRule Backreferences These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

RewriteCond Backreferences- These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0 <= N <= 9).

Functions: These are functions of the form ${NAME_OF_FUNCTION:key} where NAME_OF_FUNCTION is:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase. 
* escape URL-encodes all characters in *key*. 
* The characters 'a'..'z', 'A'..'Z', '0'..'9', '*', '-', '.', '/', '@', and '_' are left unchanged; spaces are translated to '+'; all other characters are transformed to their %xx URL-encoded equivalent. 
* unescape transforms '+' back to space and all %xx URL- encoded characters back into single characters.

>[!NOTE]
>
>There is a special substitution string: '-' that means "NO substitution." The '-' string is often useful in conjunction with the C (chain) flag. It lets you match a URL to several patterns before a substitution occurs.

**Flags** (optional)

Flags are enclosed in brackets `[]`and multiple flags are comma-separated: 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Last rule. </p> <p> Stop the rewriting process and do not apply any additional rewriting rules. Use this flag to prevent any further processing to the current URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p> Next round. </p> <p>Re-run the rewriting process (starting again with the first rewriting rule) using the URL from the last rewriting rule (not the original URL). Be careful not to create a dead loop! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p> Chained with next rule. </p> <p>This flag chains the current rule to the next rule, which can also be chained to its following rule, and so forth. If a rule matches, then the substitution process continues as usual. If the rule does not match, then all subsequent chained rules are skipped. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>No case. </p> <p>This flag makes the Pattern case-insensitive. In other words, there is no difference between 'A-Z' and 'a-z' when the pattern is matched against the current URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Skip next rule or rules. </p> <p> If the current rule matches, this flag forces the rewrite engine to skip the next num rules in the rule set. Use this to make pseudo if-then-else constructs. The last rule of the then-clause becomes a skip=N where N is the number of rules in the else-clause. (Note: This is not the same as the 'chain|C' flag!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Set environmental variable. </p> <p> This flag creates an environmental variable "VAR" set to the value VAL. VAL can contain regular expressions backreferences, $N and %N, which are expanded. You can use this flag more than once to set multiple variables. The variables can be later de-referenced in a following RewriteCond pattern via %{VAR}. Use this flag to strip and remember information from URLs. </p> </td> 
  </tr> 
 </tbody> 
</table>

Note that the Store Rewrite Rules and the Retrieve Rewrite Rules share variable values. Because of this, you can set a variable to a time-sensitive sessionid value when an embedded URL is encountered and stored. When the next URL is retrieved from the temporary storage list, the latest sessionid value can be added to it before that page is retrieved.

**Example**

Assume that you have a case-sensitive server. It handles the strings "www.mydomain.com" and "www.MyDomain.com" differently. To have your server work correctly, you must ensure that the domain is always "www.mydomain.com" even though some documents contain links that reference "www.MyDomain.com." To do this, you could use the following rule:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2 
```

This rewrite rule uses the function "tolower" to rewrite the domain portion of a URL to ensure that it is always lowercase:

1. The Pattern `(^https://([^/]*)(.*)$)` contains a backreference **`([^/]*)`** that matches all characters between "https://" and the first "/" in the URL. The pattern also contains a second backreference **(.*)** that matches all remaining characters in the URL. 

1. The Substitution `(https://${tolower:$1}$2)` tells the search engine to rewrite the URL by using the **tolower** function on the first backreference `(https://**${tolower:$1**}$2)` leaving the rest of the URL untouched `(https://${tolower:$1}*$2*)`.

Therefore, a URL of the form `https://www.MyDomain.com/INTRO/index.Html` is rewritten as `https://www.mydomain.com/INTRO/index.Html`

**RewriteCond Directive** (Optional)

The RewriteCond directive defines a rule condition. When a RewriteCond precedes a RewriteRule, the rule is only used if its pattern matches the current title and the additional conditions apply.

Rewrite condition directives take the following form:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i>
```

*TestString* is a string that can contains the following constructs:

Plain text: Text that is passed through unchanged.

Backreferences provide access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. There are two types of backreferences:

* ** RewriteRule Backreferences** These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}` 

* **RewriteCond Backreferences** These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0 <= N <= 9).

Variables These are variables of the form %{NAME_OF_VARIABLE} where NAME_OF_VARIABLE can be a string for the name of a defined variable. See the RewriteRule *`[E]`* flag for more information on setting variables.

>[!NOTE]
>
>Rewrite rules generally make use of variables. All CGI parameters from the current URL are automatically made into variables. For example, the search URL `"https://search.atomz.com/search/?sp_a=sp00000000&sp_q="Product"&session=1234&id=5678"` will automatically provide four variables, which can be referenced in the rewrite rules. In this example, one variable is called "session" and its value is "1234" while another variable is called "id", and its value is "5678." (The other two variables are `sp_a` and `sp_q`.) You should pass all necessary variables as hidden fields from the search form on your Web page. In this example, you should pass the "session" and "id" values, which identify the Web site user performing the search. To pass a hidden field on the search form, use a tag like `<input type=hidden name="session" value="1234">`.

Functions These are functions of the form ${NAME_OF_FUNCTION:key} where NAME_OF_FUNCTION is:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase. 
* escape URL-encodes all characters in *key*. The characters 'a'..'z', 'A'..'Z', '0'..'9', '*', '-', '.', '/', '@', and '_' are left unchanged, spaces are translated to '+', and all other characters are transformed to their %xx URL-encoded equivalent. 
* unescape transforms '+' back to space and all %xx URL encode characters back into single characters.

**CondPattern** is a standard Extended Regular Expression with some additions. The pattern string can be prefixed with a '!' character (exclamation mark) to specify a non-matching pattern. Instead of real regular expression strings, you can use one of the following special variants.

You can prefix all of these tests by using an exclamation mark ('!') to negate their meaning. 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern string </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Is lexically less. </p> <p> Treats the <i>CondPattern</i> as a plain string and compares it lexically to <i>TestString</i>. True if <i>TestString</i> is lexically less than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Is lexically greater. </p> <p> Treats the <i>CondPattern</i> as a plain string and compares it lexically to <i>TestString</i>. True if <i>TestString</i> is lexically greater than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Is lexically equal. </p> <p> Treats the <i>CondPattern</i> as a plain string and compares it lexically to <i>TestString</i>. True if <i>TestString</i> is lexically equal to <i>CondPattern</i>. That is, the two strings are exactly equal (character by character). If <i>CondPattern</i> is just "" (two quotation marks), this compares <i>TestString</i> to the empty string. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags** (optional)

Flags are enclosed in brackets `[]`and multiple flags are comma-separated:

'nocase|NC' (no case): This makes the test case-insensitive. In other words, there is no difference between 'A-Z' and 'a-z' both in the expanded *TestString* and in the *CondPattern*.

'ornext|OR' (or next condition): Use this to combine rule conditions with a local OR instead of the implicit AND. Without this flag you would have to write the cond/rule multiple times.

**Example**

Some Web pages assign a "sessionid" CGI variable the first time a customer arrives at a site. This variable is used to identify the customer and, as the customer browses through the site, the variable is passed along. Because the search robot looks like a customer to your site, it is assigned a "sessionid" number. The search robot maintains this single "sessionid" value, even if a second site page tries to assign a new value. To ensure this, you need the following rewrite rule:

```
RewriteCond  %{sessionid}  .+ 
RewriteRule  ^ 
<b>(.+)</b>sessionid=[^&#]+ 
<i>(.*)</i>$   
<b>$1</b>sessionid=%{sessionid} 
<i>$2</i>
```

The RewriteRule Pattern contains two backreferences: (.+) and (.*). The first backreference matches all characters before "sessionid=". The second backreference matches all characters after the sessionid's terminating '&' or '#'.

The Substitution pattern rewrites the URL using the first backreference, followed by the string "sessionid=", followed by the value of the session ID variable, which was passed as a CGI parameter in the URL, followed by the second backreference. `($1sessionid=%{sessionid}$2)`.

The **RewriteCond** examines the variable sessionid `(%{sessionid})`. If it contains at least one character (.+), then the RewriteRule matches.

Thus, if the search query is `"https://search.atomz.com/search/?sp_a=sp99999999&sp_q=word&sessionid=5678"`, then all search result URLs will be rewritten so that the "sessionid" value is "5678" instead of the "sessionid" value that the search robot encountered when it crawled your site and saved the links.

**Acknowledgment**

The rewrite engine software was originally developed by the Apache Group for use in the Apache HTTP server project (https://www.apache.org/). 

## Adding search URL rules {#task_50C77D1B53804AEEB20896F74265BD6F}

You can add search URL rules to specify how the URLs in your website search results are displayed. The rules operate on full URLs. You can manipulate any portion of the URL, including query arguments where session ID information is often kept.

<!-- 

t_adding_search_url_rules.xml

 -->

**To add search URL rules** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search URL Rules]**.
1. In the [!DNL Search URL Rules] field, enter the rules that you want.

   Blank lines and comment lines beginning with a '#' (hash) character are permitted. 
1. (Optional) On the [!DNL Search URL Rules] page, in the [!DNL Test Search URL Rules] field, enter a test URL whose crawl rules you want to test, and then click **Test**.
1. Click **Save Changes**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Search URL Rules] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## About Search Title Rules {#concept_C72D20F8DFF64EDE809AF4B72797E858}

Search Title Rules specify how titles in your web site search results are displayed. Any portion of the title can be manipulated.

<!-- 

c_about_search_title_rules.xml

 -->

A rewrite rule might be used to remove a portion of a title, like an organization name, for example. By default, site search/merchandising has no title rules and makes no title modifications.

Title rules can consist of two main elements: the RewriteRule and optional RewriteCond. An unlimited number of rules and conditions may be specified. The order of these rules is important, because the rule set is looped through rule by rule. When a rule matches, the software loops through any (optional) corresponding rewrite conditions. Search Title Rules are specified in the following fashion:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

When a title is encountered, site search/merchandising tries to match it to the Pattern of each crawl rule. If the pattern matches, the rewrite engine looks for corresponding RewriteCond directives. If no conditions are present, The title is substituted with a new value constructed from the Substitution string and continues with the next rule in the rule set. If conditions exist, they are processed in the order that they are listed. The rewrite engine tries to match a condition pattern (CondPattern) against a test string (TestString). If the two match, then the next condition is processed until no more conditions are available. If all conditions match, the URL is replaced with the Substitution specified in the rule. If the condition is not met, the complete set of conditions and the corresponding rule fails.

## RewriteRule Directive {#section_3BF2B0FF89F74A26AE79D68FA3184B9B}

Each RewriteRule directive defines one rewriting rule. Rules are applied in the order in which they are listed. A rewrite rule takes the following form:

```
RewriteRule Pattern Substitution [Flags]
```

**Pattern** A POSIX regular expression, which gets applied to the current title. The "current title" may differ from the original title, because earlier rules may have already matched and altered it.

See [Regular Expressions](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

You may use the "not" character ('!') to prefix the pattern. The "not" character lets you negate a pattern. That is, to be true only if the current title does NOT match the pattern. The "not" character can be used when it is better to match a negative pattern, or as a final default rule. Note: You cannot use both the "not" character and grouped wildcards in a pattern. In addition, you cannot use a negated pattern when the substitution string contains $N.

You may use parentheses to create a backreference, which can be referenced by the Substitution and CondPattern.

**Substitution** The title is completely replaced by the substitution string, that can contain the following:

Plain text - Text that is passed through unchanged.

**Backreferences** Provide access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. The following are two types of backreferences:

* **RewriteRule Backreferences** These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}` 

* ** RewriteCond Backreferences** These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0 <= N <= 9).

**Variables** These are variables of the form %{NAME_OF_VARIABLE} where NAME_OF_VARIABLE can be a string for the name of a defined variable. See the [E] flag for more information on setting environment variables. Variables can also be defined in the search form that generated the search results.

**Functions** These are functions of the form ${NAME_OF_FUNCTION: key} where NAME_OF_FUNCTION is:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase.

There is a special substitution string: '-' that means "NO substitution." The '-' string is often useful in conjunction with the C (chain) flag, allowing you to match a title to several patterns before a substitution occurs.

**Flags** (optional)

Flags are enclosed in brackets `[]`, and multiple flags are comma-separated: 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p> Last rule. </p> <p> Stop the rewriting process and do not apply any additional rewriting rules. Use this flag to prevent any further processing to the current title. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Next round. </p> <p> Re-run the rewriting process (starting again with the first rewriting rule) using the title from the last rewriting rule (not the original title!). Be careful not to create a dead loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Chained with next rule. </p> <p> This flag chains the current rule to the next rule (which can also be chained to its following rule, and so forth). If a rule matches, then the substitution process continues as usual. If the rule does not match, then all subsequent chained rules are skipped. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> No case. </p> <p> This flag makes the Pattern case-insensitive. That is, there is no difference between 'A-Z' and 'a-z' when the pattern is matched against the current title. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p> Skip next rule or rules. </p> <p> If the current rule matches, this flag forces the rewrite engine to skip the next num rules in the rule set. Use this to make pseudo if-then-else constructs. The last rule of the then-clause becomes a skip=N where N is the number of rules in the else-clause. (This is not the same as the 'chain|C' flag!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Set environment variable. </p> <p> This flag creates an environmental variable "VAR" set to the value VAL, where VAL can contain regular expressions backreferences, $N and %N, which will be expanded. You can use this flag more than once to set multiple variables. The variables can be later referenced in a following RewriteCond pattern via %{VAR}. Use this flag to strip and remember information from titles. </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond Directive (Optional) {#section_9D72B2AB454849A7B681BC39C506AAA3}

The RewriteCond directive defines a rule condition. When a RewriteCond precedes a RewriteRule, the rule is only used if its pattern matches the current title and the additional conditions apply.

Rewrite condition directives take the following form:

```
RewriteCond TestString CondPattern [Flags]
```

**TestString** is a string that can contain the following constructs:

Plain text - Text that is passed through unchanged.

Backreferences provide access to the grouped parts (inside parenthesis) of the Pattern or CondPattern. There are two types of backreferences:

* **RewriteRule Backreferences** These match backreferences in the corresponding RewriteRule Pattern and take the form $N (0 <= N <= 9). For example, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}` 

* **RewriteCond Backreferences** These match backreferences in the last matched RewriteCond CondPattern and take the form %N (0 <= N <= 9).

**Variables** These are variables of the form %{NAME_OF_VARIABLE} where NAME_OF_VARIABLE can be a string for the name of a defined variable. See the `[E]` flag for more information on setting environment variables. Variables can also be defined in the search form that generated the search results.

**Functions** These are functions of the form ${NAME_OF_FUNCTION:key} where NAME_OF_FUNCTION is:

* tolower makes all characters in *key* lowercase. 
* toupper makes all characters in *key* uppercase. 
* escape URL-encodes all characters in *key*. 
* The characters 'a'..'z', 'A'..'Z', '0'..'9', '*', '-', '.', '/', '@', and '_' are left unchanged, spaces are translated to '+', and all other characters are transformed to their %xx URL-encoded equivalent. 
* unescape transforms '+' back to space and all %xx URL- encoded characters back into single characters.

There is a special substitution string: '-' that means "NO substitution." The '-' string is often useful in conjunction with the C (chain) flag, allowing you to match a URL to several patterns before a substitution occurs.

**CondPattern** A standard Extended Regular Expression with some additions. The pattern string can be prefixed with a '!' character (exclamation mark) to specify a non-matching pattern. Instead of real regular expression strings, you can use one of the following special variants.

All of these tests can also be prefixed by an exclamation mark ('!') to negate their meaning. 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern string </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Is lexically less. </p> <p> Treats the <i>CondPattern</i> as a plain string and compares it lexically to <i>TestString</i>. True if <i>TestString</i> is lexically less than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p> Is lexically greater. </p> <p> Treats the <i>CondPattern</i> as a plain string and compares it lexically to <i>TestString</i>. True if <i>TestString</i> is lexically greater than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Is lexically equal. </p> <p> Treats the <i>CondPattern</i> as a plain string and compares it lexically to <i>TestString</i>. True if <i>TestString</i> is lexically equal to <i>CondPattern</i>. That is, the two strings are exactly equal (character by character). If <i>CondPattern</i> is just "" (two quotation marks), this compares <i>TestString</i> to the empty string. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags** (optional)

Flags are enclosed in brackets`[]`, and multiple flags are comma-separated: 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' (no case) </p> </td> 
   <td colname="col2"> <p>Makes the test not sensitive. That is, there is no difference between 'A-Z' and 'a-z' both in the expanded <i>TestString</i> and in the <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' (or next condition) </p> </td> 
   <td colname="col2"> <p> Use this to combine rule conditions with a local OR instead of the implicit AND. Without this flag you would have to write the cond/rule multiple times. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Example {#section_E7454FFE169E459AABD9D033651939CB}

Assume that you have a corporate Web site with a standard title format: "My Company" followed by a hyphen and then a page-specific description ("My Company - Welcome" or "My Company - News", for example). You want to strip "My Company - " from the title and to convert the whole title into uppercase letters when it indexes the site.

The following rewrite rule uses the function toupper to rewrite only the descriptive portion of a title to uppercase:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>} 
```

The rule's Pattern `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` contains a backreference **`(.*)`** that matches the title content that follows "My Company-". Remember that surrounding a portion of a pattern with parenthesis ( ) creates a backreference that can be referenced by the Substitution. In this example, the Substitution (${toupper:**$1**}) rewrites that backreference (**$1**) using the toupper function.

Thus, a title of the form "My Company - Welcome" is rewritten as "WELCOME".

**Acknowledgment**

The rewrite engine software was originally developed by the Apache Group for use in the Apache HTTP server project (https://www.apache.org/). 

## Adding search title rules {#task_155CECB74BE3444384EDBBD04F41515E}

You can add search title rules to specify how titles in your website search results are displayed. You can manipulate any portion of the title.

<!-- 

t_adding_search_title_rules.xml

 -->

**To add search title rules** 

1. On the product menu, click **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search Title Rules]**.
1. In the [!DNL Search Title Rules] field, enter the rules that you want.

   Blank lines and comment lines beginning with a '#' (hash) character are permitted. 
1. (Optional) On the [!DNL Search Title Rules] page, in the [!DNL Test Search Title Rules] field, enter a test title, and then click **Test**.
1. Click **Save Changes**.
1. (Optional) Rebuild your staged site index if you want to preview the results.

   See [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0). 
1. (Optional) On the [!DNL Search Title Rules] page, do any of the following:

    * Click **[!UICONTROL History]** to revert any changes that you have made.

      See [Using the History option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002). 
    
    * Click **[!UICONTROL Live]**.

      See [Viewing live settings](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F). 
    
    * Click **[!UICONTROL Push Live]**.

      See [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

