# Roadmap

## Fases

- [ ] **Fase 1 — Entorno base**: Raspberry Pi + CAN funcionando, con un STM32 de prueba enviando/recibiendo tramas por CAN real. Ver [`docs/entorno-raspberry-pi.md`](docs/entorno-raspberry-pi.md).
- [ ] **Fase 2 — Formación en paralelo**: curso corto de CAN bus y repaso de fundamentos AUTOSAR/embebidos (ver [`docs/recursos-formacion.md`](docs/recursos-formacion.md)) mientras avanza la Fase 1.
- [ ] **Fase 3 — Proyecto coche**: arquitectura Pi↔STM32↔CAN aplicada al coche a escala, primer hito de seguimiento de carril. Ver [`docs/proyecto-coche.md`](docs/proyecto-coche.md).
- [ ] **Fase 4 — Proyecto dron**: companion computer sobre ArduPilot/PX4 vía MAVLink, primer hito de misión autónoma con aterrizaje de precisión. Ver [`docs/proyecto-dron.md`](docs/proyecto-dron.md).
- [ ] **Fase 5 — AUTOSAR real (ampliación)**: evaluar un stack AUTOSAR real (Vector/EB, Arctic Core) sobre el nodo STM32, una vez el mini-stack propio y el patrón CAN estén dominados.

## Presupuesto estimado de hardware

Precios orientativos, componentes nuevos, gama de entrada. Varían según proveedor (AliExpress vs. tiendas especializadas tipo Mouser/RobotShop) y calidad de componentes; los rangos altos asumen piezas de marca reconocida (Pixhawk original, PiCAN2 oficial) en vez de clónicos.

| Proyecto | Componentes clave | Estimación |
|---|---|---|
| Base común | Raspberry Pi 4/5 (8GB) + PiCAN2 HAT + STM32 Nucleo + cables/conectores CAN | ~150-220 € |
| Coche a escala | Chasis RC 1/10 + motor brushless/ESC + servo + cámara + IMU + batería LiPo + cargador | ~180-350 € (+80-150 € si se añade LIDAR RPLIDAR A1) |
| Dron cuadricóptero | Frame 450 + Pixhawk/Matek + 4x motor/ESC + hélices + GPS/compass + radio telemetría + LiPo 4S + cargador | ~350-550 € |
| **Total aproximado ambos proyectos** | | **~700-1100 €** |

## Cómo leer este roadmap

Las fases 3 y 4 son independientes entre sí y pueden avanzar en paralelo una vez completada la Fase 1. La Fase 5 es una ampliación opcional, no un requisito para que los proyectos 3 y 4 funcionen.
