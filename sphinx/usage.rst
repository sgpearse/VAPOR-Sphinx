.. _usage:

=============
Using Vapor 3
=============

Vapor 3 is comprised of a set of tools called Renderers.  Each Renderer visualizes your data in different ways based on your specifications, which you specify through Vapor's user interface.

We recommend that all users either watch our :ref:`Introductory Tutorial <introTutorial>` or work through the :ref:`quickStartGuide` which will show you how to install Vapor 3, load some data, and create your first :ref:`Renderers`.  

The next step is to then learn about how to control your Renderer, using theVariables, Appearance, Geometry, and Annotation tabs.  

From here, we document each renderer individually, noting their behavior and unique attributes that they may exhibit.  

We then cover some computational and diagnostic tools included in Vapor3.  Finally, we talk about Vapor3's supported data formats, and the VDC data format which can greatly reduce Renderer computation time and enable easier data exploration. 

The User Interface
------------------

.. _controllingYourRenderers:

Controlling Your Renderers
``````````````````````````

Each of Vapor's renderers will create imagery of your variables according to color, opacity, a region of interest, and sometimes a few more specialized parameters.  While each type of renderer is unique, specifying their parameters in Vapor is mostly the same.  All renderers are controlled by the Variables, Appearance, Geometry, and Annotation tabs.

.. _variablesTab:

Variables Tab
`````````````
The Variables Tab allows the user to define what variables are used as input to a renderer.  Usually this consists of a single variable that has color and opacity mapped to it through parameters set in the Appearance Tab.

If users have converted their data into `VDC`, they will find controls that allow different levels of compression to be applied to their renderings.  This is desirable for exploratory reasons, as very large datasets can take a long time to render.  Compressing the data often allows a more interactive eperience, where users can find important observables, color those observables, then finally turn off compression for a final rendering.

Some renderers operate on a field of vectors, such as the Barb and Flow renderers.  Users should specify the X, Y, and Z vector s that these renderers will use to portray direction.  The field vector values will default to U, V, and W if those variables exist within the data set.

Renderers such as Barbs and Isosurfaces may be color-mapped according to an extra variable.  For example, a user may want to render an Isosurface of pressure at 500 mb, and color that isosurface according to the humidity field at all points on that surface.



.. _appearanceTab:

Appearance Tab
``````````````
The appearance tab controls the color and opacity of the variable being used by your renderer.  This is done primarily through an object known as a Transfer Function in the world of visualization.

The Transfer Function consists of a `Probability Density Function (PDF) <https://en.wikipedia.org/wiki/Probability_density_function>`_ of your currently selected variable.  Underneath the PDF is a color bar that designates what colors get applied to your variable's values located directly above it.

.. figure:: transferFunctionDocumentation.png
    :align: center
    :figclass: align-center

    Vapor 3's Transfer Function editor

In the figure above, we can see that our transfer function is operating on the variable P.  The user has chosen to operated on the range -1314.76 to 1268.32.  All values of P less than 1314.76 are colored deep blue.  The coloration transitions into red at the high end of the PDF, until becoming saturated at values of 1268.32 and higher.

We can skew the color distribution being applied to P's PDF by right-clicking on the Colorbar, and clicking "New Color Control Point."

.. figure:: colorControlPoint.gif
    :align: center
    :figclass: align-center

    Adding and moving color control points in the Colorbar

The three most important controls on the Transfer Function are the Colorbar, the Opacity Controller, and the Variable Range Selectors.

.. _geometryTab:

Geometry Tab
````````````
    - foo
    - bar

.. _annotationTab:

Annotation Tab
``````````````
    - foo
    - bar

|

.. _renderers:

Renderers
---------

Volume Renderer
```````````````

Isosurfaces
```````````

Flow Integration
````````````````

Slices
``````

Contours
````````

Barbs
`````

Two Dimensional Variables
`````````````````````````

Georefernced Images 
```````````````````

Wireframes
``````````

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
