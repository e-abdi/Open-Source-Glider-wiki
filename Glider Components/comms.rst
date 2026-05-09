Communication
+++++++++++++++++++++++

Electromagnetic waves do not travel well in water. Most frequencies attenuate rapidly after just a few centimeters, especially in salt water. However, in freshwater and at quite low frequencies, it is possible to get a signal down to a few meters. I have heard of hobby submarine groups operating their RC subs down to around 10 m in freshwater. Although that might have interesting applications down the line, from here on we will focus on electromagnetic communication when the glider is at the surface, and acoustic communication when it is underwater.  
It is very important to communicate efficiently in the ocean because communication is expensive in both money and power budget. This is another area where Seaglider has a much better design than Slocum. The number of kilobytes transferred by Seaglider for a similar mission is many times smaller than that of Slocum.

Iridium
=======================

The go-to communication method for extremely remote areas, since Iridium has pole-to-pole coverage. It was a marvel of engineering for its time, and it has a wild history in which its satellites nearly got shot down by rockets.
I definitely recommend checking out the book `Eccentric Orbits: The Iridium Story <https://a.co/d/aCnYIyf>`_.


SBD vs Rudics
------------------------

SBD is a simple packet-based service that does not need a SIM card, and it is mostly used for global asset tracking applications such as containers. You can use it to transfer small amounts of data.
RUDICS is a circuit-switched data transfer method used for sending larger volumes of data. All gliders except the OceanScout use this method. It is more reliable, but it comes with higher cost and power consumption.

Security
-------------

Iridium communications are not secure. A group in Germany decoded the traffic and published their tools online. Their talk is worth watching `here <https://youtu.be/JhJT7Cvh6NE?si=9_wxUTpdEPtfm7ry>`_.

FreeWave
===============

Slocum gliders use this proprietary RF communication system for short-range communication over a few kilometers.

Argos
===============

Another constellation used mostly for animal tracking, but also used on gliders as a backup system. The localization method is based on the Doppler effect, so the accuracy is quite low, but it is still a good last resort. The new generation of trackers uses GPS for better positioning and the satellites for data transmission. Apparently you can even send a few more bytes alongside the GPS lines, which could be interesting in our case, but I have not tried this yet.

LoRa
===========
This is definitely something to explore, especially in the DIY glider space, since this protocol is designed for extremely long-range, low-bandwidth, and low-power applications, which fits gliders very well. You would just need to install a gateway that can cover your operating area, possibly on a tall building or a mountain near the sea, to get fairly good coastal coverage.
There are now satellites that support LoRa links as well. One interesting example is `FOSSA Systems <https://fossa.systems/>`__, which offers low-cost two-way IoT communication over its satellite network.

Cellular
==============

For coastal applications within a few kilometers of shore, cellular protocols should be a practical option. IoT-focused standards such as LTE-M and NB-IoT are especially interesting here, and we will explore this route first because it is much more accessible than satellite links.


Antennas
=================

GPS and Iridium use very similar frequency ranges, so commercial gliders often use a single antenna for both, with an RF switch to select which device is currently connected.


Implementation in Tuba
=================================

We are currently using WiFi for communication. At this stage, we will be on site for all dives, so we do not need communication range beyond WiFi. The next step will be to upgrade this to LTE-M and possibly LoRa.
