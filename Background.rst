Background
++++++++++++++
For readers who do not come from an ocean science background, it can be useful to start with a quick overview of the main platforms used to study the ocean. That context makes it easier to appreciate what gliders do well, and also where other platforms are a better fit. 

If you want a good overview of commercially available ocean technology, take a look at `this yearly buyer's guide <https://www.rovplanet.com/orp-buyers-guide-09-04-2026>`_.

`The SCOOP catalogue <https://www.scoop-ocean.org/catalogue>`_ is a nice catalogue of low-cost marine technologies, mainly focused on sensors so far.


Stationary
==============
The simplest stationary platform is a buoy held in place by an anchor or mooring line. In oceanography, buoys are often used as surface observation nodes for waves, weather, and sea-surface conditions, and they can also act as communication gateways for instruments below. A good modern example is the commercial `Spotter buoy <https://www.sofarocean.com/products/spotter>`_, which is a compact solar-powered system for real-time surface measurements and can be extended with additional sensors below the surface.

A mooring is a broader term for a system anchored to the seafloor that may include a surface buoy or may remain fully submerged. Moorings can carry sensors at several depths for long periods and are often recovered with an acoustic release.

A lander is a type of bottom-mounted platform that rests directly on the seafloor. Landers are useful when you want measurements or imagery close to the seabed without needing a ship on site the whole time. For a low-cost example, take a look at `DORIS <https://bluerobotics.com/doris/>`_ from Ocean Discovery League, which is being developed as a more accessible deep-ocean research and imaging system.

Moving
================
Non-steerable
-------------------
The simplest moving platform is a drifter. A drifter usually stays at the surface or near-surface, follows the motion of the water, and reports its position at regular intervals. That makes drifters useful for studying currents, tracking transport pathways, or simply seeing where the water goes. For a low-cost and open-source example, see `Maker Buoy <https://www.makerbuoy.com/>`_. For a more established commercial example, the `CLS MARGET-II Argos-GPS drifter <https://telemetry.groupcls.com/argos-solutions/argos-products/tracker-beacons/mar-ge-t/#technical-specifications>`_ shows the kind of dedicated drifting beacon used in operational and environmental monitoring. A fun ultra-low-cost example is `this <https://www.onelessbottle.org/oceantracking/>`_ project, where they used a simple water bottle as a drifter.

A float is a device that monitors the water column by changing its buoyancy, allowing it to move up and down without any steering capability. Floats are different from drifters because they are designed to profile the water column rather than just follow the surface flow. Probably the best example of standardization in oceanography is the `Argo program <https://en.wikipedia.org/wiki/Argo_(oceanography)>`_, where much of the hardware, operation, and data handling has been standardized.
A French team has designed a low-cost float `here <https://github.com/ThomasLeMezo/seabot/tree/master>`_.

.. image:: /images/argo.jpg

Steerable
------------------------
Surface Vehicles
============================
Steerable surface platforms are usually called USVs, or Uncrewed Surface Vehicles. The simplest version is basically an autonomous boat: a floating vehicle with its own propulsion, navigation, communications, and control system. There are now many companies and research groups working on USVs in very different sizes, from small low-cost research boats to large long-endurance industrial platforms. For an open-source example, see the `Aqualink ASV project <https://github.com/aqualinkorg/asv>`_.
For an educational and student-focused example of long-endurance surface robotics, `Educational Passages <https://educationalpassages.org/>`_ is also worth a look.

Some USVs go a step further and harvest part of their propulsion energy from the environment rather than relying only on batteries or fuel. They may use wave motion, wind, or a hybrid approach to extend endurance and reduce power consumption. Examples include `Waveglider <https://www.liquid-robotics.com/wave-glider/how-it-works/>`_, `Autonaut <https://www.autonautusv.com/>`_, `Saildrone <https://www.saildrone.com/>`_, and my favorite is the super robust and well-designed autonomous sailboat `SailBuoy <http://www.sailbuoy.no>`_. These platforms are especially interesting when you need long missions at the surface with persistent communications and relatively low operating cost.

.. image:: /images/sailbuoy.jpg

Subsea vehicles
============================
Tethered
-------------------
An ROV (Remotely Operated Vehicle) is probably one of the best-known types of ocean platforms, often described as an underwater drone. Because ROVs are connected to a surface ship or platform by a tether, they can achieve precise localization and stable hovering. This makes them ideal for tasks that require high precision, such as offshore construction, equipment inspection, and underwater repairs.


.. image:: /images/bluerov.jpg

Untethered
-------------------------
These are called Autonomous Underwater Vehicles or AUVs. AUVs usually have one or more propellers and some kind of acoustic navigation system. They are often used for missions lasting from a few hours to about a week, where the goal is to cover a relatively large area with good control and precision.

.. image:: /images/auv.jpg

There are quite a few educational and open AUV projects, a few of which are listed below:

* `OSRF LRAUV <https://github.com/osrf/lrauv>`_
* `The MIT Sea Scout <https://oceanai.mit.edu/pavlab/pdfs/proj_seascout.pdf>`_
* `CPSdrone AUV <https://youtu.be/h1Fw6ZvO_h4?si=z4zoR22lJLV2wuVB>`_


The `OSRF LRAUV project <https://github.com/osrf/lrauv>`_ is especially worth a look. It focuses on simulation and software around MBARI's long-range AUV platform, and they seem to be onto something. Even if we are not building that exact vehicle, there is a lot to learn from how openly they share models, plugins, examples, and documentation.


A glider is usually considered a type of AUV, but it behaves quite differently from a propeller-driven vehicle. The main differences are that:

- It operates autonomously for long periods
- It moves forward by repeatedly climbing and diving through the water column in a sawtooth pattern
- It usually has very long endurance, often on the order of months
- It can cover extremely large distances, including basin-scale missions
- It is quite slow, typically around 1 knot


An underwater glider works on a similar principle to an airborne glider, except that the surrounding medium is water. Like an air glider, it has no propeller for continuous forward thrust. The key trick is that it changes its buoyancy to alternate between descending and ascending. Because the vehicle is designed to be very close to neutrally buoyant, a relatively small change in volume is enough to make it slightly heavier or lighter than the surrounding water. That change in buoyancy, together with the wings, produces the slow gliding motion through the water column.

The volume change is usually produced by a piston pump or an external oil bladder. Pitch is often controlled by moving a large internal mass, commonly the battery pack. By shifting that mass fore and aft the glider changes pitch, and by rotating it the glider can roll and steer toward a desired heading.

There is a partial vacuum inside the glider. This serves a few purposes: 

- It helps pull seals and joints together, which improves sealing
- By monitoring the internal pressure, we can detect leaks early
- It can reduce the energy needed to draw oil from an external bladder back into the vehicle

.. image:: /images/parts.png

Resources
==============

- `ROV Planet buyer's guide <https://www.rovplanet.com/orp-buyers-guide-09-04-2026>`_: A useful yearly overview of commercially available ocean technology.
- `Spotter buoy <https://www.sofarocean.com/products/spotter>`_: A modern commercial surface buoy for real-time wave and surface measurements.
- `DORIS <https://bluerobotics.com/doris/>`_: A low-cost deep-ocean research and imaging lander project from Ocean Discovery League.
- `Maker Buoy <https://www.makerbuoy.com/>`_: A low-cost open-source drifter example.
- `CLS MARGET-II Argos-GPS drifter <https://telemetry.groupcls.com/argos-solutions/argos-products/tracker-beacons/mar-ge-t/#technical-specifications>`_: An example of a commercial drifting beacon used in environmental monitoring.
- `One Less Bottle ocean tracking project <https://www.onelessbottle.org/oceantracking/>`_: A very low-cost drifter concept based on a simple water bottle.
- `Argo program <https://en.wikipedia.org/wiki/Argo_(oceanography)>`_: A major standardized float program for profiling the global ocean.
- `Seabot <https://github.com/ThomasLeMezo/seabot/tree/master>`_: A low-cost float project developed by a French team.
- `Aqualink ASV project <https://github.com/aqualinkorg/asv>`_: An open-source autonomous surface vehicle project.
- `Educational Passages <https://educationalpassages.org/>`_: Student-focused long-endurance surface robotics projects and programs.
- `Waveglider <https://www.liquid-robotics.com/wave-glider/how-it-works/>`_: A commercial wave-powered surface vehicle.
- `Autonaut <https://www.autonautusv.com/>`_: A long-endurance autonomous surface vehicle that harvests wave energy.
- `Saildrone <https://www.saildrone.com/>`_: A widely used long-endurance uncrewed surface vehicle platform.
- `SailBuoy <http://www.sailbuoy.no>`_: A robust autonomous sailboat for long-duration ocean observations.
- `OSRF LRAUV <https://github.com/osrf/lrauv>`_: An open project focused on software and simulation for long-range AUVs.
- `The MIT Sea Scout <https://oceanai.mit.edu/pavlab/pdfs/proj_seascout.pdf>`_: An educational AUV project and reference.
- `CPSdrone AUV <https://youtu.be/h1Fw6ZvO_h4?si=z4zoR22lJLV2wuVB>`_: A video reference for an open or educational AUV effort.

    