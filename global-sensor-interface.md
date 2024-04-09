# Global Sensor Interface

The FSS doesn't deal with any sensors meant for stabilization and navigation in the global frame of reference like GPS, Optical Flow Camera, Obstacle Detection Camera, LIDAR, RADAR, SONAR, UWB etc.&#x20;

### Decentralized Smart Sensors

The GSI converts I2C and SPI data to a high speed serial connection as standardized JSON data while performing basic filtering onboard to reduce bandwidth consumption. This allows for the connection of a very large number of sensors.

### Cost Savings

The primary difference between expensive microcontrollers and cheap microcontrollers is the amount of onboard IO. Removing global sensor interfaces from the microcontrollers lets us drastically reduce costs.
