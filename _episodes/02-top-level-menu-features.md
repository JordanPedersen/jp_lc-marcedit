---
title: "What is a MARC record?"
teaching: 0
exercises: 0
questions:
objectives:
- "Understand at a conceptual level what a MARC record is"
- "Know where to go to look up MARC components"
keypoints:
- "MarcEdit offers a customizable interface with a suite of tools including the MarcEditor"
- "Users can customize their preferences in the Settings module"
---

# MARC records
This quick intro is to help lay a foundational understanding for anyone who has not worked with MARC records before.

## MARC standard
MARC is an acronym that stands for *MA*chine-*R*eadable *C*ataloging . It is a set of standards for highly structured metadata, that is easily interpreted by computers. The MARC standard was developed in the 1960s, and is now used almost internationally for libraries. In different places there may be variations on the MARC standard (such as KORMARC in Korea), and in Canada we use MARC 21 (which is also used in the U.S. and most of Europe).

Within the MARC standard, there are various components, including bibliographic records (shortened to "bib records" or "bibs"), holdings records, and authorities. Bibliographic records (which is what we'll be working with for this workshop) contain information about resources that the library has, whereas the holdings record contains information about where the resources are located.

## MARC21 format
Within each MARC bibliographic record, there are fields and subfields, and each field and subfield correspond to a specific piece of information. There are also two indicators in between the field number and the subfields, and these will also help the computer read the information in the field.

We won't get too bogged down on details of MARC right now, but to provide one example:

` 245	00 $a Spudwrench $h [videorecording] : $b Kahnawake man / $c a National Film Board of Canada production. `

This is an example 245 field, and the indicators are 00. There is a subfield a,h,b,c - which we can identify by the dollarsigns that come before them in MarcEdit.
