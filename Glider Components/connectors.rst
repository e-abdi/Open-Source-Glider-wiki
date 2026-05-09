Connectors
+++++++++++++++++

There is no widely established standard for subsea connectors, but there are some promising efforts such as `Bristlemouth <https://bristlemouth.org/documentation>`__. `Blue Robotics <https://bluerobotics.com/learn/wl-connector-standard/>`__ also has a nice page on connector standardization.


External
-------------------

Probably the most well-known and widely used underwater connector are essentially wet-pluggable meaning they can be mated when submerged. This is because the seal here is silicone grease so you need to make sure you are using plenty of it when mating them.

.. image:: /images/subbconn.jpg
    :width: 400

Another popular type of connector popular on gliders is the impulse IE55 series. These are nice and low-profile but since they are dry-mate and the seal is essentially tow rubber pieces, if there is a small imperfection or handled wrongly in the field, they prone to leak. This has happened countless times and most teams are moving away from these for most applications.


.. image:: /images/IE55.png
    :width: 400

Seaglider also uses these AMTEK coax connectors for the antenna cable.

.. image:: /images/AMTEK.png
    

The exciting news here is that BlueRobotics is working on a new line of low-cost underwater connectors so this might be a game-changer.

.. image:: /images/BRconnector.png
    :width: 400

Internal
--------------------

Slocums use a combination of Molex and a circular military-spec connector which is quite strong but very annoying, difficult, and awkward to tighten and loosen.

.. image:: /images/slocumconnectors.jpg
    :width: 400

Seagliders use a combination of different TE Connectivity connectors for power and signal and SMA for antenna connection.

.. image:: /images/seagliderconnectors.png
    :width: 400

OceanScout uses these cool connectors with combined RF and digital lines.

.. image:: /images/nicomatic.png
    :width: 400



Implementation in Tuba
--------------------------------

Currently, we are using a combination of JST-XH series connectors for digital lines and SMA for RF internally, as shown in `Tuba wiring <https://github.com/e-abdi/tuba-wiring>`__. Externally, we have a single MCBH-8F bulkhead connector that acts both as the lab test and communication cable interface and as the shorting plug used to turn the glider on.

For RF, I am currently using coaxial cables passing through penetrators and sealed with Scotchcast resin. For the next version, I plan to try these relatively low-cost underwater connectors from `Blue Trail Engineering <https://www.bluetrailengineering.com/cobalt14>`__.

.. image:: /images/bluetrail.png
    :width: 400

The idea is to use popular connectors such as some of the JST series and define a standard, expandable pinout, something along the lines of `Qwiic <https://www.sparkfun.com/qwiic>`__.

Another very interesting technology that could be useful for underwater docking is `NiobiCon <https://www.northropgrumman.com/what-we-do/mission-solutions/niobicon>`__.

