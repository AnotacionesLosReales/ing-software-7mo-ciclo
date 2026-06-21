# Semana 12: Introducción a las redes inalámbricas

## Intro

Una red inalámbrica (Wireless Network) permite la comunicación entre dispositivos mediante ondas electromagnéticas, eliminando la necesidad de utilizar cables físicos.

### Características:

- Flexibilidad y movilidad.
- Fácil instalación.
- Escalabilidad.
- Menor costo de infraestructura.
- Permite conectar múltiples dispositivos
 
### Componentes principales

<table>
  <tr>
    <th>Componente</th>
    <th>Función</th>
  </tr>
  <tr>
    <td>Router o Punto de Acceso (AP)</td>
    <td>Emite la señal Wi-Fi</td>
  </tr>
  <tr>
    <td>Tarjeta de red inalámbrica</td>
    <td>Permite conectarse a la red</td>
  </tr>
  <tr>
    <td>Dispositivos clientes</td>
    <td>Computadoras, celulares, tablets</td>
  </tr>
  <tr>
    <td>Antenas</td>
    <td>Transmiten y reciben señales</td>
  </tr>
</table>

### Estándares IEEE 802.11

<table>
  <tr>
    <th>Estándar</th>
    <th>Frecuencia</th>
    <th>Velocidad</th>
  </tr>
  <tr>
    <td>802.11b</td>
    <td>2.4 GHz</td>
    <td>11 Mbps</td>
  </tr>
  <tr>
    <td>802.11g</td>
    <td>2.4 GHz</td>
    <td>54 Mbps</td>
  </tr>
  <tr>
    <td>802.11n</td>
    <td>2.4 y 5 GHz</td>
    <td>600 Mbps</td>
  </tr>
  <tr>
    <td>802.11ac</td>
    <td>5 GHz</td>
    <td>1.3 Gbps</td>
  </tr>
  <tr>
    <td>802.11ax (Wi-Fi 6)</td>
    <td>2.4 y 5 GHz</td>
    <td>Hasta 9.6 Gbps</td>
  </tr>
</table>

### Importancia de la seguridad en redes inalámbricas

La información transmitida por Wi-Fi viaja por el aire, por lo que puede ser interceptada por personas no autorizadas. Riesgos de una red insegura

- Robo de información.
- Acceso no autorizado.
- Pérdida de privacidad.
- Consumo de ancho de banda por intrusos.
- Ataques informáticos.

## Seguridad WEP

- WEP (Wired Equivalent Privacy) fue el primer mecanismo de seguridad implementado en redes Wi-Fi.
- Su objetivo era proporcionar un nivel de seguridad similar al de una red cableada.

**Características**

- Utiliza cifrado RC4.
- Claves de 64 y 128 bits.
- Fácil configuración.
- Actualmente es considerado inseguro.

**Ventajas**

- Fácil implementación.
- Compatible con dispositivos antiguos.

**Desventajas**

- Vulnerable a ataques.
- La clave puede ser descubierta en pocos minutos.
- No ofrece una protección adecuada.

### Funcionamiento de WEP

- El usuario introduce una contraseña.
- Los datos se cifran mediante RC4.
- El router y el dispositivo utilizan la misma clave para descifrar la información.

El cifrado RC4 (Rivest Cipher 4) es un algoritmo de cifrado de flujo (stream cipher) creado por Ron Rivest en 1987.
Es conocido por su velocidad y simplicidad, operando byte a byte mediante operaciones lógicas XOR. Aunque históricamente fue muy popular en redes inalámbricas (como WEP) y protocolos web (SSL/TLS) actualmente está obsoleto y se considera inseguro.

## Seguridad WPA

- WPA (Wi-Fi Protected Access) fue creado para solucionar las vulnerabilidades de WEP.
- Proporciona un nivel de seguridad mucho mayor.

**Características**

- Utiliza TKIP (Temporal Key Integrity Protocol).
- Cambia las claves de cifrado dinámicamente.
- Mayor protección contra ataques.
- Compatible con la mayoría de dispositivos.

### Funcionamiento de WPA

**Modos de operación**

- WPA Personal (WPA-PSK): Utiliza una contraseña compartida entre todos los usuarios. Ejemplo: Contraseña Wi-Fi: Redes2026@
- WPA Enterprise: Utiliza un servidor de autenticación y credenciales individuales para cada usuario. Se emplea en:
  - Empresas.
  - Universidades.
  - Organizaciones.
 
## Comparación entre WEP y WPA

<table>
  <tr>
    <th>Característica</th>
    <th>WEP</th>
    <th>WPA</th>
  </tr>
  <tr>
    <td>Año de aparición</td>
    <td>1997</td>
    <td>2003</td>
  </tr>
  <tr>
    <td>Algoritmo</td>
    <td>RC4</td>
    <td>TKIP</td>
  </tr>
  <tr>
    <td>Nivel de seguridad</td>
    <td>Bajo</td>
    <td>Medio</td>
  </tr>
  <tr>
    <td>Cambio dinámico de claves</td>
    <td>No</td>
    <td>Sí</td>
  </tr>
  <tr>
    <td>Vulnerabilidad</td>
    <td>Alta</td>
    <td>Menor</td>
  </tr>
  <tr>
    <td>Recomendado actualmente</td>
    <td>No</td>
    <td>Sí</td>
  </tr>
</table>
