Pressure Hull
+++++++++++++++++

The Seaglider pressure hull is made from several pieces of machined 6061 aluminium, whereas Slocum uses carbon-fiber hulls.

Carbon-fiber composites are generally not especially well known for their compressive strength. They perform best in tension, as in aircraft structures that are pressurized from the inside. Read `this paper <https://www.mdpi.com/2077-1312/10/10/1456>`_ for more information.

Because gliders go through repeated pressure cycles, pressure housings need to be rigorously fatigue-tested and acoustically inspected on a regular basis for cracks. If this is not done properly, it could eventually lead to an implosion similar to the infamous `Titan incident <https://en.wikipedia.org/wiki/Titan_submersible_implosion>`_.

Catastrophic pressure-housing failure may be one possible explanation for some of the more suspicious Slocum disappearances over the years.

SeaExplorer and OceanScout also use aluminium hulls.

Seals
---------------

There are generally two types of seals used in underwater housings: face (or flange) seals and radial (or piston) seals. Again, I will compare Seaglider and Slocum designs here.

Seagliders use a small number of flanges with a single O-ring, whereas Slocums use radial seals with double O-rings and a central tie rod to hold everything together. In my experience, Slocum seals are far more susceptible to leaks than Seaglider seals. This makes sense to me because face seals are generally more forgiving and easier to maintain.

I have deployed Seagliders with significant flange damage and, in general, as long as the glider holds a vacuum in the lab, there will not be a leak at sea. Slocums, on the other hand, may also hold a vacuum in the lab, but if the O-ring installation is not done perfectly, or if there is even a slight scratch on the sealing surface, there may still be a leak at depth.

Because of this, Slocums experience leaks regularly, and there are even leak-detection sensors in different sections to determine whether water has actually entered the vehicle. I have heard that a small amount of water inside is not especially uncommon. There is no equivalent concern in a Seaglider.

My view is that this is partly because, even with a tie rod, a glider still flexes slightly in the real world. Combine that movement with pressure, and it is not hard to end up with some water inside.

.. image:: /images/seals.png

Pressure Relief Valve
-----------------------
This is an important component of any subsea housing that contains batteries. Batteries can produce gas, especially when they fail, which can cause pressure to build up inside a sealed housing. This can be extremely dangerous and may lead to a major explosion. To avoid this, the use of a pressure relief valve is essential. Seagliders use these, but Slocums, for some reason, do not.

.. image:: /images/pressure_relief.jpg


Current Implementation in Tuba
--------------------------------

Tuba currently uses two 5-inch Blue Robotics aluminium pressure hulls, joined together using external brackets and six threaded rods. The new `coupler flange <https://bluerobotics.com/store/watertight-enclosures/locking-series/coupler-flanges/>`_ will be extremely useful once they release a 5-inch version.

Blue Robotics also offers a `cost-effective pressure relief valve <https://bluerobotics.com/store/watertight-enclosures/enclosure-tools-supplies/prv-m10-asm/>`_, which we are using.