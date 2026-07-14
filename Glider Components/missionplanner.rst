Mission Planner
++++++++++++++++++++++++

One of the key advantages of basing our system design on Seaglider is that its piloting and visualization tool is open-source and available on `GitHub <https://github.com/iop-apl-uw/basestation3>`_. This means we can integrate our system into it without needing to develop something from scratch.


.. image:: /images/missionplanner.png
 

SeaExplorer has a proprietary web tool called Glimpse.

.. image:: /images/glimpse.png


Slocums have another proprietary tool called SFMC.

.. image:: /images/sfmc.png


Other command and control platforms
====================================

Beyond the vendor-specific tools above, there are broader command and control frameworks worth knowing about, especially for operating multiple vehicle types from a single interface.

`Neptus <https://github.com/LSTS/neptus/tree/develop>`_ is an open-source command and control infrastructure developed by the LSTS lab at the University of Porto. It supports mission planning, real-time monitoring, and control of marine vehicles through a modular, plugin-based desktop application, and is part of the wider LSTS toolchain.

`This paper <https://www.frontiersin.org/journals/marine-science/articles/10.3389/fmars.2020.00397/full>`_ describes Oceanids C2, a unified web-based infrastructure for piloting long-range marine autonomous systems used by the UK's National Marine Equipment Pool. It aims to provide a single control interface and standardized data management across different vehicle types, and is a useful reference for thinking about how to unify piloting and data delivery.

