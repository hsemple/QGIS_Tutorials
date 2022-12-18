
Map Projections
===================


The main goals of the lab are to help you:

   * learn how to change the projections of map layers on the fly so that the map makers can quickly and accurately create maps that maintain correct distances, area, and shape of places.

   * learn how to permanently change the projections of map layers so that layers with different projections can overlay on each other. This also measurements and analysis performed on the layers can be correct  


|


Assignment
------------

In the first section of this lab, you will use QGIS to temporarily display map layers in different projections.  We will focus on projections of the world, US projections, and projections for Michigan. 


In the second section of the lab, you will use QGIS to permanently change the underlying projection and coordinate systems of the map layers, and how to convert maps with different coordinates into a common coordinate system.   

In the final section of the lab, you will use ArcGIS Online to change projections.  

|

Data
-------

Download the MapProj_QGIS.zip file from this `Github page <https://github.com/hsemple/gistutorials_datasets/blob/main/MapProj_QGIS-1.zip>`_ .  Unzip it and save the files to a working directory on your computer.


|

Displaying World Maps in Different Projections
------------------------------------------------


**Display the World in Geographic Coordinates or Plate-Carrée Projection**

1. Open QGIS from the Start menu and create a new project.

2. Click on Layer | Add Layer | Add Vector Layer and browse to the downloaded data folder. 

3. Open the world subdirectory. Select ESRI shapefiles as the file type to display, and load the .shp files into QGIS. 

.. image:: img/world_countries.png
   :alt: Landsat Imagery in QGIS

4. The layers should appear as shown below. The colors on the map will vary.

.. image:: img/world_geographic_coordinates.png
   :alt: Landsat Imagery in QGIS


5.	Study the shape and relative sizes of continents. Compare the size of Greenland with that of Africa and South America. Notice how small Greenland is on this projection. On some projections, you will notice major differences in the size of Greenland relative to Africa or South America.

6. Look at the different circles on the map (also called Tissot's indicatrix after the French mathematician who devised them in 1859). Notice that close to the equator, the circles show little distortion, but as one moves north and south of the equator, the circles show increasing distortion. The circles give an indication of how much the shape of places are being distorted on the map as one goes north and south.

7.	Examine the coordinates of the map. They are circled red on the map. (See illustration above).  As you move the cursor over the map the coordinates change. These coordinates are latitude \ longitude. They range from 0 to 90 degrees north and south of the equator and 0 to 180 degrees east and west of the Prime Meridian, which is represented by zero degrees longitude.   

8.	At the bottom-right corner of QGIS you will see EPSG:4326. This is the code for the current CRS (Coordinate Referencing System) for the project.

9.	In GIS, latitude \ longitude coordinates are also called Geographic Coordinates. This important to remember.  When they appear on a physical three-dimensional globe, we also refer to the latitudes and longitudes as unprojected coordinates because the coordinates have not been projected to a flat plane. 

10.	In the Contents browser in QGIS, uncheck the lat\long grid.

11.	To determine the projection of your entire project, we can look at the project's metadata. Click on Project and the top left of QGIS and select Properties.

12.	On the dialog that appears, click on CRS (Coordinate Referencing System). The coordinate system information shows under Geometry and Coordinate Referencing System.


.. image:: img/spatial_reference_properties.png
   :alt: Landsat Imagery in QGIS


13.	EPSG 4326 is the code for a widely used global spherical geographic coordinate system. It is based on the WGS84 datum and uses longitude and latitude in decimal degrees. For the most part, when you describe a long/lat coordinate location, those coordinates are based on the EPSG:4326 coordinate system.   

14. There is no way to visualize the EPSG: 4326 coordinate system on a two-dimensional plane (map), so most software programs project these coordinates to an equirectangular projection named Plate-Carrée.  The world map above is thus in the Plate-Carrée projection. 




|

**Display the World Using Robinson’s Projection**

The Plate Carrée is the basic projection for rendering world maps in geographic coordinates, but most of the time we want to work with other projections that better capture relative size and shape of places and distance and directions between them. 

A popular projection for rendering the entire world to create thematic maps is the Robinson's projection. If you do not know about the Robinson's projection, you should do a quick review of the lecture notes. To render our world map in Robinson's projection, do the following:

1.	Click on Project and properties and the dialog below will appear. Enter Robinson next to Filter.  Select either World Robinson or Sphere Robinson as the Coordinate System.

.. image:: img/crs_properties.png
   :alt: CRS Properties

 
2.	The map will change the arrangements of the angles of the coordinates relative to each other and consequently, the shape of the landmasses. The map will appear as shown below.

.. image:: img/robinson_projection.png
   :alt: Robinson Projection


3. What do you notice about the distortion in the circles compared to the geographic coordinates?   Are there more distortions, less distortion, or is the amount of distortion roughly similar?

4. The Robinson projection is a global map projection designed to present the whole earth with a minimum of distortion at any location, except for regions in the far north and far south.

5. The unit of measurement for projected are typically in feet or meters. That is because we are projecting the lat/long, which are in degrees, to a plane coordinate system, which are feet or meters. 

6. If you look at the coordinates at the bottom of the map, you see that the map coordinates are now in meters.  



|

**Display with Other Global Projections**

1. Using the methods described above, display the world using the following projections:

* Winkel Tripel (World-Winkel_1 EPSG: 54018)
* Mercator (WGS_1984_Web_Mercator_Auxiliary_Sphere)
* Sinudoidal (World_Sinusoidal) 


2. Arrange the projections in the layout as you did in the previous section, then submit a screenshot of your layout.

3. Write short statements on the characteristics of each projection and what mapping tasks each is best suited for.


|

**Make a Single Layout of the Different Global Projections**

1. Now, let us make a layout of the world in the different projections.  First Reset your map to the EPSG: 4326 coordinate system  then Click on Project | New Print Layout.

.. image:: img/new_layout1.png 
   :alt: New Layout
 

2. Give the new composer a name. When the canvas appears, Click on Add Items | Add Map.

3. Deliberately draw a small rectangle to hold the map so that map frames you create later will be able to fit besides it (See illustration below).  Name the map “The World in Geographic or Unprojected Coordinates” or any suitable title. 

.. image:: img/composer_layout1.png
   :alt: New Layout


4. Now, right click on the map, select copy and paste several copies on the map on the canvas, each to represent a different projection.  We will change the projections from within this area.

.. image:: img/composer_layout2.png
   :alt: New Layout


5. Click on the second map to select it, then to the right next to CRS, select Robinson as the projection for this map.


.. image:: img/composer_layout3.png
   :alt: New Layout

6. Repeat the process and set projections for the other maps. The results should appear as shown below.   Add scale bar, titles, etc, to your map. 


.. image:: img/composer_layout4.png
   :alt: New Layout

7. Export your map for submission.

 
|

**Answer the Qestions Below**

1. How well is Antarctica represented on a Mercator Projection? What do you notice about the size of places as you go farther north and south?

2. How does the size of Alaska compare with the contiguous states?

3. Is a Mercator Projection great for making world thematic maps?

4. Which of the projections used above do you think is best for making a world thematic map to show Corona Virus mortality cases by countries? Give reasons for your choice. 
 
|




Projections of the United States
----------------------------------


**Display the United States in the Geographic Coordinates**


Similar to global datasets, when working with US map layers, it is important that you set the map projection based on the purpose of the map. In this section, we will focus on how to set map projections for US data.


1.	In QGIS, click on Project | New and start a new project. Navigate to the US subdirectory in the dataset you downloaded and load the US Cities and USA layers.


.. image:: img/usa_projection1.png
   :alt: New Layout


2.	Click on the Zoom In tool and zoom into the conterminous United States. If necessary, use the Pan tool to move the map to the center of the window.

3.	Notice how wider the US map looks in geographic coordinates. Also, the 49th parallel along the US-Canada appears as a straight line. This effect occurs because, in unprojected coordinates, the meridians are drawn as parallel lines instead of converging lines. Drawing the meridians in this manner distorts the regions between them because as the poles are approached, the meridians are maintained as parallel lines, however. in reality they converge towards the poles.   

 
4.	As a general rule, you should avoid creating US maps using geographic coordinates.

.. image:: img/usa_projection2.png
   :alt: New Layout


|

**The United States in Albers Equal Area Projection**

The Albers Equal Area projection is a frequently used projection for US maps. This projection preserves the correct area of places, although it somewhat distorts the direction, distance and shape. To display a US map in geographic coordinates, do the following:

1.	Click on Project | Properties and search USA_Contiguous_Albers_Equal_Area_Conic. Clcik Apply.  The map should appear as shown below:

.. image:: img/usa_projection3.png
   :alt: New Layout


2.	Compare the shape of the United States in geographic coordinates and in Albers projection. In Albers Equal-Area Projection, the meridians converge toward one another while the successive parallels remain parallel to one another. When you reach the North Pole, the meridians converge completely.

3.	Notice also that in Albers projection, square boxes of latitude - longitude appear as elongated quadrilaterals with the bottom edges longer than their top edges. In geographic coordinates, the effect of the real convergence of the meridians is lost because the latitude and longitude grid form a set of perpendicular lines, which is what makes the United States seem wider and flatter in geographic coordinates.

4.	Another popular projection used in the US is the Lambert Equal Area. You can search for USA_Contiguous_Lambert_Conformal_Conic. Display the map in this projection. It appears as shown below.


.. image:: img/usa_projection4.png
   :alt: USA Projection


5. Now, set up layouts for the US projections.

.. image:: img/usa_projection5.png
   :alt: USA Projection


6. In the next section, we look at projections for Michigan Layers.



|


Projections of Michigan 
-------------------------

**a. View of Michigan in Geographic Coordinates**

1.	In QGIS, click on Project | New and start a new project. Navigate to the Michigan subdirectory in the dataset you downloaded and load the Michigan and lat/long dataset.

2.	Notice how unnatural, Michigan looks when displayed in geographic coordinates. 

.. image:: img/michigan_projection1.png
   :alt: Michigan Projection


|

**b. Display the Michigan Layer Using the Michigan GeoRef Coordinate Systems**

In order to present a pleasing map of Michigan, and to minimize distortion of distance in
statewide maps, we can use a state-wide coordinate system for Michigan called the Michigan GeoRef coordinate system to display Michigan layer. This coordinate system is based on a projection called the Hotine Oblique Mercator Azimuth projection.

To display a map of Michigan using the Michigan Georef Coordinate System, do the following:

1.	Click on Project |  Properties  and search for NAD_1983_Michigan_GeoRef_Meters. Select this coordinate system and click OK.

2.	In what way is this map different from Michigan in geographic coordinates? 

3.	Create single layout showing both Michigan in geographic coordinates and Michigan in the Michigan GeoRef projection. Submit the layout.

.. image:: img/michigan_projection2.png
   :alt: Michigan Projection
 

|

**Summary of Deliverables**

1. Create a Single Layout showing the world in the following coordinate systems or projections:

* Geographic Coordinates
* Robinson Projection
* Winkel Tripel (NGS - world)
* Mercator (world)
* Sinudoidal (world) 

2. Write short statements on the characteristics of each projection and what mapping tasks each is best suited for.

3. A layout showing the USA in Geographic Coordinates and Albers Equal Area Conic projection.

4. A layout showing both Michigan in geographic coordinates and Michigan in the Michigan GeoRef projection.  



|

Permanently Transforming Map Projections
------------------------------------------

When you download map layers from different websites, there is a high likelihood that the map layers you download will be in different coordinates.
 
Map layers that have different coordinates will not overlay on top of each other. In order to make the maps overlay, you have to first define their projection tool, i.e., tell the software the name of the coordinate system of each of the map layer. Secondly, you have to transform the different coordinates into a common coordinate system.  
 
In this section of the lab, we use QGIS software to practice converting map layers from one coordinate system to another.  You are given six shapefiles pertaining to Washtenaw County. Three of the files are in Geographic Coordinates or lat\long (WGS 84). They are: 

•	Streets 
•	School districts, and 
•	Census tracts 

The other three files are in Michigan GeoRef Coordinate System. The datum is NAD 83. They are:

•	Drinking water wells
•	Cities and 
•	County boundaries
 
Your task is to change the coordinate systems of the map layers Michigan State Plane, South Zone, NAD 83 Feet), so that all the map layers can correctly overlay on each other.
 
|

**Procedure**

1. Click on Project | New and start a New Project.

2. Load the following layers into QGIS: Streets, Census Tract, and School Districts.  All three of these layers have their coordinates in latitude / longitude or Geographic Coordinate System. The datum is WGS 84.
 
3. Let us check the Coordinate Reference System (CRS) of the street layer.  Right click on the name of the streets layer, then select properties. 
 
.. image:: img/street_layer_crs.png
   :alt: CRS Street Layer

 
4.  Under "Geometry and Coordinate System", notice it says Invalid Projection. This means that the projection has not been set or defined. Close the dialog.
  

.. image:: img/street_layer_crs2.png
   :alt: CRS Street Layer


5. Prior to downloading the street layer, we were told that its coordinates were Geographic Coordinates, WGS 84.  Recall that Geographic Coordinates is another name for latitude \ longitude. If you look at the bottom of the screen you can see the latitude \ longitude values.  Although QGIS recognizes those values as latitude \ longitude, it does not know which datum the latitude \longitudes are based on.   Let us provide this information to QGIS by defining the coordinate system of the map of the layer.  To do so, close the current dialog, then right click on the name of the street layer and select Set CRS | Set Layer CRS...
 
.. image:: img/street_layer_crs3.png
   :alt: CRS Street Layer


6. When the CRS Selector dialog appears, enter 'WGS 84' next to 'Filter' and search for this coordinate system.  WGS 84 is the name of the datum.  Select WGS 84 (EPSG: 4326) as the Coordinate Reference System for the new map layer.  Click Ok.

.. image:: img/street_layer_crs4.png
   :alt: CRS Street Layer
 
7.  When you click Ok, the software will update the shapefile's  .prj file by adding this projection information. For this particular projection, you won't see any changes to the shape of the map.
 
8. Now, on your own, define the coordinate system for the two layers below as WGS 84:

* School districts 
* Census tracts 

.. image:: img/define_coordinates2.png
   :alt: Define Coordinates


9. Now add the other three files below.  The coordinate system of these layers is Michigan GeoRef (NAD 83):

* Wells
* Cities 
* County boundary

10. The coordinate system of the last three files you added is Michigan Oblique Mercator.  Since this is a projected coordinate system, it is not in latitude \ longitude. Thus, when you add the layers to QGIS, they may not display because the software can only display layers in one coordinate system at a time.
  
.. image:: img/define_coordinares_georef.png
   :alt: Define Coordinates

 
11. To better work with the last set of files you loaded, I suggest that you click on Project at the top left of the screen and select "New" to start a new project.  Do not save the project. Re-add only the Wells, Cities, and Country Boundary layers.  If you look at the coordinates at the bottom of the screen, you will see coordinates values in the Michigan Oblique Mercator Coordinate System.
 
.. image:: img/layers_michigan_georef.png
   :alt: Define Coordinates

 
12. Notice the question marks next to the layer names in the Table of Content?  That means the coordinate system of the layers has not yet been defined or set as yet.  To define the coordinate system of these layers in QGIS, right click on the name of the first layer  and select Set CRS | Set Layer CRS...   When the CRS Selector dialog appears, enter Michigan GeoRef into the filter and search for this coordinate system.  Select NAD83/  Michigan Oblique Mercator as the projection for the layer.  Click Ok.
 

13. Make sure that all the layers have been defined as NAD 83/ Michigan Oblique Mercator.
 

|

**Convert All Map Layers to Michigan State Plane, NAD 83**

Now that we have defined all the map layers based on their original coordinate system, we will convert all the map layers to a common coordinate system, i.e., Michigan State Plane, NAD 83 (feet).  
 
1. Click on Project at the top left of the screen and select "New" to start a new project.  Do not save the project.  Add only the Wells, Cities, and County Boundary layers.

2.   Right click on the first layer, e.g., Wells then select Export | Save Feature as..

.. image:: img/michigan_state_plane1.png
   :alt: project Coordinates

 
3. Fill out the dialog that appears, fill it out as shown below, i.e., set a path and a name for the output file.  Don't just enter a file name, click on the triple dots icon and set the path. In the example below, I appended the word 'projected' to the original fine name. 


.. image:: img/michigan_state_plane2.png
   :alt: project Coordinates


 
4.  For CRS, click on the globe icon and enter State Plane in the filter textbox.  When the various options appear, select NAD 83, State Plane Michigan, South Zone, as shown below.   Click Ok. This will save the layer with a new name and a new coordinate system.
  
.. image:: img/michigan_state_plane3.png
   :alt: Project Coordinates

5.  Since you wish to convert all the layers to the Michigan State Plane Coordinate System, South Zone projection, repeat this process for all map layers.

6. The projected layers now appears in QGIS Table of Content. However, if you click on one of them, they may not draw. This is because the original layers in in different coordinate system compared to those that have been projected.   I suggest you save and close the current project, then open a brand new project and display only the projected layers.  If everything was done correctly, all the layers should overlay exactly on each other.  
 



|

**Convert the GCS Layers to Michigan State Plane, NAD 83**

1. Click on Project at the top left of the screen and select "NEW" to start a new project.  Do not save the project.   Add only the streets, census tracts, and school district layers.
 
2. Repeat the process described above to convert these layers to Michigan State Plane, NAD 83.
 

|

**Display all the Projected Layers**
1. Click on Project at the top left of the screen and select "NEW" to start a new project.  Do not save the project.   

2. Add all six of the projected layers.  If everything was done correctly, all the layers should overlay exactly on each other.  

3. Use map design principles and create a map that shows all six of the layers at the same time.  To accomplish this, for some of the layers, instead of using a "Fill" color which hides layers underneath, using just the outline of the features. For different layers, use different color outlines.  Here is an example map that was previously submitted by a student.
  

.. image:: img/michigan_state_plane4.png
   :alt: Final Map


|

Changing Map Projections in ArcGIS Online 
-------------------------------------------

By default, ArcGIS Online uses a projection called Web Mercator Auxiliary to display map layers. However, this projection distorts the size of places in the far north and south.  See this link  for a brief discussion.   Making non-Web-Mercator maps is possible in ArcGIS Online. First, you have to search ArcGIS Online for basemap template in the desired projection of interests, then display the basemap projection, and then upload your maps into the projection.  Here are the steps.
 
1. Download the Covid-19 Mortality by US states map we used in Lab 1. 

2. Visit arcgisonline.com and sign in.

3. Click on Add | Search for Layers

.. image:: img/arcgisonline_projections1.png
   :alt: ArcGIS Online Map Projections


4. Click on My Content | ArcGIS Online.

.. image:: img/arcgisonline_projections2.png
   :alt: ArcGIS Online Map Projections

 
5. Search for "Albers Equal Area".   Select and load one of the Albers Equal Area Basemaps.

.. image:: img/arcgisonline_projections3.png
   :alt: ArcGIS Online Map Projections

   
6. After loading the basemap, notice its shape. Observe how different it is from the Web Mercator Auxiliary projection shown above.  I strongly suggest that you use this or similar projections for plotting US wide datasets.  
  
.. image:: img/arcgisonline_projections4.png
   :alt: ArcGIS Online Map Projections


7.  If you are making global thematic maps, you can also search for something like "Equal Area Projections world basemaps" and you will be presented with different projection templates for the entire planet. Select and add them as basemaps and note the effect.   You can even make your own projection. If you are sharing datasets such as global temperatures, atmospheric pressure, income levels, Covid-19 cases, etc using ArcGIS Online, these global projections are good choices for your maps. 
 

 .. image:: img/arcgisonline_projections5.png
   :alt: ArcGIS Online Map Projections

 
8. Return to the Albers Equal Area USA projection and click on Add | Add Layers from file and load the USA Covid-19 Shapefile.  

 .. image:: img/arcgisonline_projections5.png
   :alt: ArcGIS Online Map Projections
 
9.  Using instructions from last last week's lab plus your own fiddling, plot the Covid 19 mortality cases.
 

|

**Deliverables**

1. Rerojected maps of the World, the USA, and Michigan, as described in Section 1.
2. Answers to the questions in Section 1.
3. A professional quality map showing the six layers overlaid on each other.
4.  The URL of your projected USA map in ArcGIS Online. 


|
