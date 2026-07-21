# Semana 14: Seguridad en NFC (Near Field Communication)

## Definición

La comunicación de campo cercano, más conocida por sus siglas NFC (Near Field Communication), es una tecnología que permite la comunicación inalámbrica entre dos dispositivos electrónicos próximos entre sí.
Oficialmente, la NFC admite distancias de hasta 3.80 cm, pero en la práctica puede llegar hasta a 10 cm.

**Características**

- Alcance aproximado: 10 cm.
- Frecuencia: 13.56 MHz.
- Comunicación sencilla y rápida.
- Bajo consumo energético.

## Funcionamiento

**Modos de operación**

- Modo lector/escritor
- Modo peer-to-peer
- Emulación de tarjeta

<table>
  <tr>
    <th>Modo</th>
    <th>¿Quién inicia la comunicación?</th>
    <th>Ejemplos</th>
  </tr>
  <tr>
    <td>Lector/Escritor</td>
    <td>El lector NFC</td>
    <td>Leer una etiqueta NFC</td>
  </tr>
  <tr>
    <td>Peer-to-peer</td>
    <td>Ambos dispositivos</td>
    <td>Compartir archivos entre teléfonos</td>
  </tr>
  <tr>
    <td>Emulación de tarjeta</td>
    <td>El lector NFC interactúa con un dispositivo que simula una tarjeta</td>
    <td>Pago con Google Wallet o Apple Wallet</td>
  </tr>
</table>

## Arquitectura de una comunicación via NFC

**Componentes principales**

- Dispositivo iniciador: Es el dispositivo que inicia la comunicación NFC.
- Dispositivo objetivo: Es el dispositivo que responde a la solicitud de comunicación.
- Antena NFC: Permite la comunicación inalámbrica de corto alcance (hasta 10 cm).
- Canal de comunicación: Medio inalámbrico a 13.56 MHz que transporta los datos entre ambos dispositivos.

**Proceso de comunicación**

- Detección: Los dispositivos detectan la presencia del otro a corta distancia.
- Establecimiento de conexión: Se negocian los parámetros de comunicación y se establece el enlace.
- Intercambio de datos: Se transmiten los datos de forma segura o a través del canal NFC.
- Finalización de la sesión: La comunicación se cierra y los dispositivos vuelven al estado de reposo.

## Aplicaciones de NFC

- Sector financiero: Pagos sin contacto.
- Transporte: Tarjetas de movilidad urbana.
- Empresas: Control de acceso.
- Salud: Identificación de pacientes.
- Educación: Control de asistencia.

## Amenazas de seguridad en NFC

**Principales riesgos**

- Intercepción de datos.
- Modificación de mensajes.
- Ataques de repetición.
- Clonación de tarjetas.
- Acceso no autorizado.

### Ataque de escucha (Eavesdropping)

**Descripción**

- Un ataque intercepta la comunicación NFC sin autorización.

**Consecuencias**

- Robo de información.
- Captura de identificadores.
- Obtención de credenciales.

**Ejemplo**

- Captura de datos durante una transmisión NFC.

### Ataque de reenvío (Relay)

**Descripción**

- El atacante extiende artificialmente la distancia de la comunicación NFC.

**Proceso**

- La víctima acerca su tarjeta o smartphone al atacante 1.
- El atacante 1 reenvía la comunicación a través de internet al atacante 2.
- El atacante 2 comunica la información al sistema legítimo (terminal NFC).
- El sistema legítimo procesa la solicitud creyendo que la tarjeta está cerca.

**Consecuencia**

- Permite realizar operaciones fraudulentas sin poseer físicamente la tarjeta.

### Clonación de tarjetas NFC

**Objetivo**

- Copiar la información de una tarjeta legítima.

**Posibles escenarios**

- Control de acceso.
- Transporte público.
- Sistemas de identificación.

**Impacto**

- Suplantación de identidad.
- Fraude.
- Accesos indebidos.

## Medidas de protección

- Cifrado de datos.
- Autenticación mutua.
- Tokens dinámicos.
- Monitoreo de transacciones.
- Validación de proximidad.
- Actualizaciones de firmware.
