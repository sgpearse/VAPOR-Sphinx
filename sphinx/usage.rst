.. _usage:

=============
Using Vapor 3
=============

Vapor 3 is comprised of a set of tools called Renderers.  Each Renderer visualizes your data in different ways based on your specifications.

We recommend that all users either watch our :ref:`Introductory Tutorial <introTutorial>` or work through the :ref:`quickStartGuide`.

If any feature in Vapor is not sufficenty self describing in the applicaiton, this is where to find elaboration.  Please :ref:`contact our team `<contactAndContribute>` if you think you may have found a bug, usability issue, or you'd like to request an enhancement.

.. _controllingYourRenderers:

Controlling The Renderers
-------------------------

Each of Vapor's renderers will create imagery of your variables according to color, opacity, a region of interest, and sometimes a few more specialized parameters.  

Each renderer is unique, the specification of their parameters is mostly the same.  All renderers are controlled by four tabs:

    - :ref:`Variables <variablesTab>`
    - :ref:`Appearance <appearanceTab>`
    - :ref:`Geometry <geometryTab>`
    - :ref:`Annotation <annotationTab>`

.. _variablesTab:

See the :ref:`Renderers <renderers>` section for mor information on how each of these tabs work for a given renderer.  Again, they all operate in the same way for the most part.

Variables Tab
_____________
The Variables Tab allows the user to define what variables are used as input to a renderer.  The options presented to the user in this tab depend on the renderer currently being used.

Users that have converted their data into :ref:`VDC <vdc>` will have a fidelity controller, which allows them to view compressed data to speed up their rendering time.  Making a visualization interactive lets you change parameters faster, so you can crank up the fidelity of your data for a final visualization after exploring first.

.. _appearanceTab:

Appearance Tab
______________
The appearance tab controls the `color <controllingColor>`_ and `opacity <controllingOpacity>`_ of the variable being used by your renderer.  This is done through the Transfer Function.

The Transfer Function consists of a `Probability Density Function (PDF) <https://en.wikipedia.org/wiki/Probability_density_function>`_ of your currently selected variable.  Underneath the PDF is a color bar that shows the colors that get applied to the values located directly above it.

.. figure:: transferFunctionDocumentation.png
    :align: center
    :figclass: align-center

    Vapor 3's Transfer Function editor

In the figure above, we can see that our transfer function is operating on the variable P.  The range of values within the transfer function are -1314.76 to 1268.32.  All values of P less than 1314.76 are colored deep blue.  The coloration transitions into red at the high end of the PDF, until becoming saturated at values of 1268.32 and higher.

.. _controllingColor:

Controlling Color
"""""""""""""""""

Vapor's default color map is called CoolWarm.  This is arbitrary, and may not suit your needs.  Vapor bundles several other color maps that can be loaded with the "Load TF" button at the top of the tab.

The distribution of your color map can be skewed by right-clicking on the Colorbar, and clicking "New Color Control Point."  These control points will allow us to drag color points back and forth along the color bar.

.. figure:: colorControlPoint.gif
    :align: center
    :scale: 25
    :figclass: align-center

    Adding and moving color control points in the Colorbar

These control points may also be given direct color values by either double clicking them, or right-clicking and selecting "Edit color control point".  After a color has been changed, Vapor will interpolate between control points to give a smooth color transition.

Controlling Opacity
"""""""""""""""""""

Opacity is controlled by a green piecewise line laid over the PDF.  The higher this green line is on the Y axis, the more opaque the colors will be that coincide at that point.  For example, the green bar is set to Y=0 in the image below.  All variable values will be masked out where this is the case.  The green bar then ramps up, and the values become more opaque.

.. figure:: opacityMap.png
    :align: center
    :scale: 25
    :figclass: align-center

    The green line controlls how opacity is applied to different values of the Transfer Function's color variable.  Here, the blue values are hiden completely.  White values ramp up from transparent to opaque, and red values are fully opaque.

.. _geometryTab:

Geometry Tab
____________

The Geometry tab controls where your renderer is being drawn.  By excluding some regions of data from being drawn, some observables can be seen more clearly, and compute time can be reduced by freeing up the memory of unnecessary data.

.. figure:: geometryWidget.png
    :align: center
    :scale: 25
    :figclass: align-center

    Specify the area that your renderer will apply to in the coordinate selector.  3D renderers operate on X, Y, and Z.  2D renderers currently operate on X and Y.
    
If you have a region of interest in another renderer, that region can be copied in the Geometry tab.

.. figure:: copyRegionWidget.png
    :align: center
    :scale: 25
    :figclass: align-center

    Copy geometry from one renderer to another


Sometimes it's necessary to scale, translate, rotate, or modify the origin of an individual renderer.  Users can manipulate the appearance of their renderrers with the transform table at the bottom of the Geometry Tab.

.. figure:: transformTable.png
    :align: center
    :scale: 25
    :figclass: align-center

    Individual renderers can be transformed within the Geometry widget.

.. _annotationTab:

Annotation Tab
______________

Quantifying the colors to your viewers can be done by adding a colorbar in the Annotation tab.

.. figure:: colorbarTab.png
    :align: center
    :scale: 25
    :figclass: align-center

    Colorbar size and position controlls, located in the Annotation tab

.. figure:: colorbar.png
    :align: center
    :scale: 25
    :figclass: align-center

    An exmaple colorbar

|

.. _renderers:

Renderer Deep Dive
------------------

Volume Renderer
_______________

Displays the user's 3D data variables within a volume described by the source data file, according to color and opacity settings defined by the user.  These 3D variables may be offset by a height variable.

.. figure:: DVR.png
    :align: center
    :scale: 25
    :figclass: align-center

Isosurfaces
___________

Displays the user's 3D data variables within a volume described by the source data file, according to color and opacity settings defined by the user.  These 3D variables may be offset by a height variable.

.. figure:: IsoSurface.png
    :align: center
    :scale: 25
    :figclass: align-center

Slices
______

Displays an axis-aligned slice or cutting plane through a 3D variable.  Slices are sampled along the plane's axes according to a sampling rate define by the user.

.. figure:: Slice.png
    :align: center
    :scale: 25
    :figclass: align-center

Contours
________

Displays a series of user defined contours along a two dimensional plane within the user's domain.\n\nContours may hae constant coloration, or may be colored according to a secondary variable.  Contours may be displaced by a height variable.

.. figure:: Contours.png
    :align: center
    :scale: 25
    :figclass: align-center

Barbs
_____

Displays an array of arrows with the users domain, with custom dimensions that are defined by the user in the X, Y, and Z axes.  The arrows represent a vector whos direction is determined by up to three user-defined variables. Barbs can have a constant color applied to them, or they may be colored according to an additional user-defined variable.

.. figure:: Barbs.png
    :align: center
    :scale: 25
    :figclass: align-center

Two Dimensional Variables
_________________________

Displays the user's 2D data variables along the plane described by the source data file. These 2D variables may be offset by a height variable.

.. figure:: TwoDData.png
    :align: center
    :scale: 25
    :figclass: align-center

Georefernced Images 
___________________

Displays a georeferenced image that is automatically reprojected and fit to the user's data, as long as the data contains georeference metadata.  The image renderer may be offset by a height variable to show bathymetry or mountainous terrain.

.. figure:: Image.png
    :align: center
    :scale: 25
    :figclass: align-center

Wireframes
__________

Displays a wireframe of the mesh for the selected variable

.. figure:: WireFrame.png
    :align: center
    :scale: 25
    :figclass: align-center

|

Ancillary Tools
---------------

Animation
`````````

Python Engine
`````````````

2D Plots
````````

Statistics
``````````
