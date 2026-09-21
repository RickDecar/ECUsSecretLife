# Cómo colaborar

Este proyecto nace para aprender y disfrutar en equipo construyendo vehículos autónomos a escala. Cualquier compañero interesado es bienvenido, sin necesidad de experiencia previa en automoción o embebidos — hay sitio para perfiles muy distintos.

## Perfiles que buscamos

- **Firmware / embebidos**: STM32, FreeRTOS, capas tipo AUTOSAR.
- **Redes vehiculares**: CAN bus, diseño de mensajes/DBC.
- **Robótica / ROS2**: integración de sensores, nodos de percepción y control.
- **Visión por computador**: detección de carril, marcadores ArUco/AprilTag.
- **Control**: PID, estimación de estado (IMU, encoders, GPS).
- **Drones**: ArduPilot/PX4, MAVLink, montaje y tuning de multirrotores.
- **Mecánica / hardware**: chasis, cableado, integración de baterías.
- **Ciencia de datos**: análisis de telemetría, logging, futuros modelos de percepción/predicción.

Si no ves tu perfil aquí, propónlo — el roadmap está abierto a redefinirse con el equipo.

## Por dónde empezar

1. Lee [`README.md`](README.md) y [`ROADMAP.md`](ROADMAP.md) para entender el objetivo y la fase actual.
2. Revisa la documentación del proyecto que te interese: [`docs/proyecto-coche.md`](docs/proyecto-coche.md) o [`docs/proyecto-dron.md`](docs/proyecto-dron.md).
3. Abre una **Issue** para:
   - Proponer o discutir un cambio de arquitectura.
   - Apuntarte a una tarea del roadmap.
   - Compartir hallazgos, dudas o recursos.
4. Trabaja en una rama propia y abre un **Pull Request** contra `main` cuando tengas algo revisable, aunque sea parcial.

## Convenciones

- Documentación y commits en castellano, código y nombres técnicos en inglés (convención habitual en embebidos/ROS2).
- Cambios de arquitectura relevantes (p. ej. formato de mensajes CAN, capas del mini-stack AUTOSAR) se documentan en `docs/` antes o junto con el PR que los implementa.
- Las decisiones de hardware con impacto en presupuesto se reflejan en la tabla de [`ROADMAP.md`](ROADMAP.md).

## Contacto

Para dudas rápidas o coordinación informal, usa el canal/grupo del equipo. Para todo lo que deba quedar como referencia futura, mejor una Issue o un comentario en el PR correspondiente.
