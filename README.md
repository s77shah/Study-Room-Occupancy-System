# Study Room Occupancy Detection

A project designed to enhance the management and utilization of study rooms at the University of Waterloo by providing real-time occupancy detection and booking system updates. The system ensures efficient resource allocation, reduces no-show issues, and provides a user-friendly interface for students and administrators.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [System Design](#system-design)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Testing and Validation](#testing-and-validation)
- [Contributors](#contributors)
- [License](#license)

## Overview
This project aims to solve the challenge of study room underutilization and availability at peak times. By implementing a real-time occupancy detection system using PIR sensors and integrating it with a booking interface, the system optimizes study room usage and improves the experience for students.

### Key Objectives:
- Real-time room occupancy detection.
- Automated status updates for booked and unoccupied rooms.
- User-friendly interface for booking and pausing room usage.
- Energy-efficient and privacy-conscious design.

## Features
- **Occupancy Detection:** Passive Infrared (PIR) sensors detect motion to determine room usage.
- **Automated Updates:** Updates room availability status based on occupancy and booking conditions.
- **Pause Occupancy:** A button allows users to pause occupancy detection for short breaks.
- **Real-Time Feedback:** LED indicators and LCD displays provide immediate feedback on room status.
- **Energy Efficiency:** Adheres to a maximum power draw of 30W and energy storage limit of 500mJ.
- **User Interface:** Console module for booking and managing room settings.

## System Design
The system consists of two primary modules:

### Room Module
- **PIR Sensors:** Detects room occupancy with a 7-meter range and 110x70-degree field of view.
- **Microcontroller (STM32F401RE):** Processes sensor data and communicates with the console module.
- **Pause Button & LED:** Allows users to temporarily halt occupancy detection.
- **Piezo Buzzer:** Alerts users when their booking is about to expire or a room is unoccupied.
- **LCD Display:** Shows room status and booking details.

### Console Module
- **Control Buttons:** Navigate and manage bookings.
- **Microcontroller (STM32F401RE):** Handles booking commands and communicates with the room module.
- **LCD Display:** Displays room availability and booking queue.
- **LED Indicators:** Provides visual feedback for room status.

## Hardware Requirements
- 2x Passive Infrared (PIR) Sensors (e.g., HC SR501)
- 2x Microcontrollers (STM32F401RE Nucleo Boards)
- 2x 16x2 LCD Displays
- Resistors (220Ω, 10kΩ, 250kΩ)
- Pushbuttons (SPST)
- LEDs
- Piezo Buzzer
- Wiring and connectors

## Software Requirements
- STM32CubeIDE or compatible IDE for microcontroller programming
- Python (optional for simulation)
- Libraries for UART communication

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/s77shah/study-room-occupancy-detection.git
   cd study-room-occupancy-detection
   ```
2. Assemble the hardware according to the provided schematics.
3. Program the microcontrollers using the provided pseudocode or source files.
4. Test UART communication and sensor integration.

## Usage
1. **Start the System:** Power on the modules.
2. **Book a Room:** Use the console module to navigate the booking system.
3. **Occupancy Detection:** Enter the room, and the system will update the status automatically.
4. **Pause Occupancy:** Press the pause button for a temporary break.
5. **Cancel Booking:** Hold the button to manually cancel a booking.
6. **Monitor Room Status:** Check the LCD display for real-time updates.

## Testing and Validation
- **Communication Test:** Verify UART communication loopback.
- **Sensor Accuracy:** Test PIR sensors under varying environmental conditions.
- **Power Consumption:** Ensure current draw remains below 6A.
- **Button Response:** Validate that the pause button provides LED feedback within 2 seconds.
- **System Reliability:** Test under real-world scenarios to confirm accuracy and usability.

## Contributors
- Bryan Ma  
- Sania Shah

## License
This project is licensed under the MIT License. See the LICENSE file for details.

---
For more details, refer to the [design document](./design_document.md).
