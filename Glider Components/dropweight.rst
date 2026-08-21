Drop weight
+++++++++++++++++

This is a useful mechanism to have when something major like the buoyancy engine has failed or glider has gone totally dark because of a power loss. This should be a standalone system with its own separate power source that listens for a heartbeat signal from the glider. When this weight is released however, the glider can not dive anymore and it will just drift on the surface until recovered.
Slocum has one of these and I believe so does the Seaexplorer. Seaglider doesn't come with one however. I believe the reasoning behind this decision was that UW often deploys their gliders in extremely remote areas such as the Southern Ocean. In this case if a glider releases its weight by mistake, it's certainly a lost glider because it would cost more money (more than for a new glider) to arrange a recovery! 

.. image:: /images/DropWeight.jpg
    :width: 400

Implementation in Tuba
--------------------------------
In our design, we can make use of a `Nichrome burn wire mechanism <https://esmats.eu/amspapers/pastpapers/pdfs/2012/thurn.pdf>`_ used for CubeSats.

Currently, nothing is implemented in Tuba for this subsystem.

