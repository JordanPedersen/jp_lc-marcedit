---
title: "Regular Expressions"
teaching: 0
exercises: 0
questions:
- "What are tasks?"


objectives:
- "Explain the objective"


keypoints:
- "First key point."
---
{% include links.md %}

# Introducing Regular Expressions
Regular expressions (often called "regex") allow us to identify patterns and then replace and modify data based on these patterns. Many computer programs use them, and there are different "flavours" depending on the context. This is important because what you might see in python regex documentation might be different from what will work in marcedit (marcedit uses .net regex).

A regular expression, often abbreviated to regex, is a method of using a sequence of characters to define a search to match strings, i.e. “find and replace”-like operations. In computation, a ‘string’ is a contiguous sequence of symbols or values. For example, a word, a date, a set of numbers (e.g., a phone number), or an alphanumeric value (e.g., an identifier). A string could be any length, ranging from empty (zero characters) to one that spans many lines of text (including line break characters). The terms ‘string’ and ‘line’ are sometimes used interchangeably, even when they are not strictly the same thing.

In library searches, we are most familiar with a small part of regular expressions known as the “wild card character,” but there are many more features to the complete regular expressions syntax. Regular expressions will let you:

Match on types of characters (e.g. ‘upper case letters’, ‘digits’, ‘spaces’, etc.).
Match patterns that repeat any number of times.
Capture the parts of the original string that match your pattern.
Regular expressions rely on the use of literal characters and metacharacters. A metacharacter is any American Standard Code for Information Interchange (ASCII) character that has a special meaning. By using metacharacters and possibly literal characters, you can construct a regex for finding strings or files that match a pattern rather than a specific string. For example, say your organization wants to change the way they display telephone numbers on their website by removing the parentheses around the area code. Rather than search for each specific phone number (that could take forever and be prone to error) or searching for every open parenthesis character (could also take forever and return many false-positives), you could search for the pattern of a phone number.

Since regular expressions defines some ASCII characters as “metacharacters” that have more than their literal meaning, it is also important to be able to “escape” these metacharacters to use them for their normal, literal meaning. For example, the period . means “match any character”, but if you want to match a period then you will need to use a \ in front of it to signal to the regular expression processor that you want to use the period as a plain old period and not a metacharacter. That notation is called “escaping” the special character. The concept of “escaping” special characters is shared across a variety of computational settings, including markdown and Hypertext Markup Language (HTML).

Learning common regex metacharacters
Square brackets can be used to define a list or range of characters to be found. So:

[ABC] matches A or B or C.
[A-Z] matches any upper case letter.
[A-Za-z] matches any upper or lower case letter.
[A-Za-z0-9] matches any upper or lower case letter or any digit.
Then there are:

. matches any character.
\d matches any single digit.
\w matches any part of word character (equivalent to [A-Za-z0-9]).
\s matches any space, tab, or newline.
\ used to escape the following character when that character is a special character. So, for example, a regular expression that found .com would be \.com because . is a special character that matches any character.
^ is an “anchor” which asserts the position at the start of the line. So what you put after the caret will only match if they are the first characters of a line. The caret is also known as a circumflex.
$ is an “anchor” which asserts the position at the end of the line. So what you put before it will only match if they are the last characters of a line.
\b asserts that the pattern must match at a word boundary. Putting this either side of a word stops the regular expression matching longer variants of words. So:
the regular expression mark will match not only mark but also find marking, market, unremarkable, and so on.
the regular expression \bword will match word, wordless, and wordlessly.
the regular expression comb\b will match comb and honeycomb but not combine.
the regular expression \brespect\b will match respect but not respectable or disrespectful.


So, what is ^[Oo]rgani.e\b going to match?

Other useful special characters are:

* matches the preceding element zero or more times. For example, ab*c matches “ac”, “abc”, “abbbc”, etc.
+ matches the preceding element one or more times. For example, ab+c matches “abc”, “abbbc” but not “ac”.
? matches when the preceding character appears zero or one time.
{VALUE} matches the preceding character the number of times defined by VALUE; ranges, say, 1-6, can be specified with the syntax {VALUE,VALUE}, e.g. \d{1,9} will match any number between one and nine digits in length.
| means or.
/i renders an expression case-insensitive (equivalent to [A-Za-z]).


For a regex cheatsheet, check out: https://cheatography.com/davechild/cheat-sheets/regular-expressions/ (not all options will work with marcedit, but most will).

For an environment where you can test regex, check out: https://regex101.com/


# Using Regular Expressions with find and replace

Let's put this into practice. Let's say we want to add a subfield z (public note) that says "University of Toronto access only" to the 856 field (which contains the url for e-resources), and we want it to be the first subfield.

1. Search for the =856 fields. Is there a pattern here?
2. Can we identify that pattern using our regex characters? (hint =856
3. Make groupings using brackets
4. Replace with $1$2 etc.

One solution:

> Find: (=856\s\s..)(.*)
> Replace $1$zUniversity of Toronto access only$2

###Exercise
Find all the medical subject headings (650 with second indicator 2) and change the second indicator to 7 (source specified in subfield 2), and then add a subfield 2 that says "your name's subject".
* note, this isn't a real world task exactly, what we would be more likely to do is to take those adam matthew records and change their subject headings to source not specified because they don't adhere to the LC standard. Could introduce extracting based on a certain field if there is time.

Solutions with errors:
> Find: (=650\s\s.)(2)(.*)
> Replace $12$3$7Jordan's subject
>   this is very close but it will confuse the computer into thinking that group 12 is the first thing, and we actually only have 3 groups

> Find: (=650\s\s.)(2)(.*)
> Replace $1\2$3$7Jordan's subject
>   this is very close but we get an extra indicator ex. =650  \\2$aSocial medicine.$7Jordan's subject

Can we remove this extra indicator?
> Find: (=650\s\s.)(\\)(7)
> Replace $1$3



# Tasks and Automation
