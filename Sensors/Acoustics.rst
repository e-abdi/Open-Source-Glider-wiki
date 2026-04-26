Acoustics
+++++++++++++++++++++++++

Electromagnetic waves are severely attenuated in salt water, so sound is the main tool for underwater communication, navigation, and object detection. For a deeper introduction to underwater acoustics, take a look at `DOSITS <https://dosits.org/>`__. `Blue Robotics <https://bluerobotics.com/learn/a-smooth-operators-guide-to-underwater-sonars-and-acoustic-devices/>`__ also has a practical guide to common acoustic devices. `This NOAA resource <https://www.fisheries.noaa.gov/national/science-data/sounds-ocean-mammals>`__ is another good overview of sounds in the ocean and marine mammals.

`This paper <https://www.frontiersin.org/journals/remote-sensing/articles/10.3389/frsen.2023.1106533/full>`__ looks at the use of gliders for acoustic monitoring in the ocean.

.. image:: /images/acoustics.jpg
	:alt: Acoustic soundscape

Passive
==============

Hydrophones
---------------

A hydrophone is basically a microphone encapsulated in resin, ideally with an acoustic impedance close to that of water.
The sensing element itself can be simple. Although sensitivity varies greatly, you can build a basic hydrophone with a piezoelectric ceramic element and suitable potting material. The difficult part is the analog front end, signal conditioning, and calibration. In commercial units, calibration is often a large part of the cost. We may not need that level of absolute accuracy for an open-source glider, but it is still useful to understand the options that already exist.

`Here <https://www.cetaceanresearch.com/hydrophone-systems/index.html>`__ is a selection of relatively low-cost passive acoustic monitoring systems. `The IQOE Task Team on Low-Cost Hydrophones for Research, Education, and Citizen Science <https://www.iqoe.org/groups/task-team-low-cost-hydrophones-research-education-and-citizen-science>`__ is another useful resource.
`Here <https://www.aquarianaudio.com/as-1-hydrophone.html>`__ is another fairly low-cost and popular hydrophone element.

Ocean Sonics
^^^^^^^^^^^^^^^^^^^^^^^^^^

Their icListen hydrophones have some nice capabilities. The hydrophone itself provides a web interface where you can view a live spectrogram, change settings, and download files. They also support simple onboard detection, so you can trigger an alert when sound levels in a chosen frequency band exceed a threshold. I have integrated this hydrophone on a Seaglider and designed a board to send detection events, along with a text representation of spectrogram activity, back to shore after each surfacing.

They are also a good choice for fixed moorings. With a low-power GSM modem, you can maintain a direct connection to a hydrophone deployed a few kilometers from shore.

The downside is cost, especially compared to something like a SoundTrap.

SoundTrap
^^^^^^^^^^^^^^^^^^^^^^^^

They make well-designed and relatively affordable hydrophones. I can definitely recommend them. I have not used one on a glider yet, but integrating one should be fairly straightforward.

Jasco
^^^^^^^^^^^^^^^^^^^^^^^^

They offer some of the most advanced, and also the most expensive, hydrophone systems, such as the `Ocean Observer <https://www.jasco.com/oceanobserver>`__.

.. image:: /images/jasco.png
	:alt: JASCO Ocean Observer system

DMON
^^^^^^^^^^^^^^^^^^

A neat system developed by Mark Baumgartner at WHOI for autonomous detection and classification of marine mammals. You can find more information `here <https://robots4whales.whoi.edu/>`__. There also appears to be a commercial version called `DMON2 <https://apps.dtic.mil/sti/pdfs/AD1013952.pdf>`__.

.. image:: /images/dmon.jpg
	:alt: WHOI DMON marine mammal detector


Directional sensors
--------------------

Hydrophones are usually omnidirectional, so if you want a bearing to the sound source you either need something like a `vector sensor <https://dosits.org/galleries/technology-gallery/basic-technology/vector-sensors/>`__ or you need multiple hydrophones. Vector sensors are difficult to obtain because of their military applications. You can find more information about measuring directivity `here <https://repository.oceanbestpractices.org/server9/api/core/bitstreams/9b9f72bb-2368-4429-978f-fa0778d4fbb8/content>`__.
To localize a source in three dimensions, you need at least four hydrophones. SeaExplorer seems to have a pretty nice array integrated. There have been some efforts to integrate multiple hydrophones on both Seaglider and Slocum to achieve directionality as well. I have even heard of people considering a towed array from gliders to lower the noise floor, but that sounds a bit risky.

.. image:: /images/array.png
	:alt: Hydrophone array SeaExplorer glider

Active
==================

Echo-sounder
--------------

An echo-sounder is the ocean's version of echolocation. It sends sound pulses into the water and listens for the echoes that bounce back. By measuring the return time, it can estimate depth or detect targets in the water column.

Scientific echosounders do much more than measure depth. They are used to map the seafloor, track fish, study plankton, and observe bubbles or layers of water with different acoustic properties.

The EK80 echosounder, which is the industry standard for scientific research, has been integrated on both Seaglider and Slocum platforms and is also being integrated on SeaExplorer gliders.


.. image:: /images/ek80.png
	:alt: EK80 scientific echosounder


`This project <https://www.youtube.com/@Neumi>`__ is working toward a low-cost open-source version.


Multibeam
--------------------

A multibeam system is a more capable version of an echo-sounder. Instead of sending a single pulse straight down, it transmits a fan of beams across the seafloor. That allows it to cover a wide swath in one pass. Scientists use multibeam systems to create detailed 3D maps of the seabed. They are very power-hungry and require accurate positioning, so they are generally not suitable for gliders.

`This project <https://hforsten.com/homemade-polarimetric-synthetic-aperture-radar-drone.html>`__ could be useful in the future as inspiration for creating an open-source multibeam system.

Side-scan sonar
--------------------

Side-scan sonar is like giving the seafloor a sideways glance. Instead of looking straight down, it sends sound waves to the sides. It does not measure depth directly, but it produces a detailed image of seafloor texture and objects lying on it. A transducer array sends and receives acoustic pulses while the system is towed behind or beneath a vessel at a roughly constant speed. The returned echoes are then reconstructed into an image using bright and dark regions. This is mainly used to cover large areas relatively quickly and inexpensively when looking for specific features such as shipwrecks.


Sub-bottom profiler
---------------------------

A sub-bottom profiler sends sound pulses into the seabed. Instead of reflecting only from the surface, some of that energy penetrates below it. The returning echoes reveal different subsurface layers of mud, sand, rock, and other buried structures.

This is not typically a glider payload, but the fact that gliders can operate close to the seafloor could, in theory, make such measurements more efficient.

ADCP
----------------

An ADCP, short for Acoustic Doppler Current Profiler, is like a speed radar for ocean currents. It sends out sound waves and measures how they bounce off tiny particles in the water. Thanks to the Doppler effect, it can estimate how fast the water is moving, in which direction, and at different depths.

ADCPs have been integrated on all major glider platforms, but interpreting data collected from a moving underwater vehicle is challenging.

SeaExplorer seems to have a good solution for the data analysis. From what I understand, they use the shear method explained in `this paper <https://journals.ametsoc.org/view/journals/atot/19/5/1520-0426_2002_019_0794_dvpula_2_0_co_2.xml>`__.
For Slocum, there are a few packages on GitHub such as `this one <https://github.com/JGradone/Slocum-AD2CP>`__.
UW has its own solution for this, but it is not shared publicly. I also found `this project <https://github.com/callumrollo/adcp-glider>`__ on GitHub.
`This paper <https://journals.ametsoc.org/view/journals/atot/34/2/jtech-d-16-0156.1.xml>`__ explains how this was done using Spray gliders.

.. image:: /images/adcp.png
	:alt: ADCP concept on gliders

DVL
--------------------

This stands for Doppler Velocity Log. It uses the Doppler shift to keep track of the speed and direction of an underwater vehicle relative to a solid boundary such as the seafloor. A team at WHOI has tried using this for under-ice navigation.


.. image:: /images/dvl.png
	:alt: DVL illustration

Acoustic modems
--------------------

Acoustic modems are used for communication between two underwater nodes. They are generally low-bandwidth and relatively short-range, but they can be useful, for instance, for downloading data from an underwater mooring using a glider.

.. image:: /images/modem.png
	:alt: Acoustic modem slocum glider
	:width: 400

`This modem from WHOI <https://acomms.whoi.edu/micro-modem/>`__ seems to be a nice fit for gliders.


Real-time Detection
=====================
The ability to process acoustic data in real time and detect specific acoustic events is a key goal in underwater sensing. Systems capable of identifying sounds in a way similar to `Merlin Bird ID <https://merlin.allaboutbirds.org/>`__, but for marine environments, would enable more efficient data collection, event-driven sampling, and adaptive mission behavior.

Recent advances in machine learning are making this increasingly feasible. Projects such as `NatureLM Audio Demo <https://huggingface.co/spaces/MBZUAI/NatureLM-audio>`__ demonstrate the potential of large-scale audio models for detecting and classifying biological sounds across environments.

.. image:: /images/acousticdetection.jpg
	:alt: Acoustic detection glider

Doing this in near-real-time on low-power hardware is the next goal. `This low-cost DIY project <https://github.com/IQTLabs/AISonobuoy/tree/main/Hydrophone>`__ is a good example of an effort in that direction.

Resources
==============

General acoustics
------------------

- `DOSITS <https://dosits.org/>`__: A strong general introduction to underwater acoustics and ocean sound.
- `Blue Robotics guide <https://bluerobotics.com/learn/a-smooth-operators-guide-to-underwater-sonars-and-acoustic-devices/>`__: A practical overview of common underwater sonar and acoustic devices.
- `NOAA sounds in the ocean resource <https://www.fisheries.noaa.gov/national/science-data/sounds-ocean-mammals>`__: A useful overview focused on ocean sound and marine mammals.
- `Gliders for acoustic monitoring paper <https://www.frontiersin.org/journals/remote-sensing/articles/10.3389/frsen.2023.1106533/full>`__: A paper describing the use of gliders for acoustic monitoring in the ocean.

Hydrophones and passive monitoring
-----------------------------------

- `Cetacean Research hydrophone systems page <https://www.cetaceanresearch.com/hydrophone-systems/index.html>`__: A selection of relatively low-cost passive acoustic monitoring systems.
- `IQOE low-cost hydrophones task team <https://www.iqoe.org/groups/task-team-low-cost-hydrophones-research-education-and-citizen-science>`__: A useful resource on low-cost hydrophones for research, education, and citizen science.
- `Aquarian Audio AS-1 <https://www.aquarianaudio.com/as-1-hydrophone.html>`__: A fairly low-cost and popular hydrophone element.
- `Nauta RCS <https://www.nauta-rcs.it/wp/>`__: A company based in Italy manufacturing low-cost acoustic devices.
- `JASCO Ocean Observer <https://www.jasco.com/oceanobserver>`__: An example of a high-end hydrophone and passive acoustic monitoring system.
- `WHOI DMON project <https://robots4whales.whoi.edu/>`__: Information about the DMON system for autonomous detection and classification of marine mammals.
- `DMON2 reference <https://apps.dtic.mil/sti/pdfs/AD1013952.pdf>`__: A reference describing the DMON2 system.

Directional sensing
--------------------

- `DOSITS vector sensors page <https://dosits.org/galleries/technology-gallery/basic-technology/vector-sensors/>`__: A short introduction to vector sensors for bearing estimation.
- `Directivity measurement reference <https://repository.oceanbestpractices.org/server9/api/core/bitstreams/9b9f72bb-2368-4429-978f-fa0778d4fbb8/content>`__: More information about measuring acoustic directivity.

Active acoustics
-----------------

- `Neumi open-source echosounder project <https://www.youtube.com/@Neumi>`__: A low-cost open-source echosounder effort.
- `ThinkSensor products <https://www.thinksensor.com/products>`__: This seems to be another source for low-cost echosounder.
- `Homemade polarimetric synthetic aperture radar drone project <https://hforsten.com/homemade-polarimetric-synthetic-aperture-radar-drone.html>`__: A useful source of ideas for a future open-source multibeam system.

Current profiling and glider processing
----------------------------------------

- `Shear method paper <https://journals.ametsoc.org/view/journals/atot/19/5/1520-0426_2002_019_0794_dvpula_2_0_co_2.xml>`__: A paper relevant to ADCP data analysis from moving platforms.
- `Slocum AD2CP project <https://github.com/JGradone/Slocum-AD2CP>`__: A GitHub project for working with ADCP data from Slocum gliders.
- `ADCP glider project <https://github.com/callumrollo/adcp-glider>`__: Another open GitHub project for glider ADCP processing.
- `Spray glider ADCP paper <https://journals.ametsoc.org/view/journals/atot/34/2/jtech-d-16-0156.1.xml>`__: A paper explaining ADCP processing on Spray gliders.

Acoustic modems and detection
------------------------------

- `WHOI Micro-Modem <https://acomms.whoi.edu/micro-modem/>`__: An acoustic modem that looks like a good fit for gliders.
- `Acoustic modem in gliders paper <https://www.mdpi.com/1424-8220/25/3/849>`__: An interesting paper on use of acoustic modem in gliders.
- `NatureLM Audio Demo <https://huggingface.co/spaces/MBZUAI/NatureLM-audio>`__: A demonstration of a large-scale audio model for detecting and classifying biological sounds.
- `AISonobuoy hydrophone project <https://github.com/IQTLabs/AISonobuoy/tree/main/Hydrophone>`__: A low-cost DIY project aimed at near-real-time acoustic detection on low-power hardware.

Software and reference tools
-----------------------------

- `Bioacoustics Stack Exchange <https://bioacoustics.stackexchange.com/questions>`__: A great forum for bioacoustic-related questions.
- `AudioMoth <https://www.openacousticdevices.info/audiomoth>`__: An open-source acoustic recorder.
- Some useful tools for working with acoustic files: `PAMGuard <https://www.pamguard.org/>`__, `Audacity <https://www.audacityteam.org/>`__, `Spek <https://www.spek.cc/>`__, and `Praat <https://www.fon.hum.uva.nl/praat/>`__.
- `SPL calculator <https://sengpielaudio.com/calculator-soundlevel.htm#top>`__: A handy reference for converting and comparing sound pressure level values.
