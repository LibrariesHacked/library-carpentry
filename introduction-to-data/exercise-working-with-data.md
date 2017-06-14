Exercise. Working with data
===========================

Requirements
------------

- Spreadsheet software (e.g. Excel, Libre Office, Google Sheets)
- Internet

Task
----

We will be use a couple of example datasets to have a play with some data using spreadsheets.  And to get a feel of tackling data when it's not in a structure that gives us immediate answers.

- **Library usage**, released by Newcastle libraries.  This contains number of issues, visits, and enquiries by month, for each library, from 2008. [Download this dataset](https://raw.githubusercontent.com/LibrariesHacked/library-carpentry/master/data/newcastle_usage.csv)
- **Library members**, released by Newcastle libraries.  Includes a list of members (anonymised), when they joined, were last active, and what library they are registered at. Taken from 2016. [Download this dataset](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/newcastle_members.csv)

The data is released under the Creative Commons CCZero licence.

Usage (*newcastle_usage.csv*):

| Column | Description | Example |
| ------ | ----------- | ------- |
| Library | The branch library the activity occured at | Blacklaw |
| Month | The year and month of the activity in the form YYYY-MM | 2008-04 |
| Enquiries | The number of questions asked of library staff by a member of the public | 312 |
| Visits | The number of people entering the library  | 1768 |
| Issues |The number of items loaned from the library | 1048 |
| Sessions | Usage of computers as percentage of the total available time computers can be booked | 39% |

Members (*newcastle_members.csv*):

| Column | Description | Example |
| ------ | ----------- | ------- |
| Postcode | The postcode district of the member home address | AB10 |
| Library Registered At | The branch library the member is registered at | CITY |
| Date Added | The date the member joined the library | 04/09/2015 |
| Time Added | The time the member joined the library | 08:45:00 |
| Last Used Date | The date the member last used the library | 04/09/2015 |
| Last Used Time | The time the member last used the library | 08:45:00 |

Work in groups, and share knowledge, to answer the following questions of the data.  During this time we will see each group and help out.  Brief guidance is given for each questions, and possible answers provided on a separate sheet.  Spend some time looking at the data and considering how it may need to be manipulated to reach the answer.

### Q1. Usage. Which library has had the highest number of issues since 2008?  How many?

It may be easy to guess which library loans the most, but pivot tables could be the simplest way to aggregate the data to see a total for each library.  What about also sorting the libraries in order of total items issued?

### Q2. Usage. Which year has the highest number of issues?

The key here is to group the data by Year.  How do we do that when the field is provided in year AND month (e.g. '2008-04')?

### Q3. Usage. At City library, which calendar month (January to December) is busiest for enquiries?

Similar task to above, you will need to separate out the month (e.g. '04') from the year and month field ('2008-04').  How will we decide which month is the busiest, when we have data for multiple years?

### Q4. Members. Which individual month (e.g. June 2011) saw the highest number of new members?

The data provides a 'date added' for each member.  You'll need to group by the month, but remember to not add up members across different years (e.g. June 2009 and June 2010 should be kept as separate counts).  Then find the month with the highest count of members.

### Q5. Members.  Which postcode area has the highest number of members?

In the UK, a postcode has 4 levels.  Look at the examples in the table below to see how these are structured.

| Part | Description | Example |
| ---- | ----------- | ------- |
| Postcode Area | One or two alpha characters at the start of the full postcode, the letters being derived from a town, city or district falling within the area. There are, at present, 120 postcode areas in Great Britain. | TA |
| Postcode District | A sub-area of the postcode area, specified by the character sub-string within the first half of a full postcode. There are approximately 2,800 postcode districts in Great Britain. | TA1 |
| Postcode Sector | A sub-area of a postcode district, whose area is identified by the number third from the end of a full postcode. There are approximately 9,000 postcode sectors in Great Britain. | TA1 3 |
| Postcode Unit | Postcode units are unique references and identify an average of 15 addresses. There are approximately 1.7 million postcode units in the UK. | TA1 3XZ |

The data provided by Newcastle has been anonymised to only include the member's Postcode District e.g. NE3.  We want to count how many members are in each Postcode Area e.g. NE.  Remember, Postcode Areas can be 1 OR 2 characters.  How can we convert a Postcode District to a Postcode Area?

Discuss how you would go about doing this.  In the data files, a copy of the data is also provided with the data converted to Postcode Areas (newcastle_members_postcodeareas.csv).  We'll be using this later on when doing some mapping.

After the exercise we'll go through possible answers in a demo.

### Q6.  Other Insight.  What else could be done with the data?

Spend some time looking at the data and considering each field, how could they be used for other analysis?  What are the problems with the data?  Do you use similar data in your current role?  What typical tasks may you tend to do with the data?

Key points
----------

- We can't rely on data being in the form that we need it
- We can apply key data skills to practical applications with simple library data