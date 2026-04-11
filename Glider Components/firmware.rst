Firmware
+++++++++++++++++

The software architecture of underwater gliders has historically evolved under strong constraints of power efficiency, robustness, and long-duration autonomy. In this context, the software design used in Seaglider is particularly notable for its simplicity and efficiency, and serves as a useful reference for this project.

Rather than relying on complex, continuously running control loops as seen in aerial systems, glider software typically operates in discrete phases such as dive, climb, surface, and communication. This aligns naturally with a state-machine-based design, where each phase of the mission is explicitly defined and transitions are tightly controlled.

In contrast, autopilot frameworks such as `PX4 <https://docs.px4.io/main/en/>`_ or ArduPilot are optimized for high-rate control, continuous telemetry, and systems with far more available power, such as drones. These assumptions do not map well to long-endurance underwater gliders, which may operate for months with minimal communication and extremely constrained energy budgets.

Based on this, the current idea is for the software in Tuba to follow a layered embedded architecture built on Zephyr. This enables deterministic behavior, low-power operation, and modular design. The system is structured around explicit state machines to manage mission phases, actuator control, and communication, ensuring predictable and testable behavior.


Current Implementation in Tuba
--------------------------------
The current implementation of the Tuba firmware loosely follows the operational model of a Seaglider. After power-up, the system waits for a defined period for user input before entering a recovery mode. In this mode, a simple console menu allows testing of individual hardware components, adjustment of mission parameters, and execution or simulation of dives.

During normal operation, the glider performs a dive cycle and then returns to the surface, where it again waits for user input before repeating the mission.

The console interface is accessible either through a direct cable connection or over Wi-Fi, and firmware updates can also be performed wirelessly.

The source code is available at `tuba-firmware <https://github.com/e-abdi/tuba-firmware>`_.

`Here <https://lucid.app/lucidchart/d89ac4b4-7b93-4b6b-a87e-13086683a3e1/edit?viewport_loc=-588%2C-849%2C2994%2C1373%2C0_0&invitationId=inv_726f0295-7bba-4cce-93db-fac1e61b2ddb>`_ you can find the rough flowchart of the eventual code.

.. image:: /images/flowchart.png
