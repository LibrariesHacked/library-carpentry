Teaching. Introduction to GIS
=============================

GIS data
--------

### Points, lines and polygons

When dealing with geo data, this will normally be in the form of Points, Lines, Polygons, and associated attributes.

| Data type | Description |
| --------- | ----------- |
| Points | Individual locations made up of a single coordinate set.  For example a library building would be a point. |
| Lines | Linear features made up of coordinates.  For example, a bus route may be expressed as a line where each point on that line is a bus stop. |
| Polygons | Bounded areas (shapes) made up of coordinates such as local authority boundaries and geofences. |
| Attributes | Associated with the above categories of data these may be names, or particular values e.g. *'Bath and North East Somerset'* is the local authority name that is an attribute of a polygon that represents a local authority boundary |

### Geographic coordinate systems

Whether it is points, lines, or polygons, GIS data is primarily made up of coordinates.

Wikipedia: [Geographic coordinate systems](https://en.wikipedia.org/wiki/Geographic_coordinate_system)

> A geographic coordinate system is a coordinate system that enables every location on the Earth to be specified by a set of numbers or letters, or symbols. The coordinates are often chosen such that one of the numbers represents vertical position, and two or three of the numbers represent horizontal position. A common choice of coordinates is latitude, longitude and elevation.

| Coordinate type | X | Y |
| --------------- | - | - |
| Longitude and Latitude | -3.106849 | 51.015344 |
| Eastings and Northings. | 322454 | 124580 |

### Spatial reference systems

Wikipedia: [Spatial Reference System](https://en.wikipedia.org/wiki/Spatial_reference_system).

> A spatial reference system (SRS) or coordinate reference system (CRS) is a coordinate-based local, regional or global system used to locate geographical entities.

| Reference System | Coordinates used | Who by |
| ---------------- | ---------------- | ------ |
| British National Grid | Eastings/Northings | Ordnance Survey |
| World Geodetic System 84 | Longitude/Latitude | GPS |

See the [Coordinate Converter - British Geological Survey](http://www.bgs.ac.uk/data/webservices/convertform.cfm)

**Why do we have different spatial reference systems?**

A spatial reference system defines how to to plot features on the curved surface of the earth to a flat paper or computer screen. As the earth is different in different parts of the world we need different spatial reference systems.

The more local the system, the greater the accuracy.

### File formats

There are many different formats for storing geo data.  These are a few of them.

| Format | Description | Example |
| ------ | ----------- | ------- |
| GeoJSON | JavaScript Object Notation (JSON) style geo data. |  |
| Shapefiles | Format developed by ESRI for storing geospatial data.  Rememeber that these are always distributed in more than one file!  |  |
| KML | XML type format for storing geospatial data. Used by Google Earth and Google fusion tables. |  |

Instructor: have a quick look at examples of these data types.

Geocoding and reverse-geocoding
-------------------------------

Geocoding and reverse geocoding are ways of matching address and location data with geo-coordinates.

- **Geocoding:** Address -> Geo-coordinates.  Usage example: Plotting a user address onto a map.
- **Reverse geocoding:** Geo-coordinates -> Address.  Usage example: taking coordinates retrieved from GPS to determine current location.
- **Geofencing:**  A feature in a software program that uses the global positioning system (GPS) or radio frequency identification (RFID) to define geographical boundaries. A geofence is a virtual barrier.

### Demo: Geocode a batch of addresses

1. Go to [Batch Geocoder](https://www.doogal.co.uk/BatchGeocoding.php)
2. Copy data from file [https://github.com/DaveBathnes/GIS-Tutorial/data/somersetlibraryaddresses.csv](SomersetLibraryAddresses.csv) into input field.
3. Press geocode.

### Demo: Reverse geocode a batch of coordinates
1. Go to [Batch reverse geocoder](https://www.doogal.co.uk/BatchReverseGeocoding.php)
2. Copy data from file [https://github.com/DaveBathnes/GIS-Tutorial/data/SomersetLibraryCoordinates.csv](SomersetLibraryCoordinates.csv)
3. Press reverse geocode.

### GIS Software

There are a number of desktop software packages dedicated to analysing GIS data.  These include QGIS (free and open source), MapInfo, and Arc Desktop.

Instructor Demo: demonstrate adding a layer and exploring it using QGIS.

### Web mapping - online tools

Our next couple of exercises will use Carto to load some GIS data and publish this on the web.

Source Materials
-----------------

At Taunton Developer Meetup, [Everyone Loves Maps presentation](https://github.com/DaveBathnes/GIS-Tutorial).