# Fingerprint-Based Voting System

This project implements a **Fingerprint-Based Voting System** using Arduino. It is designed to register votes by using a biometric fingerprint scanner. Each user is authenticated by their fingerprint, ensuring a secure and reliable voting process. After authentication, the voter can select their preferred candidate from the available options. Once a vote is cast, the voter cannot vote again, preventing double voting. The system also includes a functionality to display election results.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Circuit Connections](#circuit-connections)
- [How to Use](#how-to-use)
- [Installation](#installation)
- [Code Overview](#code-overview)
- [Acknowledgements](#acknowledgements)

## Project Overview

The voting system is built using an Arduino microcontroller, a fingerprint sensor for voter authentication, and a keypad to cast votes for three candidates. The system stores the vote count in EEPROM and includes a reset feature to clear votes for a new voting session. An LCD display is used to guide the voter through the process, and a buzzer provides audio feedback.

### Features
- **Fingerprint Authentication:** Only authorized users can vote.
- **Candidate Voting:** Voters can choose between three candidates.
- **Vote Storage:** Votes are stored in EEPROM to retain the data even if the system is restarted.
- **Result Display:** The vote count for each candidate can be displayed at the end of the voting session.
- **Reset Functionality:** Easily reset the system for new elections.
  
## Hardware Requirements
- Arduino (e.g., Uno, Mega)
- R305 Optical Fingerprint Sensor (or compatible sensor)
- 16x2 LCD Display
- Push Buttons (for enrolling, matching, and selecting candidates)
- Buzzer (for feedback)
- EEPROM (used to store votes)
- Jumper Wires
- Breadboard
- External Power Supply (if required)

## Software Requirements
- Arduino IDE (version 1.8.13 or higher)
- Adafruit Fingerprint Sensor Library ([Download Here](https://github.com/adafruit/Adafruit-Fingerprint-Sensor-Library))
- LiquidCrystal Library (comes pre-installed with Arduino IDE)

## Circuit Connections
- **Fingerprint Sensor:**
  - VCC: 5V
  - GND: GND
  - TX: Pin 2
  - RX: Pin 3
- **LCD Display (16x2):**
  - Connect to pins 12, 11, 10, 9, 8, 7 (or according to your setup)
- **Buttons:**
  - Enroll, Delete, Up, Down, Match buttons connected to appropriate digital pins (e.g., Pin 14, 15, 16, etc.).
- **Buzzer:** Connected to Pin 6.
- **Voting Switches (for candidates):**
  - Connect to Pin 5, 2, 3, 4 respectively for candidate selection.
- **EEPROM:** Built-in to the Arduino.

## How to Use
1. **Setup the Circuit:** Connect all components as described in the circuit section.
2. **Upload Code:** Upload the provided `.ino` code to your Arduino using Arduino IDE.
3. **Enroll Users:** 
   - Press the enroll button and follow the prompts on the LCD to register the user's fingerprint.
4. **Cast a Vote:**
   - After authentication, choose your candidate using the buttons and press the match button to cast your vote.
   - Once the vote is cast, the system prevents double voting.
5. **View Results:** 
   - Press the result button to view the voting results on the LCD.
6. **Reset System:** If you want to start a new voting session, reset the system using the designated reset button.

## Installation

1. **Clone or Download the Repository**:
   - Clone the repository:
     ```bash
     git clone https://github.com/your-username/Fingerprint-based-Voting-System.git
     ```
   - Or download the ZIP and extract it.
   
2. **Install the Required Libraries:**
   - Open Arduino IDE, go to **Sketch -> Include Library -> Manage Libraries**, and install the `Adafruit Fingerprint Sensor` and `LiquidCrystal` libraries.
   
3. **Upload the Code:**
   - Open the `.ino` file in Arduino IDE and upload it to your Arduino board.

## Code Overview

### Main Functionalities
- **Fingerprint Enrollment:** Enroll fingerprints using the `Enroll()` function. Each fingerprint is stored in EEPROM.
- **Voting:** After fingerprint matching, the `Vote()` function allows users to vote by pressing one of the voting buttons.
- **Results Display:** The system can display vote counts for all candidates on the LCD screen using `voteSubmit()`.
- **Reset:** The system can be reset by clearing the EEPROM, allowing for new elections.

### Libraries Used
- **EEPROM.h**: Used to store vote data persistently.
- **LiquidCrystal.h**: For controlling the 16x2 LCD display.
- **Adafruit_Fingerprint.h**: To interface with the fingerprint sensor for enrolling and matching fingerprints.

## Acknowledgements

This project was inspired by the need for a secure and reliable voting system using biometrics. Special thanks to [Prateek](https://justdoelectronics.com) for initial guidance on fingerprint-based voting systems.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

