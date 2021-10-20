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


# Bringing records into the MARC editor

With MarcEdit we are able to open files, but we can also import records from various catalogues around the world if we would like. This process requires setting up a Z39.50 client in MarcEdit. Z39.50 is an international standard for communicating with databases, and is used by a lot of library applications. The way that we are going to use it is to query the University of Toronto Library catalogue for records.

1. Open the MarcEdit program. Click on the icon labelled Z39.50/SRU Client.
2. Click on Modify Databases from the menu on the left side.
3. Click on Add Database from the Options menu, and choose "Add New Z39.50 Server."
4. Fill in the form as follows:
` Name: University of Toronto (Alma)
Host: utoronto.alma.exlibrisgroup.com
Database: 01UTORONTO_INST
Port: 1921
Syntax: MARC21 `

5. Ensure Show Database is checked.
6. Click Save.

Return to Search Mode, or Batch Search Mode, and you will see U. of Toronto as one of the databases you can now query.

Searching UTL in MarcEdit6's Z39.50
Use Search Types > Custom: @attr 1=12 to search by Sirsi catkey.
****CONFIRM THIS IS TRUE*******

ADDITIONAL NOTES
This process can be used with other Z39.50 databases and the search can be done using other fields.

For a list of all attributes: Bib-1 attribute set ( https://www.loc.gov/z3950/agency/defns/bib1.html )
For other Z39.50 databases: ( http://irspy.indexdata.com/ )
This website also lists the attributes supported by each database.

# Bringing in records with the ISBN 0199370680

In Z39.50 

Search mode, search by ISBN 0199370680, double click on a result, change the save file path, and then "Download record" .
- Append record setting
Batch mode - 
