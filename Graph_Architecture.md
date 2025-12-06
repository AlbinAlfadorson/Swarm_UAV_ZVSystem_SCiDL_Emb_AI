ZV-Legacy-Embedded-Erchitecture-AI-Swarm-System/          # Твой основной репозиторий
├── .github/                   # Автоматизации GitHub
│   └── workflows/            # CI/CD пайплайны
├── hardware/                  # ВСЁ железо (SKiDL, KiCad)
│   ├── skidl/                # SKiDL скрипты
│   ├── kicad/                # KiCad проекты
│   ├── gerber/               # Файлы для производства
│   └── bom/                  # Ведомости материалов
├── firmware/                  # Код для микроконтроллеров
│   ├── stm32-flight/         # Полетный контроллер (C/C++)
│   └── esp32-swarm/          # Роевая логика (MicroPython)
├── ai/                        # Искусственный интеллект
│   ├── computer_vision/      # OpenCV/YOLO
│   ├── swarm_algorithms/     # Роевые алгоритмы
│   └── simulation/           # Gazebo/ROS2 симуляции
├── docs/                      # ⭐⭐⭐ ВОТ ЭТА ДОКУМЕНТАЦИЯ ⭐⭐⭐
│   ├── ARCHITECTURE.md       # Главный архитектурный документ
│   ├── DECISIONS.md          # Архитектурные решения
│   ├── DEPLOYMENT.md         # Инструкции развертывания
│   ├── hardware/             # Документация по железу
│   │   ├── INTERFACES.md     # Аппаратные интерфейсы
│   │   ├── POWER_ANALYSIS.md # Расчет потребления
│   │   └── RF_PLANNING.md    # Планирование радиоканалов
│   ├── software/             # Документация по софту
│   │   ├── API.md           # API документация
│   │   ├── PROTOCOLS.md     # Протоколы связи
│   │   └── ALGORITHMS.md    # Описание алгоритмов
│   ├── diagrams/             # Все диаграммы
│   │   ├── system-architecture.puml
│   │   ├── data-flow.drawio
│   │   └── deployment-diagram.mmd
│   └── api/                  # API спецификации
│       └── openapi.yaml     # OpenAPI спецификация
├── tests/                    # Автоматические тесты
├── pyproject.toml           # Python зависимости (Poetry)
├── README.md                # Главная страница проекта
└── LICENSE                  # Лицензия GPL v3.0
