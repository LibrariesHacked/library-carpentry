Exercise.  Mapping libraries
============================

Requirements
------------

- Laptop or tablet
- Internet
- Data files (see downloads)

Downloads
---------

For this exercise we will be using two files.

- [Libraries taskforce libraries dataset](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/taskforce.csv).  A listing of English Libraries including their address and postcode.
- [UK postcodes](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcodes.csv]).  A full list of UK postcodes, taken from 'Code Point Open', an Ordnance Survey open data product.

There should be no need to download these files.  They're held online so we'll let Carto access them.

Task
----

In this task we are going to take a dataset published by the Libraries Taskforce on [30th March 2017](https://librariestaskforce.blog.gov.uk/2017/03/30/library-data-the-story-so-far-and-next-steps/).  This includes addresses of all libraries in England.  We will load this into the online tool Carto (will will create an account).  We will then use the location of Postcodes, provided by Ordnance Survey, to **'geocode'** these libraries.  Finally, we'll plot them on a web map, and you'll have a chance to play around with how they're displayed.

- In your browser navigate to [https://carto.com/](https://carto.com/).
- In the Menu navigate to **Signup** or navigate to [https://carto.com/signup/](https://carto.com/signup/).
- You'll notice you can sign up using your GitHub account.  Feel free to use the one you created earlier, or fill in the details and create a new account.
- When prompted for additional details fill these out if you wish to.  There's no need to provide phone number.
- Once logged in on the Menu navigate to **Maps > Your Datasets**.
- Select **New Dataset**.
- In the URL field enter: **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/taskforce.csv**
- Click Submit
- There is no a number of options as to whether you want to Sync the data. These options are provided with paid account.  Select the default of **'Never'** and **'Connect Dataset'**
- The dataset will be displayed.  You could choose then to create a map but nothing would be displayed as there is no *geometry* data (no coordinates).
- Return to the Data menu (the top left 'dot') and add a new dataset.
- This time use the URL: **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcodes.csv**
- Import the data as before.  This may take some extra time as the postcode dataset is a lot bigger!

We now have two datasets loaded into Carto.  One with all the libraries, including their postcodes.  Another with all the postcodes, including their coordinates.  We need to merge in the postcode coodinates to the librasries dataset so we have a datset of libraries with coordinates.

- Go into the **postcodes** dataset.  Select at the bottom the option to show **SQL**.  This will show:

```SQL
SELECT * FROM postcodes
```

This is showing that the view is currently showing all columns (*) from the postcodes dataset.  We can change this toa view that would show a selection from multiple tables.

- Change the SQL to the following.

```SQL
SELECT library_name, library_service, postal_address,
(select postcodes.the_geom from postcodes where postcodes.postcode = taskforce.postcode)
FROM taskforce
```

- Click **'Apply'**.  Carto will chug away for a little while fetching the data.

- Spend 5 minutes playing with the interface