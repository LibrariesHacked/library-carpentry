Exercise.  Mapping Members
==========================

Requirements
------------

- Carto Account
- Laptop or tablet
- On the  Internet

Data files
----------

We've used these files in 

- [Newcastle member data](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/newcastle_members_postcodeareas.csv).  As used in the previous data exercise, this is the Newcastle member data but 
- [Postcode areas](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcode_areas.geojson).  These are taken from OS Code Point Open and show the geometric polygons that represent postcode areas.  The polygons were created by Geolytix.

Task
----

In this exercise we are going to analyse library member locations.

- In Carto, login and navigate to the Datasets page and select to **'Add new dataset'**.
- Use the URL for the Newcastle Member data: https://github.com/LibrariesHacked/library-carpentry/raw/master/data/newcastle_members_postcodeareas.csv
- We'll import the data as before.  We're also going to rename the dataset to '**members**'.
- The we'll repeat the process and add the postcode areas: https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcode_areas.geojson
- We'll rename the dataset to **'areas'**.

We could immediate create a map showing the postcode areas in the UK.  However, we want some associated member data to make the map meaningful.

- Open the **areas** dataset and open the SQL editor. This time we'll change it to:

```SQL
SELECT *,
(select count(*) from members where postcode_area = postarea) as members
FROM areas
```

This is adding an additional column of data to each postcode area.  It's adding a count of members for the postcode area.

- On the dataset menu select to **'Create Dataset from query'**.  Rename this new dataset to **'areas_members'**.
- From the new Dataset create a map.

As before we'll play with the map options, including shading postcode areas by member count.
