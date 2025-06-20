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

**The system is designed with the following key objectives**:
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

#### Hardware Block Diagram
![Hardware Block Diagram](https://github.com/Ismail-Sadaqat/DeepLearning-CR-Allocation/blob/7422f0db8af95d24fbeaac50a0ae422174e60269/Hardware/Hardware%20Block%20Diagram.png)

The Hardware Block Diagram illustrates this operational scenario, where the central node receives transmission requests from secondary users (SUs) over a dedicated 440 MHz control channel. When SU-1 submits a request, it enters a FIFO queue. Simultaneously, the RTL-SDR collects I/Q samples, which are analyzed by a CNN-based spectrum sensing (SS) model. The model outputs [1, 0], indicating that the 433 MHz band is occupied while 500 MHz is free. The central node then allocates the available 500 MHz band to SU-1, ensuring efficient spectrum utilization.

#### Experimental Setup
![Hardware Experimental Setup](https://github.com/Ismail-Sadaqat/DeepLearning-CR-Allocation/blob/c7f62bcadec88a3a4345f4e45120ab2b31bf2c31/Hardware/Experimental%20Setup.png)

#### Software
- **Python:** Used for the central node's software on the Raspberry Pi, including the DL algorithms. 
- **C++:** Used for programming Arduino nodes for sensor data collection and communication. 
- **TensorFlow Lite:** Used for model compression (quantization to Float 16) to enable efficient deployment on resource-limited devices like the Raspberry Pi. The model size was reduced by 83% (from 48.12 MB to 8.02 MB). 
- **GNU Radio:** Used for configuring SDRs and capturing I/Q samples for dataset creation.

### Repository Contents
- /code: Contains the source code for the Raspberry Pi-based system, including code for the Primary User (PU) and Secondary User (SU) implemented on Arduino, as well as scripts for training the deep learning model.
- /docs: Includes the final project report, presentation slides, and project poster.
