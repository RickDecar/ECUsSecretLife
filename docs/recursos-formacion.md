# Recursos de formación

Cursos y literatura para ponerse al día en las áreas que toca el proyecto: sistemas embebidos, CAN, AUTOSAR, robótica y percepción.

## Cursos de Coursera

| Curso / Especialización | Por qué |
|---|---|
| **Self-Driving Cars Specialization** (Universidad de Toronto) | Percepción, control, planificación de trayectorias — base conceptual del coche a escala. |
| **Introduction to Embedded Systems Software and Development Environments** (CU Boulder) | Fundamentos de C embebido y toolchains, necesario antes de tocar AUTOSAR. |
| **Embedded Systems Essentials with Arm** (Arm Education) | Arquitectura de microcontroladores, RTOS, interrupciones. |
| **Modern Robotics: Mechanics, Planning, and Control** (Northwestern) | Cinemática/dinámica aplicable tanto al coche como al dron. |
| **Robotics Specialization** (UPenn) | Incluye "Aerial Robotics", casi un mini-curso de dinámica de cuadricópteros. |
| **Internet of Things Specialization** (UC San Diego) | Buen puente entre Data Science y hardware. |

No hay curso "AUTOSAR" nativo de buena reputación en Coursera — ese hueco lo cubre mejor Udemy.

## Cursos de Udemy

| Curso | Aporta |
|---|---|
| **AUTOSAR - Classic Platform** / **Automotive Cyber Security & AUTOSAR** | Arquitectura AUTOSAR, RTE, MCAL, capas BSW. |
| **Learn CAN, CAN FD, LIN, and Automotive Networking** | Trama CAN, arbitraje, DBC files, herramientas (CANoe/PCAN/SavvyCAN). |
| **Complete Raspberry Pi Bootcamp** | Entorno base, GPIO, SPI/I2C. |
| **ROS2 for Beginners** (Edouard Renard / The Construct) | Middleware de integración por encima de CAN en la Pi. |
| **Drone Programming with Python / MAVLink & DroneKit** | Comunicación con Pixhawk/ArduPilot desde la Pi. |
| **Embedded Systems Programming on ARM Cortex-M3/M4** (Israel Gbati) | Para el microcontrolador CAN-node (STM32). |

Prioriza cursos actualizados en los últimos 12-18 meses y revisa el syllabus antes de comprar (los de AUTOSAR varían mucho en calidad).

## Literatura relevante

**AUTOSAR / arquitectura software automotriz**
- *AUTOSAR Compendium* (Ahmed Elmahdy) — introducción práctica.
- Documentación oficial AUTOSAR (autosar.org), especialmente "Layered Software Architecture" y "Requirements on Communication Stack" — gratuitos y son la referencia real.
- *Software Engineering for Modern Automotive Systems* (Springer) — arquitecturas E/E modernas (zonal, SOA sobre Ethernet/AUTOSAR Adaptive).

**CAN bus**
- *A Comprehensible Guide to Controller Area Network* (Wilfried Voss) — el clásico de referencia.
- Bosch CAN Specification 2.0 (documento oficial, gratuito).
- ISO 11898 (estándar).

**Robótica y control**
- *Modern Robotics: Mechanics, Planning, and Control* (Lynch & Park) — gratuito online, complementa el curso de Coursera homónimo.
- *Probabilistic Robotics* (Thrun, Burgard, Fox) — SLAM/localización, útil si escala el proyecto del coche.
- *Small Unmanned Aircraft: Theory and Practice* (Beard & McLain) — referencia estándar en dinámica y control de UAVs.

**Sistemas embebidos y tiempo real**
- *Real-Time Systems* (Jane W. S. Liu) — fundamentos de scheduling/RTOS que subyacen a AUTOSAR OS y FreeRTOS.
- *Making Embedded Systems* (Elecia White) — práctico para pasar de programar en PC a microcontroladores.

**Conducción autónoma / percepción**
- *Autonomous Driving: Technical, Legal and Social Aspects* (Maurer et al., Springer, open access).

**Puente con perfil de Data Science**
- Material del curso *Self-Driving Cars* de Toronto (Coursera).
- *Multiple View Geometry in Computer Vision* (Hartley & Zisserman), útil para el aterrizaje de precisión del dron y el lane-keeping del coche.
