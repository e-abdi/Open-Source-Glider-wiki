Ocean Acidification
++++++++++++++++++++++

Ocean acidification is the process where the ocean becomes more acidic because it absorbs carbon dioxide (CO₂) from the atmosphere.
When CO₂ dissolves in seawater, it reacts with the water to form carbonic acid, which then lowers the pH of the ocean. A lower pH means the water becomes more acidic.

Besides CO₂, other gases like methane (CH₄) can also dissolve in seawater and play roles in changing ocean chemistry, but CO₂ is the main driver of acidification.

Why does this matter?

* Many marine creatures, like corals, shellfish, and some plankton, need carbonate ions to build their shells and skeletons. Acidification reduces the amount of carbonate available, making it harder for them to survive and grow.

* Changes in pH can also affect the behavior and health of fish and other marine life.

* On a bigger scale, ocean acidification can weaken the ocean’s ability to absorb CO₂, making climate change even worse over time.

In short, ocean acidification is a major threat both to ocean ecosystems and to the planet’s climate balance.


The most promising sensor for CO2 and CH4 currently is the `-4H-JENA engineering HydroC <https://www.4h-jena.de/en/maritime-technologies/sensors/hydrocrco2/>`_.
I've helped integrate this on a Seaglider and the results can be found in `this paper <https://os.copernicus.org/articles/20/1403/2024/>`_.


.. image:: /images/CO2.png
    :alt: CO2 and ocean acidification diagram

They have a new version of this sensor which measures both of these variables and uses a thruster instead of a pump!

.. image:: /images/HydroC.jpg
    :alt: -4H-JENA engineering HydroC sensor
    :width: 400

SeaExplorers have the `Franatech Methane sensor <https://www.franatech.com/mets_methane_sensor.html>`_ and `ProOceanus CO2 <https://pro-oceanus.com/products/mini-series/mini-co2>`_ integrated, but apart from some results in areas with high concentrations of methane and CO2, such as above an `active underwater volcano <https://www.researchgate.net/publication/360839100_Real-Time_and_Continuous_Monitoring_of_Submarine_Volcanism_with_a_Seaexplorer_Glider_Perspective_for_Carbon_Storage_Monitoring>`_ and the `Nord Stream gas pipeline sabotage <https://en.wikipedia.org/wiki/Nord_Stream_pipelines_sabotage>`_, I have not seen any scientific results with these, so I am a bit sceptical about the quality of these sensors.

.. image:: /images/Franatech.jpg
    :alt: Franatech methane sensor

Currently the most interesting pH sensor for gliders is the `ANB pH sensor <https://www.anbsensors.com/>`_ in my opinion. It has a small size and has an interesting method of keeping track of the sensor drift and therefore not needing calibration!  

.. image:: /images/ANB.png
    :alt: ANB pH sensor
    :width: 400


