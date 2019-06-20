.. _usage:

=================
Usage
=================

Vapor3 is comprised of a set of tools called Renderers.  Each Renderer depicts your data in different ways based on your specifications, which you specify through Vapor's user interface.

We recommend that all users either watch our :ref:`Introductory Tutorial <introTutorial>` or work through the :ref:`quickStartGuide` which will show you how to install Vapor3, load some data, and create your first :ref:`Renderer`.  The next step is to then learn about the Variables, Appearance, Geometry, and Annotation tabs, which are used to specify Renderer behavior.  From here, we document each renderer individually, noting their behavior and unique attributes that they may exhibit.  

We then cover some computational and diagnostic tools included in Vapor3.  Finally, we talk about Vapor3's supported data formats, and the VDC data format which can greatly reduce Renderer computation time and enable easier data exploration. 

|

.. _data:

Data in Vapor3
--------------

.. _VDC:

Vapor Data Collection (VDC)
```````````````````````````

.. _WRF:

WRF
```

.. _NetCDF-CF:

NetCDF-CF
`````````

.. _MPAS:

MPAS
````

|

User Interface Basics
---------------------

.. _ControllingYourRenderers:

Controlling Your Renderers
``````````````````````````

Each of Vapor's renderers will create imagery of your variables according to color, opacity, a region of interest, and sometimes a few more specialized parameters.  While each type of renderer is unique, specifying their parameters in Vapor is mostly the same.  All renderers are controlled by the Variables, Appearance, Geometry, and Annotation tabs.

.. _VariablesTab:

Variables Tab
`````````````
    - foo
    - bar

.. _AppearanceTab:

Appearance Tab
``````````````
    - foo
    - bar

.. _GeometryTab:

Geometry Tab
````````````
    - foo
    - bar

.. _AnnotationTab:

Annotation Tab
``````````````
    - foo
    - bar

|

.. _Renderers:

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
