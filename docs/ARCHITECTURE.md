## 🏗 System Overview

```mermaid
graph TB
    subgraph "Ground Segment"
        BS["Базовая станция |Улейn| <br/>NVIDIA Jetson Орин"]
        PS["Энерго система<br/>Solar + 48V LiFePO4"]
        CS["Система зарядки<br/>Auto Battery Swap"]
    end
    
    subgraph "Air Segment - Swarm"
        QU["Queen(центральный узел)UAV<br/>Socionext SynQuacer(24-ядра ARM)"]
        W1["Трутень UAV 1<br/>STM32H7 + ESP32-S3"]
        W2["Трутень UAV 2<br/>STM32H7 + ESP32-S3"]
        RU["Refuel UAV<br/>Fuel Cell + Docking"]
    end
    
    BS -->|LoRa 868MHz| QU(королева)
    BS -->|Ethernet| PS(внешний мир)
    PS --> CS(модули увеличивают автономность трутней до 35% от заявленной на первом стенде)
    QU -->|ESP-NOW Mesh| W1
    QU -->|ESP-NOW Mesh| W2
    W1 -.->|Data Relay| W2
    RU -->|Inductive Charge| W1
    RU -->|Inductive Charge| W2
