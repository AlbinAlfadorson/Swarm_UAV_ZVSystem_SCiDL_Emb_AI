## 🏗 System Overview

```mermaid
graph TB
    subgraph "Ground Segment"
        BS["Базовая станция |Улейn| <br/>NVIDIA Jetson Орин"]
        PS["Энерго система<br/>Solar + 48V LiFePO4"]
        CS["Система зарядки<br/>Auto Battery Swap"]
    end
    
    subgraph "Air Segment - Swarm"
        QU["Queen(центральный узел) UAV<br/>Socionext SynQuacer (24-ядра ARM) + CPU-only инференс"]
        W1["Worker UAV 1<br/>STM32H7 + ESP32-S3"]
        W2["Worker UAV 2<br/>STM32H7 + ESP32-S3"]
        RU["Refuel UAV<br/>Fuel Cell + Docking"]
    end
    
    BS -->|LoRa 868MHz| QU
    BS -->|Ethernet| PS
    PS --> CS
    QU -->|ESP-NOW Mesh| W1
    QU -->|ESP-NOW Mesh| W2
    W1 -.->|Data Relay| W2
    RU -->|Inductive Charge| W1
    RU -->|Inductive Charge| W2
