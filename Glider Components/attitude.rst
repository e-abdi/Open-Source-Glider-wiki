Attitude control
++++++++++++++++++++++++++

To control the vehicle's pitch, all gliders move the battery, usually the heaviest item inside, forward and aft to pitch the vehicle down or up respectively. Both Seagliders and SeaExplorers also rotate the battery clockwise or anticlockwise to achieve port and starboard roll.

In the case of Slocums, the change in heading is achieved by a rudder, which changes the glider's yaw. Although the rudder is magnetically coupled to an internal rotor, it still counts as an external moving part. The advantage of this method is that it is more responsive and manoeuvrable because it can take sharper turns, but that comes with the disadvantage of introducing an external control surface that can malfunction after months of operation at sea, as does occasionally happen in practice, resulting in the complete loss of steering authority.

.. image:: /images/attitude.png

Current Implementation in Tuba
--------------------------------
In the current Tuba implementation, pitch control is achieved by moving the battery pack along a simple T8 lead screw, driven by a geared DC motor. For roll control, the system uses `this planetary gearset <https://www.thingiverse.com/thing:4655373>`_, driven by a second geared DC motor.
