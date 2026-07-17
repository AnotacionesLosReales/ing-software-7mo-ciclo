# Semana 5: Embedded Application Development

## Interfaz de Hardware y Control

### Definición

- En el desarrollo embebido, el código no solo procesa datos; interactúa con el mundo físico en tiempo real.
- La arquitectura debe ser resiliente, asíncrona y basada en eventos.

### E/S Digital como Eventos de Negocio

- Configurar un pin con pinMode() altera su comportamiento eléctrico interno.
- Usar INPUT_PULLUP protege contra estados flotantes que generan datos corruptos en el sistema de inventario.

<img src="https://i.imgur.com/wsDmVpY.png" width="80%">

### Gestión del Tiempo: Ejecución Bloqueante vs. Concurrente

- La función delay() suspende toda la ejecución.
- Para sistemas industriales que requieren multitarea real, millis() permite evaluar intervalos asíncronos sin bloquear el ciclo principal.

### Estructuras de Control para Máquinas de Estado

- switch...case y break son fundamentales para orquestar la lógica empresarial secuencial.
- Evitan anidamientos profundos de if...else, garantizando un flujo de ejecución predecible y fácil de auditar.

<img src="https://i.imgur.com/1bqyAJ7.png" width="80%">

### Ejecución Asíncrona mediante Interrupciones

- attachInterrupt() delega el monitoreo de eventos críticos (como un paro de emergencia) directamente al hardware del controlador.
- Pausa el programa principal, ejecuta la rutina (ISR) y retorna sin latencia de software.

<img src="https://i.imgur.com/QOXYxON.png" width="80%">

## Gestión de Memoria y Datos

### Optimización de la Huella de Memoria (Data Types)

- En arquitecturas de 8 bits, procesar un float es exponencialmente más lento que un número entero.
- Utilice la aritmética de enteros para métricas financieras y físicas siempre que sea posible.

<img src="https://i.imgur.com/UVqC3yM.png" width="80%">

### Rompiendo el Límite de SRAM con PROGMEM

- Almacenar metadatos estáticos (como identificadores de productos o mensajes de interfaz) en la memoria Flash mediante PROGMEM y la biblioteca pgmspace.h salva la SRAM crítica para las variables de tiempo real.

<img src="https://i.imgur.com/SFOPTkf.png" width="80%">

### Ámbito de Variables y Modificadores de Hardware

- El modificador volatile le ordena al compilador que no optimice la variable en los registros, obligándolo a leerla directamente de la RAM.
- Es un requerimiento arquitectónico estricto para variables alteradas por interrupciones.

<img src="https://i.imgur.com/TU8aEak.png" width="80%">

### Manipulación de Cadenas y Fragmentación del Heap

- El objeto String asigna memoria dinámicamente.
- En despliegues loT a largo plazo (días o meses sin reiniciar), esto fragmenta el heap, causando bloqueos impredecibles.
- Utilice arreglos de caracteres terminados en null (ASCII 0) сcon búferes estáticos.

<img src="https://i.imgur.com/O1fRKBB.png" width="80%">
