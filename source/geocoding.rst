
Geocoding
============


If you have a large number of street addresses and wish to turn them into points on a map, you can use QGIS to generate X,Y coordinates from the addresses. This process is called geocoding.  QGIS uses a plugin called MMQGIS for geocoding. 



|

Basic Steps for Geocoding
--------------------------


1. Obtain the List of Addresses*.  The addreses must be stored in a csv file.  The address information split into multiple columns, e.g.,  street address, state, and 5-digit ZIP code.  For latitude and longitude data, make sure there are 2 columns and any extraneous characters are deleted (i.e. commas, parenthesis).  


2. Install the MMQGIS Plugin.

3. After installation, access the plugin by clicking on MMQGIS | Geocoding from the top menu bar.

.. image:: img/geocoding_mmqgis.png
   :alt: Lidar Data

4.  When the dialog appears, enter the path to the csv file that contains the list of addresses for geocoding.

5. Select the columns in the csv file that contain the street addresses, city, and state.

6. Select OpenStreetMap as the Web Service to use for geocoding.

7. Browse to a folder where you want the resulting shapefile to be and supply a complete path inluding file name for the shapefile that will be created.

8. Supply a path and file name for a new csv file that will be created to store the addresses the software could not find. 

9. Click Apply. A new shapefile with the geocoded points will appear.




**References**

1.  https://www.gislounge.com/how-to-geocode-addresses-using-qgis/

2. https://guides.library.ucsc.edu/DS/Resources/QGIS

3.  https://www.youtube.com/watch?v=FOAM0vfsSns