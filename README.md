# drone-dev — Vehículos autónomos a escala (CAN + AUTOSAR-like + Raspberry Pi)

Proyecto personal/de equipo para construir **modelos a escala autónomos** —un coche eléctrico RC y un dron cuadricóptero— usando una arquitectura inspirada en la automoción real: Raspberry Pi como computador de percepción/decisión, un microcontrolador (STM32) como ECU de actuación, y **bus CAN** como red de comunicación entre ambos.

Nace del interés en aplicar, de forma práctica, conceptos de automatización, sistemas embebidos y ciencia de datos (grado de Ciencia de Datos, UOC) a plataformas físicas reales a escala reducida y bajo coste.

## Objetivo

Aprender y prototipar, en dos plataformas en paralelo, el mismo patrón arquitectónico que usa la industria del automóvil y la robótica aérea:

- **Raspberry Pi** = "ECU de dominio" / companion computer (percepción, planificación, decisión).
- **STM32 (o similar)** = ECU de actuación conectada por **CAN**, con un software de capas inspirado en **AUTOSAR** (COM, PDU Router, capa de aplicación).
- **ROS2** como middleware de integración en la Pi.

> **Nota técnica**: AUTOSAR Classic Platform está pensado para microcontroladores automotrices certificados, no para Linux/Raspberry Pi. Aquí no se pretende ser 100% compliant, sino aprender el patrón arquitectónico (capas, separación de responsabilidades, comunicación por bus) con un stack propio simplificado, dejando la puerta abierta a evaluar stacks reales (Vector/EB, Arctic Core) más adelante.

## Los dos proyectos

| | Coche eléctrico a escala | Dron cuadricóptero |
|---|---|---|
| Documento | [`docs/proyecto-coche.md`](docs/proyecto-coche.md) | [`docs/proyecto-dron.md`](docs/proyecto-dron.md) |
| Primer hito | Seguimiento de carril con velocidad constante, comandos por CAN real | Misión autónoma a waypoints + aterrizaje de precisión por visión (ArUco) |
| Estado | 🟡 Definición de arquitectura | 🟡 Definición de arquitectura |

## Documentación

- [`docs/entorno-raspberry-pi.md`](docs/entorno-raspberry-pi.md) — cómo preparar la Raspberry Pi (SO, CAN HAT, SocketCAN, ROS2, toolchain STM32).
- [`docs/proyecto-coche.md`](docs/proyecto-coche.md) — arquitectura, hardware y primer hito del coche a escala.
- [`docs/proyecto-dron.md`](docs/proyecto-dron.md) — arquitectura, hardware y primer hito del dron.
- [`docs/recursos-formacion.md`](docs/recursos-formacion.md) — cursos (Coursera/Udemy) y literatura recomendada.
- [`ROADMAP.md`](ROADMAP.md) — fases del proyecto, checklist de progreso y presupuesto estimado de hardware.
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — cómo colaborar y qué perfiles buscamos.

## ¿Por qué este repo es abierto al equipo?

Este es un proyecto para disfrutar aprendiendo en equipo, no un producto cerrado. Si te interesa la automoción, la robótica, los sistemas embebidos, CAN/AUTOSAR, ROS2, visión por computador o simplemente montar cacharros que vuelan o ruedan, **estás invitado a colaborar** — revisa [`CONTRIBUTING.md`](CONTRIBUTING.md) para ver por dónde empezar.
