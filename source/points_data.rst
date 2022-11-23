Collecting Points Data
=========================

In thhis module, we will examine the collection of points data using the different methods, i.e., extraction from Google Maps, GPS and Geocoding.

|

Generating X,Y Coordinates from Google Maps
----------------------------------------------

1. Open Google maps with a web browser at maps.google.com

2. Use the Search field to find your selected location of interest.
     
3. Zoom in, move the map, and then click on the specific location you identify as your most accurate data point.  
     
4. Generate latitude and longitude information, using one of these methods:
    a. Click on a select location, to open a small box with location details, or
    b. Control/right-click on a spot to open a menu, select “What’s here?”, or
    c. Click on a red location marker, select “What’s here?” if needed.
     

5. Click on the latitude and longitude data that appears in decimal degrees in the location information box at the bottom. These latitude and longitude details will appear in the Google Search field.
     
6. Highlight and Copy both the latitude and longitude data together from the Search field. (Do not copy the version with the hemispheric initials, i.e.  N,W,E,S).
     
7. In Excel or Google Sheets, create a new workbook. Name the workbook and save it on your local drive. Title the first three columns, “Name,” “Latitude” and “Longitude.” 
     
8. Paste the copied latitude and longitude data into the respective columns. 

9. You are ready to import the geographic data into software, such as ArcGIS Pro, ArcGIS Online, Carto, Datawrapper, or ArcGIS, to create maps for data analysis and visualization.  


|


Generating Points Data by Geocoding
-------------------------------------
If you have a large number of street addresses and wish to turn them into points on a map, doing so using the method described above can be time consuming and tedious. ArcGIS Pro and ArcGIS Online have tools that can generate GIS coordinates from addresses. This process is called geocoding.  Free geocoding tools include GPS Visualizer, Geocodio, and Social Explorer .


|