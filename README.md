# pH Cultivos

Aplicación web progresiva (PWA) para interpretar lecturas de pH según el cultivo seleccionado.

## Estado actual

La versión 3.5 está publicada con GitHub Pages. Funciona en iPhone desde Safari con lectura manual y en Chrome para Android incorpora la conexión directa experimental con el medidor YINMIK YK-S01. La navegación usa una estrategia de red primero y caché como respaldo para evitar mostrar versiones antiguas cuando hay conexión.

La interpretación utiliza una barra continua con transición gradual de rojo para pH bajo, verde para el rango adecuado y azul para pH alto. El marcador conserva la posición proporcional de la lectura dentro de la escala específica de cada cultivo.

Las mediciones pueden guardarse localmente con cultivo, valor de pH, categoría, fecha, hora y fuente de lectura. Las lecturas recibidas por Bluetooth conservan también la temperatura y el paquete original para facilitar futuras migraciones. Opcionalmente, el usuario puede solicitar la ubicación del teléfono y guardar latitud, longitud, precisión y hora de captura. El historial utiliza una estructura versionada en el almacenamiento del navegador, permite abrir la ubicación guardada en un mapa y eliminar registros individuales.

Sitio publicado:

`https://miguelandresamado-design.github.io/pH-cultivos/`

Repositorio:

`miguelandresamado-design/pH-cultivos`

## Cultivos implementados

El usuario selecciona el cultivo, introduce manualmente una lectura de pH y la aplicación la clasifica gráficamente en una escala cualitativa de cinco niveles.

### Reglas para Café — escala de cinco niveles

- **MUY BAJO:** pH < 4.50
- **BAJO:** pH entre 4.50 y menos de 5.00
- **ADECUADO:** pH entre 5.00 y menos de 5.50
- **MODERADAMENTE ALTO:** pH entre 5.50 y menos de 6.00
- **ALTO:** pH igual o superior a 6.00

Fuente de rangos: Cenicafé.

### Reglas para Banano — escala de cinco niveles

- **MUY BAJO:** pH < 5.00
- **BAJO:** pH entre 5.00 y menos de 5.80
- **ADECUADO:** pH entre 5.80 y menos de 6.54
- **MODERADAMENTE ALTO:** pH entre 6.54 y menos de 7.30
- **ALTO:** pH igual o superior a 7.30

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

Funciones incorporadas:

- guardar mediciones
- fecha y hora
- historial
- ubicación GPS opcional

Siguientes mejoras posibles:

- recomendaciones por rango
- gráficas de evolución
- finca / lote

### Etapa 3 — Bluetooth

La primera integración real con un medidor físico mediante Bluetooth Low Energy (BLE) está implementada para Chrome en Android.

Primer equipo considerado para pruebas:

- **YINMIK YK-S01**

Flujo implementado:

`Medidor YINMIK → Bluetooth BLE → lectura en vivo → confirmación → interpretación en pH Cultivos`

Protocolo validado con el equipo físico:

- nombre Bluetooth: `YK-S01`
- servicio GATT: `FF01`
- característica de medición: `FF02`
- propiedades: lectura, escritura y notificación
- pH y temperatura decodificados y contrastados con la pantalla del medidor

La aplicación no guarda automáticamente cada notificación. Muestra la última lectura y el usuario pulsa **Usar esta lectura** antes de interpretarla o guardarla.

Safari en iPhone no ofrece Web Bluetooth. La PWA mantiene allí todo el flujo manual; la conexión directa en iPhone requerirá una aplicación nativa o una envoltura híbrida que reutilice este mismo decodificador.

## Continuidad del proyecto

Este README es la referencia principal del proyecto.

Para continuar el desarrollo, el README y el historial del repositorio funcionan como referencia principal:

`miguelandresamado-design/pH-cultivos`

## Estado al 28 de agosto de 2026

- Repositorio creado: sí
- GitHub Pages activado: sí
- Prueba en laptop: correcta
- Prueba en Safari de iPhone: correcta
- Café implementado: sí
- Banano implementado: sí
- Selector de cultivo: sí
- Escala cualitativa de cinco niveles: sí
- Guardado local e historial: sí
- Ubicación GPS opcional: sí
- Finca y lote: pendiente
- Bluetooth YK-S01 en Chrome para Android: implementado para prueba física
- Bluetooth directo en iPhone: pendiente de envoltura nativa
