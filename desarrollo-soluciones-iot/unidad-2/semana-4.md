# Semana 4: Basic IoT Solution Design

## IoT System general architecture

- Physical Layer: La capa física está compuesta por nodos sensores y actuadores, que permiten el seguimiento y control de magnitudes físicas relacionados con los objetos físicos.
- Data Exchange Layer: La capa de intercambio de datos tiene como objetivo proporcionar capacidades de conexión a Internet a los nodos sensores y actuadores. En particular, los datos se recopilan de los nodos sensores y se comparten a través de Internet. Se pueden enviar comandos a los actuadores.
- Information integration layer: La capa de integración de información también se conoce como capa de middleware. Almacena, analiza y procesa la gran cantidad de datos que provienen de la capa de intercambio de datos. Emplea varias tecnologías, incluidas bases de datos, computación en la nube y módulos de procesamiento de big data.
- Application service layer: La capa de servicio de aplicación consta de servicios digitales que permiten la gestión de todo el sistema IoT o partes de él mediante el uso de la abstracción proporcionada por la capa de integración. En particular, los usuarios finales pueden interactuar con los nodos IoT visualizando la información integrada y enviando comandos operativos que seimplementan en la capa de integración de la información.

## IoT System Design Guidelines

1. Definicion de los requisitos del sistema.
2. Eleccion de la topologia del sistema IoT.
3. Definicion de los requisitos para la capa fisica.
4. Definicion de los requisitos para la capa de intercambio de datos.
5. Definicion de los requisitos para la capa de integracion de la informacion.
6. Definicion de los requisitos para la capa de servicio de la aplicacion.
7. Eleccion de las arquitecturas de las capas de intercambio de datos e integracion de informacion.
8. Eleccion de los sensores y actuadores.
9. Eleccion del microcontrolador y transceptores de radio.
10. Definicion del procesamiento de datos por cada nodo en la nube.
11. Analisis del tiempo de procesamiento.
12. Definicion de la interfaz de usuario (UI).

### Definition of the system requirements

Definición de los requisitos del sistema en términos de
- Capacidades de suministro de energía.
- Restricciones de time-delay

### Selection of the IoT system typology

Elección de IoT Typology (la tipología del sistema IoT), según las definiciones mencionadas anteriormente.

### Definition of physical layer requirements

Definición de los requisitos relacionados con la capa física en términos de:
- Número y tipos de nodos sensores y actuadores.
- Consumo máximo de energía para cada nodo.
- Target uncertainty (incertidumbre objetivo), relacionada con las cantidades físicas medidas por cada sensor.
- Target accuracy and precision (Exactitud y precisión objetivo) de los actuadores.
- Tipología de las interfaces digitales para adquirir las medidas proporcionadas por los sensores y para dirigir los actuadores.
- Esfuerzo computacional para los algoritmos de procesamiento de datos que se implementarán en el nodo.
- Time-delay requerido para el procesamiento de datos.

### Definition of exchange layer requirements

Definición de los requisitos relacionados con la capa de intercambio, en términos de
- Máximo time-delay permitido para el envío o recepción de paquete hacia o desde los nodos.
- Tipología decomunicaciones, inalámbrica o alámbrica.
- Topología de red.
- Distancia máxima para las comunicaciones entre los nodos sensores/actuadores, los nodos sensores/actuadores y los concentrador, los nodos sensores/actuadores y el gateway, el concentrador y el gateway.
- Consumo de potencia máximo permitido para la comunicación.
- Tipo de criptografía de datos.

### Definition of information layer requirements

Requisitos relacionados con la capa de integración de la información:
- Definición de los usuarios finales.
- Definición del número y tipos de servicios que deben proporcionarse a cada usuario final.
- Definición de las necesidades de información integrada para implementar cada servicio.
- Definición de la arquitectura de la capa de integración de información, en términos de algoritmos de procesamiento de datos que se implementarán en los nodos o en el cloud.
- Evaluación de la complejidad computacional de los algoritmos para procesar los datos medidos para proporcionar la información integrada.
- Definición del tiempo de procesamiento necesario para proporcionar cada información integrada.

### Definition of application service layer requirements

Requisitos relacionados con la capa de servicio de la aplicación:
- Definición de la interfaz de usuario para cada servicio prestado.
- Definición de la complejidad computacional relacionada con la algoritmos de procesamiento que se implementarán en el dispositivo de usuario final.
- Definición de las tipologías para plataformas de usuario final, que se utilizarán para implementar la interfaz de usuario.

### Selection of the architectures of data exchange and information integration layers

Elección de la arquitectura para capa de intercambio de datos y la capa de integración de
información, según los requisitos antes mencionados y el análisis del time-delay necesario para
enviar y recibir datos desde y hacia el nodos.

### Selection of the sensors and the actuators

Selección de los sensores y actuadores a embeber en los nodos de la capa física según sus características metrológicas y eléctricas.

### Selection of the microcontroller and radio transceivers

Selección del microcontrolador y transceptores de radio a ser incrustado en los nodos (nodos de sensor/actuador, gateway y concentrador), de acuerdo con su consumo de energía, capacidades computacionales, y los periféricos digitales y analógicos disponibles.

### Definition of the data processing for each node and in Cloud

Definición de los algoritmos de procesamiento de datos a ser implementadas en los nodos y definición de los procedimientos realizados en el cloud.

### Analysis of the processing time

Análisis del esfuerzo computacional de cada algoritmo y evaluación del tiempo requerido para realizarlos.

### Definition of the graphical user interface

Definición de la interfaz gráfica de usuario en los dispositivos de usuario final según la tipología de servicio a brindar.
