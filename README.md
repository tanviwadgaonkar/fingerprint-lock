# fingerprint-lock
SecureEntry is a smart, secure, and efficient biometric door lock system built using the ESP32 microcontroller and R305 fingerprint sensor. This project provides an affordable solution for access control using fingerprint authentication, ideal for use in labs, home automation, classrooms, and office cabins.

📌 Objective
To develop a contactless, secure access system that uses fingerprint-based identity verification to control the opening and locking of doors, ensuring only authorized personnel can gain access.

🧰 Components Used
Component	Quantity	Description
ESP32 Board	1	Wi-Fi & Bluetooth-enabled microcontroller
R305 Fingerprint Sensor	1	Optical fingerprint module for biometric input
16x2 LCD Display (I2C)	1	Displays status messages
Buzzer	1	Provides audio feedback
Relay Module	1	Controls high-voltage solenoid lock
Solenoid Lock	1	Electrically operated lock
Power Supply (5V/12V)	1	Power source for ESP32 and lock
Resistors, Transistors	As req.	Used in circuit protection and switching
Jumper Wires, Breadboard	As req.	For connections and prototyping

⚙️ Features
🔐 Fingerprint-Based Authentication: Uses R305 module to register and verify users.

💾 EEPROM Storage: Stores authorized fingerprints persistently.

🔊 Real-Time Feedback: Status shown via LCD and buzzer (e.g., Access Granted, Access Denied).

🛠️ Relay-Controlled Locking: Controls solenoid lock safely using a relay module.

🧱 Modular Design: Easy to upgrade or modify for keypad, RFID, or mobile access in future.

🔌 Power Efficient: Operates efficiently on standard 5V or 12V power supply.

🔍 How It Works
User Enrollment:

Admin can add authorized users via serial monitor or through a defined interface.

Fingerprints are saved to the sensor’s internal memory and mapped to user IDs.

Authentication:

On system startup, the ESP32 scans for a fingerprint using the R305 sensor.

If the fingerprint matches a stored ID, access is granted.

Lock Operation:

When matched, a relay is triggered to unlock the solenoid for a set time (e.g., 5 seconds).

The buzzer gives an audio confirmation, and LCD displays "Access Granted".

For failed attempts, the buzzer gives an error beep and LCD displays "Access Denied".

Security Feedback:

Optional counter for invalid attempts can trigger alerts.

Can be extended to log entry time using RTC or send SMS alerts via GSM module.

💻 Code & Setup
Written in Embedded C++ using the Arduino framework for ESP32.

Utilizes libraries:

Adafruit_Fingerprint for interfacing with R305

LiquidCrystal_I2C for LCD display

EEPROM for storing state (optional)

IDE: Arduino IDE with ESP32 board manager installed

To upload:

Connect ESP32 via USB.

Open .ino file in Arduino IDE.

Select proper board and COM port.

Upload and monitor via Serial Monitor.





🧪 Possible Extensions
📱 Integrate with mobile app via Bluetooth or Wi-Fi

🗓️ Add RTC for time-based access control

📧 Send entry logs via email or to cloud

📊 Display access log on a web dashboard
