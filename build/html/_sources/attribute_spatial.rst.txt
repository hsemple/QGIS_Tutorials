Attribute and Spatial Queries
============================== 

Within a GIS, data can be queried in two ways; attribute queries and spatial queries. For attribute queries, features are selected using attribute data. Results can be mapped or presented in conventional database form. 

Spatial query is used extract features based solely on their topological relationship to other features. Combined, attribute and spatial queries are a powerful way of exploring spatial patterns in the data.  


|


Assignment
-----------


In the first part of this lab, we explore how to join an Excel file containing attribute data to a shapefile's attribute table.  After joining the tables, we will run some attribute queries to explore the data.   You will also experiment with summarizing the attribute data to see numeric and geographic patterns associated with the data.

In the second part of the lab, we will explore how to perform spatial queries in QGIS using tornada and parcel data.  



|


Working with Attribute Data
-----------------------------
Recall that in Lab 2, we made a map of Covid-19 cases by counties in the USA using data that were already available in the attribute table of the shapefile.  How did so much data get into the shapefile's attribute table?   The answer is through table joins.  

To illustrate the process, we will make of Michigan showing current Covid-19 cases by counties. The Covid-19 data are available as Microsoft Excel files on the Michigan.gov website, so we will download the data, process it a bit, and then join it to the shapefile's attribute data. Table joins are important in GIS as it saves us the need to manually enter data into the attribute table.
 
Once we are done joining the tables, we will perform attribute queries to understand the spatial pattern of the disease in Michigan.  The output for submission for this section is a set of questions that appears in "m' below.

|

**Downloading Data**

1.  Download and unzip the  Michigan Counties shapefile in Canvas to a folder on your computer.
 
2. Click on this `link <https://www.michigan.gov/coronavirus/stats>`_ to visit the Michigan State Govt website that carries data on Covid-19.
 
3. Copy the data in the table named "Confirmed COVID-19 Cases by Jurisdiction (Counties)" and paste the values into Excel.  
 
4. Edit the Excel file in the following ways:

 *	Enter zero as the value for those counties that didn't report any deaths.  
 *	Reduce the length of the field names. For example, instead of "Confirmed Cases", simply reduce it to "Cases".  
 * For "Reported Deaths", change it to "Deaths". In QGIS, field names can't have more than 11 characters. 
 *	In the shapefile's attribute table, St. Clair and St. Joseph have periods in their names following "St". However, there are no periods in these names in the data you downloaded. Include the periods in St. Clair and St. Joseph in the Excel table so that they match the shapefile's county names exactly. Otherwise, these two records will not be joined. 
 * Include an entry in the Excel table for Alger County. This county's name is present in the shapefile's attribute table, but not in the Excel file.
 *	The edited table should appear similar to the example below.


.. image:: img/covid19_attribute_data.png
   :alt: Covid19 Attribute Data
   

5. Save the file to the same folder as the shapefiles.  Save as a CSV file.

.. image:: img/save_as_csv.png
   :alt: Covid19 Attribute Data
   
 

|

**Joining the Excel File to the Shapefile's Attribute Table**


1. Open QGIS, start a new project, and load the shapefile and CSV file into QGIS.
 
2. Since we studied map coordinates in the last module, let's determine the map coordinates of our project. Whichever map layer goes into the map area first, that layer sets up the coordinates of the Project. Since the Michigan layer was the first map layer opened in the map, then the project took on the coordinates of the Michigan layer.  So, click on Project on the main menu then select Properties. In the dialog, the selected coordinate system is the project's coordinate system. It is called "NAD 83/ Michigan Oblique Mercator".   When you are done inspecting the values, click OK and close the dialog.

.. image:: img/attribute-query3.png
   :alt: Covid19 Attribute Data

 
3. Now, right click on the name of the shapefile, select Attribute Table, and examine the contents of the attribute table.  There are a lot of demographic data in the table. Inspect the various categories of data. 

9. Now, let us join the Covid-19 table to the shapefile's attribute table.  To do so, right click on the name of the shapefile and select "Properties.  To the left of the dialog that appears, select Joins.  
 


.. image:: img/attribute-query4.png
   :alt: Covid19 Attribute Data


4. Fill out the dialog with the appropriate information.  We will be doing a one-to one join.  The table join requires both tables to have a field that contains the same data to base the join. Since both tables have a field that contains the county names, we will use those two fields to join the table. The name of the fields does not matter, just the fact that they contain the same data.   In the illustration above, select the Covid19 standalone table as the join layer.  Select County as the field to base the join.  Select NAME_1 as the target field.  I selected NAME-1 as the field in the County layer because the county names in this field are lower case similar to the names in the County field in the CSV file. Click Ok. 

5. When the table join is completed, open the attribute table of the shapefile to make sure that the data from the CSV file is now present in the shapefile's attribute table. If the process failed, repeat the steps paying close attention to any error message.
 
6. Table joins are temporary procedures. This means that you can easily remove the joins between the two table. To make the join permanent, right click on the joined shapefile and select Export | Save Features as .. and export the shapefile to your data folder with a new name.
 

|

**Performing Attribute Queries to Answer the Questions Below:**
 
1. Which county has the fifth highest number of confirmed cases? (1 pt). (Tip: This question requires that you sort the table field. To do this, right click on the field that contains the confirmed cases and select "Sort Descending").
 
2. How many counties have more than 3,000 confirmed cases. Which counties are they?  (2 pts). Although you can look at the table to get this information, let's write an attribute query to get the answer. On the main menu, click on the Select Features dropdown and choose "Select Features by Expression". A dialog will appear similar to the one in the illustration below. Click on "Fields and Values". This will show the list of field names in the attribute table. Scroll down and double click on the confirmed cases field. The field will appear to the right in the editor. Complete the expression by so that it reads "Cases > 30000" where Cases is the field name. Note, your field name will be different.


3. Now click on "Select Features at the bottom right of the screen. This will select the counties on the map that meet the query criteria.  Open the attribute table. The results are shown on both the table and the map.


.. image:: img/attribute-query5.png
   :alt: Covid19 Attribute Data

 
4. Write a query to find counties with more than 8,000 cases?  Where in geographic terms are these counties located? (1 pts)
 
5. How many counties have between 3,000 - 10,000 confined cases?  (2 pts)
 
6. Where in geographic terms are the counties located with less than 200 cases located?  Make a screenshot and show the counties on your map. (2pt).  
 
7. How many counties have more than 3,000 confirmed cases and also more than 500 deaths? Which counties are they?  Show on a screenshot (2 pts)
 
8. What is the average number of confirmed cases per counties? What is the standard deviation? What does the standard deviation tell you? To get this information, right click on the "Cases" field and select Statistics.  (3pts)
 

|

**Rates Calculation**

We will now calculate rates of confirmed cases by county. Rates are usually a better way of comparing disease events than counts because it allows us to take population size into account.
 
1. First, we need to create a new field in the attribute table to hold the rates.  To create the new field, open the attribute table, then click on the Toggle button to the far left. Next, click on the New Field button, then fill out the dialog as shown below. I entered Rates as the field name and decimals for the data type.

.. image:: img/attribute-query6.png
   :alt: Covid19 Attribute Data


2. To calculate rates, first click on the Field Calculator button in. This will bring up the Field Calculator. 

.. image:: img/attribute-query7.png
   :alt: Covid19 Attribute Data

  
3. In the Field Calculator dialog, first click on update an existing field, then select Rates as the field to update. Now create an expression as shown below, i.e., (Confirmed Cases / Population) * 10000.  Your field names will differ. Substitute the correct field names.   

4. Once the rates are calculated, create a thematic map of the values. Create a screenshot to show your rates map. (Note: To make the thematic map, click on Appearance on the main menu, then select Symbology | Graduated Color.

.. image:: img/attribute-query8.png
   :alt: Covid19 Attribute Data


|


Spatial Queries
------------------
In this section, we will practice spatial queries, which is querying map features by location and spatial relationship to other map features.  The map features need not be in the same layer. 
 
The dataset for this exercise can be downloaded from Canvas.

|


**A. Selecting Cities within a Given State**
 
1. Select a state (except Michigan) from the states layer, as shown below.  Right click on the layer name, select Export | Save Features as ..  and export the layer to create a separate map layer of only the selected layer.  Note, I clicked on Project | Properties and changed the projection to Albers Equal Area Contiguous.  Also, when you are exporting make sure you select, "Save Only Selected Features", See illustrations below:


.. image:: img/spatial_queries1.png
   :alt: Spatial Queries




.. image:: img/spatial_queries2.png
   :alt: Spatial Queries



2. Write a query to select all cities that are "completely within" the state you selected.  

.. image:: img/spatial_queries3.png
   :alt: Spatial Queries



3. To select the cities that fall only within Michigan, we will use a Select by Location tool. Click on Vector in the main menu, then select Research Tools | Select by Location.    In the dialog that opens, set the city layer as  the layer to select features from. The spatial operation is "are within". Select Michigan as the layer that will be compared with. Click Run.  The selected cities should be highlighted.


.. image:: img/spatial_queries4.png
   :alt: Spatial Queries


.. image:: img/spatial_queries5.png
   :alt: Spatial Queries


  
4. Right click on the name of the cities.  Select Export | Save Features as and create a layer only of cities that fall within your state. You will need the exported layer for the next query.  (2 pt).
 
5. Run an attribute query on the cities within the state you selected to find cities that have population greater than 25,000.  (Note: This is a Select by Attributes Query). To create a map of the selected cities, right click on the layer, then select Data | Export data).  (2 pt)


|

**B. Selecting Cities that are within 50 miles of a Great Lake**

 
In this section of the lab, you will select one of the Great Lakes and create a separate layer of the lake.  For the lake you selected, create a buffer of 50 miles around the lake and identify all the cities within the buffered areas (Geoprocessing | Buffer). 



1. To select a Great Lake of interest, first click on the Select Features tool, then click on a lake to select it. 

2. To make a layer only of the lake you selected, right click on the name of the lakes layer in the Table of Content, then select Export | Save Features as and fill out the dialog that appears. Click Run.   


.. image:: img/spatial_queries6.png
   :alt: Spatial Queries


3.  Next, buffer the lake. To do so, select Analysis in the main menu, Tools | Buffer.   Fill out the dialog. Make sure the buffer distance is set to 50 miles. (Note: the map units are in degrees so the buffer distance will be computed in degrees. To avoid this issue, we should permanently convert the map to a projected coordinate. However, to avoid this, we will use a rough estimate of 0.72 of a degree as the buffer distance).


4. Select all cities that fall with the buffer zone. To do this, click on the Select By Location dialog and fill out the dialog. Since you want to select cities, then the cities layers should be in the input features box. The spatial relationship is ' within'  the Buffer.  Click Run. 


5. Right click on the cities layer, go to Export and save the selected cities to make a map only of the selected cities.
 

|


**C. Selecting Properties within a Given Proximity of a Tornado Path**

Download this dataset that shows a tornado track across a residential area.  The tornado destroyed property within a 550 m swath, so the authorities need to assess the damage done.  Specifically, they would like to assess damages for: 
 
 * properties for which any part was in the storm's path and 
 * properties that were completely within the storm's path.

As the GIS analyst, you are required to use ArcGIS Pro Spatial Queries functions to identify the two types of properties and calculate their total assessed values. 

1. Let's identify properties that were partially in the storm's path. First, load the tornado dataset into QGIS. Afterwards, use the Select by Location tool to select parcels that intersect the tornado path.  


.. image:: img/spatial_queries7.png
   :alt: Spatial Queries



2. Export the selected parcels to make a separate map.


3. To get the assessed value of the damaged properties, simply click View in the main menu, then select Panels | Statistics Panel. This will bring up a panel from which you can choose the field of interest. It will then show summary statistics for the field. 
  
4. Identity the worst affected properties, i.e., those where the entire property was contained in the path of the storm.  Note. For this problem, you have to first make buffer of 550 m around the tornado path, then find all parcels within the buffer region.


.. image:: img/spatial_queries8.png
   :alt: Spatial Queries




|

Joining Tables - ArcGIS Online
--------------------------------

ArcGIS Online has simplified the process of table joining for people using this platform for GIS. To join a table using ArcGIS Online, follow the steps below:
 
1. Upload both the shapefile and CSV to ArcGIS Online. When uploading the CSV file, upload as Table.


.. image:: img/table_join1_arcgisonline.png
   :alt: Table Join ArcGIS Online

 
2. Click on Analysis | Summarize | Join Features.

.. image:: img/table_join2_arcgisonline.png
   :alt: Table Join ArcGIS Online

 
3. In the dialog that appears, select the Michigan County shapefile as your target. This means that the table associated with this shapefile will receive data from the CSV table. The CSV table is the table that will be be joined to the target layer.
 

.. image:: img/table_join3_arcgisonline.png
   :alt: Table Join ArcGIS Online


4. The type of joins will be fields to match.  Note that you can also do spatial queries in ArcGIS Online. In that case, you would click on "Choose a spatial relationship".  Select the fields to use to base the join. Select also the type of join. As before, the join is a one to one join, i.e., one record in one table will be joined to one and only one record in the other table.
  
5. Click OK.

6. Create a thematic map using either the Confirmed Cases field or the Rates field.
 
 
|

Summary of Deliverables
------------------------

**Section 1 (10 pts)**

* Answers to the questions in Section 1 under "Performing Attribute Queries to Answer the Questions ..." and under "Rates Calculation".

 
**Section 2 (10 pts)**

* A screenshot of the map of the state you selected showing all cities with the state.
* A screenshot of the map of the state you selected showing cities that have population greater than 25,000. 
* A map showing a 50-mile buffer drawn around one of the Great Lakes and cities with the buffered zone.
* Screenshot of a map showing properties for which any part was in the storm's path. Submit also a statement of the total and average assessed properties damages. 
* Screenshot of a map showing properties that were entirely in the storm's path.  A statement of the total and average assessed properties damages.  
* Submit also a statement of the total and average assessed properties damages. 
 

**Section C (5 pts)**

* The URL of an ArcGIS Online map showing the Covid 19 rates or confirmed cases by counties for Michigan
 


