# pH Cultivos

Aplicación web progresiva (PWA) para interpretar lecturas de pH según el cultivo seleccionado.

## Estado actual

La segunda versión funcional está publicada con GitHub Pages y funciona en iPhone desde Safari.

Sitio publicado:

`https://miguelandresamado-design.github.io/pH-cultivos/`

Repositorio:

`miguelandresamado-design/pH-cultivos`

## Cultivos implementados

El usuario selecciona el cultivo, introduce manualmente una lectura de pH y la aplicación la clasifica gráficamente como BAJO, MEDIO o ALTO.

### Reglas para Café

- **BAJO:** pH < 5.0
- **MEDIO:** pH entre 5.0 y 6.0, incluyendo ambos límites
- **ALTO:** pH > 6.0

### Reglas para Banano

- **BAJO:** pH < 5.5
- **MEDIO:** pH entre 5.5 y 6.5, incluyendo ambos límites
- **ALTO:** pH > 6.5

## Tecnología actual

La aplicación está construida como una PWA sencilla con:

- HTML
- CSS
- JavaScript
- `manifest.json`
- `service-worker.js`
- GitHub Pages para publicación HTTPS

La app puede añadirse a la pantalla de inicio de un iPhone desde Safari mediante **Compartir → Añadir a pantalla de inicio**.

## Filosofía del proyecto

El desarrollo se hará de forma incremental y sencilla. Primero se validará la lógica agronómica y la experiencia de uso antes de integrar hardware o funciones más complejas.

La interpretación agronómica debe basarse inicialmente en reglas y datos suministrados por el propietario del proyecto, no en decisiones improvisadas por inteligencia artificial.

## Próximos pasos previstos

### Etapa 1 — Varios cultivos

Continuar agregando cultivos y sus rangos específicos.

Flujo:

`Cultivo → pH manual → BAJO / MEDIO / ALTO → indicador gráfico`

### Etapa 2 — Mejoras de uso

Posibles funciones:

- recomendaciones por rango
- guardar mediciones
- fecha y hora
- historial
- gráficas de evolución
- finca / lote
- ubicación GPS

### Etapa 3 — Bluetooth

Integrar un medidor físico de pH mediante Bluetooth Low Energy (BLE).

Primer equipo considerado para pruebas:

- **YINMIK YK-S01P**

Objetivo futuro:

`Medidor YINMIK → Bluetooth BLE → pH Cultivos → interpretación automática`

Antes de integrar Bluetooth será necesario identificar y validar el servicio y las características GATT utilizadas por el medidor.

## Principio para futuras conversaciones con ChatGPT

Este README es la referencia principal del proyecto.

Para continuar el desarrollo en otro chat, basta con indicar:

> Lee el README de mi repositorio `miguelandresamado-design/pH-cultivos` y continuemos desde allí.

## Estado al 25 de agosto de 2026

- Repositorio creado: sí
- GitHub Pages activado: sí
- Prueba en laptop: correcta
- Prueba en Safari de iPhone: correcta
- Café implementado: sí
- Banano implementado: sí
- Selector de cultivo: sí
- Bluetooth: pendiente
