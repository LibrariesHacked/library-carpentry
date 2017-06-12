Teaching. Foundations
=====================

Jargon Busting
--------------

| Terms | Description |
| ----- | ----------- |
| Dataset | A collection of related sets of information that is composed of separate elements but can be manipulated as a unit by a computer. |
| Pivot table | A pivot table can automatically sort, count, total or average the data stored in one table or spreadsheet, displaying the results in a second table showing the summarized data. |
| Data science | An interdisciplinary field about scientific methods, processes, and systems to extract knowledge or insights from data in various forms, either structured or unstructured. |
| Group | A term used to describe aggregating data (e.g. providing a total) by a particular field or fields. |
| Formula | An expression telling the computer what mathematical operation to perform upon a specific value. |
| Average | A number expressing the central or typical value in a set of data, in particular the mode, median, or (most commonly) the mean, which is calculated by dividing the sum of the values in the set by their number |
| Algorithm | A list of rules to follow in order to solve a problem. |
| Big data | Extremely large data sets that may be analysed computationally to reveal patterns, trends, and associations, especially relating to human behaviour and interactions. |
| Outlier | A person or thing differing from all other members of a particular group or set. |
| Open data | Open data is data that can be freely used, re-used and redistributed by anyone - subject only, at most, to the requirement to attribute and sharealike. |
| Aggregation | A process in which information is gathered and expressed in a summary form, for purposes such as statistical analysis. |
| Anonymisation |  The process of turning data into a form which does not identify individuals and where identification is not likely to take place. |
| Regular expression | A sequence of symbols and characters expressing a string or pattern to be searched for within a longer piece of text. |
| Data mining | The practice of examining large pre-existing databases in order to generate new information. |
| Data protection | Data protection principles govern how your personal information is used by organisations, businesses or the government. |

We'll  spend some time on some foundation level stuff - a combination of best practice and generic skills that frame what you'll encounter across Library Carpentry.

The Computer is Stupid
----------------------

This does not mean that the computer isn’t useful. Given a repetitive task, an enumerative task, or a task that relies on memory, it can produce results faster, more accurately, and less grudgingly than you or I. Rather when I say that you should keep in mind that the computer is stupid, I mean to say that computer only does what you tell it to. If it throws up an error it is often not your fault, rather in most cases the computer has failed to interpret what you mean because it can only work with what it knows (ergo, it is bad at interpreting). This is not to say that the people who told the computer what to tell you when it doesn’t know what to do couldn’t have done a better job with error messages, for they could. So keep in mind as we go along that if you find an error message frustrating, it isn't the computer's fault that it is giving you an archaic and incomprehensible error message, it is a human person's.

Why take an automated or computational approach?
------------------------------------------------

Otherwise known as the 'why not do it manually?' question. To start with, I'm not anti-manual. I do plenty of things manually that a machine could do in an automated way because either:

a) I don’t know how to automate the task or;
b) I’m unlikely to repeat the task and estimate that automating it would take longer

However once you know you'll need to repeat a task, you have a compelling reason to consider automating it. This is one of the main areas in which programmatic ways of doing outside of IT service environments are changing library practice. Andromeda Yelton, a US based librarian closely involved in the Code4Lib movement, put together an excellent American Library Association Library Technology Report called 'Coding for Librarians: Learning by Example.' The report is pitched at a real world relevance level, and in it Andromeda describes scenarios library professionals told her about where learning a little programming, usually learning ad-hoc, had made a difference to their work, to the work of their colleagues, and to the work of their library.

Keyboard shortcuts are your friend
----------------------------------

Though we will get more computational over the course of the programme, we can start our adventure into programming - as many of you will have already - with very simple things like keyboard shortcuts. 

| Shortcut | What does it do |
| -------- | --------------- |
| Ctrl + s | Saves the current document |
| Ctrl + c | Copies the current selection to the clipboard |
| Ctrl + x | Cuts the current selection to the clipboard |
| Ctrl + v | Pastes the current clipboard contents to the current document |


Plain text formats are your friend
----------------------------------

Why? Because computers can process them!

If you want computers to be able to process your stuff, try to get in the habit where possible of using platform-agnostic formats such as .txt for notes and .csv or .tsv for tabulated data (the latter pair are just spreadsheet formats, separated by commas and tabs respectively). 

### CSV Files


### TXT Files


### Markdown



These plain text formats are preferable to the proprietary formats used as defaults by Microsoft Office because they can be opened by many software packages and have a strong chance of remaining viewable and editable in the future. Most standard office suites include the option to save files in .txt, .csv and .tsv formats, meaning you can continue to work with familiar software and still take appropriate action to make your work accessible. Compared to .doc or .xls, these formats have the additional benefit of containing only machine-readable elements. Whilst using bold, italics, and colouring to signify headings or to make a visual connection between data elements is common practice, these display-orientated annotations are not (easily) machine-readable and hence can neither be queried and searched nor are appropriate for large quantities of information (the rule of thumb is if you can’t find it by CTRL+F it isn’t machine readable). Preferable are simple notation schemes such as using a double-asterisk or three hashes to represent a data feature: in my own notes, for example, three question marks indicate something I need to follow up on, chosen because ??? can easily be found with a CTRL+F search.
??? was also chosen by me because it doesn’t clash with existing schemes. Though it is likely that notation schemes will emerge from existing individual practice, existing schema are available to represent headers, breaks, et al. One such scheme is Markdown, a lightweight markup language. Markdown files are as .md, are machine readable, human readable, and used in many contexts - GitHub for example, renders text via Markdown. An excellent Markdown cheat sheet is available on GitHub for those who wish to follow – or adapt – this existing schema. Notepad++ http://notepad-plus-plus.org/ is recommended for Windows users as a tool to write Markdown text in, though it is by no means essential for working with .md files. Mac or Unix users may find Komodo Edit, Text Wrangler, Kate, or Atom helpful. Combined with pandoc, a markdown file can be exported to PDF, LaTeX or other formats, so it is a great way to create machine-readable, easily searchable documents that can be repurposed in many ways. It is a universal document converter.


Naming files sensible things is good
------------------------------------



Working with data is made easier by structuring your stuff in a consistent and predictable manner.
Why?
Without structured information, our lives would be much poorer. As library and archive people we know this. But I’ll linger on this a little longer because for working with data it is especially important.
Examining URLs is a good way of thinking about why structuring research data in a consistent and predictable manner might be useful in your work. Good URLs represent with clarity the content of the page they identify, either by containing semantic elements or by using a single data element found across a set or majority of pages.
A typical example of the former are the URLs used by news websites or blogging services. WordPress URLs follow the format:
ROOT/YYYY/MM/DD/words-of-title-separated-by-hyphens
http://cradledincaricature.com/2015/07/24/code-control-and-making-the-argument-in-the-humanities/
A similar style is used by news agencies such as a The Guardian newspaper:
ROOT/SUB_ROOT/YYYY/MMM/DD/words-describing-content-separated-by-hyphens
http://www.theguardian.com/uk-news/2014/feb/20/rebekah-brooks-rupert-murdoch-phone-hacking-trial
In data repositories, URLs structured by a single data element are often used. The NLA’s TROVE structures its online archive using the format:
ROOT/record-type/REF
http://trove.nla.gov.au/work/6315568
And the Old Bailey Online uses the format:
ROOT/browse.jsp?ref=REF`
http://www.oldbaileyonline.org/browse.jsp?ref=OA16780417

What we learn from these examples is that a combination of semantic description and data elements make for consistent and predictable data structures that are readable both by humans and machines. Transferring this to your stuff makes it easier to browse, to search, and to query using both the standard tools provided by operating systems and by the more advanced tools Library Carpentry will cover.

In practice, the structure of a good archive might look something like this:

A base or root directory, perhaps called 'work'.

A series of sub-directories such as ‘events', ‘data’, ‘ projects’ et cetera

Within these directories are series of directories for each event, dataset or project. Introducing a naming convention here that includes a date element keeps the information organised without the need for subdirectories by, say, year or month.
All this should help you remember something you were working on when you come back to it later (call it real world preservation).
The crucial bit for our purposes, however, is the file naming convention you choose. The name of a file is important to ensuring it and its contents are easy to identify. ‘Data.xslx’ doesn’t fulfil this purpose. A title that describes the data does. And adding dating convention to the file name, associating derived data with base data through file names, and using directory structures to aid comprehension strengthens those connection.


Key Points
----------

- Data structures should be consistent and predictable
- Consider using semantic elements or data identifiers to data directories
- Fit and adapt your data structure to your work
- Apply naming conventions to directories and file names to identify them, to create associations between data elements, and to assist with the long term readability and comprehension of your data structures

Source Material
---------------

[Library Carpentry - Data Intro - Foundations](https://data-lessons.github.io/library-data-intro/03-foundations/)