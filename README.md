# GeminiFlight-Documentation

## Introduction

GeminiFlight is an innovative open-source drone ecosystem designed to provide a comprehensive solution for drone enthusiasts and professionals. This ecosystem comprises hardware, firmware, and software components, with a unique architecture that separates the traditional flight controller into two distinct units: the [Flight Stabilization System (FSS)](flight-stabilization-system/flight-stabilization-system.md) and the [Autonomous Guidance System (AGS)](autonomous-guidance-system/autonomous-guidance-system.md).

## Features

* Split architecture with FSS and AGS for enhanced control and abstraction.
* Precise orientation estimation with MPU6050 IMU on FSS.
* AGS acts as an intermediary, reducing pilot effort with layered abstractions.
* NAVIC constellation support for improved accuracy in the Indian subcontinent.
* Onboard GPS for stable position hold capabilities.
* High-quality, low-latency video transmission for FPV flying.
* Machine learning model support on AGS for advanced applications.
* Long-range WiFi for pilot communication and 4G IoT for BVLOS capabilities.
* NPNT compliance and readiness for BVLOS operations in compliance with future regulations.

### GeminiFlight is for:

* Manufacturers,
* Entrepreneurs,
* Researchers,
* Trainers, and
* Hobbyists

## Getting Started

## Design Philosophy

* **Highly Cost Effective**
  * Ground-up redesign of the modern flight controller with the benefit of hindsight
  * Bring down hardware cost and the complexity of the development and iteration process
  * Focus on eliminating components using System-On-Module(SOM) boards
  * Use Commercial-Off-The-Shelf(COTS) components to support global use
* **Maximize Development Speed**
  * Optimize for developer readability, hackability, and maintainability over absolute code performance
  * Use popular programming languages
  * Use a visual programming paradigm
* **Maintain Modularity & Interoperability**
  * Each component of the GeminiFlight Ecosystem should be capable of being used independently.
  * Must have at least second class interoperability with existing drone technologies.
* **Most advanced features**
  * Flatten the learning curve for becoming a pilot
  * Develop a high level programming interface for the user to be able to visually program missions and adapt to using different payloads.
  * Provide FPV for every drone&#x20;
  * Integrate with the Indian Infrastructure to use NAVIC and include NPNT2.0 Compliance and BVLOS-first operations

## Roadmap

## Contribute
