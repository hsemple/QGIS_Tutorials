
Collecting Points Data 
=======================

In this lab, you will collect coordinates for at least twenty similar features in your neighborhood.  I suggest fire hydrants, but you can record the location of anything that is of interest to you including trees, churches, restaurants, bus stops, etc.

For each feature of interest, you will record its coordinates and its physical condition. You can also consider taking photographs of the features.  Afterwards, we will display and analyze the data using geospatial software. 

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

Selecting a Smart Phone GPS App
---------------------------------

There are many smart phone GPS mapping applications available. Some require purchases while others are free. Each app has its own advantages and disadvantages, but in choosing a mapping application, there are certain things that need to considered. These include:  

*  Ease of learning how to use the app   
*  Whether the app allows you to add and edit notes associated with the features. Notes should be in the form of text and 
   images. Videos are a plus.
*  Whether the app is in active development 
*  Whether the app has GPX support (i.e., able to create waypoints, customizable log intervals)
*  Whether one can load data offline into the app.  
*  The stated accuracy level of the app.

For this lab, there is no restriction on which app you can use, however, ArcGIS Survey123 is a recommended one. The best place to start looking for an app is on your phone. Check to see if one is already installed on your phone.  If you locate one, do a quick Internet review to ascertain its capabilities. 

If no GPS app is present on your phone, or you wish to install one that you really like, you can get one from the Play Store or the App Store.  Here are some useful GPS apps that are available for downloaded from Google Play Store or Apple’s App Store.   


**Android Apps**

1. GeoPaparazzi.  This app is good for recording the location and attribute of feature events. It allows feature attributes to recorded in the form of text, audio or pictures.  Files can be exported as KML and GPX, which are popular formats for storing points data. 

2. GPS Essentials. This is a good app for fieldwork in the social and environmental sciences. Logs waypoints and routes and can attributes of features. It will also allow you to export to KML and GPX.

3. ESRI Collector. Many organizations use ESRI Collector for collecting location-based data, e.g., utility lines, other assets, geological data, etc. This is a good app to master if you work in the ESRI world. The software also smoothly integrated with other ArcGIS Products when it comes to data visualization and data analysis.

4. ArcGIS Survey123.  This is an excellent app for conducting surveys that involves some location questions. It smoothly integrated with other ArcGIS Products when it comes to data visualization and data analysis.

5. OpenDataKit. This app lets you log GPS positions and save them to an offline database.

6.  GPS Benchmark. This app compares a user-entered ground truth location to GPS data from the mobile device to calculate true accuracy of the GPS. Other apps will only show the estimated location error that is calculated by the device, which (as GPS Benchmark shows) can be far from accurate.

7. GAIA GPS. This is a great hiking navigation app that can be utilized for field data collection. Has an excellent collection of base maps that can be used offline.

8.  Geology Sample Collector.  This app has a built-in theodolite, GPS, Clinometer, Camera. Data backup can be done to its server database and synced with the mobile device as well. 

9.  Maverick GPS Navigation.  This app is good for recording tracks and points in GPX format and importing them in QGIS to create shapefiles. https://play.google.com/store/apps/details?id=com.codesector.maverick.lite&hl=en

10. DataScope (https://www.mydatascope.com) They have an Android and iOS app, it works perfect offline and then you can synchronize the information. It's simple like Google forms but you can gather more things such as photos and signatures. They have a free versions ;)



**IOS Apps**

1.  EpiCollect. EpiCollect will work on both iOS and Android. 

2.  FileMaker Go. If you want a solution that is proven to work for form creation on iOS, this is it. It does work, but it’s not Open Source.
       
3.  Gaia GPS.  This is a great hiking navigation app that can be utilized for field data collection.



Since each GPS app is different, it will be your responsibility to familiarize yourself with the details of how the app you selected phone works. However, this is a straight forward process and there is broadly similarity in how the apps work. Later in this Chapter, I will illustrate how to collect GPS data using GeoPaparazzi.


|

Pre-Planning your GPS Project
-------------------------------

To successfully carry out a GPS data collection project, some amount of pre-planning is necessary.  Some things that you need to do include: 

**1. Decide on the coordinate system that will be used to collect the GPS points.**
For the most part, the default setting of the GPS apps will be latitude \longitude. You should collect your data in latitudes/longitudes unless there is a good reason not to. It is also a good idea to collect the coordinates in decimal degrees (DD) format, as the default setting of most GIS software is decimal degrees, and this will make it easy to import your coordinates into the GIS software. In decimal degrees format, the coordinates will appear as shown below: Latitude: 40.714; Longitude: -74.006

Finally, you should be aware of the datum used for your coordinates. The datum defines the size and shape of the earth and is the starting point for all maps.  The US GPS uses the WGS 84 datum.  In the US, current topographic maps are based on the GRS 1980 datum, which is functionally equivalent to WGS 84. This means that GPS points will be exactly located on maps that are based on GRS 1980 datum. 


**2. Ascertain the level of accuracy of your GPS.**  
You should be aware that a single measurement of a point feature using a smart phone GPS is likely to yield positional errors in the region of 5-10 meters without differential correction.  The effect of this is that when the point is displayed in a GIS software or even Google Earth, it may not exactly reference the feature of interest.  For this project, this level of accuracy is acceptable, but you should be aware that each project has its accuracy tolerance.
To improve the quality of the coordinates you collect, make sure that you get a clear view of the sky when you are collecting the points so that the GPS signals are not being affected by trees or buildings.  Also, stand at a given location for at least a minute to give the receiver sufficient time to settle on the coordinates of your position.   Finally, you should wait for your receiver to be receiving signals from at least 4 satellites before recording data.


**3. Decide on the best time of the day to best collect the GPS points.** 
Recall the concept of Position Dilution of Precision (PDOP).  Poor satellite geometry may give rise to unacceptable errors in the coordinates of points collected. This problem can be reduced by selecting a time of the day to collect data when the overhead positions of satellite will result in in good PDOP. 

Trimble, a company that makes GPS receivers, has a software on their website that can be used to plan the best time of day to collect GPS coordinates. Let’s hop over to Trimble and have a look at their website - www.trimble.com/GNSSPlanningOnline  
The main page of the website is shown below. To the left is a list of GNSS satellites and their status.  To the far right is a locator map. 

a.  Click on the map and scroll to the area where you want to conduct your GPS field work and click on it.  This action will population the latitude/longitude in the middle of the screen.  
 
b. Make sure you select the date and time range for the field work. 

c. The software will use this data to show overhead positions of the satellite on the day you selected.   

d. Once you have entered all the data, click “Apply”. Now click on Charts menu at the top of the screen. The software will now show you charts of the number of satellites overhead during your field work period, the visibility status of the satellites, PDOP status, etc.

e. Since we are particularly interested in PDOP, please look over the DOPs chart.  Look at PDOP values for different times of the day.  Generally, PDOP values below 6 are good enough and values below 4 are even better.  Values at 9 or higher mean that the user should not rely on the accuracy of that data collected at that time and should wait until a better PDOP value could be attained by the satellites.

 

|

Field Data Collection with Geopaparazzi
-----------------------------------------

I will illustrate the details of smart phone GPS field data collection using an app named Geopaparazzi. If you want to use this app, first download it from the app store, install it, then click on the app icon to start the program.


1. After starting Geopaparazzi, the main dashboard appears.  This screen is shown below with labels.
 
2.  A useful way to start interacting with the application is to click on the Project Info icon and enter basic information such as the name of your project, a description of the project, date, creator, etc.  I strongly recommended that you create a new project for each field survey you conduct so as to avoid confusion in the registered data.   Projects are saved in a single file in the home directory of the phone. The file is called geopaparazzi.gpap. 

3. Once you are done entering basic project information, click on the three vertical dots on the top of the screen above the project info icon to access the GPS settings. Afterwards, click on “Status” to view the list of satellites ‘visible’ to the GPS in your smart phone.  The screen also shows your current coordinates, elevation, speed, PDOP and other information.

4. Now click on the Map View icon.  This action will allow you to see Geopaparazzi’s base map of your location.  Also, Geopaparazzi comes with its own base map, it is possible for you import your own base map into the app. This is particularly useful if your work requires specialized maps of the study area.
Within the Map View area, tools are available to center the map, manage bookmarks (waypoints), and manage notes. From within the View, you can also access the GPS log of collected tracks and waypoints.

5. Let’s start logging features. Go to the first feature of interest. Stand next to it for a moment then click on the GPS Toggle icon.  When the dialog opens, enter a name for the point feature or use the default name. When you click ok, the GPS Toggle icon should turn orange and the GPS would begin logging.  As further evidence that the GPS is logging data, the GPS icon at the top right of the screen would change to blue. 

6. By default, the app will log the path you traverse. To record a single waypoint or marker along the path, click on the Map View icon. This time, you will be presented with a map zoomed in to the location whose coordinates you are logging.  
 
7. Click on the star icon to the left of the screen. This will prompt you to enter the name of a bookmark or waypoint. Enter a name and click Ok. Immediately, the point location will be recorded.

8. While still in the Map View, you can click on the topmost icon to the top left of the page to access the Notes section. Enter notes for the feature you just recorded. You can enter text (text note), take a photo of the feature (image notes) draw a sketch of something of interest (sketch), or make a map note. 

9.  Once you are done taking notes, return to the Map View area.  Continue moving along your path, while stopping at intervals to create a bookmark.  Every time you want to create a bookmark, just click on the bookmark start icon, enter a name for the bookmark, and click ok.

10. If you wanted to see a list of the bookmarks you created, just click and hold down the bookmark star icon. The list of bookmarks appears. You can edit this list if you wish.
 
11.  You can stop GPS logging features at any time.  Simply back out of the Map View screen then click the GPS Toggle button to stop logging. To start GPS logging again, select the toggle button and enter a new log name.


12. You can view the GPS log to make sure that the point was successfully logged. To do so, tap on the bright orange icon at the left top of the Map View window. When the dialog opens, click on “GPS data list”. There you should see a record of the logs you created (See illustration below).
 

In the next section, we will focus on how to export your field data from Geopaparazi and import it into Google Earth and QGIS for viewing. 


**References**
Geopaparzzi manual - https://www.slideshare.net/silli/2014-10-
27foss4gosakageopapworkshophttps://itstillworks.com/iphone-gps-work-its-out-range-18021.html

Mobile data collection with GeoPaparazzi and QGIS - http://blog.sourcepole.ch/2016/12/23/mobile-data-collection-with-geopaparazzi-and-qgis/

A Mobile Field-Data Collection Workflow. - https://www.slideshare.net/silli/geopaparazzi-workshop-foss4geparishttp://isaacullah.github.io/A-mobile-field-data-collection-workflow/

How to Create Data Entry Forms for Geopaparazzi - http://downloads.gvsig.org/download/events/gvSIG-Festival/1st-gvSIG-Festival/Reports/7-Digital_field_mapping_with_Geopaparazzi_and_gvSIG.pdf



|


Exporting GPS Data from Smart Phones
-------------------------------------

Once you are done collecting GPS data, your next step is to move the data from the smart phone to a GIS or similar software for viewing or analysis.  The details of this process are specific to the equipment that you are using. However, the general idea is that the GPS receiver must be connected to the computer that has the GIS software. The connection can be done via cable or wirelessly.  Appropriate software is then used to transfer the data.  

1. To begin exporting your data from Geopaparazzi, click on the export icon at the main menu.
 
2. When the Export dialog, appears, select a file format to use. I suggest either kmz or GPX format, as both of these formats can be easily read by Google Earth.  
 
3. After exporting the data, the next step is to move the data to your computer. There are various ways to accomplish this task. One of the simplest ways to do it is by simply connecting your phone to a computer using a USB cable.  You can then access your phone’s storage from the File Explorer on your PC.   When you connect the two devices, they should detect each other’s presence.  

4. If your phone does not contain any data when viewed from the computer, it may be because you did not click on ‘File Transfer mode’ on your phone.   Back on the main screen you will see a screen that says “Charging: Tap for other options” or something similar. When you tap the screen a dialog similar to the one below appears. Select the File Transfer Options and you should be able to access your phone’s storage from your computer.
 
5. After gaining access to GeoPaparazzi’s project folder, copy the data to a folder on your computer. 



|

Displaying GPS Points in Google Map  
-------------------------------------

1.  Google Earth is a popular software for viewing GPS waypoints or routes.  Let’s visualize our GPS data using Google Earth. 

2.  If you do not have Google Earth Pro on your computer, then download at at this website: https://www.google.com/earth/versions/  Make sure you download the Desktop version. 

3.  Once Google Earth Pro is installed, double click on the KMZ file you transferred from your smart phone. This will launch Google Earth Pro. The software will open and zoom to the location of the points or tracts that you logged.

4.  Browse around in Google Earth Pro and examine the points carefully. Were they accurately recorded? Are you satisfied with the amount of error involved?

 

|



Importing GPS Points into QGIS
--------------------------------

To view your data in QGIS, do the following:

1. Click on the QGIS icon and start a new QGIS Project.

2. Click on Layer/Add Layer/Add Vector Layer as shown below. 

3. When prompted for a data source select the KMZ file you just exported. You may have to ensure that your browser is searching for all filetypes.
 
4. Once this is done you should have a vector layer which displays all of the notes and bookmarks you made on the project. 

 

 

Uploading GPS Points in ArcGIS Online 
--------------------------------------


ArGIS Online is a popular ESRI software used for viewing and sharing data online   If you want to share your GPS data with colleagues near and far via the web maps, ArcGIS Online is a good choice. To do so, follow the steps below:

1. Visit ArcGIS Online and sign up for a free account.

2.  Once you are done signing up, click on “Map” to create a new map.

3. Click on “Add”you load the data into the software.



|
 

Loading a GPS File into Your Phone 
------------------------------------------------------

1.  Email the GPX file to yourself.

2. Load file into your app by clicking on the GPX file in your mail app

3.  Select the GPS viewing app you want to open the file. 

4. The waypoints or tracks should show up and look something like this. 



Loading a GPX file by Google Drive (Or Dropbox)
1) Get Google Drive for iTunes or Google Drive for Android and one of the GPX Viewing apps mentioned above like ARA GPX Viewer
2) Open a file in Google Drive
3. Click on the three dots in the upper right corner. On the next screen, click "Open in" 
4. Next, choose the GPX viewing app:
5. You should now see the file. 

 


|

Generating Points Data by Geocoding
-------------------------------------
If you have a large number of street addresses and wish to turn them into points on a map, doing so using the method described above can be time consuming and tedious. QGIS and ArcGIS Online have tools that can generate GIS coordinates from addresses. This process is called geocoding. 


**Geocoding Using QGIS**

Click on the links below for tutorials on how to perform geocoding using QGIS.

1.  https://www.gislounge.com/how-to-geocode-addresses-using-qgis/

2. https://guides.library.ucsc.edu/DS/Resources/QGIS

3.  https://www.youtube.com/watch?v=FOAM0vfsSns


|