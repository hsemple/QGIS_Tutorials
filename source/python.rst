Automating Processes with Python
=================================


|

Getting Started

1. Add this WFS layer to QGIS - Add Layer - Add WFS Layer..., then select New and provide this URL: https://maps.gns.cri.nz/geology/wfs

2. Right-click the layer called NZL_GNS_250K_faults (it is near the bottom of the list) and select Add Layer to Project. The layer should appear in the project table of contents.

3.  Select Plugins - Python Console from the main menubar.  It will open up somewhere in the window (you may find it easier to work with if you detach it from the main window.

4.  The lower part of this display with the >>> prompt is where you can type commands. Try an oldie-but-goodie

   >>> print("Hello, World!")


5. Since we are running Python inside QGIS,  core pyqgis modules are loaded. Try this

   >>> layer = iface.activeLayer()
   >>> layer.sourceName()


6.  You should get the response in the upper half of the console

'NZL_GNS_250K_faults'


7. iface refers to the interface, and the activeLayer() function returns an object representing the active layer, which in our project is the only layer loaded. Now try



|

**Let's try a few things**

Let us count the number of features in the layer:

>>> layer.featureCount()


That was easy. How about we add together their lengths? Inspection of the layer tells us there is an attribute called length, so we could do this:

>>> lengths = []
>>> for fault in layer.getFeatures():
        lengths.append(fault.attribute("length"))
>>> print(sum(lengths))


>>> for fld in layer.fields():
        print(fld.name())




You'll start to see the limitions of the console here. You have to indent by hand (it doesn't do it automatically), but if you get past that it works. 


|

The Editor Window
-------------------

An alternative to using the Console is to use the Editor window.  The editor is accessed by right-clicking Show Editor in the upper part of the console.



Jupyter notebook
-------------------

If you are familiar with Jupyter notebook, then put it to use with QGIS. You can install the pyqgis modules into an environment and work with them directly outside of the application itself. And ESRI are also into notebooks, see here for more!



Create a Python GIS environment  - https://autogis-site.readthedocs.io/en/latest/course-info/create-python-gis-environment.html



|

Resources
------------

Getting Started With Python Programming (QGIS3) - https://www.qgistutorials.com/en/docs/3/getting_started_with_pyqgis.html

Customizing QGIS with Python (Full Course Material) - https://courses.spatialthoughts.com/pyqgis-in-a-day.html

Free and Open Source GIS Ramblings - https://anitagraser.com/pyqgis-101-introduction-to-qgis-python-programming-for-non-programmers/


GIS Python API documentation - https://qgis.org/pyqgis/master/

PyQGIS Developer Cookbook - https://docs.qgis.org/3.16/en/docs/pyqgis_developer_cookbook/index.html

Streamlining GIS with Automation - https://www.geospatialworld.net/prime/technology-and-innovation/streamlining-gis-with-automation/


|