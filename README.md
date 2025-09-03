# 🏠 ESP32 Home Automation with Arduino IoT Cloud

This project demonstrates how to control **home appliances** (lights, fans, etc.) using an **ESP32**, an **8-channel relay module**, and **tactile switches**.  
It integrates with **Arduino IoT Cloud**, so devices can be controlled **both manually (switches)** and **remotely (IoT Cloud dashboard / mobile app)**.

---

## ✨ Features
- Control 4 appliances (extendable to more relays).  
- Sync **manual switch presses** with **IoT Cloud dashboard**.  
- Cloud monitoring with real-time status updates.  
- Automatic **WiFi LED indicator** for connection status.  
- Works with **active-LOW relay modules**.  

---

## 🖥️ Hardware Requirements
- ESP32 DevKit (ESP32-WROOM / ESP32-DevKitC recommended)  
- 4-channel (or 8-channel) relay module  
- 4 tactile push buttons (for manual control)  
- Jumper wires & breadboard  
- WiFi connection  

---

## 📌 Pin Mapping

| Device       | ESP32 Pin |
|--------------|-----------|
| Relay 1      | GPIO 23   |
| Relay 2      | GPIO 19   |
| Relay 3      | GPIO 18   |
| Relay 4      | GPIO 5    |
| Switch 1     | GPIO 13   |
| Switch 2     | GPIO 12   |
| Switch 3     | GPIO 14   |
| Switch 4     | GPIO 27   |
| WiFi LED     | GPIO 2    |

⚠️ Note: Relays are **active LOW** → `LOW = ON`, `HIGH = OFF`.

---

## ☁️ Arduino IoT Cloud Setup
1. Create a new **Thing** in [Arduino IoT Cloud](https://create.arduino.cc/iot/).  
2. Add the following **Cloud Switch variables** (type = Switch, permission = Read & Write):  
   - `light1`  
   - `light2`  
   - `light3`  
   - `light4`  
3. Download the **Secret Key PDF**.  
4. Copy your **DEVICE_ID** and **SECRET_KEY** into the code:  
   ```cpp
   const char DEVICE_LOGIN_NAME[]  = "YOUR_DEVICE_ID";
   const char DEVICE_KEY[]         = "YOUR_SECRET_KEY";
   const char SSID[]               = "YOUR_WIFI_SSID";
   const char PASS[]               = "YOUR_WIFI_PASSWORD";
