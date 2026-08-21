Variable Buoyancy Device
++++++++++++++++++++++++
As the name suggests, this part of the glider changes the vehicle's buoyancy, allowing it to dive or climb through the water column. In practice, it does this by changing the glider's volume and therefore its overall density relative to the surrounding water.


Piston Design
------------------
This is basically a large piston that displaces seawater to create a buoyancy change. The design is mechanically simpler and usually achieves volume displacement quickly, but it becomes less efficient as depth increases. For that reason, it is generally used for gliders down to around 200 m, while deeper-diving designs usually use a bladder system.

For our design, we will focus on this approach first because it is the simpler option. The current idea is to use the strongest linear actuator we can get our hands on, and if that is still not enough, we can experiment with the motor and gearbox to increase the available force.

In Slocum, they use a 90-watt motor and a rolling diaphragm to achieve this.

Rolling Diaphragm
************************

A rolling diaphragm is a type of seal in which most of the pressure is supported by the piston head, while only a very small amount of pressure is exerted on the narrow convolution between the piston and cylinder. Compared with a conventional piston seal, this has several advantages, which is why it is often the preferred approach. In a piston seal, tolerances are much more critical and lubrication is usually necessary, so it is not an ideal fit for this application.

This will probably be the most difficult and critical part of the whole build to get right. Commercial gliders commonly use EPDM, but we will try silicone first because it is much more accessible and easier to work with.

.. image:: /images/rollingdiaphragm.png

Bladder Design
-------------------
At the surface, a normally closed solenoid valve is opened and oil is drawn into the pressure hull. This reduces the displaced volume and makes the glider denser than the surrounding water, so it dives. When the glider reaches the desired depth, it pumps oil back out into the external bladder. That increases the displaced volume again and causes the glider to climb through the water column.

The main issue with this approach is finding a reliable pump. One option worth testing is `this small hydraulic pump <https://huinaconstructiontoys.com/products/8mpa-mini-hydraulic-pump-high-pressure-for-kabolite-336-966-huina-1580-ec160e-rc-excavator-bulldozer-upgrade-parts?pr_prod_strat=use_description%E2%89%BArec_id%3D4eb47c173%E2%89%BArec_pid%3D7790484259035%E2%89%BAref_pid%3D7790484291803%E2%89%BAseq%3Duniform>`_. For the bladder itself, an accumulator bladder could be used just as in commercial gliders.

.. image:: /images/BladderDesign.png

Implementation in Tuba
--------------------------------
Currently, the VBD in Tuba is implemented using a custom silicone rolling diaphragm made with 3D-printed molds, and could potentially be printed directly in silicone using `Filament2 <https://www.filament2.com/>`_ on a Prusa XL, driven by a simple linear actuator. One of the main design challenges was achieving a reliable seal between the diaphragm and the housing. This was addressed with a large snap ring that applies uniform pressure across the diaphragm, combined with silicone adhesive. Pulling a partial vacuum then does the rest of the work, tightening the seal even further.

The next step is to add a gearbox to the linear actuator motor. This should allow lower operating speeds while providing substantially more force.

.. image:: /images/Tuba_VBD.png

