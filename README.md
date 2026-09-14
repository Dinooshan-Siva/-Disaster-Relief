# 🌍 Embedded Monitoring System for Post-Disaster Supply Transport

> An ATmega328P-based embedded monitoring system designed to continuously monitor temperature and humidity during the transportation and storage of temperature-sensitive post-disaster relief supplies.

![MCU](https://img.shields.io/badge/MCU-ATmega328P-blue)
![Language](https://img.shields.io/badge/Language-Embedded%20C-orange)
![Communication](https://img.shields.io/badge/Communication-I2C-green)
![Domain](https://img.shields.io/badge/Domain-Embedded%20Systems-purple)
![Application](https://img.shields.io/badge/Application-Disaster%20Relief-red)
![University](https://img.shields.io/badge/University-University%20of%20Jaffna-success)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📌 Project Overview

Post-disaster relief operations require the safe transportation and storage of essential supplies such as medicines, vaccines, food items, and medical kits.

Many of these supplies are sensitive to environmental conditions. Exposure to temperature or humidity levels outside their safe operating ranges can affect their quality, effectiveness, and usability.

This project presents a portable and low-power **embedded environmental monitoring system** designed to continuously monitor temperature and humidity during the transportation and storage of relief supplies.

The system is built around a standalone **ATmega328P microcontroller** and provides real-time environmental monitoring with threshold-based alerts.

When the measured temperature or humidity exceeds predefined safety limits, the system generates an alert so that timely corrective action can be taken.

The system is designed to be:

* 🔋 Low Power
* 💰 Cost Effective
* 📦 Portable
* ⚡ Reliable
* 🌍 Suitable for Disaster Relief Applications

---

## 🎯 Objectives

The main objectives of this project are:

* Develop a standalone ATmega328P-based monitoring system.
* Continuously monitor temperature and humidity.
* Detect environmental conditions outside predefined safety limits.
* Generate real-time alerts for abnormal environmental conditions.
* Display environmental measurements through a monitoring interface.
* Implement I2C-based communication.
* Develop a portable and low-power system architecture.
* Provide a cost-effective monitoring solution for disaster relief operations.
* Improve the safety and reliability of temperature-sensitive relief supplies during transportation and storage.

---

## 🏗️ System Architecture

```text
                     ┌────────────────────┐
                     │ Temperature Sensor │
                     └──────────┬─────────┘
                                │
                                │
                     ┌──────────▼─────────┐
                     │  Humidity Sensor   │
                     └──────────┬─────────┘
                                │
                              I2C Bus
                          SDA   │   SCL
                                │
                     ┌──────────▼─────────┐
                     │     ATmega328P     │
                     │  Microcontroller   │
                     └──────────┬─────────┘
                                │
                 ┌──────────────┼──────────────┐
                 │              │              │
                 ▼              ▼              ▼
          Data Processing   Threshold       Alert System
                            Analysis
                 │              │              │
                 └──────────────┼──────────────┘
                                │
                                ▼
                     Monitoring Interface
                                │
                                ▼
                     Environmental Status
```

---

## ⚙️ Working Principle

The monitoring system continuously acquires environmental measurements from temperature and humidity sensors.

The **ATmega328P microcontroller** receives the sensor data through the **I2C communication protocol**, processes the measurements, and compares them against predefined threshold values.

The general operating sequence is:

```text
                         START
                           │
                           ▼
                  Initialize ATmega328P
                           │
                           ▼
                     Initialize I2C
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
                     ┌─────┴─────┐
                     │           │
                     ▼           ▼
                  NORMAL      ABNORMAL
                     │           │
                     ▼           ▼
               Display Data   Activate Alert
                     │           │
                     └─────┬─────┘
                           │
                           ▼
                  Continue Monitoring
```

---

## 🔍 Environmental Monitoring

### 🌡️ Temperature Monitoring

The temperature sensor continuously measures the environmental temperature surrounding the transported or stored supplies.

The measured temperature is transferred to the **ATmega328P microcontroller** and compared with the predefined safe temperature range.

If the measured temperature exceeds the specified threshold, the system activates the corresponding alert mechanism.

---

### 💧 Humidity Monitoring

Humidity is continuously monitored because excessive or unsuitable humidity levels can negatively affect certain relief supplies and storage environments.

The measured humidity value is transferred to the microcontroller and compared against the configured threshold.

If the humidity exceeds the acceptable range, the system generates an appropriate warning.

---

## 🚨 Alert Mechanism

The system uses a threshold-based decision mechanism to identify abnormal environmental conditions.

```text
                 Sensor Measurement
                        │
                        ▼
                 Compare With Limit
                        │
                 ┌──────┴──────┐
                 │             │
                 ▼             ▼
          Within Safe Range   Limit Exceeded
                 │             │
                 ▼             ▼
          Normal Operation       ALERT
                 │             │
                 └──────┬──────┘
                        │
                        ▼
                 Continue Monitoring
```

This mechanism allows abnormal environmental conditions to be detected quickly and provides an opportunity for timely intervention.

---

## 📡 I2C Communication

The system uses **I2C (Inter-Integrated Circuit)** communication for data transfer between the **ATmega328P microcontroller** and compatible sensors or peripheral devices.

I2C is a synchronous serial communication protocol that requires only two communication lines:

* **SDA — Serial Data Line**
* **SCL — Serial Clock Line**

The ATmega328P acts as the main controller and communicates with the connected I2C devices using their respective addresses.

### I2C Communication Architecture

```text
        ┌────────────────────┐
        │ Temperature Sensor │
        └──────────┬─────────┘
                   │
                   │
        ┌──────────▼─────────┐
        │  Humidity Sensor   │
        └──────────┬─────────┘
                   │
                I2C Bus
             SDA   │   SCL
                   │
        ┌──────────▼─────────┐
        │     ATmega328P     │
        │  Microcontroller   │
        └──────────┬─────────┘
                   │
                   ▼
            Data Processing
                   │
                   ▼
          Environmental Status
```

The I2C protocol enables efficient communication between the microcontroller and multiple peripheral devices while requiring only two communication lines.

---

## 🔌 I2C Connections

For the ATmega328P, the I2C communication pins are:

| Signal | ATmega328P Pin | Function     |
| ------ | -------------- | ------------ |
| SDA    | PC4 / ADC4     | Serial Data  |
| SCL    | PC5 / ADC5     | Serial Clock |
| VCC    | VCC            | Power Supply |
| GND    | GND            | Ground       |

A typical I2C connection can be represented as:

```text
               ATmega328P
          ┌───────────────────┐
          │                   │
      PC4 │ SDA           VCC │
          │  │                │
      PC5 │ SCL           GND │
          │  │                │
          └──┼────────────────┘
             │
        ┌────┴──────────────┐
        │      I2C Bus      │
        └────┬─────────┬────┘
             │         │
             ▼         ▼
       Temperature   Humidity
         Sensor       Sensor
```

---

## 🧩 Hardware Components

The major components used in the system include:

* **ATmega328P Microcontroller**
* **Temperature Sensor**
* **Humidity Sensor**
* **Display / Monitoring Interface**
* **Resistors**
* **Capacitors**
* **I2C Pull-Up Resistors**
* **Power Supply**
* **Supporting Electronic Components**

---

## 💻 Software & Technologies

| Category                 | Technology                     |
| ------------------------ | ------------------------------ |
| Microcontroller          | ATmega328P                     |
| Programming Language     | Embedded C                     |
| Communication Protocol   | I2C                            |
| Communication Lines      | SDA & SCL                      |
| Environmental Monitoring | Temperature & Humidity Sensors |
| Interface                | Real-Time Monitoring Interface |
| System Type              | Embedded Monitoring System     |
| Application              | Disaster Relief Logistics      |

---

## 🔌 Hardware Design

The system was designed around a **standalone ATmega328P microcontroller** rather than relying on a complete development board.

This approach provides greater control over the hardware architecture and allows the system to be optimized for:

* Portability
* Low power consumption
* Cost reduction
* Compact implementation
* Resource-constrained environments

The temperature and humidity sensors communicate with the microcontroller through the **I2C bus**.

Pull-up resistors are used on the **SDA** and **SCL** communication lines to ensure reliable I2C communication.

### Circuit Diagram

Add your circuit diagram inside the `Images` folder:

```markdown
![Circuit Diagram](Images/Circuit_Diagram.png)
```

> **Note:** Make sure the filename matches the actual circuit diagram uploaded to your `Images` folder.

---

## 🖥️ Monitoring Interface

A user-friendly monitoring interface was developed to display environmental measurements obtained by the embedded system.

The interface provides real-time visibility of:

* 🌡️ Temperature
* 💧 Humidity
* 🟢 Environmental Status
* 🚨 Alert Conditions

### Interface Screenshot

Add your monitoring interface screenshot using:

```markdown
![Monitoring Interface](Images/Monitoring_Interface.png)
```

> Make sure the filename matches the screenshot uploaded to your `Images` folder.

---

## 📊 Results

The developed embedded monitoring system was tested under different environmental conditions.

The system successfully demonstrated:

* ✅ Continuous temperature monitoring
* ✅ Continuous humidity monitoring
* ✅ Real-time display of sensor measurements
* ✅ Threshold-based environmental monitoring
* ✅ Detection of abnormal temperature conditions
* ✅ Detection of abnormal humidity conditions
* ✅ Real-time alert generation
* ✅ I2C-based sensor communication
* ✅ Reliable data transfer through SDA and SCL
* ✅ Reliable operation using the ATmega328P microcontroller

---

## 🧪 Testing

Testing was performed under different environmental conditions to verify the operation of the monitoring, communication, and alert mechanisms.

| Test Condition                       | Expected Response                 |
| ------------------------------------ | --------------------------------- |
| Normal Temperature                   | Normal Operation                  |
| High Temperature                     | Temperature Alert                 |
| Normal Humidity                      | Normal Operation                  |
| High Humidity                        | Humidity Alert                    |
| Temperature & Humidity Within Limits | Normal Monitoring                 |
| Multiple Abnormal Conditions         | Appropriate Alerts                |
| I2C Sensor Communication             | Sensor Data Successfully Received |
| I2C Communication Failure            | Sensor / Communication Error      |

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
                        │
              ┌─────────▼──────────┐
              │   Humidity Sensor  │
              └─────────┬──────────┘
                        │
                      I2C Bus
                  SDA   │   SCL
                        │
                        ▼
                 ┌─────────────┐
                 │  ATmega328P │
                 │     MCU     │
                 └──────┬──────┘
                        │
                        ▼
                  Data Processing
                        │
                        ▼
                Threshold Comparison
                        │
                   ┌────┴────┐
                   │         │
                   ▼         ▼
                Normal    Abnormal
                   │         │
                   ▼         ▼
              Display Data   Alert
                   │         │
                   └────┬────┘
                        │
                        ▼
                 User Monitoring
```

---

## 👨‍💻 My Contributions

* Designed the complete embedded monitoring architecture.
* Developed the ATmega328P-based embedded system.
* Programmed the microcontroller using Embedded C.
* Integrated temperature and humidity sensors.
* Implemented I2C communication.
* Configured SDA and SCL communication.
* Implemented sensor data acquisition using I2C.
* Implemented threshold-based alert mechanisms.
* Developed the real-time monitoring interface.
* Performed hardware integration and system testing.
* Debugged and optimized the complete system.
* Designed the system for portable and low-power operation.

---

## 🧠 Skills Demonstrated

* Embedded Systems
* Embedded C Programming
* ATmega328P Programming
* Microcontroller Architecture
* Sensor Interfacing
* I2C Communication
* I2C Sensor Interfacing
* SDA / SCL Configuration
* Hardware-Software Integration
* Electronic Circuit Design
* Real-Time Monitoring
* Low-Power System Design
* Hardware Debugging
* System Testing

---

## 🚀 Future Improvements

Possible future enhancements include:

* 📡 Wireless communication using ESP32 / LoRa
* 📍 GPS-based supply tracking
* ☁️ Cloud-based environmental monitoring
* 📱 Mobile application integration
* 🌐 IoT-based remote monitoring
* 💾 Data logging and historical analysis
* 🔋 Battery and power-consumption monitoring
* 🧠 Predictive analysis of environmental conditions
* 📊 Remote environmental data visualization
* 📡 Wireless alert notifications

---

## 📁 Suggested Repository Structure

```text
Embedded-Monitoring-System/
│
├── README.md
│
├── Code/
│   ├── main.c
│   ├── i2c.c
│   ├── i2c.h
│   ├── sensors.c
│   └── sensors.h
│
├── Images/
│   ├── Circuit_Diagram.png
│   ├── Monitoring_Interface.png
│   ├── Prototype.png
│   └── System_Block_Diagram.png
│
├── Documentation/
│   ├── Project_Report.pdf
│   └── Circuit_Design.pdf
│
└── LICENSE
```

---

## 📂 Source Code Structure

The embedded software can be organized into separate modules:

```text
main.c
│
├── System Initialization
├── I2C Initialization
├── Sensor Initialization
├── Temperature Reading
├── Humidity Reading
├── Threshold Comparison
├── Alert Control
└── Continuous Monitoring

i2c.c / i2c.h
│
├── I2C Initialization
├── I2C Start
├── I2C Stop
├── I2C Write
├── I2C Read
└── Device Communication

sensors.c / sensors.h
│
├── Sensor Initialization
├── Temperature Acquisition
└── Humidity Acquisition
```

---

## 🎓 Academic Information

### Project Title

**Embedded Monitoring System for Post-Disaster Supply Transport**

### Institution

**University of Jaffna**

### Project Area

**Embedded Systems and Design**

### Project Duration

**February 2026 – April 2026**

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
  <b>Embedded Monitoring System for Post-Disaster Supply Transport</b>
</p>

<p align="center">
  Developed by <b>Dinooshan</b>
</p>

<p align="center">
  Department of Electrical and Electronic Engineering<br>
  University of Jaffna
</p>
