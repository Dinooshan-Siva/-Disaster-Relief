# 🌍 Embedded Monitoring System for Post-Disaster Supply Transport

> An ATmega328P-based embedded monitoring system designed to continuously monitor temperature and humidity during the transportation and storage of temperature-sensitive post-disaster relief supplies.

![MCU](https://img.shields.io/badge/MCU-ATmega328P-blue)
![Language](https://img.shields.io/badge/Language-Embedded%20C-orange)
![Communication](https://img.shields.io/badge/Communication-UART-green)
![Domain](https://img.shields.io/badge/Domain-Embedded%20Systems-purple)
![Application](https://img.shields.io/badge/Application-Disaster%20Relief-red)
![University](https://img.shields.io/badge/University-University%20of%20Jaffna-success)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📌 Project Overview

Post-disaster relief operations require the safe transportation and storage of essential supplies such as medicines, vaccines, food items, and medical kits.

Many of these supplies are sensitive to environmental conditions. Exposure to unsuitable temperature or humidity levels can affect their quality, effectiveness, and usability.

This project presents a **portable and low-power embedded environmental monitoring system** designed to continuously monitor temperature and humidity during the transportation and storage of relief supplies.

The system is built around a standalone **ATmega328P microcontroller** and provides real-time environmental monitoring with threshold-based alerts.

When temperature or humidity exceeds predefined safety limits, the system generates an alert so that corrective action can be taken.

The system is designed to be:

- 🔋 Low Power
- 💰 Cost Effective
- 📦 Portable
- ⚡ Reliable
- 🌍 Suitable for Disaster Relief Applications

---

## 🎯 Objectives

The main objectives of this project are:

- Develop a standalone ATmega328P-based monitoring system.
- Continuously monitor temperature and humidity.
- Detect environmental conditions outside predefined safety limits.
- Generate real-time alerts for abnormal conditions.
- Display environmental measurements through a monitoring interface.
- Implement UART-based communication.
- Develop a portable and low-power system architecture.
- Provide a cost-effective monitoring solution for disaster relief operations.
- Improve the safety of temperature-sensitive relief supplies.

---

## 🏗️ System Architecture

```text
                ┌────────────────────┐
                │ Temperature Sensor │
                └─────────┬──────────┘
                          │
                          ▼
                ┌────────────────────┐
                │  Humidity Sensor   │
                └─────────┬──────────┘
                          │
                          ▼
                ┌────────────────────┐
                │     ATmega328P     │
                │  Microcontroller   │
                └─────────┬──────────┘
                          │
             ┌────────────┼────────────┐
             │            │            │
             ▼            ▼            ▼
       Data Processing    UART      Alert System
             │            │            │
             │            ▼            │
             │     Monitoring          │
             │      Interface          │
             │                         │
             └────────────┬────────────┘
                          │
                          ▼
                Environmental Status
```

---

## ⚙️ Working Principle

The system continuously obtains environmental measurements from the temperature and humidity sensors.

The **ATmega328P** processes the sensor data and compares the measured values with predefined safety thresholds.

```text
                    START
                      │
                      ▼
              Initialize ATmega328P
                      │
                      ▼
               Initialize Sensors
                      │
                      ▼
          Read Temperature & Humidity
                      │
                      ▼
              Process Sensor Data
                      │
                      ▼
            Compare With Thresholds
                      │
               ┌──────┴──────┐
               │             │
               ▼             ▼
            NORMAL        ABNORMAL
               │             │
               ▼             ▼
          Display Data   Activate Alert
               │             │
               └──────┬──────┘
                      │
                      ▼
             Continue Monitoring
```

---

## 🌡️ Temperature Monitoring

The temperature sensor continuously measures the environmental temperature surrounding the transported or stored supplies.

The ATmega328P processes the measured temperature and compares it with the predefined safe operating range.

If the temperature exceeds the configured threshold, the system activates an alert.

---

## 💧 Humidity Monitoring

Humidity is continuously monitored to protect relief supplies from unsuitable environmental conditions.

The measured humidity value is compared against a predefined threshold.

If the humidity exceeds the acceptable range, the system generates a warning.

---

## 🚨 Alert Mechanism

The system uses a **threshold-based decision mechanism** to identify abnormal environmental conditions.

```text
            Sensor Measurement
                    │
                    ▼
            Compare With Limit
                    │
             ┌──────┴──────┐
             │             │
             ▼             ▼
       Within Range    Limit Exceeded
             │             │
             ▼             ▼
      Normal Operation    ALERT
             │             │
             └──────┬──────┘
                    │
                    ▼
            Continue Monitoring
```

This allows abnormal environmental conditions to be detected quickly and enables timely corrective action.

---

## 📡 UART Communication

UART communication is used to transfer sensor measurements between the embedded system and the monitoring interface.

```text
Temperature Sensor ──┐
                     │
Humidity Sensor ─────┤
                     │
                     ▼
               ┌────────────┐
               │ ATmega328P │
               │    MCU     │
               └─────┬──────┘
                     │
                    UART
                     │
                     ▼
            Monitoring Interface
                     │
                     ▼
              Real-Time Data
```

---

## 🧩 Hardware Components

The major hardware components include:

| Component | Purpose |
|---|---|
| ATmega328P | Main microcontroller |
| Temperature Sensor | Environmental temperature measurement |
| Humidity Sensor | Environmental humidity measurement |
| Monitoring Interface | Display real-time measurements |
| Power Supply | Provides system power |
| Resistors & Capacitors | Circuit support and conditioning |
| Supporting Components | Hardware integration |

---

## 💻 Software & Technologies

| Category | Technology |
|---|---|
| Microcontroller | ATmega328P |
| Programming Language | Embedded C |
| Communication | UART |
| Sensors | Temperature & Humidity |
| Interface | Real-Time Monitoring Interface |
| System Type | Embedded Monitoring System |
| Application | Disaster Relief Logistics |

---

## 🔌 Hardware Design

The system is designed around a **standalone ATmega328P microcontroller** instead of relying on a complete development board.

This allows the hardware architecture to be optimized for:

- Portability
- Low power consumption
- Cost reduction
- Compact implementation
- Resource-constrained environments

### 📐 Circuit Diagram

Add the circuit diagram to the `Images` folder and use:

```markdown
![Circuit Diagram](Images/Circuit_Diagram.png)
```

---

## 🖥️ Monitoring Interface

A monitoring interface is used to display environmental information received from the embedded system.

The interface provides real-time visibility of:

- 🌡️ Temperature
- 💧 Humidity
- 🟢 Environmental Status
- 🚨 Alert Conditions

### Interface Screenshot

```markdown
![Monitoring Interface](Images/Monitoring_Interface.png)
```

---

## 📊 Results

The developed embedded monitoring system was tested under different environmental conditions.

The system successfully demonstrated:

- ✅ Continuous temperature monitoring
- ✅ Continuous humidity monitoring
- ✅ Real-time sensor measurement display
- ✅ Threshold-based environmental monitoring
- ✅ Abnormal temperature detection
- ✅ Abnormal humidity detection
- ✅ Real-time alert generation
- ✅ UART-based communication
- ✅ Reliable ATmega328P operation

---

## 🧪 Testing

| Test Condition | Expected Response |
|---|---|
| Normal Temperature | Normal Operation |
| High Temperature | Temperature Alert |
| Normal Humidity | Normal Operation |
| High Humidity | Humidity Alert |
| Temperature & Humidity Within Limits | Normal Monitoring |
| Multiple Abnormal Conditions | Appropriate Alerts |

---

## 📈 System Workflow

```text
          Environmental Conditions
                    │
                    ▼
          ┌────────────────────┐
          │ Temperature Sensor │
          └─────────┬──────────┘
                    │
                    ▼
          ┌────────────────────┐
          │  Humidity Sensor   │
          └─────────┬──────────┘
                    │
                    ▼
              ┌───────────┐
              │ ATmega328P│
              │    MCU    │
              └─────┬─────┘
                    │
                    ▼
              Data Processing
                    │
                    ▼
           Threshold Comparison
                    │
              ┌─────┴─────┐
              │           │
              ▼           ▼
           Normal      Abnormal
              │           │
              ▼           ▼
         Display Data    Alert
              │           │
              └─────┬─────┘
                    │
                    ▼
              UART Interface
                    │
                    ▼
              User Monitoring
```

---

## 👨‍💻 My Contributions

- Designed the embedded monitoring architecture.
- Developed the ATmega328P-based embedded system.
- Programmed the microcontroller using Embedded C.
- Integrated temperature and humidity sensors.
- Implemented threshold-based alert mechanisms.
- Implemented UART communication.
- Developed the real-time monitoring interface.
- Performed hardware integration and system testing.
- Debugged and optimized the complete system.
- Designed the system for portable and low-power operation.

---

## 🧠 Skills Demonstrated

- Embedded Systems
- Embedded C Programming
- ATmega328P Programming
- Microcontroller Architecture
- Sensor Interfacing
- UART Communication
- Hardware-Software Integration
- Electronic Circuit Design
- Real-Time Monitoring
- Low-Power System Design
- Hardware Debugging
- System Testing

---

## 🚀 Future Improvements

Possible future developments include:

- 📡 Wireless communication using ESP32 / LoRa
- 📍 GPS-based supply tracking
- ☁️ Cloud-based environmental monitoring
- 📱 Mobile application integration
- 🌐 IoT-based remote monitoring
- 💾 Environmental data logging
- 📊 Historical data analysis
- 🔋 Battery and power-consumption monitoring
- 🧠 Predictive analysis of environmental conditions

---

## 🎓 Academic Information

**Project Title:**  
Embedded Monitoring System for Post-Disaster Supply Transport

**Institution:**  
University of Jaffna

**Project Area:**  
Embedded Systems and Design

**Project Duration:**  
Dec 2025 – April 2026

---

# 👤 Author

## Dinooshan

**Final Year Undergraduate**  
Department of Electrical and Electronic Engineering  
University of Jaffna

---

## ⭐ Support

If you found this project useful or interesting, consider giving the repository a **⭐ Star**.

---

<p align="center">
  Developed by <b>Dinooshan</b><br>
  Department of Electrical and Electronic Engineering<br>
  University of Jaffna
</p>
