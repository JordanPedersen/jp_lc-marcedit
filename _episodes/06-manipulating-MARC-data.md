---
title: "Manipulating MARC data"
teaching: 0
exercises: 0
questions:
- "How can MARC data be manipulated?"
- "How can the RDA Helper be used?"
- "How can fields, subfields, and/or indicators be added, changed, or removed?"
- "How can fixed fields be manipulated?"
- "How can Select Records for Edit be used to manipulate a subset of your MARC file?"
- "What is the difference between save and compile?"


objectives:
- "Explain how to add, update, and remove fields, subfields, indicators, and fixed fields"
- "Explain the functions RDA Helper and Select Records for Edit"
- "Explain the difference between save and compile"
- "Successfully manipulate MARC data"
- "Successfully save your MARC data"
- "Successfully compile your MARC data"


keypoints:
- "MarcEdit can be used to edit any part of the MARC data including the Leader, fixed fields, fields, indicators, subfields and the content in those fields."
- "MarcEdit comes with an array of tools to manipulate data and validate MARC."
---

{% include links.md %}


# Manipulating MARC data

MarcEdit is useful because we can modify the records individually, or as a group. We'll look at regular expressions in the next section, which will allow us to make powerful changes in batch to fields based on the patterns that are present in them, but for now we'll make some manual changes using the RDA helper, find and replace, and the built in editing functions.

# RDA helper

As mentioned at the beginning the MARC standard (which tells us how the data is structured) works in conjunction with other standards (such as cataloguing standards like RDA). RDA stands for "resource description and access:, and it tells cataloguers the best way to describe resources, and can be used with many data schemas such as MARC, Dublin Core, etc.. The precursor to RDA was called AACR2, and now it's possible that we will now have records that follow AACR2 and RDA within our catalogue. This isn't a major problem for us, but if we're going to be working with records anyway, it can be nice to try to update the AACR2 records so that they are more consistent with RDA.

The major changes you will see between AACR2 and RDA records are:

> RDA records will not have General Material Designators (GMD’s—245 $h). Instead each RDA record will have a 336 for the content type, a 337 for media type, and a 338 for carrier type. Rather than a single non-repeatable 260 containing the publication, distribution, manufacture and copyright information, this information is given in the repeatable 264. If needed, multiple 264s are used to individually call out the publisher, distribution, manufacture, and copyright information. 
> https://www.librarianshipstudies.com/2017/07/resource-description-and-access-rda.html

###Exercise###
Knowing what we know about the RDA standard, use find to see if you can see any indication of fields or subfields from the AACR2 standard 
- are there 245$h fields? How many?
- how many records have 3XX fields?
- how many records have 260 fields vs. 264s?
Write down the numbers to each question.

Now we're going to update our records. To do this, MarcEdit has a built in tool called the RDA helper, which we can access by clicking on tools > RDA helper. 
Check the boxes for all the 3XX field updates, the 260/264 updates, modify 040, and delete GMD. Click process.

Run your find searches again and see what has changed.


# Find and replace
Another thing that we can do to make changes in a record is find and replace. 
For example, searching for the 100 fields (author), we'll notice that one record contains "Mrs. Hey" as the author. There have been projects in libraries to identify women by their proper names, and not as Mrs. X (see https://www.libraryjournal.com/?detailStory=identifying-1257-married-women-by-their-full-names-in-columbia-university-rare-book-and-manuscript-library-finding-aids-peer-to-peer-review if you're interested).
While we don't actually know Mrs. Hey's first name, let's assume we did some sleuthing and found out that it was Mary. To replace this, we could type it in to each record that contains her name, or if we want to change every instance in our file (assuming that her name comes up more than once), we could use find and replace.

Select Edit > Find and Replace, and find "$aHey,$cMrs." (subfield a is "Personal name" and subfield c is "Titles and words associated with a name"). In the replace box, we can replace it with "$aMary Hey". Click replace all.

Review record

Note: match case can be finicky!


# Built in editing functions

1. Show off editing shortcuts and give examples
2. Tools - add and delete field, build new fields, etc.

###Exercise###
Use tools, change indicators for 650 "\0" which stands for no level of encoding specified, library of congress subject heading to "\4" which means the source of the subject heading is not specified.


# Introducing Special Undo
When making record changes, if you find that the wrong records were altered or that you would like to undo the operation, select Edit > Special Undo. 
