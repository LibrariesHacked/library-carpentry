Exercise.  Mapping libraries
============================

Requirements
------------

- Laptop or tablet
- Internet

Data files
----------

For this exercise we will be using two files.

- [Libraries taskforce libraries dataset](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/libraries.csv).  A listing of libraries in England, including their address and postcode.  Released under the [Open Government Licence](http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/). This must be acknowledged as: *Contains public sector information licensed under the Open Government Licence v3.0.*
- [UK postcodes](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcodes_england.csv]).  A full list of postcodes in England, taken from 'Code Point Open', an [Ordnance Survey open data product](https://www.ordnancesurvey.co.uk/business-and-government/licensing/using-creating-data-with-os-products/os-opendata.html).  This must be acknowledged as: *Contains OS data © Crown copyright and database right 2017. Contains Royal Mail data © Royal Mail copyright and Database right 2017. Contains National Statistics data © Crown copyright and database right 2017.*

There should be no need to download these files.  They're held online so we'll let Carto access them.

Task
----

In this task we are going to take a dataset published by the Libraries Taskforce on [30th March 2017](https://librariestaskforce.blog.gov.uk/2017/03/30/library-data-the-story-so-far-and-next-steps/).  This includes addresses and postcodes of all libraries in England.  We will load this into the online mapping tool, Carto.  We'll then use postcodes locations, provided by Ordnance Survey, to **'geocode'** these libraries.  Finally, we'll plot them on a web map, and you'll have a chance to play around with how they're displayed.

- In your browser navigate to [https://carto.com/](https://carto.com/).
- In the Menu navigate to **Signup** or navigate to [https://carto.com/signup/](https://carto.com/signup/).
- You'll notice you can sign up using your GitHub account.  Feel free to use the one you created earlier, or fill in the full details and create a new account.
- When prompted for additional details, fill these out if you wish to.  There's no need to provide a phone number.

Everyone should now have a Carto account, or ideally be near someone who does.  We'll run through a demo of uploading a dataset and mapping it.  Carto provides a free option so there should be no need to enter any payment details or sign up for a paid account.  These are expensive, but could be something your organisation considers as it offers access to some powerful data analytics and extra data storage.

Instructor Demo
---------------

- Once logged in, on the Menu navigate to **Maps > Your Datasets**.
- Select **New Dataset**.
- In the URL field enter: **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/libraries.csv**
- Click **'Submit'**
- There are a number of options as to whether you want to Sync the data. These are only available with a paid account.  Leave the default of **'Never'** and select **'Connect Dataset'**.
- The dataset will be displayed.  We could choose to create a map, but nothing would be displayed as there is no *geometry* data (no co-ordinates).

The following three steps may already have been completed by the instructor, as they can take a little while (maybe 10 mins).

- Return to the Data menu (the top left 'dot'), and select to **'Add a new dataset'**.
- This time use the URL: **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcodes_england.csv**
- Import the data as before.  This may take some extra time as the postcode dataset is a lot bigger: over a million rows.

We now have two datasets loaded.  One with all the libraries, including their postcodes.  Another with all the postcodes in England, including their coordinates.  We need to merge postcode co-ordinates into the libraries dataset, so we have a dataset of libraries with co-ordinates.  Before we do that we can *index* the postcodes dataset. This isn't always necessary but considering it's so large we can use indexes to make it quicker to find data.

- Go into the **postcodes_england** dataset.  Select at the bottom the option to show **SQL**.
- Remove the current text shown in the SQL editor and replace with:

```SQL
CREATE INDEX idx_postcodesengland_postcode ON postcodes_england (postcode)
```

- Click **Apply**.

This tells the underlying database to create an index (called *idx_postcodesengland_postcode*) on the *postcodes_england* table, using the column called *postcode*.

- Go into the **libraries** dataset.  Select at the bottom the option to show **SQL**.  This will display:

```SQL
SELECT * FROM libraries
```

This tells us that the current data view is showing all columns (*) from the libraries dataset.  We can change this to a view that would show a selection of columns from multiple datasets.

- Change the SQL to the following.

```SQL
SELECT library_name, library_service, postal_address,
(SELECT postcodes_england.the_geom FROM postcodes_england WHERE postcodes_england.postcode = libraries.postcode)
FROM libraries
```

This is selecting to view the *library_name*, *library_service*, *postal_address*, and *geometry* for each library.  The geometry is retrieved by using a *sub-query* to retrieve from the postcodes dataset by matching on the postcode field.

- Click **'Apply'**.  Carto will chug away for a little while fetching the data.
- Once it is done, on the dataset menu icon (three little dots after the dataset name) select to **'Create dataset from query'**.  Carto will chug away again.
- Once that's done you will have a new dataset.
- Within the dataset opt to **'Create Map'**.

The instructor will now explore some of the options within maps.

Attendee exercise
-----------------

To save some time, a CSV file has been created with libraries already linked to postcode geometry.  Spend 15 minutes running through this exercise and playing with some of the map features.

- Navigate to **Maps > Your Datasets**.
- Select **New Dataset**.
- In the URL field enter: **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/libraries_geo.csv**
- Click Submit
- Leave the default of **'Never'**, and select **'Connect Dataset'**.
- The dataset will be displayed.  You can then choose then to **'Create map'**

Spend some time exploring the map options and playing with the extended features of Carto.  When you're done, publish a map.  Think about the following questions:

- how can you ensure that the data attribution guidelines are followed when publishing a map?
- not all the libraries are shown, why not?