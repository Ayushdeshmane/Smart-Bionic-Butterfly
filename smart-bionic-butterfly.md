---
publishDate: 2025-12-31

title: Smart Bionic Butterfly-A Gesture-Assisted Therapeutic Companion

excerpt: An IoT-enabled bionic butterfly that uses wing motion, sensor awareness, and human interaction to support calm and engaging therapeutic experiences.

image: cover-bionic-butterfly.jpg

tags:
  - iot
  - esp32
  - embedded-systems
  - assistive-technology
  - bionics
  - healthcare

---

A bio-inspired butterfly that combines autonomous motion and simple human interaction to explore the role of IoT in therapeutic companionship.

## Acknowledgements

We sincerely thank the MYOSA team for providing the platform and resources that made this project possible. The MYOSA IoT ecosystem was crucial for experimenting with embedded systems, wireless communication, and sensor integration. 
We also appreciate our faculty mentor for their guidance and feedback during the ideation and development phases. 
Lastly, we recognize the collaborative efforts of all team members. Their contributions in design, implementation, and testing were essential for this project.

## Overview

The Smart Bionic Butterfly is a robotic system that uses IoT technology and takes inspiration from biology. It is designed for gentle, controlled motion and interactive behavior for therapeutic and assistive purposes. The project highlights smooth wing movement, reliable system behavior, and clear feedback, making it ideal for calming and engaging human interaction.

The system features a two-node setup. The butterfly unit has a MYOSA motherboard based on the ESP32. This component runs the main control logic. Once the program is uploaded and the system is turned on, the butterfly executes controlled wing movements based on set command sequences. This primary function does not rely on user gestures and ensures consistent and repeatable performance.

A separate base station unit, also built on the ESP32, allows for optional human interaction and system monitoring. This unit includes a gesture sensor and an OLED display. Simple left and right hand gestures detected at the base station can be sent wirelessly to the butterfly unit as extra directional commands.

The base station and the butterfly communicate using the ESP-NOW protocol. This method permits fast data exchange without needing a Wi-Fi network. The butterfly unit processes incoming gesture inputs carefully.

The system includes onboard motion sensing and environmental awareness through a gyroscope and a pressure sensor attached to the butterfly. Key system states and sensor readings appear on the OLED display of the base station, offering clarity during operation. This design shows how distributed IoT systems can be used for bio-inspired and therapeutic robotic applications, expanding beyond traditional industrial uses.

## Demo / Examples
### Images

<p align="center">
  <img src="butterfly_internal_electronics_assembly.png" width="800"><br/>
  <i>Internal electronics assembly of the Smart Bionic Butterfly features the MYOSA ESP32-based motherboard, sensors, power distribution, and wiring layout.</i>
</p>

<p align="center">
  <img src="complete_butterfly_cad_assembly.png" width="800"><br/>
  <i>Complete CAD assembly of the Smart Bionic Butterfly shows wing structure, actuator placement, and overall mechanical setup.</i>
</p>

<p align="center">
  <img src="rear_wing_hinge_mounting_bracket.png" width="800"><br/>
  <i>Rear wing hinge mounting bracket CAD model created for secure attachment and smooth rotational support.</i>
</p>

<p align="center">
  <img src="rear_wing_hinge.png" width="800"> <br/>
  <i>Rear wing hinge mechanism that allows controlled angular movement of the butterfly wing during actuation.</i>
</p>

<p align="center">
  <img src="wing_hinge_joint.png" width="800"><br/>
  <i>Wing hinge joint CAD model forms the main rotational connection between the wing and internal linkage system.</i>
</p>

### Videos

<video controls width="100%">
  <source src="/smart_bionic_butterfly_demo.mp4" type="video/mp4">
</video>

<p align="center">
  <i>
  Complete demonstration of the Smart Bionic Butterfly system, including sensor testing, CAD model visualization, internal electronics assembly, controlled wing actuation, and gesture-assisted directional motion during operation.
  </i>
</p>


## Features 

1. Command-Based Wing Motion Control

The butterfly operates based on control commands programmed into the MYOSA motherboard mounted on it. After uploading the firmware and powering on the system, the control logic executes these commands to create continuous and predictable wing movement.

Two mini digital coreless servo motors drive the wings. Each servo controls one wing independently, which allows for symmetric and coordinated motion. Motion parameters like angle range and speed are limited in software to ensure smooth transitions and gentle behavior that is safe for close human interaction.

This command-based method is essential for the system’s behavior. It guarantees stable, repeatable, and safe operation without relying on external inputs.

2. Gesture-Assisted Directional Interaction

The system supports gesture-assisted interaction through a dedicated base station unit. Simple left and right hand gestures detected by the gesture sensor are used to introduce directional influence to the butterfly’s motion.

Gesture input enhances user engagement by allowing intuitive interaction without requiring physical contact. When a gesture is detected, the corresponding directional information is transmitted wirelessly to the butterfly unit, where it is smoothly integrated into the ongoing command-based motion.

This interaction model allows users to gently guide the butterfly’s behavior while preserving stable and predictable operation, making it suitable for therapeutic and assistive environments.
This simple gesture system allows for easy interaction without sudden or overwhelming responses.

3. Wireless Communication Using ESP-NOW

The system uses a dual-ESP setup with the ESP-NOW communication protocol. One ESP32-based MYOSA board is on the butterfly, and a second ESP32-based unit acts as a base station for interaction and monitoring.

ESP-NOW allows quick, direct communication between the two ESP devices without needing a Wi-Fi network or external infrastructure. The base station sends simple directional influence data to the butterfly unit, which interprets this information in a limited and controlled way.

This approach to communication provides responsive interaction while keeping the system simple and reliable.

4. Orientation Monitoring Using Gyroscope

An MPU6050 accelerometer and gyroscope module is attached to the butterfly to track its orientation and movement. Gyroscope data monitors tilt and position changes during wing motion and directional adjustments.

By continuously checking its orientation, the system avoids excessive deviation and helps ensure smooth and controlled movement. The orientation information is also displayed at the base station, which makes the system more transparent during demonstrations.

5. Environmental Awareness Through Pressure Sensing

A barometric pressure sensor gives the system environmental awareness. The butterfly continuously samples atmospheric pressure data and transmits this for display.

This data is not used for flight or altitude control. Instead, it shows real-time environmental sensing as part of the IoT functionality of the project and helps the system reflect its surroundings.

6. Real-Time System Feedback via OLED Display

An OLED display is built into the base station unit to show real-time system information. The data displayed includes orientation status, pressure readings, and operational indicators.

Providing visible feedback helps caregivers, therapists, and observers understand the internal state of the system during operation. This enhances usability, trust, and clarity during live demonstrations.

7. Lightweight Battery-Based Power System

The Smart Bionic Butterfly runs on lightweight 3.7V lithium-phosphate batteries. Two batteries provide stable power while keeping the overall weight low. This choice helps with smooth servo operation and reliable sensor performance without adding too much mass to the structure.

Using onboard battery power lets the butterfly work independently of external wired supplies during demonstrations. The lightweight batteries fit with the bio-inspired design goals and support future plans for untethered operation.

The battery-powered setup will be shown in the project video to emphasize the system’s portability and readiness for standalone use.

## Usage Instructions

1. Assemble the butterfly structure. Make sure the MYOSA motherboard, servo motors, gyroscope, pressure sensor, and power supply are securely mounted on the butterfly unit.

2. Power the butterfly unit with the onboard lightweight batteries. Upload the control firmware to the MYOSA board. Once powered on, the butterfly operates according to the programmed commands, generating smooth and controlled wing motion.

3. Set up the base station unit by powering the secondary ESP32 along with the gesture sensor and OLED display. The base station initializes automatically and establishes wireless communication with the butterfly unit using the ESP-NOW protocol.

4. During operation, the butterfly follows its predefined motion while continuously monitoring sensor data such as orientation and environmental pressure.

5. Hand gestures performed near the base station can gently influence the butterfly’s direction. These interactions improve user engagement while keeping the system stable and predictable.

6. The OLED display at the base station provides real-time feedback, allowing observers to view the system status and sensor readings throughout the demonstration.

7. After use, safely power down the system by switching off the battery supply to both the butterfly and base station units.


## Tech Stack

- MYOSA Motherboard (ESP32-based)  
  The MYOSA motherboard is mounted on the butterfly and serves as the main control unit. It runs the command-based control logic, processes data from onboard sensors, and operates the wing actuation system. The board coordinates sensing, communication, and motion control in real time.

- ESP32 Base Station Unit  
  A second ESP32 acts as a base station for user interaction and system monitoring. This unit detects gestures, shows system information on the OLED, and communicates wirelessly with the butterfly unit using the ESP-NOW protocol.

- ESP-NOW Communication Protocol  
  ESP-NOW enables direct, low-latency wireless communication between the butterfly ESP and the base station ESP. It allows for efficient transmission of simple directional commands without needing a Wi-Fi network or internet access, making the system responsive and lightweight.

- MPU6050 Accelerometer and Gyroscope  
  The MPU6050 is mounted on the butterfly to monitor its orientation and motion. The gyroscope tracks tilt and movement during wing actuation and directional influence, helping maintain stable and controlled behavior.

- BMP180 Barometric Pressure Sensor  
  The pressure sensor continuously measures ambient pressure, providing environmental awareness. This data adds to the IoT aspect of the project and is used for real-time system feedback rather than flight or altitude control.

- APDS9960 Gesture Sensor  
  The gesture sensor is part of the base station unit, allowing for intuitive, non-contact interaction. It detects simple left and right gestures and translates them into directional commands sent to the butterfly.

- SSD1306 I2C OLED Display  
  The OLED display at the base station shows real-time system information like orientation status, pressure readings, and operational indicators. This increases transparency and makes demonstrations easier.

- Mini Digital Coreless Servo Motors (2 Units)  
  Two servo motors actuate the butterfly's wings. Each motor controls one wing independently, allowing for smooth and gentle flapping motion guided by command-based control logic.

- Embedded Firmware (ESP32 / Arduino-based)  
  The system firmware handles sensor interfacing, wireless communication, command execution, and servo control. The code is designed for predictable timing, smooth motion transitions, and safe operation.

- Power System (3.7V Lithium-Phosphate Batteries)  
  The butterfly unit uses lightweight 3.7V lithium-phosphate batteries, enabling portable and untethered operation during demonstrations while keeping the overall system weight low.

- Mechanical Structure (PLA, Carbon Fiber, Lightweight Plastics)  
  The butterfly's structure consists of 3D-printed PLA for the body and mounts, along with carbon fiber and lightweight plastic for the wings. This combination offers strength, flexibility, and a design inspired by nature.

## Requirements / Installation

1. Hardware Requirements
- MYOSA motherboard (ESP32-based) mounted on the butterfly unit
- Secondary ESP32 for the base station
- Two mini digital coreless servo motors
- MPU6050 accelerometer and gyroscope module
- BMP180 barometric pressure sensor
- APDS9960 gesture sensor
- SSD1306 I2C OLED display
- Two lightweight 3.7V lithium-phosphate batteries
- Connecting wires, mounts, and mechanical fasteners

2. Software Requirements
- Arduino IDE or a compatible ESP32 development environment
- ESP32 board support package installed in the IDE
- Required libraries for MPU6050, BMP180, APDS9960, and SSD1306
- ESP-NOW communication support for ESP32

3. Installation and Setup

1. Assemble the butterfly structure and securely mount the MYOSA motherboard, servo motors, gyroscope, pressure sensor, and batteries on the butterfly unit.
2. Connect all onboard sensors and servo motors to the MYOSA board using the appropriate I2C and GPIO connections.
3. Upload the command-based control firmware to the MYOSA board, then check the wing motion and sensor initialization.
4. Assemble the base station unit by connecting the secondary ESP32 with the gesture sensor and OLED display.
5. Upload the base station firmware and ensure ESP-NOW communication is established between the base station and butterfly units.
6. Power both units with their respective power sources, then check wireless communication, display output, and gesture-assisted interaction.