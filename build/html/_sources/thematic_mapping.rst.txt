

Thematic Mapping
=======================
   
A popular way of presenting information about spatial patterns is to use a thematic map. A thematic map shows the spatial distribution of one or more specific data themes for selected geographic areas. The data may be quantitative (e.g., percentage population change, income distribution) or qualitative  (e.g., predominant farm types, mineral distribution in the USA, mountain systems in the Americas).

With a GIS software, the basic way to create a vector thematic map is to identify one of the fields in the attribute table of the map layer and then display the data using the software's thematic mapping engine.  If the data is quantitative, we create a quantitative thematic map, which may vary in appearance depending on how the map is symbolized, the number of classes utilized, classification method, and whether the data is normalized.  If the data is qualitative, we create a qqualitative thematic map, which may also vary in appearance depending on the details of the data.

The data in a GIS attribute table can be entered manually or we can join tables obtained from other sources to the attribute table of the shapefile.  With practice, the actual mapping process can be accomplished very quickly.  



|

Data
-------------------------
1. For this tutorial, please visit the Github page at this `link <https://github.com/hsemple/-Covid19/blob/master/USA-2.zip>`_, click on the *Download* button and download the USA states shapefile: 


2. After downloading the file, unzip or extract it to a location that you can remember.


|




Mapping Data Stored in the Attribute Table
--------------------------------------------

1. Load the map layer into QGIS.


2. Right click on the name of the layer and select Open Attribute table. Inspect the attribute table. We will use the column that contains population data for the US. Examine the population data, then close the attribute table.


3. Now, right click on the layer name again and choose ‘Properties’.

.. image:: img/mapping_attributes1.png
   :alt: Layer Propertie
 

4. When the layer properties dialog opens, select the "Symbology" tab to the left of the dialog.

.. image:: img/mapping_attributes2.png
   :alt: QGIS Symbology Dialog


5. Click on the drop-down button at the top right of the Symbology dialog and you will see several options, e.g., Single Symbol, Categorized, Graduated, Rule Based, etc.


.. image:: img/mapping_attributes2b.png
   :alt: QGIS Symbology Dialog




.. image:: img/mapping_attributes3.png
   :alt: Mapping Attributes



6. The graduated style is used when you want to map fields in which the data are numerical quantities.  The graduated scheme will create choropleth maps, i.e., maps in which varying colors are used to represent different sized quantities.  Categorized is used when the values in the columns refer to categories of information, e.g. Democrats = 1, Republicans = 2, Independents = 3. In this case, the numbers 1,2, and 3 are not quantities, but categories.
 



7. To map the population column, select Graduated as the Style.  Select Population as the column to map. Click on the dropdown next to Color Ramp and select also a color ramp. For numerical data that goes from lower values to higher values, one can select a single color ramp.  Lower values will be given a lighter version of the color while higher values will be given a darker version of the color.

.. image:: img/mapping_attributes4.png
   :alt: Mapping Attributes

   


8. Select the default 5 as the number of classes. Most cartographers suggest 5-6 classes as providing the best results.  Since we selected five classes, QGIS will place the population totals of the 50 states into 5 groups.  


9. Next to "Mode", select "Natural Breaks" as the method of classification or grouping the data. Natural breaks means that the software will rank the data from highest to lowest and then create five groups such that each group contains numbers that are generally similar to each other. The goal is to create groupings of similar numbers rather than groups of equal number of cases. You can also experiment with equal interval, standard deviation, etc. to see their effect. Click Classify.  

.. image:: img/mapping_attributes4.png
   :alt: Mapping Attributes



10. You can also set the boundaries of the groups manually. Click on the Histogram tab then select Load Data.  You can now edit the class boundaries by moving the vertical lines with your mouse. You can also click on an empty space to add new class boundaries. 


.. image:: img/mapping_attributes5b.png
   :alt: Histogram


11. Next to Legend Format, the %1 - %2 lets you control how you want the lower and upper numbers to appear in the legend. %1 is the lower number and %2 is the upper number.  Precision controls the number of decimal places that will appear in the legend while the Trim option removes excess trailing zeroes.


12. Click OK and see the map in the main QGIS window. This map definitely conveys a lot more useful information that just numbers in a table.  


.. image:: img/mapping_attributes5.png
   :alt: Mapping Attributes

 

|

Proportional Symbol Maps
------------------------

Creating proportional symbols maps in QGIS is relatively. The workflow entails obtaining a points layer of the dataset and then symbolizing the points layer. The points layer can be symbolized as proportional symbols or graduated proportional symbols.


1. If the data is a polygon layer, you can convert the polygon layer into a points layer by clicking on Vector in the top menu, then selecting Geometry Tools | Centroids.

.. image:: img/thematic_maps_proportional_symbolmap1.png
   :alt: Points Map 


2. When the dialog appears, ensure that the polygon layer is selected as the input file then click Run.  This will create a points layer from the polygon layer. All attribute fields will be preserved.

.. image:: img/thematic_maps_proportional_symbolmap2.png
   :alt: Mapping Attributes


3. Right click on the *Centroid* layer that was created and select *Properties*.


4.  Click on *Symbology* then fill out the dialog.  Start by selecting *Single Symbol* to create a single symbol map. 

.. image:: img/thematic_maps_proportional_symbolmap3.png
   :alt: Single Symbol Map


5. Make sure that Simple Marker is highlighted then click on the dropdown to the right of the Size textbox. This will reveal the Assistant.

.. image:: img/thematic_maps_proportional_symbolmap4.png
   :alt: Select Simple Marker


6. When the Assistant dialog appears, click on the dropdown to the right of Source and select the field that you wish to map. In this case, select the *Pop_2015* field. 

.. image:: img/thematic_maps_proportional_symbolmap5.png
   :alt: Assistant Dialog


7. To the far right of the 'Values From' text box, click on the refresh button to load the minimum and maximum values for the selected values. In this case, there are several zeroes, so these are ignored and the next lowest value, 580000 was entered manually. I also adjusted the maximum symbol size to 20 to enhancee the appearance of fhe map. 


8. The resultant map should appear as shown below.

.. image:: img/thematic_maps_proportional_symbolmap6.png
   :alt: Default Proportional Symbol Map


9. By default, QGIS does not create a legend. To manually create a legend, double click on the name of the proportional symbol layer to bring up the properties dialog. 


10. Click on Marker, then click on Advanced | Data-Defined Size Legend.

.. image:: img/thematic_maps_proportional_symbolmap7.png
   :alt: Data-Defined Size Legend


11. In the dialog that appears, select Collapsed legend then click Ok.

.. image:: img/thematic_maps_proportional_symbolmap8.png
   :alt: Collapsed legend


12. In the Table of Content, expand the legend of the Centroid layer.  It should appear as shown below.

.. image:: img/thematic_maps_proportional_symbolmap9.png
   :alt: New Legend





|
 
Preparing Maps for Printing in QGIS
------------------------------------

1. Now that you are familiar with the process of creating a thematic map, the final step is "compose" the thematic map to give it a professional touch.   QGIS comes with an application called "Composer" that is used to create professional quality layouts.  Key components of a professional map include:
	•	The map body
	•	The title of the map 
	•	The scale bar
	•	The north arrow  
	•	The legend 
	•	Data Source (optional)
 
 
2. With the map you are working on still opened in QGIS,  click on Project on the main menu, then ‘New Print Layout'.  


.. image:: img/composing_map1.png
   :alt: Composing Map



3. Enter a name for the new print composer object that will be created, e.g., "Population Distribution USA". A new print Composer window will open.  You may have to use the Zoom button to adjust the size of the main map area of composer.

.. image:: img/composing_map2.png
   :alt: Composing Map


4. The Print Composer tool contains four main parts: (1) a menu at the top of the screen, (2) a toolbar to the left, (3) the main map area, which has blank canvas where you would be composing the map, and (4) a panel with three tabs to the right, Composition, Item Properties, and Guides.
 

5. To add a map to composer, click on Add Item on the main menu, then click "Add Map".  Now draw a rectangle container on the canvas to hold the map.  When you end the rectangle, the map will appear.  Note: If you do not like the rectangle size, you can always resize it afterwards.
 

.. image:: img/composing_map3.png
   :alt: Composing Map


 
6. If you wanted to enlarge the map and show only the contiguous states, then go back to the map area, and enlarge the view there. You may have to delete the rectangle and redraw it.


7. Click inside the box and drag the map container until it is centered on the page. 


8. To add a scalebar, click on Add Item on the main menu, then select "Add Scalebar".  Draw a rectangle on the composition where you want to place the scale bar then release. The scalebar will appear. Resize the scalebar to suit your taste.
 

9. With the scalebar selected, click on "Item Properties" to the right of the composer. Here you can fiddle with the different values to adjust elements of the scalebar's appearance.
 

10. Repeat the same process as described in 8 above to add north arrow and legend to your map. Title and other text are added with the "Add Label" button on the Toolbar to the left.  Here is an illustration of my completed map.
 

.. image:: img/composing_map4.png
   :alt: Composing Map

 
11. Once you are satisfied with the map, you can export it as Image, PDF or SVG. For this tutorial, let’s export it as a PNG image. Click onLayout | Export as Image.  Select a path and a name for the exported image.  This image can be uploaded to Canvas Dropbox.
 

12. Creating attractive maps requires knowledge about map design and map communication principles.  There is a large body of literature on elements of good map design. In Module 1.6,  I present some basic maps design ideas.  Please read these design ideas and try to integrate them as much as possible into your own map design. 
 

13. As a rule, always try to create beautiful maps that effectively communicate spatial information. Conversely, always try to avoid creating ugly maps that fail to effectively communicate useful information.


14. Submit this map as proof that you completed the tutorial.
 


|


On your Own
------------

1. Create a thematic choropleth map showing Covid19 cases for Counties in the USA for February 2022.  Download a USA County Shapefile with Covid19 data February 2022 `here <https://github.com/hsemple/-Covid19/blob/master/usa_counties_covid_Feb25_2021.zip>`_.


2. If you wish to join Covid19 data to the county shapefile's attribute table, then download Covid19 attibute data here -



|


Resources
----------

Covid19 datasets (csv files). These files must be joined to the shapefile's attribute table before creating the thematic map.
https://github.com/nytimes/covid-19-data

Create a Proportional Symbol Map and Legend Using QGIS 3.x (Youtube)
https://www.youtube.com/watch?v=lmw1AZPyXiY&t=320s

|

Deliverables
------------

1. Map showing distribution of population by states in the USA.

2.  Map showing distribution of Covid19 cases by counties in the USA for January, 2022.

