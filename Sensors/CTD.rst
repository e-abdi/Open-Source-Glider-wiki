CTD
++++++++++
Stands for Conductivity, Temperature and Depth. This is a standard sensor on all gliders. Conductivity can be used in conjunction with temperature and depth to measure water salinity.
For more information about measuring salinity, check out `this resource <https://salinometry.com/>`_.
The most common method of measurement is the use of a conductivity cell in which seawater flows through two electrodes. Applying a voltage to this electrodes results in a current proportional to water salinity.
Seabird has been the dominent manufacturer of CTDs for many years now and they produce extremely accurate sensors, but they don't have the best design and service for gliders.

.. image:: /images/CTsail.png

Another newer method of measuring conductivity is by using an inductive conductivity cell where instead of directly measuring the resistance, the sensor measure changes in the electric field inside a toroidal coil. 
RBR which manufactures some other excellent sensors, seems to have the new CT of choice for gliders!
These are much easier to install and remove (at least from Seagliders) and have a much quicker calibration time. RBR offers a Three-or-Free calibration guarantee where if they don't manage to calibrate these within three weeks, it's free of charge! Whereas Seabird calibration can often take anywhere from three months to a year!
Another advantage is that these won't get mistaken for a handle on Seagliders!

.. image:: /images/legato.png

Current Implementation in Tuba
--------------------------------
There seem to be a few good low-cost and/or open options for us to use in Tuba. `Here <https://github.com/OceanographyforEveryone/OpenCTD>`_ is an open-source version. There is also `this <https://atlas-scientific.com/probes>`_ website which seem to have other sensors such as oxygen and PH!


