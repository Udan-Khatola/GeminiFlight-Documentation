# Flight Stabilization System

The FSU is a crucial component of GeminiFlight, consisting of a Teensy 4.0 microcontroller module. This unit processes data from the MPU6050 Inertial Measurement Unit (IMU) to create an accurate and real-time estimate of the drone's orientation. This estimation is performed thousands of times per second, allowing the FSU to calculate precise motor inputs based on the desired state received either from the APU or directly from the pilot.
