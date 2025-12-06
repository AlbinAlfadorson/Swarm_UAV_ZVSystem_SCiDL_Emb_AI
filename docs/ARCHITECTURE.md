# ZV UAV embedded & AI Swarm System - Architecture

## 🏗 System Overview

```mermaid
graph TB
    subgraph "Ground Segment"
        BS[Hive Base Station<br/>NVIDIA Jetson Orin]
        PS[Power System<br/>Solar + 48V LiFePO4]
        CS[Charging System<br/>Auto Battery Swap]
    end
    
    subgraph "Air Segment - Swarm"
        QU[Queen UAV<br/>Qualcomm QRB5165 + Edge TPU]
        W1[Worker UAV 1<br/>STM32H7 + ESP32-S3]
        W2[Worker UAV 2<br/>STM32H7 + ESP32-S3]
        RU[Refuel UAV<br/>Fuel Cell + Docking]
    end
    
    BS -->|LoRa 868MHz| QU
    BS -->|Ethernet| PS
    PS --> CS
    QU -->|ESP-NOW Mesh| W1
    QU -->|ESP-NOW Mesh| W2
    W1 -.->|Data Relay| W2
    RU -->|Inductive Charge| W1
    RU -->|Inductive Charge| W2
