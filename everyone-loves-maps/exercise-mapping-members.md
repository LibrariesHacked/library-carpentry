Exercise.  Mapping Members
==========================

Requirements
------------

- Carto Account
- Laptop or tablet
- Internet

Data files
----------

We've used these files in our previous data exercise.  In this exercise we're going to use them to view member postcode areas on a map.

- [Newcastle member data](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/newcastle_members_postcodeareas.csv).  As used in the previous data exercise, this is the Newcastle member data but with *postcode areas* as well as *postcode districts*.  All rights are waived with this data but maybe attribute Newcastle Libraries anyway.
- [Postcode areas](https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcode_areas.geojson).  These are derived from Ordnance Survey's Code Point Open product and show the geometric polygons that represent postcode areas (e.g. NE).  The polygons were created by Geolytix.  The attribution is the same as previously with OS open data but with the addition of Geolytix.

Task - Instructor led exercise
------------------------------

In this exercise we are going to analyse library member locations.

- In Carto, login and navigate to the Datasets page and select to **'Add new dataset'**.
- In the URL field use the URL for the Newcastle Member data (with postcode areas): **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/newcastle_members_postcodeareas.csv**
- We'll import the data as before.  We're also going to rename the dataset to '**members**' (to make it simpler!).
- The we'll repeat the process and add the postcode areas: **https://github.com/LibrariesHacked/library-carpentry/raw/master/data/postcode_areas.geojson**
- We'll rename this dataset to **'areas'**.

We could create a map showing the postcode areas in the UK.  However, we want some member data to make the map meaningful.

- Open the **areas** dataset and open the SQL editor. This time we'll change it to:

```SQL
SELECT *,
(SELECT COUNT(*) FROM members WHERE members.postcode_area = areas.postarea) AS members
FROM areas
```

This is adding an additional column of data to each postcode area: a count of library members who live in that area.

- On the dataset menu select to **'Create Dataset from query'**.  Rename this new dataset to **'area_members'**.
- From the new Dataset create a map.

As before we'll play with the map options, including shading postcode areas by member count.  Depending on how much time we have, spend some time tailoring your maps.
