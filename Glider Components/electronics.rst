Electronics
++++++++++++++++++

Initially both Seaglider and Slocum used a combination of Persistor CF2 and Tattletale 8 (TT8). Persistor was a microcontroller with a compact flash and Tattletale was a mini computer capable of running DOS. My understanding is that Persistor is used as a supervisor and would only turn to TT8 when specific tasks were going to be carried out. I believe this was done to both reduce the power consumption and add a layer of safety.
The transition to ARM-based systems in both Seaglider and Slocum was primarily driven by the obsolescence of their original hardware platforms. Instead of fully rewriting their software, developers largely preserved existing mission logic by porting and adapting legacy DOS-based code to run on modern embedded systems.

Initially, the system was intended to be based on `PX4 <https://docs.px4.io/main/en/>`_ in order to facilitate integration with the broader autopilot ecosystem. However, the operational requirements of underwater gliders differ significantly from those of aerial drones or even ROVs and AUVs.

In particular, drones typically rely on continuous real-time telemetry, higher update rates, and comparatively less constrained energy budgets. In contrast, gliders are designed for long-duration deployments, operating autonomously for extended periods with minimal communication, often transmitting only small amounts of data at infrequent intervals. These differences have important implications for system architecture, power management, and software design.

Based on this, a more suitable approach is to adopt a layered embedded architecture built around Zephyr. This allows for fine-grained control over power consumption, deterministic behavior, and modular system design, which are critical for long-endurance autonomous platforms. Integration with existing autopilot ecosystems can be considered at a later stage, once the core system architecture has been validated.

Zephyr is a modern, open-source real-time operating system hosted by the Linux Foundation and originally initiated by Intel. It follows industry best practices for safety, security, and modularity, and benefits from a broad, vendor-neutral ecosystem. Unlike many traditional RTOS solutions that are tightly coupled to a single vendor, Zephyr is highly portable and hardware-agnostic, making it well suited for flexible and scalable embedded system design.


Implementation in Tuba
--------------------------------
The current implementation in Tuba is based on readily available modules rather than using the individual chips directly. At the moment, the electronics stack consists of the following components:

* MCU: ESP32-DevKitC
* DC-DC converter: MP1584
* Compass: HMC6343
* Internal pressure sensor: BMP180
* GPS: NEO-M8U
* Data logger: OpenLog
* External pressure sensor: BlueRobotics Bar Pressure Sensor

The current version of the PCB is available at `tuba-pcb <https://github.com/e-abdi/tuba-pcb>`_.


`This block diagram <https://lucid.app/lucidchart/8746efec-c75f-44b0-9be7-4c806a048f1b/edit?viewport_loc=-11%2C-155%2C2219%2C1017%2C0_0&invitationId=inv_f7b1ec5a-b75d-4923-b846-12c5eede53f9>`_ represents the eventual target architecture rather than the exact current implementation. Again any comments and contributions are welcome.

.. image:: /images/blockdiagram.png
