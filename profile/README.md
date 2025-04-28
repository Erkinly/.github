# Erkinly – Automated Smart Parking System

---

## Overview:
**Erkinly** (Arabic slang for "Park for me" – اركنلي) is a fully functional prototype of an **Automated Parking System (APS)** developed as a **Graduation Project** by our team. The system minimizes parking space usage and automates the vehicle parking and retrieval process. It integrates embedded systems, cloud communication, and mobile app functionalities into a seamless parking experience.

One of the key features of **Erkinly** is the ability to **book a parking slot in advance**, making it even more convenient for users to ensure they have a spot waiting for them before they arrive at the parking facility. Users can also choose between multiple garages (if available), with the app showing a list of garages and the number of available slots, helping users choose the most convenient garage if some are full or near full.

---

## Project Components:
This project is divided into multiple repositories, each responsible for a different part of the system. The main components are:

### 1. **Backend**  
This repository contains the **server-side code** that handles user requests, manages parking slot availability, communicates with the **ESP32** to control the system, and processes payments. The backend also manages the communication with the mobile app, verifying the parking or retrieval request and ensuring secure transactions.  
Repository: [erkinly_backend](https://github.com/Erkinly/erkinly_backend)

### 2. **LCD Interface Project**  
This repository contains the code for the **DWIN LCD Touchscreen Interface**, which acts as the user interface for drivers to interact with the system. It handles parking and retrieval actions, generates QR codes, and displays system status.  
Repository: [dwin_lcd](https://github.com/Erkinly/dwin_lcd)

### 3. **Arduino Code**  
This repository contains the **Arduino code** for controlling the motors and actuators that move the cars. The Arduino receives commands from the **ESP32**, which directs the system to park or retrieve cars.  
Repository: [arduino_code](https://github.com/Erkinly/arduino_code)

### 4. **ESP32 Code**  
This repository contains the **ESP32 firmware**, which serves as the "brain" of the system. It handles communication between the **backend server** and the **Arduino**, sending commands to control motors and retrieve parking information.  
Repository: [esp32_code](https://github.com/Erkinly/esp32_code)

### 5. **Project Documentation**  
This repository contains all **important project documentation** including design diagrams, flowcharts, and technical specifications.  
Repository: [Docs](https://github.com/Erkinly/Docs)

### 6. **Mobile App**  
This repository contains the **mobile app** developed in **Flutter**. The app provides the user interface for interacting with the parking system, including the ability to scan QR codes, initiate parking or retrieval requests, and process payments. The payment logic is handled by the backend server, but the mobile app provides the user-facing interface to complete the transaction.  
Repository: [erkinly_flutter](https://github.com/Erkinly/erkinly_flutter)

---

## How Erkinly Works:

### 🚗 Parking Journey:
1. The driver arrives at the entrance and interacts with the **DWIN touchscreen**.
2. The user selects "Park", and a unique **QR code** is generated on-screen.
3. The driver scans the QR code using the **Erkinly mobile app**.
4. The app communicates with the **backend server** to verify the parking request, check slot availability, and process the payment.
5. The server sends a confirmation to the **ESP32**, which then opens the entrance door via Arduino commands.
6. After the car enters, the system automatically moves the car to an available parking slot using motors controlled by Arduino.

### 🅿️ Booking a Parking Slot in Advance:
- Users can **reserve a parking slot** through the **mobile app** before they even arrive at the parking facility.
- The app shows real-time availability of multiple garages (currently only one garage is available, but the system is designed to support more).
- The app displays the **number of available parking slots** in each garage, helping users make an informed decision about which garage to visit, especially if some garages are full or near full.
- Once the user selects a garage, the system **automatically selects an empty parking slot** for them within the chosen garage.
- The server ensures that the selected slot is reserved, and the system is ready for the user to park when they arrive.

### 🚙 Retrieval Journey:
1. The driver selects "Retrieve" on the touchscreen.
2. A QR code is shown; the driver scans it using the Erkinly app.
3. The server verifies the request and sends a signal to the **ESP32**.
4. The **ESP32** commands the Arduino to retrieve the car from its parking slot.
5. The car is brought to the retrieval point, and the door opens for the driver to pick up the car.

All payments and user verifications are managed securely via the **mobile app**.

---

## Project Structure:

### Repositories:
- **[erkinly_backend](https://github.com/Erkinly/erkinly_backend):** Server-side logic, API integration, and payment processing.
- **[dwin_lcd](https://github.com/Erkinly/dwin_lcd):** User interface code for the LCD touchscreen.
- **[arduino_code](https://github.com/Erkinly/arduino_code):** Arduino firmware for controlling motors and actuators.
- **[esp32_code](https://github.com/Erkinly/esp32_code):** ESP32 firmware for communication and control.
- **[Docs](https://github.com/Erkinly/Docs):** Project documentation, diagrams, and technical specifications.
- **[erkinly_flutter](https://github.com/Erkinly/erkinly_flutter):** Mobile app code, QR code scanning, parking/retrieval requests, and payment interface.

---

## Key Technologies:
- **Microcontrollers:** Arduino Uno, ESP32
- **User Interface:** DWIN LCD Touch Display
- **Communication:** Wi-Fi (ESP32 <-> Server), Serial (ESP32 <-> Arduino)
- **Motors and Actuators:** DC Motors, Servo Motors, Motor Drivers (L298N)
- **Sensors:** Ultrasonic Sensors, Limit Switches
- **Programming Languages:** C/C++ (Arduino IDE), Embedded Systems Programming
- **Server Communication:** REST APIs (HTTP protocol)
- **Mobile App Integration:** QR Code Scanning, Payment Processing
- **Mobile App Development:** Flutter
- **Payment Processing:** Managed via backend server and interfaced through the mobile app.

---

## Our Role:
As a team, we worked together to bring **Erkinly** to life, with each member contributing their expertise across various areas of the project:

- **Project Management:** The team handled all aspects of project planning, coordination, and testing.
- **Systems Architecture:** Designed and implemented the overall system architecture, connecting hardware, firmware, server, and mobile app.
- **Embedded Development:**  
  - Developed Arduino code for motor control and car movement automation.
  - Developed ESP32 firmware for server communication and system logic.
  - Designed and programmed the DWIN touchscreen user interface.
- **Mobile App Development:**  
  - Developed the mobile app using **Flutter**.
  - Implemented QR code scanning, user parking/retrieval requests, and payment interface.
- **Backend Development:**  
  - Managed the backend server responsible for handling user authentication, parking requests, payment processing, and communication with the ESP32.
- **Integration and Testing:** The team ensured the successful integration of the full system, optimizing for performance and troubleshooting any issues.

---

## Demo Video:
For a comprehensive demo of the **Erkinly** system, check out our **YouTube channel** containing all project demos:  
[Erkinly YouTube Channel](https://www.youtube.com/@Erkinly)

[Watch the full Erkinly Demo Video](https://youtu.be/_xDPV_9PKwc)

---

## Source Code:
You can find the source code for each part of the project in the following repositories:

- **Backend:** [erkinly_backend](https://github.com/Erkinly/erkinly_backend)
- **LCD Interface:** [dwin_lcd](https://github.com/Erkinly/dwin_lcd)
- **Arduino Code:** [arduino_code](https://github.com/Erkinly/arduino_code)
- **ESP32 Code:** [esp32_code](https://github.com/Erkinly/esp32_code)
- **Mobile App:** [erkinly_flutter](https://github.com/Erkinly/erkinly_flutter)

---

## About This Project:
**Erkinly** was developed as our **Graduation Project** to explore the intersection of **embedded systems, IoT, and automation**. The project integrates real-time communication, hardware control, and a user-friendly interface into a working prototype that automates the parking experience. The **booking feature** allows users to secure a parking spot before arriving, enhancing the convenience and efficiency of the parking process.

---

## License:
This project is licensed under the MIT License - see the [LICENSE](https://github.com/Erkinly/erkinly_backend/blob/main/LICENSE) file for details.
