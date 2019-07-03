.. _gettingDataIntoVapor:

Getting Data into Vapor3
--------------

Vapor can currently read the following data formats:

- :ref:`VDC`: Vapor Data Collection

WRF-ARW, NetCDF files that follow the CF Convention, and MPAS model data.

Files of these types can be directly imported into Vapor, and rendered to a user's needs.  

.. _vdc:

Vapor Data Collection (VDC)
```````````````````````````

One of Vapor's key strengths is its VDC data format, which allows users to render their data at different levels of compression.  Viewing compressed data reduces the time a rendering takes to complete, which allows users to interact with their data without having to wait.  Typically, a user will render their data at a compressed fidelity first.  Then when they have found the general settings for rendering their observabbles, they can render their data at an uncompressed fidelity for their final visualization.

.. _wrf:

WRF
```

.. _netCDF-CF:

NetCDF-CF
`````````

.. _mpas:

MPAS
````

