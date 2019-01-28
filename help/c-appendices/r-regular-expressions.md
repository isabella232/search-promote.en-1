---
description: A refresher concerning the syntax and rules of constructing regular expressions.
seo-description: A refresher concerning the syntax and rules of constructing regular expressions.
seo-title: Regular Expressions
solution: Target
title: Regular Expressions
topic: Appendices,Site search and merchandising
uuid: 369b54f6-372a-41de-bb5d-3ae0bd640199
index: n
internal: n
snippet: y
---

# Regular Expressions{#regular-expressions}

A refresher concerning the syntax and rules of constructing regular expressions.

See also [Configuring an incremental index of a staged website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Syntax of regular expressions** 

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Text</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Any single character </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [chars] </p> </td> 
   <td colname="col3"> <p> Character class: One of chars </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [^chars] </p> </td> 
   <td colname="col3"> <p>Character class: None of chars </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> text1|text2 </p> </td> 
   <td colname="col3"> <p> Alternative: text1 or text2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Quantifiers</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ? </p> </td> 
   <td colname="col3"> <p> 0 or 1 of the preceding text </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> * </p> </td> 
   <td colname="col3"> <p> 0 or N of the preceding text (N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> + </p> </td> 
   <td colname="col3"> <p>1 or N of the preceding text (N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Grouping</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> (text) </p> </td> 
   <td colname="col3"> <p> Grouping of text, either to set the borders of an alternative or to make back references where the Nth group is used on the RHS of a RewriteRule with $N) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Anchors</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ^ </p> </td> 
   <td colname="col3"> <p> Start of line anchor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> $ </p> </td> 
   <td colname="col3"> <p> End of line anchor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Escaping</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> </td> 
   <td colname="col2"> <p>\char </p> </td> 
   <td colname="col3"> <p>Escape the particular char. For example, to specify the chars ".[]()" and so forth. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Rules about regular expressions**

* An ordinary character—not one of the special characters described below—is a one-character regular expression that matches itself. 
* A backslash (\) followed by any special character is a one-character regular expression that matches the special character itself. Special characters include the following:

    * `.` (period), `*` (asterisk), `?` (question mark), `+` (plus sign), `[` (left square bracket), `|` (vertical pipe), and `\` (backslash) are always special characters, except when they appear within square brackets. 
    * `^` (caret or circumflex) is special at the beginning of a regular expression, or when it immediately follows the left of a pair of square brackets. 
    * `$` (dollar sign) is special at the end of a regular expression. 
    * `.` (period) is a one-character regular expression that matches any character, including supplementary code set characters with the exception of new-line. 
    * A non-empty string of characters enclosed in `[ ]` (left and right square brackets) is a one-character regular expression that matches one character, including supplementary code set characters, in that string.

      If, however, the first character of the string is a `^` (circumflex), the one-character regular expression matches any character, including supplementary code set characters, with the exception of new-line and the remaining characters in the string.

      The `^` has this special meaning only if it occurs first in the string. You can use `-` (minus sign) to indicate a range of consecutive characters, including supplementary code set characters. For example, [0-9] is equivalent to [0123456789].

      Characters specifying the range must be from the same code set. When the characters are from different code sets, one of the characters specifying the range is matched. The `-` loses this special meaning if it occurs first (after an initial `^`, if any) or last in the string. The `]` (right square bracket) does not terminate such a string when it is the first character within it, after an initial `^`, if any. For example, []a-f] matches either a `]` (right square bracket) or one of the ASCII letters a through f inclusive. The four characters listed as special characters above stand for themselves within such a string of characters.

**Rules for constructing regular expressions from one-character regular expressions**

You can use the following rules to construct regular expressions from one-character regular expressions:

* A one-character regular expression is a regular expression that matches whatever the one-character regular expression matches. 
* A one-character regular expression followed by a `*` (asterisk) is a regular expression that matches zero or more occurrences of the one-character regular expression, which may be a supplementary code set character. If there is any choice, the longest leftmost string that permits a match is chosen. 
* A one-character regular expression followed by a `?` (question mark) is a regular expression that matches zero or one occurrences of the one-character regular expression, which may be a supplementary code set character. If there is any choice, the longest leftmost string that permits a match is chosen. 
* A one-character regular expression followed by a `+` (plus sign) is a regular expression that matches one or more occurrences of the one-character regular expression, which may be a supplementary code set character. If there is any choice, the longest leftmost string that permits a match is chosen. 
* A one-character regular expression followed by `{m}`, `{m,}`, or `{m,n}` is a regular expression that matches a range of occurrences of the one-character regular expression. The values of m and n must be non-negative integers less than 256; `{m}` matches exactly m occurrences; `{m,}` matches at least m occurrences; `{m,n}` matches any number of occurrences between m and n inclusive. Whenever a choice exists, the regular expression matches as many occurrences as possible. 
* The concatenation of regular expressions is a regular expression that matches the concatenation of the strings matched by each component of the regular expression. 
* A regular expression enclosed between the character sequences ( and ) is a regular expression that matches whatever the unadorned regular expression matches. 
* A regular expression followed by a `|` (vertical pipe) followed by a regular expression is a regular expression that matches either the first regular expression (before the vertical pipe) or the second regular expression (after the vertical pipe).

You can also constrain a regular expression to match only an initial segment or final segment of a line, or both.

* A `^` (circumflex) at the beginning of a regular expression constrains that regular expression to match an initial segment of a line. 
* A `$` (dollar sign) at the end of an entire regular expression constrains that regular expression to match a final segment of a line. 
* The construction ^regular expression$ constrains the regular expression to match the entire line.

There are some predefined character class names that you can use in place of complex bracketed regular expressions. For example, a digit can be represented by the one-character regular expression [0-9] or by the character class one-character regular expression [[:digit:]].

The predefined character classes and their meanings are the following:  

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Character class </p> </th> 
   <th colname="col2" class="entry"> <p>Meaning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:alnum:]] </p> </td> 
   <td colname="col2"> <p> An alphabetic character or a digit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:alpha:]] </p> </td> 
   <td colname="col2"> <p>An alphabetic character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:blank:]] </p> </td> 
   <td colname="col2"> <p>A space or a tab. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:cntrl:]] </p> </td> 
   <td colname="col2"> <p> A control code; non-printing character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:digit:]] </p> </td> 
   <td colname="col2"> <p>A digit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:graph:]] </p> </td> 
   <td colname="col2"> <p> Any printing character except space. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:lower:]] </p> </td> 
   <td colname="col2"> <p>A lower-case alphabetic character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:print:]] </p> </td> 
   <td colname="col2"> <p> Any printing character including space. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:punct:]] </p> </td> 
   <td colname="col2"> <p> Punctuation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:space:]] </p> </td> 
   <td colname="col2"> <p> White space such as a space, a tab, or an end-of-line. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:upper:]] </p> </td> 
   <td colname="col2"> <p> An upper-case alphabetic character. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:xdigit:]] </p> </td> 
   <td colname="col2"> <p> A hexadecimal digit, upper- or lower-case. </p> </td> 
  </tr> 
 </tbody> 
</table>

Two special character class names match the null space at the start and the end of a word. In other words, they do not match an actual character. A word is considered to be any sequence of alphabetic characters, digits, or underscores (_).  

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Character class </p> </th> 
   <th colname="col2" class="entry"> <p>Meaning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:&lt;:]] </p> </td> 
   <td colname="col2"> <p> start of a word </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:&gt;:]] </p> </td> 
   <td colname="col2"> <p>end of a word </p> </td> 
  </tr> 
 </tbody> 
</table>

