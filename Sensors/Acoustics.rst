Acoustics
++++++++++++++++++++++++++

Electromagnetic waves get severely attenuated in salt water so sound is the name of the game for communication, navigation and object detection and characterization underwater. For a fantastic deep dive into the science of sound in the sea I recommend taking a look at `this <https://dosits.org/>`__ website. Also `Blue Robotics <https://bluerobotics.com/learn/a-smooth-operators-guide-to-underwater-sonars-and-acoustic-devices/>`__ has a great guide about acoustics.

`This paper <https://www.frontiersin.org/journals/remote-sensing/articles/10.3389/frsen.2023.1106533/full>`__ looks at the use of gliders for acoustic monitoring of the oceans.

.. image:: /images/acoustics.jpg
	:alt: Acoustic sensing overview

Passive
==============

Hydrophones
---------------

Basically a microphone that's molded inside a resin (preferably) with the same density as that of water. 
The hydrophone element is simple. Although the sensitivity can vary greatly, you can build an extremely simple hydrophone using a piezo ceramic element and some resin around it. What you do with the signal is the important and tricky part! In commercial hydrophones, the most expensive thing you pay for is the calibration. We don't need to worry about that for our purposes here, nevertheless I will go through some of the commercial units I have worked with.

Ocean Sonics
^^^^^^^^^^^^^^^^^^^^^^^^^^

Their icListen hydrophones have some nice capabilities. You will get a web interface for the unit in which you can view the live spectrogram, change settings and download files. You also have some simple detection capability in which you can get a notification when a sound level of your chosen frequency range above a set threshold. I have integrated this hydrophone on a Seaglider and designed a board to transmit back these detection events in addition to a text version of the spectrogram events back to shore after every surfacing. 
They are also a good choice if you want to have a mooring with hydrophones. If you use a low power GSM modem, you can easily have a direct connection to a hydrophone deployed a few kilometers away from the shore like we did `here  <https://www.orcaireland.org/smartwhalesounds>`_.
They are also a good choice if you want to have a mooring with hydrophones. If you use a low power GSM modem, you can easily have a direct connection to a hydrophone deployed a few kilometers away from the shore like we did `here  <https://www.orcaireland.org/smartwhalesounds>`__.

The downside is that they are quite expensive especially compared to something like a SoundTrap. 

SoundTrap
^^^^^^^^^^^^^^^^^^^^^^^^
They make well-designed and relatively affordable hydrophones. I can definitely recommend these. I haven't used these on gliders yet but it should be fairly straightforward to attach one of these to a glider.

Jasco
^^^^^^^^^^^^^^^^^^^^^^^^
They have the most advanced but then also the most expensive hydrophone systems like the `Ocean Observer <https://www.jasco.com/oceanobserver>`__. 

.. image:: /images/jasco.png
	:alt: JASCO Ocean Observer system

DMON 
^^^^^^^^^^^^^^^^^^
A neat system developed by Mark Baumgartner from WHOI for autonomous detection and classification of marine mammals. You can find more info `here <https://robots4whales.whoi.edu/>`__ and there seem to be a commercial version called `DMON2 <https://apps.dtic.mil/sti/pdfs/AD1013952.pdf>`__ soon available.

.. image:: /images/dmon.jpg
	:alt: WHOI DMON marine mammal detector


Hydrophone array
--------------------
Hydrophones are usually omnidirectional so in order to get a bearing on the sound source, you either need to use something like a `vector sensor <https://dosits.org/galleries/technology-gallery/basic-technology/vector-sensors/>`_ (which is basically impossible to get a hold of one because of their military application) or you could use multiple hydrophones. In order to localize a source three dimensions, you need at least four hydrophones. 

.. image:: /images/array.png
	:alt: Hydrophone array concept

Active
==================

Echo-sounder
--------------

An echo-sounder is kind of like the ocean’s version of echolocation—it sends sound pulses down into the water and listens for the echoes that bounce back. By measuring how long it takes for the sound to return, it can figure out how deep the water is or what’s in it.

Scientific echosounders are used for way more than just measuring depth—they help researchers map the seafloor, track fish, study plankton, and even look at bubbles or layers of water with different properties.

The well-known EK80 Echosounder which is the industry standard for scientific research has been integrated on both Seaglider and Slocums and it's also going to be integrated on SeaExplorers.


.. image:: /images/ek80.png
	:alt: EK80 scientific echosounder


`This guy <https://www.youtube.com/@Neumi>`__ is working on a low-cost open-source version.


Multibeam
--------------------

A multibeam is like a fancy version of an echo-sounder. Instead of just sending one sound pulse straight down, it sends out a whole fan-shaped spread of sound beams across the seafloor. That way, it can cover a wide area all at once. Scientists use multibeam systems to make super detailed 3D maps of the ocean floor. They are very power-hungry and need accurate positioning therefore are not really suitable for gliders.

Side-scan sonar
--------------------

Side-scan sonar is like giving the ocean floor a sideways glance. Instead of looking straight down, it sends out sound waves to the sides—kind of like sweeping a flashlight beam across a dark room. It doesn't measure depth directly, but it gives you a detailed image of the seafloor’s texture. It has a transducer array which sends and receives acoustic pulses as it's being towed underneath or behind a vessel at a constant speed. Doing this they can reconstruct an image of the received echos that represents the seafloor and what's on it using dark and bright areas. This is mainly used to cover a large area relatively quickly and inexpensively when looking for a specific feature such as a shipwreck.


Sub-bottom profiler
---------------------------

A system used for sending sound pulses down into the seabed, and instead of just bouncing off the surface, those pulses actually penetrate below it. The echoes that come back tell us about the different layers of mud, sand, rock, or whatever’s hiding under the bottom. 
Again not typically applicable on gliders, however the fact that gliders get closer to seafloor should in theory make this more efficient.

ADCP
----------------

An ADCP—short for Acoustic Doppler Current Profiler—is like a speed radar for ocean currents. It sends out sound waves and measures how they bounce off tiny particles in the water. Thanks to the Doppler effect, it can figure out how fast the water is moving and in which direction—at different depths.
They have been integrated on all major gliders but making sense of the data they collect from a moving underwater vehicle, is a challenging task.

SeaExplorers seem to have a pretty good solution for the data analysis. From what I understand, they are using the Shear method explained in `this paper <https://journals.ametsoc.org/view/journals/atot/19/5/1520-0426_2002_019_0794_dvpula_2_0_co_2.xml>`_.
For Slocum there are a few packages on GitHub such as `this one <https://github.com/JGradone/Slocum-AD2CP>`__.
UW has their own solution for this which is not shared publicly. But again I found `this <https://github.com/callumrollo/adcp-glider>`__ on GitHub.
`This paper <https://journals.ametsoc.org/view/journals/atot/34/2/jtech-d-16-0156.1.xml>`__ explains how this was done using a Spray gliders.

.. image:: /images/adcp.png
	:alt: ADCP concept on gliders

DVL
--------------------

Stands for doppler velocity logger, and it uses yet again the doppler shift to keep track of speed and direction of an underwater vehicle relative to a solid object such as the seafloor. A team at WHOI have tried using this for under ice navigation.


.. image:: /images/dvl.png
	:alt: DVL illustration
