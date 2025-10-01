# 📡 GSM Based Smart Door Lock with SMS + Cloud Logging

## 🔧 Overview
This project is a **Smart Door Lock System** controlled via **SMS commands** using the SIM800L GSM module and Arduino.  
It can also log all commands and door status events to the **ThingSpeak IoT cloud** via GPRS, so users can monitor remotely.

## 🚀 Features
- Unlock/lock door by sending an SMS ("unlock").
- Only pre-registered phone numbers are accepted.
- Automatic re-lock after 20 seconds.
- Reply SMS for confirmation.
- Cloud logging to ThingSpeak (command, phone number, status).
- Easy to extend with RFID, keypad, or fingerprint sensor.

## 🛠️ Components Used
- Arduino Uno / Nano
- SIM800L GSM Module
- Relay Module / Solenoid Lock / Servo
- Power Supply (5V regulated + capacitor for GSM spikes)
- (Optional) LCD/OLED, Buzzer, LEDs

## 📡 Circuit Diagram
- SIM800L TX → Arduino Pin 2
- SIM800L RX → Arduino Pin 3
- Relay IN → Arduino Pin 4
- Relay VCC → 5V, GND → GND
- SIM800L VCC → 4V (use buck converter)
- SIM800L GND → GND

## 📊 Cloud Integration (ThingSpeak)
1. Create a free ThingSpeak account.
2. Create a new channel with fields:
   - Field1: Command
   - Field2: Sender Number
   - Field3: Status
3. Copy your Write API Key and paste it into the Arduino code.
4. Arduino will log events using SIM800L’s GPRS.

## ▶️ Demo Flow
1. User sends SMS "unlock".
2. Arduino unlocks relay for 20 sec.
3. Door auto-locks after timeout.
4. Reply SMS is sent back.
5. Data is logged to ThingSpeak dashboard.

## 📂 Repository Structure
- `/Arduino_Code` → Arduino sketch
- `/Diagrams` → Circuit + block diagrams
- `/Docs` → Flowcharts, report, and setup guide

## 📽️ Future Improvements
- Dual authentication (SMS + RFID / Fingerprint).
- Real-time Blynk mobile app control.
- GPS tracking for mobile locks.
- Custom PCB and 3D-printed enclosure.

---
