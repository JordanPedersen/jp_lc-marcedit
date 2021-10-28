---
title: "Working in the MarcEditor"
teaching: 0
exercises: 0
questions:
- "How do I use different reports to get an overview of my MARC file?"
- "How do I locate errors in my records?"
- "How do I use the Edit Shortcuts tool to identify and fix common errors?""
objectives:
- "Access reports for getting an overview of your MARC data"
- "Find tools to locate errors in your MARC records by using the MARCedit Edit toolbar"
keypoints:
- "First key point."
---

{% include links.md %}


# Working in the MarcEditor

MarcEdit is technically available for both windows and mac users, but the experience is more user friendly on windows. That said, the tools available should be the same between both. Tools include the MarcEditor (for editing marc records), Marcbreaker and Marcmaker (for combining and splitting marc files), the delimited text translator (for converting excel files or csv files to marc records), and more.

The MarcEditor is the tool we will be working with for the rest of this workshop. To open the MarcEditor, open MarcEdit and click on the icon for "MarcEditor". 

# Reports in MarcEditor
The first thing that we will do once we have the marceditor open is to open a file. We will click on file in the top-left corner and choose open. We will then search for our file (with a .mrc , .mrk or .xml extension). Alternatively, if we had a marc file on our computer that we wanted to open, we could right click on the file and choose "preview with marcedit", which will open the file without corrupting it.

Because our marc files can be quite large (tens of thousands of records), it is helpful to be able to get an overview of our data. A report that is used commonly (and is handily built-in) is the field count report. To access the report, go to the top of the page, click on reports, then "field count report". This report will show you the number of times each field occurs in your file. This is helpful if you want to see at a quick glance how robust files are, or if you want to see if fields have been repeated an excessive number of times, which may indicate the records were created by webscraping and are actually of poor quality.


## Following up with find
We might notice that there are a tonne of 650 fields in these records (497 for only 40 records), which could be suspicious, especially if that isn't divided evenly amongst records. To follow up on things like this we can use find. 

It looks like some of our records have lots of 650 fields. We can click on them and jump to record, and we can determine if the file looks like it is good quality or not (would it be useful to our users if they searched by any of these subject terms).

