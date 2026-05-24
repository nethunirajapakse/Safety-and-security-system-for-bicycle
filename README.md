# Smart Safety and Security System for Bicycles

An Arduino Mega-based IoT and embedded system solution designed to protect bicycles from theft, detect road accidents in real-time, provide navigation tracking, and monitor live cycling metrics. 

## 🚀 Features

* **Smart Lock Control:** Lock and unlock your bicycle electronically using two SG90 servo motors via a custom mobile application.
* **Accident Detection & Emergency Alerts:** Utilizes an ADXL335 accelerometer to detect sudden impacts and falls. A built-in buzzer sounds for 30 seconds to allow the rider to cancel false alarms before an automated emergency SMS containing a live Google Maps location is sent via GSM.
* **Anti-Theft GPS Tracker:** Remotely tracks and fetches the bicycle's real-time geographic location by texting "Location" from an authorized smartphone.
* **Digital Speedometer:** Uses a 3144 Hall Effect sensor and a magnet on the wheel hub to calculate and display real-time speed in km/h on a 16x2 LCD screen.
* **Battery Management & Monitoring:** Features an intelligent voltage-divider sensor circuit to view remaining battery life as a percentage over the mobile application.

---

## 🛠️ Hardware Requirements

### Core Components
* **Microcontroller:** Arduino Mega 2560
* **GPS Module:** GY-NEO-8M (uBlox M8N architecture)
* **GSM Module:** SIM900A
* **Accelerometer:** ADXL335
* **Actuators:** 2x SG90 Servo Motors
* **Speed Sensor:** 3144 Hall Effect Switch & Magnet
* **Display:** 16x2 LCD Display with I2C Module
* **Notification:** 5V Active Buzzer & Push Button

### Power Electronics
* **Battery Pack:** 2P2S Lithium-Ion Battery Configuration (7.4V–8.4V output)
* **BMS:** 2S Battery Management System
* **Step-Down Buck Converters:** LM2596 (tuned to 3.4V) & XL4015 (tuned to 4.8V)
* **Voltage Sensor Circuit:** Custom voltage divider using 30K and 7.5K resistors

---

## 📱 Mobile Application
The companion app was built using **MIT App Inventor**. It pairs with the on-board Bluetooth module to send lock/unlock commands and seamlessly capture real-time battery status updates.

---

## ⚙️ Circuit Architecture
The electronics were mapped and designed using **EasyEDA**. 
* **Power Supply Design:** Step-down regulators ensure clean, separate rails for voltage-sensitive processing components vs high-draw actuators like the servo motors and GSM system.
* **Simulated Multithreading:** The firmware implements a non-blocking architecture using `millis()` loops instead of `delay()`, ensuring accident detection routines, GPS fetching, and speedometer tracking run concurrently without performance bottlenecks.

---

## 💻 Firmware Installation & Setup

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/your-username/bicycle-safety-system.git](https://github.com/your-username/bicycle-safety-system.git)
    ```
2.  **Required Libraries:** Install the following libraries through the Arduino IDE Library Manager:
    * `TinyGPS++`
    * `LiquidCrystal_I2C`
    * `Servo`

3.  **Configuration:** Open the main project `.ino` file and update your authorized mobile contacts and emergency contacts under the GSM configuration lines:
    ```cpp
    String EmergencyContact = "+947XXXXXXXX"; 
    String Contact1 = "+947XXXXXXXX";
    ```

4.  **Upload:** Select **Arduino Mega 2560** under `Tools -> Board` and upload the firmware.

---

## Block Diagram
<img width="700" height="1024" alt="block diagram" src="https://github.com/user-attachments/assets/6ddac7c5-90a7-492d-aa5c-f0496126e213" />
---
## Schematic Diagram
<img width="1280" height="864" alt="Schematic diagram" src="https://github.com/user-attachments/assets/ecfc1e84-20d2-4e34-ae75-7fc85ef9a3c4" />
---
## PCB design
<img width="2048" height="1003" alt="PCB design" src="https://github.com/user-attachments/assets/3f6b30ac-7b7e-4f20-9aae-69276f209272" />
---
## Final Product
<img width="512" height="384" alt="final product" src="https://github.com/user-attachments/assets/08be7173-bec0-4d0d-a959-df1d9366d5f1" />

