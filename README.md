# IoT-Based Smart Agriculture Monitoring System

## Problem Statement
Design an IoT-based monitoring solution for agriculture to monitor soil parameters and trigger alerts.

## Scenario
This project focuses on monitoring soil moisture and temperature in agricultural fields and triggers an irrigation alert when soil moisture goes below a defined threshold.

## System Architecture
The system consists of sensors connected to a microcontroller, which sends data to the cloud through a gateway. The cloud processes the data and sends alerts to the user.

### Architecture Flow
Soil Moisture Sensor + Temperature Sensor  
↓  
ESP32 Microcontroller (Edge Device)  
↓  
Wi-Fi Gateway  
↓  
Cloud Server  
↓  
Dashboard / Alert System  

## Sensor Selection and Justification
- **Soil Moisture Sensor**: Measures the water content in soil and helps decide irrigation needs.
- **Temperature Sensor (DHT11/DHT22)**: Measures ambient temperature which affects crop growth.
- **ESP32 Microcontroller**: Built-in Wi-Fi, low power consumption, and easy cloud integration.

## Data Flow Explanation
1. Sensors collect real-time soil moisture and temperature data.
2. Sensor data is sent to the ESP32 microcontroller.
3. ESP32 transmits the data to the cloud using Wi-Fi.
4. Cloud stores and analyzes the data.
5. If soil moisture falls below the threshold, an alert is generated.
6. Users can monitor data and alerts on a dashboard.

## Alert Logic
If soil moisture < 30%, irrigation alert is triggered.

## Sample JSON Output
```json
{
  "device_id": "ESP32_001",
  "timestamp": "2026-02-07T10:30:00",
  "soil_moisture": 28,
  "temperature": 35,
  "status": "ALERT",
  "message": "Soil moisture low. Irrigation required."
}
