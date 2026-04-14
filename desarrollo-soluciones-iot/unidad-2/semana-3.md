# Semana 3: IoT Sensors, Devices and Connectivity

## Sesion 1: IoT Devices

### Definicion

- Se refiere a cualquier cosa que obtenga informacion y la transmita.
- Los dispositivos pueden funcionar solos o sincronizados con otros dispositivos.

### Caracteristicas

#### Adquisición y control de datos.

- Recopila información analógica en un intervalo de tiempo fijo.
- Transmite la informacion como una señal digital a un dispositivo de salida remoto para una lectura digital.
- Sensores: elementos del dispositivo cuya funcion es detectar cambios en el entorno. Ej.: nivel de luz, humedad, temperatura, etc.
- Actuadores: Un motor o rotor. Puede ser usado junto con sensores dependiendo del caso.
- Resolucion: representa la cantidad más pequeña de cambio que el sensor puede leer de manera confiable. Por ejemplo, un sensor de temperatura analógico con 10 bits de resolución representa una lectura de temperatura utilizando un valor numérico entre 0 y 1023. Los bits son binarios, por lo que 10 bits proporcionan dos a la potencia de 10, o 1024 valores posibles en total.

#### Procesamiento y almacenamiento de datos.

- Algunos dispositivos IoT pueden procesar datos directamente, mientras que otros transmiten estos datos a otros dispositivos, dispositivos de puerta de enlace o aplicaciones en la nube para una mayor agregación y análisis.
- Edge Analytics: realiza análisis de datos at-the-edge (en los bordes) de una red en lugar de en una ubicación centralizada.
- Los datos se pueden analizar en tiempo real en los propios dispositivos, o se pueden analizar en un gateway device (como router) conectado a los dispositivos IoT, en lugar de transmitir grandes volúmenes de datos a un servidor en la nube o centro de datos para su posterior análisis.
- Edge Analytics reduce el procesamiento upstream y los requisitos de almacenamiento alivian la carga de la red.

#### Conectividad.

- LAN: WiFi.
- WAN: 3GPP Cellular, LTE, 3G, 2G.
- PAN: Bluetooth, Thread, Zigbee, NFC.
- LPWAN: 3GPP, LTE-M, LoRA, Sigfox, NG-IoT.

#### Administración de energía.

- Dependen del procesamiento requerido por los servicios o aplicaciones que consumen los datos.
- Una single-board computer como la Raspberry Pi 4 requiere alrededor de 700 a 1000 mA de corriente para funcionar con un uso típico.
- Si conecta un módulo de cámara, el amperaje requerido aumenta unos 250 mA cuando la cámara está en uso. Además, los sensores normalmente requieren energía para funcionar; los pines GPIO en la Raspberry Pi suministran 3,3 V o 5 V, hasta un total de 50 mA de corriente en todos los pines. 

### Of-the-shelf Hardware

- El desarrollo de aplicaciones de IoT es más accesible con la creciente disponibilidad de off-the-shelf hardware development boards, plataformas y prototyping kits de bajo costo.
- Arduino, entre otros kits de desarrollo.

### System-on-a-chip (SoC)

- Los SoC agrupan capacidades como procesamiento de datos, almacenamiento y redes en un solo chip.
- Los microcontroladores forman parte de esta familia.
- Los microcontroladores contienen un core (o cores) de procesador, memoria (RAM) y erasable programmable read-only memory (EPROM) para almacenar los programas personalizados que se ejecutan en el microcontrolador.
- Las microcontroller development boards son printed circuit boards (PCBs) con circuitos adicionales para admitir el microcontrolador para que sea más conveniente crear prototipos y programar el chip.

#### GPIO

- Sensors y actuators se conectan al microcontroller a través de pines de General Purpose Input/Output (GPIO) digitales o analógicos, o a través de un hardware bus.
- Los protocolos de comunicación estándar como InterIntegrated Circuit (I2C, también conocido como I2C o IIC) y Serial Peripheral Interface (SPI) se utilizan para la comunicación entre dispositivos con los componentes que están conectados con el bus.

#### Device platforms

- Arduino: Arduino Uno, Particle's Electron, que incluye un módem celular integrado.
- Espressif Systems: Las placas de desarrollo más populares que se basan en ESP8266 incluyen NodeMCU, WeMos D1 y Feather Huzzah de AdaFruit.

### Single-Board Computers (SBC)

- Single board computers (SBC) son un paso adelante de los microcontroladores.
- Le permiten conectar dispositivos periféricos como teclados, ratones y pantallas, además de ofrecer más memoria y potencia de procesamiento.

#### Expansion Boards

- Al igual que con los microcontroladores, las capacidades de los dispositivos SBC se pueden ampliar mediante la adición de placas de expansión apilables conocidas como hats en Raspberry Pi y capes en BeagleBone Black, y mediante la adición de módulos externos, como controladores de motor o analog-to-digital convertes, para mitigar las limitaciones con las capacidades built-in del dispositivo.

### ESP32 en Cirkit Designer

El ESP32 tiene los siguientes pines:

- 3V3: Power supply pin (3.3V).
- GND: Ground pin.
- D15: General-purpose I/O pin.
- D2: General-purpose I/O pin.
- D4: General-purpose I/O pin.
- RX2: Serial receive pin for UART2.
- TX2: Serial transmit pin for UART2.
- D5: General-purpose I/O pin.
- D18: General-purpose I/O pin.
- D19: General-purpose I/O pin.
- D21: General-purpose I/O pin.
- RX0: Serial receive pin for UART0.
- TX0: Serial transmit pin for UART0.
- D22: General-purpose I/O pin.
- D23: General-purpose I/O pin.
- EN: Enable pin (active high).
- VP: Analog input pin (V+).
- VN: Analog input pin (V-).
- D34: General-purpose I/O pin (input only).
- D35: General-purpose I/O pin (input only).
- D32: General-purpose I/O pin.
- D33: General-purpose I/O pin.
- VIN: Power supply pin (input voltage).
- D13: General-purpose I/O pin.
- D12: General-purpose I/O pin.
- D14: General-purpose I/O pin.
- D27: General-purpose I/O pin.
- D26: General-purpose I/O pin.
- D25: General-purpose I/O pin.

### Conceptos 

Sensores: Elementos o componentes que su función es capaz de detectar cambios en su entorno.
Actuadores: Elementos o componentes que su función es capaz de realizar una acción en su entorno.

Single Board Computer (SBC): Es un tipo de computadora completa construida en una sola placa de circuito impreso, que incluye un procesador, memoria, almacenamiento y puertos de entrada/salida. Ejemplos: Raspberry Pi, BeagleBone, Arduino.

Off-the-Shelf Hardware: Se refiere a componentes o dispositivos que están disponibles comercialmente y pueden ser adquiridos fácilmente para su uso en proyectos de IoT. Ejemplos: sensores de temperatura, módulos Wi-Fi, cámaras.

System on a Chip (SoC): Es un circuito integrado que combina todos los componentes de una computadora o sistema electrónico en un solo chip. Ejemplos: Qualcomm Snapdragon, Apple A-series.

Microcontroller: Es un pequeño dispositivo de computación que contiene un procesador, memoria y periféricos integrados en un solo chip. Se utiliza comúnmente en aplicaciones de IoT para controlar dispositivos y recopilar datos. Ejemplos: Arduino Uno, ESP8266, STM32.

General Purpose Input/Output (GPIO): Son pines en un microcontrolador o SBC que pueden ser configurados como entradas o salidas para interactuar con sensores, actuadores u otros dispositivos electrónicos.

Expansion Boards: Son placas adicionales que se conectan a un microcontrolador o SBC para proporcionar funcionalidades adicionales, como más puertos GPIO, interfaces de comunicación, sensores integrados o acceso a Wi-Fi.

Cirkit Designer: Es una herramienta de diseño de circuitos electrónicos que permite a los usuarios crear y simular circuitos de manera visual. Es útil para diseñar y probar circuitos antes de implementarlos físicamente.

