---
description: You can define the date formats that are used when it parses and indexes any field with a "date" data type.
seo-description: You can define the date formats that are used when it parses and indexes any field with a "date" data type.
seo-title: Date Formats
solution: Target
title: Date Formats
topic: Appendices,Site search and merchandising
uuid: d97d6945-8d27-4d5b-889d-c6eaced0632a
index: y
internal: n
snippet: y
---

# Date Formats{#date-formats}

You can define the date formats that are used when it parses and indexes any field with a "date" data type.

 The format of the date and time is specified with a format string. The format string consists of zero or more conversion specifications (a conversion specification consists of a percent sign and one other character) and ordinary characters. A default list is provided of date format strings for each date field.

You have complete control over this list and may add to or modify it to suit your site's needs. The top format string takes precedence and subsequent format strings are only used if parsing a given metadata tag's content yields an error.

For example, suppose you have specified the following date formats:

<table id="table_46E4B024856D432EBFE5DBCEC823BC76"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d, %Y %T %Z </p> <p>%b %d, %Y %T %Z </p> <p>%A %B %d, %Y %T %Z </p> <p>%A %b %d, %Y %T %Z </p> <p>%a %B %d, %Y %T %Z </p> <p>%a %b %d, %Y %T %Z </p> <p>%d %b %Y %T %Z </p> </td> 
  </tr> 
 </tbody> 
</table>

The first format, "%B %d, %Y %T %Z", matches dates like the following "September 20, 2014 13:12:00 PDT". If the metadata tag content cannot be parsed with this format string, the next available format "%b %d, %Y %T %Z" is tried. This format matches dates like the following: "Sep 20, 2014 3:12:00 PDT". If the metadata tag content cannot be parsed with this format string, site search/merchandising moves down the list of format strings until it finds a format string that works.

The following table describes the available date format strings:

<table id="table_31CBAA23CE484050BB08732F2864AA75"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Data format </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p>Matches the national representation of the full weekday name, for example, "Monday." The national representation is determined from the "Language" setting on the "Words &amp; Languages" Option </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> matches the national representation of the abbreviated weekday name, where the abbreviation is the first three characters, e.g. "Mon." The national representation is determined from the "Language" setting on the "Words &amp; Languages" Option </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> matches the national representation of the full month name, e.g. "June." The national representation is determined from the "Language" setting on the "Words &amp; Languages" Option </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> matches the national representation of the abbreviated month name, where the abbreviation is the first three characters, e.g. "Jun." The national representation is determined from the "Language" setting on the "Words &amp; Languages" Option </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p> is equivalent to "%m/%d/%y", e.g. "06/06/01" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> matches the day of the month as a decimal number (01-31) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> matches the day of month as a decimal number (1-31); single digits are preceded by a blank </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> matches the hour (24-hour clock) as a decimal number (00-23) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> matches the national representation of the abbreviated month name, where the abbreviation is the first three characters, e.g. "Jun" (the same as %b) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> matches the hour (12-hour clock) as a decimal number (01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> matches the day of the year as a decimal number (001-366) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> matches the hour (24-hour clock) as a decimal number (0-23); single digits are preceded by a blank </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> matches the hour (12-hour clock) as a decimal number (1-12); single digits are preceded by a blank </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> matches the minute as a decimal number (00-59) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> matches the month as a decimal number (01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> matches the national representation of either "ante meridiem" or "post meridiem" as appropriate, e.g. "PM." The national representation is determined from the "Language" setting on the "Words &amp; Languages" Option </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p> is equivalent to "%H:%M", e.g. "13:23" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p> is equivalent to "%I:%M:%S %p", e.g. "01:23:45 PM" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> matches the second as a decimal number (00-60) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p> is equivalent to "%H:%M:%S", e.g. "13:26:47" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> matches the week number of the year (Sunday as the first day of the week) as a decimal number (00-53) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p> is equivalent to "%e-%b-%Y", e.g. "6-Jun-2001" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> matches the year with century as a decimal number, e.g. "2001" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> matches the year without century as a decimal number (00-99) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> matches the time zone name </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> matches "%" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Default Format Strings**

The following default format strings are used by templates. You can add to this list or edit it as necessary.

<table id="table_684D549E013945328E4E0B8A2000283B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Default format string </p> </th> 
   <th colname="col2" class="entry"> <p>Resulting example </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> September 5, 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sep 5, 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sunday September 5, 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sunday Sep 5, 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sun September 5, 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sun Sep 5, 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d %b %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 5 Sep 1999 13:12:00 PDT </p> </td> 
  </tr> 
 </tbody> 
</table>

