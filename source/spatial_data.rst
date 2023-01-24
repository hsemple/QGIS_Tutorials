
Downloading Different Types of Spatial Data and Making Maps
==============================================================================

A typical GIS project involves working with multiple types of spatial layers overlaid on each other using a common coordinate system.  Some of the layers may be vectors while others may be rasters. 

An important objective of this lab is to help you develop the ability to visually recognize and distinguish between popular GIS raster and vector data products such as shapefiles, orthophotos, DEMs, satellite imagery, and WMS and WFC layers.  Additionally, the lab seeks to help you do the following:

   * develop basic file management skills necessary to deal with the large number of files that are typically needed for a GIS project. 

   * become comfortable with loading multiple map layers into QGIS and rearranging the layers to suit your information needs. 

   * become comfortable interpreting details on various types of spatial data.

   * develop cartographic skills needed for effective presentation of multiple map layers.


The lab is divided into six sections. In Section 1 of the lab, you will download map layers then upload them to ArcGIS Online or QGIS Cloud for sharing with your colleagues.

In Section 2 of the lab, you will download, unzip, and display shapefiles in QGIS and create a professional quality involving multiple layers.

In Section 3, you will download and display a digital elevation model in QGIS and create a professional quality map.

In Section 4, you will download and display an orthophoto and create a professional quality map using QGIS.

In Section 5, you will load multiple bands of satellite imagery into QGIS and then create maps using different band combinations.

In Section 6, you will load multiple web map layers into QGIS.

In Section 7, you will display different band combinations of Landsat 8 satellite imagery using a free online platform called Landsat Explorer. Landsat Explorer manages the satellite imagery, so users only have to concentrate on manipulating the data.


|

Assembling Shapefile & Uploading to ArcGIS Online
---------------------------------------------------------

You work for an environmental monitoring company conducting a project in Michigan. As the GIS expert on the project, you are asked to assemble several shapefiles pertaining to the geographic extent of the study area. Download the map layers from the Michigan CGI archived GIS and then upload them to ArcGIS Online so they can be viewed by all members of the project. Follow the steps below to complete this section of the lab.



**Download Data**

1. Create a folder on your computer to store all the files that you plan to download.

2. Visit the `Michigan CGI archived GIS website <https://web.archive.org/web/20160201222536/http://www.mcgi.state.mi.us/mgdl/?action=thm>`_ and download the following datasets for a county of your choice.:

    * Census Tracts
    * Drinking Wells
    * Wetlands
    * SSURGO Soils
    * Town/Range
    * Political Framework


3. If you encounter problems downloading from the Michigan CGI site, you can download layers for Wayne County, Michigan that I pre-assembled for this tutorial. The layers can be downloaded from my Github site or from Canvas.  

4. After downloading the zipped files to your local computer, follow these `instructions <https://docs.google.com/document/d/147gzsdNa_ftIsVoWLqeOlOy73D80mPx4/edit>`_ to upload the layers to ArcGIS Online. (Note: You can also upload to QGIS Cloud). This is an important skill to master as often we wish to share out datasets with colleagues or others who may not have access to GIS software.  ArcGIS Online or QGIS Cloud allow users to view the map layers using their browsers.

5. After uploading the shapefiles, save your web map in ArcGIS Online. Also, click on the Share button and share the web map with the public.  Copy the URL of the web map and submit it as proof that you completed this section of the assignment.



|


Displaying Multiple Shapefiles in QGIS & Making a Map  
--------------------------------------------------------

1. Return to the folder where you download the original files.


2. Unzip the layers to that folder, as shown below.  

.. image:: img/unzipping_data.png
   :alt: Unzipping Data

 

3. Load the shapefiles into QGIS by clicking on Layer | Add Layer | Add Vector Layer, as shown below.

.. image:: img/load_vectorlayer.png
   :alt: Loading Vector Layer into QGIS


4.  After the layers are loaded, right click on the name of each shapefiles and open the attribute tables of the map layers. Try to understand the data they contain.




|


**Make a Professional Quality Layout**

1. The deliverables for this section of the lab is a professional quality layout using only shapefiles. It is easier if you decide on a theme when creating the layout.  For example, I will use my layers try to show water wells in relation to urban areas in Wayne County.

2.  Uncheck all the layers except the shapefile.

3. Rearrange the order of the shapefiles to suit your preference by dragging them up and down in the Table of Contents. Check to see if some of the layers at the top of the list are hiding others below. If so, further re-arrange the layers. One rule we use is that point features should be at the top of the set, followed by layers that contain line features, then those that contain area features. 

4. Change the color of the layers. To do so, double click on the map icons of each layer, then go to Symbology and change the color to a color that you like. 
 

5. Experiment with happens when you click on “Fill” versus when you click on “Simple Fill”.  You will may find yourself using Simple Fill more often.  

.. image:: img/simple_fill.png
   :alt: GPS Data  


6. You may want to use no fill color for some of the layers, relying on the outline to provide the color. This will allow you to see right through the layer to other layers below. 


7.  Change Stroke or line widths to show emphasis.


8.  Double click on the name of the layer, then go to Source and from there you can change the layer name.

.. image:: img/cities_lab2.png
   :alt: GPS Data  



9. My final map appears as shown below.
 
.. image:: img/final_shapefile_map.png
   :alt: GPS Data  


10. Go to the Composer and compose the final map.
 
.. image:: img/final_shapefile_map2.png
   :alt: GPS Data  


11. Click on Layout | Export as Image.  Select a path and a name for the exported image.   Once you are satisfied with the map, you can export it PNG format. The image can be uploaded to Canvas Dropbox. 


|




Loading and Displaying a DEM 
--------------------------------

1. Visit the `Michigan CGI archived GIS website <https://web.archive.org/web/20160201222536/http://www.mcgi.state.mi.us/mgdl/?action=thm>`_ and download a Digital Elevation Model for the county of your choice. 

2. Unzip the file you downloaded.

3. Start a new instance of QGIS then click on Layers | Add Raster Layer.  Navigate to the folder where the DEM is stored, e.g, C:/Wayne_dem24_30m/Wayne/Topography/dem/. 

4. Select the file named w001001.adf. Make sure it is the adf file with the larger file size.

5. If the DEM is loaded and doesn’t show up, simply right click on it and select Zoom to Layer.

.. image:: img/wayne_dem.png
   :alt: Digital Elevation Model

6. The numbers below the name of the DEM in the Table of Content refer to elevation in ft.  If you click on the Identify button then click anywhere on the map, it will return the elevation at that location.


7. To change the color of the DEM, double click on its name in the Table of Content and select Symbology. Change the Render Type from SingleBand Gray to SingleBand Psuedocolor.  

8. Select a color ramp that suits your taste. Make sure the color ramp does justice in showing the subtle variations in elevation. 

9. You can also click on the Classify button and experiment with the impact that different classifications methods have on the visual appearance of the DEM.


.. image:: img/dem_symbology.png
   :alt: Digital Elevation Model




|

Loading and Displaying Orthophoto Tiles
-----------------------------------------------

1. Click on Layers | Add Raster Layer and navigate to the folder where the file is stored.  


.. image:: img/ann_arbor_east.png
   :alt: Loading Orthophoto

2. There may be more than one files associated with the orthophoto. Select the file that has a raster format ending, e.g., .tif, .ing, .sid, .png, etc., and add it to the display.

3. Create a layout of the orthophoto.




|



Loading and Displaying Landsat Imagery
----------------------------------------

1. Visit the Earth Explorer website (https://earthexplorer.usgs.gov/) and download Landsat 8 imagery for an area of interest.  If you are not familiar with the downloading process, click on this `link <https://guides.library.uwm.edu/c.php?g=567847&p=5338445>`_ for instructions on this process.  You can also download a Landsat imagery datset from Canvas.


2. The Landsat imagery that you download will contains several layers or bands all of which pertain to the same area.  After unzipping the data, load the files into QGIS by selecting the desired layers, as shown below.

.. image:: img/landsat_imagery1.png
   :alt: Landsat Imagery 

3. After the files are loaded, they should appear as shown below. You can uncheck and then recheck each layer to observe it in detail. You can also zoom in and inspect different parts of the imagery. 

.. image:: img/imagery_in_qgis.png
   :alt: Landsat Imagery in QGIS

4. Click on Raster in the main menu, then select Miscellaneous | Build Virtual Raster.  This step will combine the rasters into a single layer.  Fill out the dialog that appears.

.. image:: img/virtual_raster.png
   :alt: Landsat Imagery in QGIS

5. Select the layers you want to use. I selected bands 1 through 8.  Click OK when you are done.

.. image:: img/multiple_selected_rasters.png
   :alt: Selecting Landsat Bands for Display in QGIS

 
6. In the main menu, click Run in Background. A new layer called "Virtual" will be created.

.. image:: img/build_virtual_raster1.png
   :alt: Building a Virtual Raster in QGIS

 
7. Right click on the layer named "Virtual" and select Properties.
 

.. image:: img/virtual_raster2.png
   :alt: Landsat Imagery in QGIS


8.  To generate an image that represents a 5-4-3 band combination, fill out the dialog similar to the illustration below. The key selections are as follows: 
* Render Type: Multiband Color
* Red Band – 5
* Green Band – 4
* Blue Band - 3.

.. image:: img/symbolizing_virtual_raster.png
   :alt: Symbolizing Virtual Rasters



9. When you are done, click Apply to view the image. Afterwards, click Ok.

10. As you may be aware, the Landsat 8 5-4-3 band combination is the traditional False Color Infrared image. It is good for identifying different types of vegetation as well as their health. Healthy vegetation appears bright red. Each shade of red represents a different type of vegetation. From visual inspection, we can detect many shades of red, however, the computer can detect lots more shade.
    
11. Now, display an image using a 5-6-4 band combination. This is also a popular band combination for looking at vegetation cover. It contains two infrared bands (bands 5 and 6). Different vegetation types can be clearly defined, appearing as shades of orange and green. 

12. In the 5-6-4 band combination, land/water interface is very clear and for this reason, this is probably the most common band combination in Landsat 8 for differentiating between land and water.  Lakes and ponds of varying sizes can be easily identified. Water appears in shades of dark blue to black.  Ice, if present, stands out as a vibrant magenta color.

13. Display an image using a 7-6-4 band combination. This combination is useful for visualizing urban environments, particularly in situations where haze is an issue. 



|

Loading and Displaying a WMS Layer
-----------------------------------

To Add a WMS Layer, do the following:

1. In QGIS, click on Layer | Add WMS/WMTS Layer.

2. Select "New" in the Data Source Manager dialog box.

.. image:: img/wms_new_connection.png
   :alt: GPS Data Source Connection 


3. In the 'Create a new WMS connection' dialog, enter a name for the conection and the appropriate URL (e.g. https://mrdata.usgs.gov/services/active-mines?version=1.3.0)

.. image:: img/new_wms_connection.png
   :alt: GPS Data  


4. Select OK.

5. In the Sever Connection dialog, select "Connect" and then "Add". THe WMS layer should now be added.

.. image:: img/wms_connection_dialog.png
   :alt: GPS Data  

6. Select Close.

|




Loading and Displaying an ArcGIS REST Service Layer 
-----------------------------------------------------


To Add an ArcGIS Server Layer to QGIS, do the following:

1. In QGIS, click on Layer | Add ArcGIS Rest Server Layer.

2. Select "New" in the Data Source Manager dialog box.

.. image:: img/arcgis_server_connection.png
   :alt: GPS Data Source Connection 


3. In the 'Create a new ArcGIS Rest Server connection' dialog, enter a name for the conection (e.g., NAIP Imagery), and the appropriate URL (e.g. https://gis.apfo.usda.gov/arcgis/rest/services/NAIP/USDA_CONUS_PRIME/ImageServer?)


4. Select OK.


5. In the Sever Connection dialog, select "Connect". 


6. When the NAIP Imagery connection appears, expand it then select the web map layer. Click "Add". The NAIP imagery layer should now be added.  Select Close.

.. image:: img/arcgis_server_imagery_connection.png
   :alt: GPS Data  


7. The NAIP imagery should now appear in the map area of QGIS.

.. image:: img/arcgis_server_imagery.png
   :alt: GPS Data  



For more information, please view this `YouTube Video <https://www.youtube.com/watch?v=eW41DrPFquQ>`_.



|



Landsat Explorer
---------------------------

ESRI has a web mapping application called `Landsat Explorer <https://livingatlas2.arcgis.com/landsatexplorer/>`_ that can be used to quickly create Color Composites. With this application all the bands are preloaded, so there is no need to download data.

1. Open Landsat Explorer and locate San Francisco.

2. Display Landsat imagery using a 5-4-3 combination.  Comment on vegetation patterns you notice in the imagery. Zoom in to see patterns clearer.

3. Display Landsat imagery using a 7-6-4 combination.  Comment on how well you can detect urbanized areas in this imagery, particularly when you zoom in.

4. What is NDVI? (See Module 2.7).  Display San Francisco using the NDVI index (Tip: use "Vegetation Index". Also, make sure you click on the question mark next to this renderer to learn more about it). 

5. Where in the San Francisco region would you find areas that have moderate NDVIs (between 0.2 to 0.3) and high NDVIs (0.6 to 0.9).


.. image:: img/ndvi-1.png
   :alt: GPS Data 

|



**Example Map**


.. image:: img/oakland_dem.png
   :alt: DEM map 


|


Summary of Deliverables
-------------------------

1. A professional quality map consisting of three or four vector layers showing the relationship between bedrock geology, water wells, and urban areas.
2. A professional quality map showing the Digital Elevation Model you downloaded.
3. Screenshots showing the satellite imagery you downloaded displayed in the following band combinations: 5-4-3; 5-6-4 and 7-6-4.
4. A short write up-of the usefulness of the different band combinations that you displayed.
5. A professional quality map showing either the orthophoto tile or tiles you downloaded. 
6. A professional quality map showing mines in the USA based on web services data that you accessed.
7. Screenshots of satellite imagery band combinations that you generated using Landsat Pro and associated comments. 


 
