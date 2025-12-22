Background
++++++++++++++
For people who are not coming from Ocean Studies background (as this was the case for me), it might be useful to start with a basic introduction to different types of platforms and systems used to study the oceans. This will help appreciating the gliders for the amazing tool they are but also knowing their limitations. 

Stationary
==============
The simplest type of stationary platform is a buoy, which is held in place by an anchor. Buoys are primarily used for marking locations, but if they are equipped with sensors, they can also function as weather stations, especially in coastal areas.
A mooring is a structure anchored to the seafloor that may have a surface buoy or be completely submerged. It often carries sensors at various depths and is typically recovered using a release mechanism.
A lander is a type of mooring that rests directly on the seafloor and measures environmental variables, such as currents.

Moving
================
Non-steerable
-------------------
The simplest kind of moving platform is called a drifter. It’s essentially a buoyant structure that floats on the water surface, drifting with currents, and transmits information such as its location at specified intervals.  Check out `this <https://www.onelessbottle.org/oceantracking/>`_ project where they used a simple water bottle as a drifter. 

A float is a device that monitors the water column by changing its buoyancy, allowing it to float up and down without any steering capability. Probably the best example of standardization in oceanography is the `Argo program <https://en.wikipedia.org/wiki/Argo_(oceanography)>`_ where they have standardized everything. All the way from hardware to data. 
A French team has designed a low-cost float `here <https://github.com/ThomasLeMezo/seabot/tree/master>`_.

.. image:: /images/argo.jpg

Steerable
------------------------
Surface Vehicles
============================
There are a few interesting systems in this category such as the `Waveglider <https://www.liquid-robotics.com/wave-glider/how-it-works/>`_, `Autonaut <https://www.autonautusv.com/>`_ and `Saildrone <https://www.saildrone.com/>`_ but my favorite is a simple autonomous sailboat called `SailBuoy <http://www.sailbuoy.no>`_. This is probably one of the most elegantly designed vehicles I have seen in this field. It just does what it needs to do, efficiently and robustly.

.. image:: /images/sailbuoy.jpg

Subsea vehicles
============================
Tethered
-------------------
An ROV (Remotely Operated Vehicle) is probably the best-known type of ocean platform, often described as an underwater drone. Because ROVs are connected to a surface ship or platform by a tether, they can achieve precise localization and stable hovering. This makes them ideal for tasks that require high precision, such as offshore construction, equipment inspection, and underwater repairs.


.. image:: /images/bluerov.jpg

Untethered
-------------------------
These are called Autonomous Underwater Vehicles or AUVs. AUVs usually have one or more propeller and some kind of acoustic navigation system. They are usually used for short missions (few hours to a week or so) to cover a relatively large area with precision. 

.. image:: /images/auv.jpg

There seem to be many educational AUV projects, a few of which are listed below:

* `The MIT Sea Scout <https://oceanai.mit.edu/pavlab/pdfs/proj_seascout.pdf>`_
* `CPSdrone AUV <https://youtu.be/h1Fw6ZvO_h4?si=z4zoR22lJLV2wuVB>`_


A glider is considered a type of AUV, but the main differences are that:

- It's completely autonomous for hours at a time
- Its propulsion system requires it to move up and down the water column in a sawtooth pattern in order to move forward. 
- It usually has a very long endurance (in the order of few months)
- It can cover extremely large distances, such as the Atlantic Ocean
- It's quite slow; around 1 knot


An underwater glider works on a similar principle as a normal air glider where the medium is water. There is no propeller in either glider, but the main difference is that unlike air gliders, underwater gliders use a neat trick to climb back up the water column after gliding down. They do this by changing their density. Gliders are carefully designed to have a density very close to that of water. Then by simply changing their volume (which can be achieved using a simple piston pump or an inflating oil bladder), they can change their density and use the buoyancy force to fly up and down the water column.
By moving a large weight internally (usually the battery pack) it can control its pitch and by rotating the weight, it can roll and therefore fly towards a certain heading. 

There is a partial vacuum inside the glider. This serves a few purposes: 

- Sucking all the seal joints together, creating a tighter seal
- By monitoring the internal pressure we will know right away if there is a leak somewhere. 
- In order to get oil from external bladder inside the glider, we just open a solenoid valve and the air pressure pushes the oil inside so we save power on pumping

.. image:: /images/parts.png

    