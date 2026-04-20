Battery
+++++++++++++++++

It's important to remember that one of the most important properties of gliders is their endurance.
Therefore power output is not as important as energy density and safety.
Also it usually is a nightmare to ship large lithium packs therefore a pack design that can be easily filled up with cells at the deployment country is highly desired.



Lithium Primary
================
Generally has around twice volumetric energy density compared to rechargeable options so this is the preferred option for long deployments.
The popular cells in marine domain (at least ones more accessible in EU) are Saft specifically the LS33600 and LSH20 cells.  
Both Seagliders and Slocums use Electrochem cells in their packs. 


Lithium Rechargeable
====================

Both Slocum and SeaExplorer offer rechargeable batteries, which is quite convenient for certain types of operation. 
I have also created a custom rechargeable pack for Seagliders which was convenient for doing short tests.

We will base the design around the popular 18650 cells for now and will explore primary batteries for longer endurance at a later stage.

Implementation in Tuba
=================================

We are currently using a custom 4s9p pack made with Panasonic NCR18650 cells and this `BMS <https://enepaq.com/product/battery-management-system-bms-30a-set-tinybms-s516/>`_. It has an ignition key that is used to power the glider up with a shorting plug. It also has a Bluetooth connection for monitoring the cells.

