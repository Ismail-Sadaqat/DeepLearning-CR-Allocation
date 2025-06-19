# Cognitive Radio Spectrum Sensing and Allocation: A Low-Complexity Deep Learning Approach

A low-complexity deep learning-based cognitive radio system for intelligent spectrum sensing and dynamic allocation, with a hardware implementation to enhance spectral efficiency.

## Team Memebers
- Hamza Ahmed Abushahla  
- Ghanim Abdulla Alarai Al-Ali  
- Sultan Khalid Abdalla  
- Muhammad Ismail Sadaqat

## Supervisor
- Dr. Mohamed AlHajri  
- Dr. Taha Landolsi

**Date Submitted**: May 4, 2024

## Abstract
The rapid growth of mobile devices, IoT applications, and other connected technologies has placed immense pressure on spectrum resources, pushing 4G and 5G networks to their limits. Traditional static spectrum allocation methods can no longer meet this rising demand, resulting in increased congestion, interference, and degraded communication performance. Surprisingly, many licensed bands remain underutilized, highlighting the inefficiency of current approaches and the urgent need for smarter, more dynamic spectrum management.

Our project proposes an intelligent spectrum management system utilizing advanced Deep Learning (DL) algorithms and Cognitive Radio (CR) techniques. The core of this solution is a Convolutional Neural Network (CNN) model designed to enhance Spectrum Sensing (SS) capabilities, continuously monitoring and dynamically allocating available spectrum resources to mobile and IoT devices. This approach aims to maximize spectrum utilization and translate DL-based SS research into a practical, real-world implementation, encompassing both algorithmic contribution and practical system implementation. 

The system is designed with the following key objectives:
- **Spectrum Optimization:** Implement an SS and spectrum allocation solution to maximize the use of available frequency bands. 
- **Interference Mitigation:** Minimize interference among devices sharing the same spectrum resources. 
- **Deep Learning Integration:** Utilize advanced DL techniques to improve SS accuracy and adaptability. 
- **Algorithm Design:** Incorporate a low-complexity SS algorithm for core functionality. 
- **Practical Implementation:** Include a tangible hardware implementation to test and showcase optimized operation. 

### System Architecture & Components

The system is based on a centralized CR network architecture, with a central node managing spectrum resources and coordinating SU activities. 

#### Hardware
- **Raspberry Pi 4 Model B (Central Node):** Responsible for SS and Dynamic Spectrum Allocation (DSA) using an RTL-SDR antenna and a compressed, pre-trained DL model. It also manages channel allocation requests from SUs via a LoRa RF transceiver. 
- **Arduino Uno R3 Microcontrollers (PU and SU Nodes):** Serve as both Primary User (PU) and Secondary User (SU) nodes, equipped with sensors and LoRa RF transceivers for data collection and communication.
- **Adafruit RFM9x LoRa Transceiver Module:** Essential for long-range, low-power wireless communication between all nodes and the central node. 
- **RTL-SDR Dongle and Antenna:** Attached to the central node for continuous RF spectrum monitoring. 

#### Software
- **Python:** Used for the central node's software on the Raspberry Pi, including the DL algorithms. 
- **C++:** Used for programming Arduino nodes for sensor data collection and communication. 
- **TensorFlow Lite:** Used for model compression (quantization to Float 16) to enable efficient deployment on resource-limited devices like the Raspberry Pi. The model size was reduced by 83% (from 48.12 MB to 8.02 MB). 
- **GNU Radio:** Used for configuring SDRs and capturing I/Q samples for dataset creation. 
- **RadioHead library:** Facilitates reliable communication for SU transmission requests. 

