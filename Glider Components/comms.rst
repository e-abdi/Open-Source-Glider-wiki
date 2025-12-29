Communication
+++++++++++++++++++++++

Electromagnetic waves don't do well in water. Most frequencies attenuate rapidly after a few centimeter of water, especially salt water. However, if you are in freshwater and using quite low frequencies, you could get your signal down to a few meters. I have heard of the hobby submarine community operating their RC subs down to 10m or so in freshwater. Although this might have interesting applications down the line, from here on, we will be either talking about electromagnetic based communication when glider is at surface, or acoustic communication when glider is underwater.  
It's very important to communicate efficiently in the oceans because communication is expensive both in terms of money and power budget. Here is another point where Seaglider has a far better design than Slocum. Seaglider kbytes transferred for a similar mission is many times smaller than that of Slocum. I think we can do even better than Seaglider in our design.

Iridium
=======================

The go-to communication method of extremely remote areas, since Iridium has a pole to pole coverage. A marvel of engineering for its time and with a crazy story of how all of its satellites almost got shot down by rockets!
I definitely recommend checking out the book  `Eccentric Orbits: The Iridium Story <https://a.co/d/aCnYIyf>`_.


SBD vs Rudics
------------------------

SBD is simple packet-based service which doesn't need a SIM card and it's mostly used for global asset tracking like containers. You can use this for transferring small amount of data.
Iridium is a circuit switched data transfer method used for sending larger data. All gliders except for the OceanScout use this method. It's more reliable but it comes with a higher cost and more power consumption.

Security
-------------

Iridium comms are not secure. A group in Germany has decoded the data and published their tool online! Listen to their very interesting talk `here <https://youtu.be/JhJT7Cvh6NE?si=9_wxUTpdEPtfm7ry>`_.

FreeWave
===============

Slocum gliders use this proprietary RF communication system for short range communication (a few kilometers).

Argos
===============

Another constellation used mostly for animal tracking but used on gliders as a backup system. The localization method is based on doppler effect so it's quite low accuracy but a good last resort! The new generation of trackers actually use GPS for more location accuracy and actually use the satellites for data transmission. Apparently you can even sent a few more bytes alongside the GPS lines which could be interesting in our case! but haven't tried this yet.

LoRa
===========
This is definitely something to explore especially in the DIY glider space, since this protocol is designed for extremely long range, low bandwidth and low power applications, so fits gliders perfectly! You will just need to install a gateway that can cover the area you will operate at, possibly on a high building or a mountain near the sea and you can have a pretty decent coastal coverage. 
There are now satellites that use LoRa for downlinks, and `TinyGS <https://tinygs.com/>`__ is a community-driven global network of ground stations that receive those LoRa satellite transmissions. 

GSM
==============

For coastal application within a few kilometers from the shore, GSM should suffice. We will explore this option first since it's much more readily accessible.

Antennas
=================

GPS and Iridium use very similar frequency range so commercial gliders use a single antenna for both with a RF switch to select which device is currently using the antenna.
