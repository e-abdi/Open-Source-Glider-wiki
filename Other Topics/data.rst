Data Management
+++++++++++++++++++++

Data management is perhaps one of the most overlooked aspects of open-source glider projects from an engineering perspective — but arguably the most important to get right. Without `FAIR data <https://www.go-fair.org/fair-principles/>`_ (Findable, Accessible, Interoperable, Reusable), nothing else matters: the hardware can work perfectly, the sensors can be well-calibrated, and the missions can be executed flawlessly, but if the data cannot be found, understood, or reused by others, the scientific value is severely limited.

Although there are many ongoing efforts to improve the standardization and interoperability of glider data, we are not there yet — meaning data coming directly out of the instrument is not in the agreed standard format. Every glider, and every oceanographic instrument more broadly, tends to produce its own version of output data, so some post-processing is needed to convert it into a community-agreed format. That format is currently `OG1 <https://oceangliderscommunity.github.io/OG-format-user-manual/OG_Format.html>`_, and contributing towards it is what this project is aiming for.
The goal here is to follow the FAIR principles together with the existing efforts and standards listed below to help improve the open data format and visualization tools together with the community.

* `OceanGlider's glider tools list <https://github.com/OceanGlidersCommunity/glider-tools-list>`_
* `OceanGliders OG Format <https://oceangliderscommunity.github.io/OG-format-user-manual/OG_Format.html>`_
* `OceanGliders Controlled Vocabulary <https://oceangliderscommunity.github.io/OG-format-user-manual/vocabularyCollection/tableOfControlledVocab.html>`_
* `OceanSITES <https://goosocean.org/who-we-are/observations-coordination-group/global-ocean-observing-networks/oceansites/>`_
* `SeaDataNet data management protocols for glider data <https://repository.oceanbestpractices.org/bitstream/handle/11329/2118/Seadatanet%20data%20management%20protools.pdf?sequence=4&isAllowed=y>`_
* `ERDDAP <https://github.com/ERDDAP/erddap>`_
* `GANDALF-US AUV network piloting and data management tool <https://gandalf.gcoos.org/about/gandalf>`_
