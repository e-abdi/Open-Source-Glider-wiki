Battery
+++++++++++++++++

It's important to remember that one of the most important properties of gliders is their endurance.
Therefore power output is not as important as energy density and safety.


Certification and Shipping
===========================

Certifying a large battery pack (e.g. UN38.3) is hard and expensive. Certification bodies require several physical samples of the exact pack to be crushed, dropped, punctured, and otherwise destroyed during testing. For a large custom pack, building and sacrificing that many samples is a significant capital investment on its own, before any of the glider work even starts.

A common way around this is to build the large pack out of smaller packs that are already certified. This is what Teledyne does with the Slocum's rechargeable packs, which are assembled from many smaller rechargeable packs, likely ones already certified and used in their other products. Reusing an existing certified sub-pack avoids re-running destructive certification on a new large-format design.

Shipping is a related headache. Large lithium packs are regulated as hazardous goods, need to be packaged according to that regulation, and typically require the shipper to be Hazmat certified to pack and ship them. This makes it important to stay flexible: a pack design that can be shipped as separate, unregulated (or less regulated) cells and assembled at the deployment country is highly desirable, rather than shipping a single large certified pack internationally.

The best approach we've come up with so far is a custom battery holder, where the user buys the standard cells locally and installs them into the holder themselves rather than receiving a pre-built pack. This sidesteps both the certification and shipping problems, but making such a holder mechanically and electrically reliable (good contacts, vibration/shock resistance) is the real engineering challenge.


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

