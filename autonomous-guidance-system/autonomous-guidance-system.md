# Autonomous Guidance System

The AGS is a Raspberry Pi Zero2W running the GeminiFlight-Host software. This unit acts as an intermediary between the pilot and the FSS, introducing layers of abstraction for standard manual flight mode. Equipped with onboard GPS and utilizing the NAVIC constellation, the AGS provides stable position hold capabilities, particularly beneficial in the Indian subcontinent. GeminiFlight is currently the only flight controller natively supporting NAVIC.

The AGS also features an onboard camera for high-quality, low-latency video transmission to the pilot, facilitating First Person View (FPV) flying. Moreover, it supports the execution of various machine learning models for advanced applications.

## What does the AGS do?

* **GeminiLink Server:** Interoperates between [the FSS](../flight-stabilization-system/flight-stabilization-system.md), the [Global Sensor Interface (GSI)](global-sensor-interface.md) and any connected Users on the GeminiFlight App.
* **Position/Altitude Hold:** This capability requires a heavier Kalman Filter along with data from various Global Sensor Interfaces.
* **Waypoint Navigation:**  Receives a Mission Plan from the GeminiFlight App and follows
