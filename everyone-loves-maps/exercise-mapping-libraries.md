Exercise.  Mapping libraries
============================

Requirements
------------

- Laptop or tablet
- Internet

Data files
----------

For this exercise we will be using two files.

- [Libraries taskforce libraries dataset](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/taskforce.csv).  A listing of English Libraries including their address and postcode.  Released under the Open Government Licence.
- [UK postcodes](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcodes.csv]).  A full list of postcodes in England, taken from 'Code Point Open', an Ordnance Survey open data product.

There should be no need to download these files.  They're held online so we'll let Carto access them.

Task
----

In this task we are going to take a dataset published by the Libraries Taskforce on [30th March 2017](https://librariestaskforce.blog.gov.uk/2017/03/30/library-data-the-story-so-far-and-next-steps/).  This includes addresses and postcodes of all libraries in England.  We will load this into the online mapping tool, Carto.  We'll then use postcodes locations, provided by Ordnance Survey, to **'geocode'** these libraries.  Finally, we'll plot them on a web map, and you'll have a chance to play around with how they're displayed.

- In your browser navigate to [https://carto.com/](https://carto.com/).
- In the Menu navigate to **Signup** or navigate to [https://carto.com/signup/](https://carto.com/signup/).
- You'll notice you can sign up using your GitHub account.  Feel free to use the one you created earlier, or fill in the full details and create a new account.
- When prompted for additional details, fill these out if you wish to.  There's no need to provide a phone number.

Everyone should now have a Carto account, or ideally be near someone who does.  We'll run through a demo of uploading a dataset and mapping it.

Instructor Demo
---------------

- Once logged in, on the Menu navigate to **Maps > Your Datasets**.
- Select **New Dataset**.
- In the URL field enter: **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/libraries.csv**
- Click **'Submit'**
- There are a number of options as to whether you want to Sync the data. These options are only available with a paid account.  Leave the default of **'Never'** and select **'Connect Dataset'**.
- The dataset will be displayed.  You could choose then to create a map, but nothing would be displayed as there is no *geometry* data (no co-ordinates).

The following three steps will already have been completed by the instructor as they can take a little while (maybe 10 mins).

- Return to the Data menu (the top left 'dot'), and select to add a new dataset.
- This time use the URL: **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcodes.csv**
- Import the data as before.  This may take some extra time as the postcode dataset is a lot bigger, over a million rows.

We now have two datasets loaded.  One with all the libraries, including their postcodes.  Another with all the postcodes in England, including their coordinates.  We need to merge the postcode co-ordinates into the libraries dataset, so we have a dataset of libraries with co-ordinates.

- Go into the **libraries** dataset.  Select at the bottom the option to show **SQL**.  This will show:

```SQL
SELECT * FROM libraries
```

This tells us the view of data is currently showing all columns (*) from the libraries dataset.  We can change this to a view that would show a selection of columns from combined datasets.

- Change the SQL to the following.

```SQL
SELECT library_name, library_service, postal_address,
(select postcodes.the_geom from postcodes where postcodes.postcode = taskforce.postcode)
FROM libraries
```

This is selecting to view the library name, library service, address, and geometry of the postcode for each library.  The geometry of the postcodes are retrieved by matching on the postcode field from each dataset.

- Click **'Apply'**.  Carto will chug away for a little while fetching the data.
- Once it is done, on the dataset menu icon (three little dots after the dataset name) select to **'Create dataset from query'**.  Carto will chug away again.
- Once that's done you will have a new dataset.
- Within the dataset opt to **'Create Map'**.

The instructor will now explore some of the options within maps.

Attendee exercise
-----------------

To save some time, a dataset has been created with libraries already linked to postcode geometry.  Spend 15 minutes running through this exercise and playing with some of the map features.

- Navigate to **Maps > Your Datasets**.
- Select **New Dataset**.
- In the URL field enter: **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/libraries_geo.csv**
- Click Submit
- Leave the default of **'Never'**, and select **'Connect Dataset'**.
- The dataset will be displayed.  You can then choose then to **'Create map'**

Spend some time exploring the map options and playing with the extended features of Carto.  When you're done, publish a map.