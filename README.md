# Smart IoT Robot Car with Node-RED Control

[cite_start]This repository contains the implementation of a **Smart IoT Robot Car** powered by an **ESP32** and controlled via a custom **Node-RED Dashboard**[cite: 1, 21, 22]. [cite_start]The project features a robust data pipeline that transforms raw ultrasonic sensor readings into actionable environmental classifications, including automated NaN mitigation for reliable navigation[cite: 13, 19, 40].

---

## 🚀 Project Overview
[cite_start]This project implements a smart mobile robot car controlled through an IoT dashboard[cite: 21]. [cite_start]The robot uses a scanning ultrasonic array to map its surroundings, allowing it to differentiate between safe traversal zones and structural hazards[cite: 16, 17, 42].

### Key Features
* [cite_start]**Security**: A secure login flow prevents access to robot controls until credentials are checked[cite: 62, 63].
* [cite_start]**Real-Time Control**: Manual movement commands (Forward, Back, Left, Right, Stop) and an autonomous "Auto Mode"[cite: 23, 50].
* [cite_start]**Data Logging**: Automated CSV generation (`robot_data.csv`) that logs timestamps and distance readings for further analysis[cite: 23, 35, 53].
* [cite_start]**Intelligent Sensing**: A 180-degree scanning ultrasonic sensor handles "NaN" readings by mapping them to a maximum sensor range (e.g., 400 cm) to indicate a clear path[cite: 29, 40, 42].
* [cite_start]**Live Analytics**: A dynamic dashboard featuring live line charts for real-time distance monitoring[cite: 53, 64].

---

## 🛠 Hardware Components
* [cite_start]**Microcontroller**: ESP32 DevKitV1[cite: 26].
* [cite_start]**Motor Driver**: L298N Dual H-Bridge[cite: 27].
* [cite_start]**Sensors**: HC-SR04 Ultrasonic Distance Sensor[cite: 28].
* [cite_start]**Actuators**: 2x DC Motors and an SG90 Servo Motor for 180-degree scanning[cite: 22, 29].
* [cite_start]**Chassis**: 2WD acrylic robot chassis with a front caster wheel[cite: 25].
* [cite_start]**Power**: Battery-powered with a USB serial connection for communication[cite: 30].

---

## 💻 Software & Workflow
[cite_start]The dashboard was created using `node-red-dashboard` and `node-red-node-serialport`[cite: 49].

* [cite_start]**Communication**: Commands are transmitted through serial communication on **COM10** at **115200 baud**[cite: 51].
* **Login Credentials**:
    * **Username**: `admin`
    * **Password**: `1234`
* [cite_start]**Data Pipeline**: Raw Time-of-Flight (ToF) data is cleaned, normalized, and processed using PCA and Wavelet Transforms for edge detection and noise filtering[cite: 43, 45, 46].

### Classification Categories
The processed features are classified into three categories:
1.  [cite_start]**Class 0**: Clear Path [cite: 47]
2.  [cite_start]**Class 1**: Linear Obstacle [cite: 47]
3.  [cite_start]**Class 2**: Corner or Complex Obstacle [cite: 47]

---

## 📈 Performance Metrics
[cite_start]The system was especially effective at identifying clear paths due to the NaN mitigation logic[cite: 59].

| Metric | Value |
| :--- | :--- |
| **Accuracy** | [cite_start]0.89 [cite: 57] |
| **Precision** | [cite_start]0.87 [cite: 57] |
| **Recall** | [cite_start]0.85 [cite: 57] |
| **F1-score** | [cite_start]0.86 [cite: 57] |

---

## 👥 Team Members
* [cite_start]Avronia Magdy Tawfik Boutros (202303908) [cite: 5]
* [cite_start]Amira Samy Ebrahim (202301561) [cite: 6]
* [cite_start]Sandra Samer Samir (202303334) [cite: 7]
* [cite_start]Rosana Zarif Sadek Semean (202303306) [cite: 8]
* [cite_start]Merhan Hossam Mohamad (202301681) [cite: 9]
