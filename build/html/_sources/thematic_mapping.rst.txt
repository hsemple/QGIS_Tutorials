

Thematic Mapping
==========================================
GIS is concerned with mapping the location of events and phenomena so that map readers can understand the geographic pattern of phenonomena and incorporate the implications of these patterns into decision making.   

A basic way of presenting information information about spatial pattern is to use a thematic map. A thematic map shows the spatial distribution of one or more specific data themes for selected geographic areas. The map may be qualitative in nature (e.g., predominant farm types, mineral distribution in the USA, mountain systems in the Americas) or quantitative (e.g., percentage population change, income distribution).

With a GIS software, the basic way to create a vector thematic map is to select one of the fields in the attribute table of the map layer and then display the data using the software's thematic mapping engine. The data in attribute field may be quantitative or qualitative. If the data is qualitative, we create a qualitative thematic map.  If the data is quantitative, we create a quantitative thematic map.

The data in the attribute table can be entered manually or we can join tables obtained from other sources to the attribute table of the shapefile.  With practice, the actual mapping process can be accomplished very quickly.  

The next section below shows how to perform thematic mapping in QGIS.




|

Mapping Data Stored in the Attribute Table
--------------------------------------------

1. Load the map layer into QGIS.


2. Right click on the name of the layer and select Open Attribute table. Inspect the attribute table. We will use the column that contains population data for the US. Examine the population data, then close the attribute table.


3. Now, right click on the layer name again and choose ‘Properties’.

.. image:: img/mapping_attributes1.png
   :alt: Mapping Attributes
 

4. When the layer properties dialog opens, select the  "Symbology" tab to the left of the dialog.

.. image:: img/mapping_attributes2.png
   :alt: Mapping Attributes


5. Click on the drop-down button at the top right of the Symbology dialog and you will see several options, e.g., Single Symbol, Categorized, Graduated, Rule Based, etc.



6. The graduated style is used when you want to map columns in which the data are numerical quantities.  The graduated scheme will create choropleth maps, i.e., maps in which varying colors are used to represent different sized quantities.  Categorized is used when the values in the columns refer to categories of information, e.g. Democrats = 1, Republicans = 2, Independents = 3. In this case, the numbers 1,2, and 3 are not quantities, but categories.
 

.. image:: img/mapping_attributes3.png
   :alt: Mapping Attributes


7. To map the population column, select Graduated as the Style.  Select Population as the column to map. Click on the dropdown next to Color Ramp and select also a color ramp. For numerical data that goes from lower values to higher values, one can select a single color.  Lower values will be given a lighter version of the color while higher values will be given a darker version of the color.

.. image:: img/mapping_attributes4.png
   :alt: Mapping Attributes

   


8. Select the default 5 as the number of classes. Most cartographers suggest 5-6 classes as providing the best results.  Since we selected five classes, QGIS will place the population totals of the 50 states into 5 groups.  


9. Next to "Mode", select "Natural Breaks" as the method of classification or grouping the data. Natural breaks means that the software will rank the data from highest to lowest and then create five groups such that each group contains numbers that are generally similar to each other. The goal is to create groupings of similar numbers rather than groups of equal number of cases. You can also experiment with equal interval, standard deviation, etc. to see their effect. Click Classify.  

.. image:: img/mapping_attributes4.png
   :alt: Mapping Attributes



10. Click OK and see the map in the main QGIS window. This map definitely conveys a lot more useful information that just numbers in a table.  


11. The steps outlined above show how to create a basic choropleth map in QGIS.  You should also take a look at the video below for a brief description of the process. 
 
 

|
 
Preparing maps for printing in QGIS
------------------------------------

1. Now that you are done creating the map, the final step is "compose" the map to give it a professional touch.  QGIS comes an application called "Composer" that is used to  create professional quality maps.  Key components of a professional map include:
	•	The map body
	•	The title of the map 
	•	The scale bar
	•	The north arrow  
	•	The legend 
	•	Data Source (optional)
 
 
2. With the map you are working on still opened in QGIS,  click on Project on the main menu, then ‘New Print Layout'.  


.. image:: img/composing_map1.png
   :alt: Composing Map


 
 
3. Enter a name for the new print composer object that will be created, e.g., "USA_Population Distribution Layout". A new print Composer window will open. The Print Composer tool contains four main parts(1) a menu at the top of the screen, (2) a toolbar to the left, (3) the main map area, which has blank canvas where you would be composing the map, and (4) a panel with three tabs to the right, Composition, Item Properties, and Guides.
 

.. image:: img/composing_map2.png
   :alt: Composing Map


 
 
4.  To add a map to composer, click on Add Item on the main menu, then click "Add Map".  Now draw a rectangle container on the canvas to hold the map.  When you end the rectangle, the map will appear.  Note: If you do not like the rectangle size, you can always resize it afterwards.
 


.. image:: img/composing_map3.png
   :alt: Composing Map


 
5. If you wanted to enlarge the map and show only the contiguous states, then go back to the map area, and enlarge the view there. You may have to delete the rectangle and redraw it.


6. Click inside the box and drag the map container until it is centered on the page. 


7. To add a scalebar, click on Add Item on the main menu, then select "Add Scalebar".  Draw a rectangle on the composition where you want to place the scale bar then release. The scalebar will appear. Resize the scalebar to suit your taste.
 

8. With the scalebar selected, click on "Item Properties" to the right of the composer. Here you can fiddle with the different values to adjust elements of the scalebar's appearance.
 

9. Repeat the same process as described in 8 above to add north arrow and legend to your map. Title and other text are added with the "Add Label" button on the Toolbar to the left.  Here is an illustration of my completed map.
 

.. image:: img/composing_map4.png
   :alt: Composing Map

 
10. Once you are satisfied with the map, you can export it as Image, PDF or SVG. For this tutorial, let’s export it as a PNG image. Click onLayout | Export as Image.  Select a path and a name for the exported image.  This image can be uploaded to Canvas Dropbox.
 
11. Creating attractive maps requires knowledge about map design and map communication principles.  There is a large body of literature on elements of good map design. In Module 1.6,  I present some basic maps design ideas.  Please read these design ideas and try to integrate them as much as possible into your own map design. 
 
12. As a rule, always try to create beautiful maps that effectively communicate spatial information. Conversely, always try to avoid creating ugly maps that fail to effectively communicate useful information.
 
