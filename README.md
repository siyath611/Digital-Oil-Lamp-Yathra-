# Digital Oil Lamp Yathra

A smart ceremonial lamp control system built around an ESP32 web interface and an Arduino Mega controller. This project is designed to control 20 lamps using a web page, OLED status display, and serial communication between the ESP32 and Mega.

The repository contains the project documentation and control code for the Yathra 2026 installation, including wiring guidance, pin mapping, and troubleshooting notes.

## Project Overview

This system is intended for a festival or ceremonial lighting setup where each lamp can be toggled individually or as a group through a local web interface. The ESP32 hosts a lightweight web server, while the Arduino Mega manages the actual lamp outputs and timing logic.

### Core components
- ESP32 for Wi-Fi and web interface
- Arduino Mega for lamp control and command processing
- OLED display for system status
- Relay module for master power control
- 20 lamp/button outputs mapped to Mega digital pins
- Serial communication between ESP32 and Mega

## Features
- Control up to 20 lamp channels individually
- Local web dashboard over Wi-Fi
- Serial command support for direct testing
- OLED visual feedback
- Grand finale lighting sequence
- Diagnostic and troubleshooting support
- Works with hardware serial and legacy serial options

## Repository Contents

The project files are stored in the `yathra_2026/` directory:

- `yathra_2026/esp32 code .txt` — ESP32 firmware for Wi-Fi, web control, and serial output
- `yathra_2026/ardino mega.txt` — Arduino Mega logic for lamp behavior and controller logic
- `yathra_2026/DEEP_VERIFIED_ESP32_MEGA_PIN_CONNECTIVITY.txt` — detailed connection map and hardware troubleshooting guide

## Hardware Layout

The project uses an ESP32 and Arduino Mega together:

- ESP32 Wi-Fi access point: `TECH_B`
- ESP32 password: `12345678`
- ESP32 GPIO 21 → OLED SDA
- ESP32 GPIO 22 → OLED SCL
- ESP32 GPIO 19 / GPIO 18 used for serial communication to Mega
- Arduino Mega pin 4 → relay input

## Lamp Mapping

The Mega pins are mapped as follows:

| Lamp / Button | Mega Pin |
|---|---:|
| 1 | 53 |
| 2 | 51 |
| 3 | 49 |
| 4 | 47 |
| 5 | 45 |
| 6 | 43 |
| 7 | 41 |
| 8 | 39 |
| 9 | 37 |
| 10 | 35 |
| 11 | 33 |
| 12 | 31 |
| 13 | 52 |
| 14 | 50 |
| 15 | 48 |
| 16 | 46 |
| 17 | 44 |
| 18 | 42 |
| 19 | 40 |
| 20 | 38 |

## System Behavior

The ESP32 acts as a controller interface, sending commands such as:

- `1:ON`
- `1:OFF`
- `ALL:ON`
- `ALL:OFF`
- `TEST`

Those commands are transmitted to the Arduino Mega, which then switches the relevant lamp outputs and manages timing sequences.

The project also includes a ceremony finale flow where all lamps are turned on, briefly darkened, then lit gradually in sequence before final relay activation.

## Getting Started

### 1. Install required tools
- Arduino IDE
- ESP32 board support package
- Required libraries for OLED and display support
- USB drivers for the ESP32 and Mega

### 2. Upload the firmware
- Upload the ESP32 code to the ESP32 board
- Upload the Mega code to the Arduino Mega board

### 3. Connect the hardware
Follow the wiring details in `yathra_2026/DEEP_VERIFIED_ESP32_MEGA_PIN_CONNECTIVITY.txt` before powering the system.

### 4. Power and test
- Ensure common ground between ESP32 and Mega
- Confirm serial communication is wired correctly
- Open the serial monitor for hardware checks
- Connect to the ESP32 Wi-Fi network and open the web interface

## Web Interface

Once the ESP32 is running, it hosts a local web page for lamp control. The interface allows lamp toggling and can be used to send commands to the controller board.

## Troubleshooting

This project includes several diagnostic checks:

- Power-on self-test sequence
- Direct PC serial monitor testing
- Live serial logging between ESP32 and Mega

Common issues to verify:
- Shared ground between ESP32 and Mega
- Correct TX/RX wiring
- Correct serial port configuration
- OLED I2C connection
- Relay control logic

## Safety Notes

- Double-check all power and ground connections before applying power.
- Use proper current limiting and resistors for each lamp output.
- Avoid powering inductive loads directly without suitable relay protection.
- Verify relay module wiring before running the finale sequence.

## License

This repository does not currently include a license file. If you plan to distribute or reuse this project, add a suitable open-source license based on your intended usage.

## Project Status

This is a custom embedded hardware project for ceremonial lighting control and is intended for personal or installation-specific use. The firmware and documentation are tailored to the Yathra 2026 lighting setup and the accompanying hardware layout.

## Contributing

Contributions, bug fixes, and hardware improvements are welcome. If you modify the project, document your changes clearly and keep the wiring guide updated alongside the firmware.

## Contact

For project-specific questions, refer to the repository owner or the hardware notes included in this project.

---

This README is intended to help users understand the project structure, hardware wiring, and control workflow quickly.
