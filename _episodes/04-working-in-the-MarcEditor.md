---
title: "Bringing records into the MARC editor"
teaching: 0
exercises: 0
questions:
- "What is the MarcEditor?"
- "How are MARC files organized in the MarcEditor"
objectives:
- "Explain what the MarcEditor does"
- "Explain how the MarcEditor features can help work with MARC files"
keypoints:
- "First key point. "
---

{% include links.md %}


# Install requirements
This section is really only possible if either all learners are using PCs, or if there are explicit instructions to install everything needed to support the Z39.50 client for the Mac version: https://marcedit.reeset.net/marcedit-mac-enabling-z39-50-support

In all liklihood we will not do these exercises because the other skills required (using the terminal to install homebrew and yaz, which might be too much (and really not critical to being able to use MarcEdit).

# Bringing records into the MARC editor

With MarcEdit we are able to open files, but we can also import records from various catalogues around the world if we would like. This process requires setting up a Z39.50 client in MarcEdit. Z39.50 is an international standard for communicating with databases, and is used by a lot of library applications. The way that we are going to use it is to query the University of Toronto Library catalogue for records.

1. Open the MarcEdit program. Click on the icon labelled Z39.50/SRU Client.
2. Click on Modify Databases from the menu on the left side.
3. Click on Add Database from the Options menu, and choose "Add New Z39.50 Server." (the interface will look a little different for mac users - you'll click on settings - add/delete/edit databases and then where there is a drop-down menu with the option "Add", you'll click on it and select "Z39.50 Database")
4. Fill in the form as follows:

> Name: University of Toronto (Alma)
> Host: utoronto.alma.exlibrisgroup.com
> Database: 01UTORONTO_INST
> Port: 1921
> Syntax: MARC21

5. Ensure Show Database is checked if it is an option that is available to you. Also, if there is an option for "6 second override" (or something similar) check the box as well. It will keep the program from freezing if it encounters oddities in the records.
6. Click Save.

Return to Search Mode, or Batch Search Mode, and you will see University of Toronto as one of the databases you can now query.

Ensure that you are searching the right database by clicking on "Select database" and picking University of Toronto.


ADDITIONAL NOTES
This process can be used with other Z39.50 databases and the search can be done using other fields.

For a list of all attributes you can search using the Z39.50 client, this is a great resource: Bib-1 attribute set ( https://www.loc.gov/z3950/agency/defns/bib1.html ). What this means is that you can search other parts of the records that are indexed.
For other Z39.50 databases, and the attribute searching that they allow: ( http://irspy.indexdata.com/ ) . 


# Bringing in records with the ISBN 0199370680

In Z39.50 

Search mode, search by ISBN 0199370680. Ensure that "retrieve unicode" is checked, and that UTF8 is selected as the server character set (this will keep non-Roman characters from being corrupted because UTF8 is the way we format our records).


Click on a result and choose "View selected record". While we have the record open, on windows you will see an option to change the save file path (I recommend just saving to your desktop for this workshop) and then click on "Download record". For mac users, you will select the record, click on "Download selected records" and then change the save file path and Download. I'm calling mine Mcwhinney (the .mrc extension will be added automatically).

***Exercise***
Download another record. 
Maybe talk about appending.


# Batch mode

To be most efficient, we will often want to download records in groups. Because we have a file called "Mcwhinney", I'm going to download a batch of records about horses and medicine (their subject contains "horse" or "medicine"). To do this we'll switch to searching by subject, and we'll use the file that is shared as our input. 

We'll need to set the download path again. I'll save mine on my desktop and call it "horse_batch". Our other unicode settings will stay the same. If we keep our record limit to 20, we will only take the first 20 results from each search. We can download larger batches, but for our workshop today we'll stick to our 40 records (20 with the subject horse, 20 with the subject medicine).





