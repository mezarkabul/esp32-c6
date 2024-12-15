---

# ESP32-C6 Multi-Sensor Board

## Overview
This repository provides the hardware design, block diagrams, and schematics for the ESP32-C6 Multi-Sensor Board. The board integrates Wi-Fi/Bluetooth communication, motor driver control, and IMU sensor, making it suitable for IoT and robotics applications.

![esp32-c6-block_diagram](https://github.com/user-attachments/assets/a721194b-b750-4792-a321-2f3cb19888d9)


---

## Features & Block Diagram

The ESP32-C6 Multi-Sensor Board includes the following features:

### **Power Management**
- **Power Input:** 5V @ 250mA via connector  
- **Battery Management:**
  - Battery Charger (max 200mA charging current)
  - Voltage Regulator: Converts 4.2V to 3.3V  
  - Battery Level Monitoring via ADC  

### **Microcontroller**
- **ESP32-C6:**
  - Wi-Fi 6 and BLE 5.0 support
  - GPIOs for control and communication  
  - I2C for peripherals  

### **Motor Driver**
- **DRV8830 Motor Driver:**  
  - Controlled via I2C  
  - Outputs: **Motor_P** and **Motor_N**  
  - Supports motor currents up to 400mA  

### **Sensors**
- **IMU (ICM-42605):**  
  - Accelerometer and Gyroscope  
  - Interrupt Pins: **INT1** and **INT2/FSYNC**  

### **User Interface**
- **RGB LED:** Controlled via 3 PWM GPIOs:  
  - **GPIO10:** Red Channel  
  - **GPIO11:** Green Channel  
  - **GPIO12:** Blue Channel  
- **External Button:** GPIO Input for interrupts  

---

## Pinout Table

| **Pin Name**       | **ESP32-C6 GPIO**  | **Description**                  | **Function**           |
|---------------------|--------------------|----------------------------------|------------------------|
| **+V_BAT**         | -                  | Battery Input Voltage            | Power Supply           |
| **+3V3**           | -                  | 3.3V Regulated Output            | Power Supply           |
| **+V_POWER_IN**    | -                  | 5V Input                         | Power Supply           |
| **GND**            | -                  | Ground                           | Power Supply           |
| **ESP32_I2C_SCL**  | GPIO8              | I2C Clock                        | I2C Communication      |
| **ESP32_I2C_SDA**  | GPIO9              | I2C Data                         | I2C Communication      |
| **DRV_FAULTN**     | GPIO7              | Motor Driver Fault Interrupt     | GPIO Input             |
| **Motor_P**        | -                  | Motor Driver Output Positive     | Motor Control          |
| **Motor_N**        | -                  | Motor Driver Output Negative     | Motor Control          |
| **ICM_INT1/INT**   | GPIO5              | IMU Interrupt Pin 1              | IMU Communication      |
| **ICM_INT2/FSYNC** | GPIO6              | IMU Interrupt Pin 2 / Sync Pin   | IMU Communication      |
| **LED_PWM_RED**    | GPIO10             | Red Channel of RGB LED           | PWM Output             |
| **LED_PWM_GREEN**  | GPIO11             | Green Channel of RGB LED         | PWM Output             |
| **LED_PWM_BLUE**   | GPIO12             | Blue Channel of RGB LED          | PWM Output             |
| **BUTTON**         | GPIO4              | External Button Input            | GPIO Input             |
| **VBAT_MEAS**      | GPIO3              | Battery Voltage Meas. 1:2 Ratio  | ADC Input              |
| **VIN_MEAS**       | GPIO2              | Input Voltage Meas. 1:2 Ratio    | ADC Input              |
| **ESP32_ENABLE**   | GPIO1              | Enable Pin for ESP32             | GPIO Control           |

---

## Schematics

The schematics for the project are available:

[esp32_c6_a1_schematic.PDF](https://github.com/user-attachments/files/18142218/esp32_c6_a1_schematic.PDF)



- **Top Page:** High-level connectivity overview
- **SoC Integration:** ESP32-C6 Wifi/BT SoC
- **Power Circuit:** Battery, Charger, and Regulator design
- **Sensors and GPIOs:** ICM-42605, Button, and LED connections



---

### Credits
Designed and documented by **Ali Fatih Demir**.

---
