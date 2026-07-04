# Semana 15: Seguridad en Bluetooth

## Intro

### Qué es Bluetooth

- Es una tecnología de comunicación inalámbrica a corta distancia que permite a los dispositivos conectarse e intercambiar datos entre sí sin usar cables.
- Funciona mediante ondas de radio en la banda de 2.4 GHz.
- Permite conectarse a audífonos, altavoces, smartwatches y automóviles
- Es necesario emparejar dos dispositivos para iniciar la comunicación mediante un PIN.

### Características

- **Alcance:** hasta 100 metros según la clase de dispositivo.
- **Frecuencia:** 2.4 GHz (banda ISM).
- **Salto de frecuencia:** cambia de canal ~1600 veces por segundo.
- **Bajo consumo:** variante BLE (Bluetooth Low Energy).

### Clases de potencia

- **Clase 1:** Uso industrial y equipos de largo alcance - Hasta 100 metros.
- **Clase 2:** Uso común: móviles, audífonos, altavoces - Hasta 10 metros.
- **Clase 3:** Corto alcance, uso para accesorios y wearables - Hasta 1 metro.

### Aplicaciones de Bluetooth

- **Audio:** Altavoces y audífonos.
- **Wearables:** Relojes y bandas fitness.
- **Automotriz:** Manos libres y multimedia.
- **Salud:** Monitores y sensores médicos.
- **Periféricos:** Teclados, mouses e impresoras.

## Funcionamiento de Bluetooth

<table border="1">
  <tr>
    <th> Perfil </th>
    <th> Función </th>
    <th> Ejemplo </th>
  </tr>
  <tr>
    <th> A2DP </th>
    <td> Transmisión de audio estéreo </td>
    <td> Escuchar música en audífonos </td>
  </tr>
  <tr>
    <th> HFP </th>
    <td> Manos libres para llamadas </td>
    <td> Llamadas en el automóvil </td>
  </tr>
  <tr>
    <th> HID </th>
    <td> Dispositivos de interfaz humana </td>
    <td> Teclado o mouse inalámbrico </td>
  </tr>
  <tr>
    <th> OBEX </th>
    <td> Transferencia de objetos y/o archivos </td>
    <td> Enviar una foto a otros dispositivos móviles </td>
  </tr>
</table>

## Arquitectura de una comunicación Bluetooth

### Componentes principales

- **Dispositivo maestro:** Inicia y controla la conexión Bluetooth.
- **Dispositivo esclavo:** Responde y se sincroniza con el dispositivo maestro.
- **Piconet:** Red formada por un dispositivo maestro y hasta 7 dispositivos esclavos.
- **Canal de comunicación:** Banda ISM de 2.4 GHz con salto de frecuencia.

### Proceso de comunicación

- **Descubrimiento:** Los dispositivos se detectan entre sí.
- **Emparejamiento:** Se autentican mediante PIN o clave segura.
- **Conexión:** Se establece el canal seguro de datos.
- **Transferencia:** Se transmite audio, datos o comandos.

## Amenazas de seguridad

### Principales riesgos

- **Bluejacking:** Envío de mensajes no solicitados.
- **Bluesnarfing:** Robo de información.
- **Bluebugging:** Control remoto del dispositivo.
- **Ataques de fuerza bruta al PIN:** Robo de credenciales.
- **Ataques Man-in-the-Middle (MITM):** Intercepción de mensajes en la red Bluetooth.

### Dispositivos

- Dispositivos como los sniffers Bluetooth USB permiten capturar y analizar el tráfico Bluetooth cercano (Flipper Zero).

### Bluejacking

Un atacante envía mensajes o archivos no solicitados a dispositivos Bluetooth cercanos y visibles.

**Consecuencias**

- Robo de información.
- Captura de identificadores.
- Obtención de credenciales.

**Ejemplo**

- Envío de mensajes de spam o phishing a través de Bluetooth sin autorización del usuario.

### Bluesnarfing

- **Víctima:** Smartphone con Bluetooth visible.
- **Atacante:** Explota una vulnerabilidad de emparejamiento.
- **Datos sustraídos:** Contactos, mensajes y archivos.

**Procedimiento**

- Primero, el atacante detecta un dispositivo con Bluetooth visible/emparejable.
- Luego, explota fallas del protocolo OBEX para acceder sin autorización.
- Finalmente, copia contactos, mensajes o archivos sin que la víctima lo note.

### Bluebugging

**Objetivo:** Tomar el control remoto del dispositivo mediante una vulnerabilidad Bluetooth.

**Posibles acciones**

- Realizar o escuchar llamadas.
- Leer y enviar mensajes.
- Activar el micrófono sin permiso.

**Impacto**

- Espionaje.
- Suplantación de identidad.
- Pérdida de privacidad.

## Medidas de protección

**Buenas prácticas**

- Desactivar Bluetooth cuando no se use.
- Configurar el dispositivo como "no visible".
- Usar códigos o PINs robustos.
- Actualizar el firmware regularmente.
- Verificar la identidad del dispositivo antes de emparejar.
- Monitorear las conexiones activas.
