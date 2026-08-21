Altimeter
++++++++++++

Gliders are generally more efficient in deeper waters. This is because they spend a smaller percentage of the dive on pumping and surface communication. There are two major methods used for avoiding hitting the bottom. One is relying on a digitized bathymetry map of the area and the other is the use of an altimeter. Seaglider uses a combination of these two while Slocum relies only on altimeter readings.

Seaglider uses a 12KHz `Applied Acoustics altimeter/transponder combo <https://ftp.soest.hawaii.edu/pilot/seaglider_testing_logs/Seaglider146/SG146_Thumb_Drive_Kongs_Feb2016/User_Manuals/OEM_Manuals/Applied_Acoustics_Underwater_Technology/SPC-5414-8000-3_LF%20Transponder%20Altimeter%20Manual.pdf>`_ which can also be used to locate the glider using a topside unit.

.. image:: /images/SeagliderAltimeter.png
	:alt: Seaglider components

Slocum, on the other hand, uses a 170KHz `Airmar altimeter unit <https://www.airmar.com/Product/200m-Mini-Altimeter-Kit-Smart-Sensor>`_.

.. image:: /images/SlocumAltimeter.png
	:alt: Slocum glider components


Implementation in Tuba
-----------------------

The `BlueRobotics altimeter <https://bluerobotics.com/store/sonars/echosounders/ping-sonar-r2-rp/>`_ seems to be a perfect fit for our purposes here.
