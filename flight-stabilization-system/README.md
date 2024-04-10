# Flight Stabilization System

The FSU is a crucial component of GeminiFlight, consisting of a Teensy 4.0 microcontroller module. This unit processes data from the MPU6050 Inertial Measurement Unit (IMU) to create an accurate and real-time estimate of the drone's orientation. This estimation is performed thousands of times per second, allowing the FSU to calculate precise motor inputs based on the desired state received either from the APU or directly from the pilot.

## What the FSS does:

* Handles Pilot RC input (Supporting PPM, PWM, S.Bus, & DSM-Rx)
* Communicates with the AGS over GeminiLink
* Handles sensor inputs & calibration
* Runs a Madgwick Filter to fuse sensor data
* Runs PID Control loop
* Outputs motor & servo commands



## What the FSS doesn't do:

* **Custom IMU Mounting Orientation**: The IMU must always be mounted in the proper orientation at the Center of Mass for proper control of Roll, Pitch and Yaw. Providing custom mounting angles would make the calibration routine a lot more complex. Instead we have a removable IMU module so it can be mounted seperately from the Flight Controller. A custom orientation can be hard-coded for applications that have a hard requirement for it.
