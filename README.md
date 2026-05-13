# Smart IoT Robot Car with Node-RED Control

This repository contains the implementation of a **Smart IoT Robot Car** powered by an **ESP32** and controlled via a custom **Node-RED Dashboard**The project features a robust data pipeline that transforms raw ultrasonic sensor readings into actionable environmental classifications, including automated NaN mitigation for reliable navigation.

---

## 🚀 Project Overview
This project implements a smart mobile robot car controlled through an IoT dashboard The robot uses a scanning ultrasonic array to map its surroundings, allowing it to differentiate between safe traversal zones and structural hazards

### Key Features
* **Security**: A secure login flow prevents access to robot controls until credentials are checked
***Real-Time Control**: Manual movement commands (Forward, Back, Left, Right, Stop) and an autonomous "Auto Mode"
  **Data Logging**: Automated CSV generation (`robot_data.csv`) that logs timestamps and distance readings for further analysis
* **Intelligent Sensing**: A 180-degree scanning ultrasonic sensor handles "NaN" readings by mapping them to a maximum sensor range (e.g., 400 cm) to indicate a clear path
* **Live Analytics**: A dynamic dashboard featuring live line charts for real-time distance monitoring

---

## 🛠 Hardware Components
* **Microcontroller**: ESP32 DevKitV1
* **Motor Driver**: L298N Dual H-Bridge
* **Sensors**: HC-SR04 Ultrasonic Distance Sensor
* **Actuators**: 2x DC Motors and an SG90 Servo Motor for 180-degree scanning
* **Chassis**: 2WD acrylic robot chassis with a front caster wheel
* **Power**: Battery-powered with a USB serial connection for communication

---

## 💻 Software & Workflow
The dashboard was created using `node-red-dashboard` and `node-red-node-serialport`

* **Communication**: Commands are transmitted through serial communication on **COM10** at **115200 baud**
* **Login Credentials**:
    * **Username**: `admin`
    * **Password**: `1234`
***Data Pipeline**: Raw Time-of-Flight (ToF) data is cleaned, normalized, and processed using PCA and Wavelet Transforms for edge detection and noise filtering

### Classification Categories
The processed features are classified into three categories:
1. **Class 0**: Clear Path
2.**Class 1**: Linear Obstacle 
3. **Class 2**: Corner or Complex Obstacle 

---

## 📈 Performance Metrics
The system was especially effective at identifying clear paths due to the NaN mitigation logic

| Metric | Value |
| :--- | :--- |
| **Accuracy** | 0.89 
| **Precision** |0.87 
| **Recall** | 0.85 
| **F1-score** |0.86 

---
