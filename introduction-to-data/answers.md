Exercise Answers
================

Answers include methods for Microsoft Excel and Google Sheets. We're not specifically advocating for either of these, but they are commonly used tools and possibly represent a work/home split (work - often Microsoft Office, Home - Google Docs).  Other spreadsheet software will have very similar functionality but will differ in some respects.

Possible methods
----------------

There are no absolute 'correct' ways of going about doing these tasks.  These are possible methods.

### A1. Usage. Which library has had the highest number of issues since 2008.  How many?

One way of approaching this is to use a Pivot table to group the data by branch.  Then display a sum of issues for each branch.

#### Excel

1. Open *newcastle_usage.csv* in Excel.  Highlight all the data
2. On the Excel menu select **Insert > Pivot table** to launch a new Pivot table
3. Accept the default options and click **OK**
4. In the Pivot table selections, drag the **'Library'** field into the **'Rows'** section
5. Drag the **'Issues'** field into the **'Values'** section
6. Excel will calculate a 'Count of issues' for each library. This is actually the number of rows of data for that library.  Instead, we want the SUM of the issues (each value added together). In the pivot table selections click on **'Count of issues'** and select **'Value field settings'**.  Select **'Sum'** and click **OK**.
7. To sort the table, click the drop down on the pivot table labelled **'Row labels'**.  Click **'More sort options'** and select **'Sum of issues'**.

#### Google Sheets

1. In Google Sheets (https://docs.google.com/spreadsheets) start a new blank sheet.
2. Import the data.  Select **File > Import > Upload**. Drag the file newcastle_usage.csv to be uploaded, or use the file selection tool.
3. When prompted, select to replace the existing spreadsheet and click Import.
4. Select from the menu **Data > Pivot table**.
5. On the Pivot menu for the **Rows** option add the field Library.
6. On the **Values** option add the field Issues (ensure it says **'Summarise by SUM'**)
7. On the Rows options change 'Sort by: Library' to **'Sort by: SUM of issues'**.

You should finish with a table like the following (top 3 shown only).

| Row labels | Sum of issues |
| ---------- | ------------- |
| Outer West | 830724 |
| Gosforth | 1292978 |
| City | 2874941 |

The library with the most issues is City.  The number of issues is 2,874,941.

### A2. Usage. Which year has the highest number of issues?

Using pivot tables, as in the previous question, we can aggregate by particular fields, and sort the data.  However, the trickier part here is grouping by year, when we only have the data by month AND year (e.g. '2008-04').

We can use a calculated column to create a new column showing the year.

#### Excel

1. Within Excel go back to the main data worksheet.
2. Add a new Column called Year.
3. In Excel, the **'YEAR()'** function within a formula extracts the year part from a date.  However, we don't have valid dates, in column B we have a 'sortof' date as a year and month ('2008-04').  We can write a formula that will convert that data into a full date (e.g. '2008-04-01'), and then extract the year.  In the first data row of your new column enter the formula: **=YEAR(CONCATENATE(B2,"-01"))**
4. This is combining two functions: CONCATENATE and YEAR.  CONCATENATE appends the text '-01' to the data, to make it into a full date.  On this we then use the function called YEAR, which extracts the year.  The year should then apear as '2008'.
5. Use **'Fill Down'** in Excel to copy the formula for all cells of the column. Shortcut: Highlight the cell with the formula and use the keyboard shortcut **Ctrl+Shift+End**.  Then on the Excel menu select **Fill Down**.
5. Repeat the pivoting process as in the previous question but group the data by the Year column.

#### Google Sheets

1. Start a new sheet and import the data, or use the previous sheet.
2. Create a new column and call it 'Year'
3. Google sheets will already understand the existing month column is representing a Date value (they will add a day of 01).  In the first data row of the new Year column enter the formula: **=YEAR(B2)**
4. You should see that the data for the first row becomes '2008'
5. Copy this formula field and paste it into every field for the column.
6. Repeat the process from question 1 to pivot the data by year.

2010 was the year with the highest number of issues.  It had 1,387,851.

| Year | Sum of issues |
| ---- | ------------- |
| 2011 | 1180355 |
| 2009 | 1341039 |
| 2010 | 1387851 |

### A3. Usage. At City library, which month (January to December) tends to be busiest for enquiries?

This is similar to the previous question, but we need to extract month instead of year.  We also need to determine which calendar month *tends* to be the busiest for enquiries.  One month (e.g. January) could be busiest one year, but less busy the next.  We can calculate an average for each calendar month across all years.

#### Excel

1. Within Excel go back to the main data sheet.
2. Add a new Column called **'Month Number'**.
3. We could do the same as the previous question, but using the 'Month' function.  However, lets try something different.  We know to get the month we just need the last two numbers from the year/month field, as that field is always in the format '2008-04'.  Create another formula but use: **=RIGHT(B2,2)**
4. This will take the two numbers from the right hand side to give a month.
5. Repeat the process as before to pivot the data.  Filter to only include City library.  To do this drag the Library field into the Filter section.  On the pivot table you can then change from *'All' to **'City'**.
6. Drag the Enquiries field into the values section and change the Value field setting to **'Average of enquiries'**.
7. Drag the 'Month number' field into the Rows section and sort the pivot table as before.

#### Google Sheets

1. Start a new sheet and import the data, or use the previous sheet.
2. Create a new column and call it 'Month number'
3. As before, Google sheets will already understand the original date column as a date value.  In the first data row of the new column enter the formula: **=MONTH(B2)**
4. The data for the first row becomes '04' (April).
5. Copy this field and paste it for all fields in the column.
6. Pivot the data by month number.
7. In the Filter options, add the Library field and select to only show City.
8. In the Value options add the Enquiries field and select 'Summarise by: AVERAGE'
9. In the Rows options select to 'Sort by: Average of enquiries'

In City library, October is the busiest for enquiries, with an average of 30,294 enquiries since 2008.

### A4. Members. Which individual month (e.g. June 2011) saw the highest number of new members?

Again, we're going to group the data.  This time starting with the 'Date Added' column, that has a full date and converting it to a representation of year and month.

#### Excel

1. Open *newcastle_members.csv* in Excel.
2. Add a new column called **'Month Added'**
3. We're going to use a different Excel function.  The 'Text' function converts text into a defined format.  In the Month Added column enter the formula: **=TEXT(C2,"YYYY-MM")**
4. Here we are specifying the format we want the data.  In this just the year and the month. Try variations of this format such as "YY/MM" or "MMM YYYY".  For the first row you should see it change to 2015-09.
5. Use **'Fill Down'** in Excel to copy the formula into all cells of the column.
5. Repeat the pivoting process to group the data by the new 'Month Added' column.
6. When adding a Value field to the pivot table we just need a count of rows.  Add any field to the Values section.
7. Sort the pivot table.

#### Google Sheets

1. In Google Sheets (https://docs.google.com/spreadsheets) start a new blank sheet.
2. Import the data.  Select **File > Import > Upload**. Drag the file newcastle_members.csv to be uploaded, or use the file selection tool.
3. When prompted, select to replace the existing spreadsheet and click Import.
4. Add a new column called 'Month Added'
4. In the first data row of the new Year column enter the formula: **=TEXT(C2,"YYYY-MM")**
5. Here we are specifying the format we want the data in.  In this case just the year and the month.  Try variations of this format such as "YY/MM" or "MMM YYYY".  For the first row you should see it change to 2015-09.
6. Copy this field and paste it into every field for the column.
7. Pivot the data by this new column to get a count by each month.

August 1996 seems to have been the best month for registrations. 4375 new members!  Does this seem likely?

### A5. Members.  Which postcode area has the highest number of members?

This is a tricky question because we need to group the data by postcode area (e.g. TA) where we only have it as postcode district (e.g. TA1).

It is not as simple as, for example, taking the first two characters from the data.  For a postcode district of B1 that would keep it as B1 when it should become just B.  We need to remove all the numbers from the text.

This kind of problem is perfect for regular expressions. We'll go through doing this as a demo.  But here are two ways of doing it.

#### Excel

1. Go back to the data worksheet.
2. Create a new column called **'Postcode Area'**
3. In the first data row of your new column, enter manually what the Postcode Area should be, based upon the member Postcode field (hint: AB)
4. In the next row do the same thing.
5. Do this a few more times.
6. Select the next empty row in your new column.  In Excel on the data menu click **'Flash Fill'** (you may have to hunt around for it)
7. Excel magically completes the column for all members!
8. Pivot the data to get a count by postcode area.

This feels like cheating as it doesn't feel like a logical data process.  It's worth knowing about though!

#### Google Sheets

1. Start a new sheet and import the member data.
2. Create a new column call 'Postcode Area'
3. In the first data row of the new Year column enter the formula: **=REGEXREPLACE(A2,"\d","")**
4. This is using a regular expression to replace all numbers from the data in the column A2.
5. Copy this field and paste it into every field for the column.
6. Pivot the data by this new column to get a count by each month.
