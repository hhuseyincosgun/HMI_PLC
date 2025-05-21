# Siemens PLC - Product Transfer System

## 🚀 Project Overview

- 🎯 **Goal**: Automatically transfer a defined number of products based on their color using a color sensor.
- ⚙️ **System**: A conveyor belt detects products (Green or Blue) and separates them using actuators.
- 📥 **User Input**: Enter the number of products to transfer via HMI.
- 🟢 **Process Start**: Press `Start` to initiate transfer.
- 🛑 **Stop**: Press `Stop` to pause operation.
- 🔁 **Reset**: Press `Reset` to clear product count and start fresh.
- ✅ **Auto Stop**: System stops automatically when the required product quantity is reached.

This project simulates a **Product Transfer System** using Siemens PLC, HMI (SIMATIC), and a 3D virtual environment. It detects product colors and transfers them to the correct line based on the specified quantity.

🏭 Product Transfer System Simulation

[![System Operation Demo](https://github.com/hhuseyincosgun/HMI_PLC/blob/main/demo.gif)](https://github.com/hhuseyincosgun/HMI_PLC/blob/main/demo.gif)  
 
## 🧩 Components Used

- Siemens S7- CPU 1211C PLC (or compatible)
- SIMATIC HMI Panel - KTP700 Basic PN (Profinet)
- Factory I/O (3D simulation software)


# Project Structure Overview

This document provides a simplified overview of the project directory structure, focusing on the core components for a Programmable Logic Controller (PLC) and Human Machine Interface (HMI) application.

## Project Directory Tree
```
Project/
├── PLC_1/
│ ├── Device configuration
│ ├── Program blocks
│ ├── PLC tags
│ │── Online backups
└── HMI_1/
├── Device configuration
├── Screens
├── HMI tags
└── Connections
```  

---
## 🏭 Factory IO Simulation

Below is the layout of the Factory IO simulation used in this project:

![FactoryIO Simulation](https://github.com/hhuseyincosgun/HMI_PLC/raw/main/FactoryIO.png)

---

## 📊 HMI Display Features

- **System Status**: Shows real-time operation info (e.g., "Green product is being transferred").
- **Product Quantity Input**: Enter number of items to transfer.
- **Blue Product Count**: Live count of blue items transferred.
- **Green Product Count**: Live count of green items transferred.
- **Control Buttons**: Start, Stop, Reset.

---


![HMI Interface](https://github.com/hhuseyincosgun/HMI_PLC/raw/main/HMI.png)

---



## 📷 Vision Sensor Details

The system uses a **Vision Sensor** to detect product type and color on the conveyor belt.

### 🔧 Sensor Specifications

- **Type**: Vision Sensor  
- **Detection**: Raw Materials, Product Lids, Product Bases  
- **Color Detection**: Blue, Green, Metal  
- **LED Indicator**: Red (when detecting)  
- **Sensing Range**: 0.3 - 2 meters

---

### 🔢 Operating Modes

The Vision Sensor can be configured to output in different modes:

| Mode            | Description                                                       |
|-----------------|-------------------------------------------------------------------|
| **All Digital**   | Outputs four digital signals (bits) for each item               |
| **All Numerical** | Outputs a numerical code (1–9) based on the item detected       |
| **All ID**        | Outputs a unique identifier (like RFID/barcode) for each item   |

### 🔧 Sensor Specifications

- **Sensor Type**: Vision Sensor  
- **Detection**: Product Lids and Product Bases  
- **Colors Used in This Project**: Green and Blue  
- **Sensing Range**: 0.3 – 2 meters  
- **Detection Indicator**: Red LED (active while detecting)  
- **PLC Interface**: Analog input (IW30)  
- **Sensor Mode**: All Numerical (returns integer values)

---
---

### 🧬 Detection Encoding Table

| Item                  | All Digital (Bits 0–3) | All Numerical | All ID |
|-----------------------|------------------------|----------------|--------|
| None                  | 0000                   | 0              | 0      |
| Blue Raw Material     | 1000                   | 1              | ID     |
| Blue Product Lid      | 0100                   | 2              | ID     |
| Blue Product Base     | 1100                   | 3              | ID     |
| Green Raw Material    | 0010                   | 4              | ID     |
| Green Product Lid     | 1010                   | 5              | ID     |
| Green Product Base    | 0110                   | 6              | ID     |
| Metal Raw Material    | 1110                   | 7              | ID     |
| Metal Product Lid     | 0001                   | 8              | ID     |
| Metal Product Base    | 1001                   | 9              | ID     |

---








