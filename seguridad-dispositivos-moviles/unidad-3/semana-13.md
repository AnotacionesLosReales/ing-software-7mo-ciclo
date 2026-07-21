# Semana 13: Seguridad WPA2 y WPA3 

## Seguridad WPA2

### Definición

WPA2 (Wi-Fi Protected Access 2) fue aprobado en 2004 por la Wi-Fi Alliance, basado en el estándar IEEE 802.11i.
Reemplazó definitivamente a WEP y WPA al incorporar cifrado AES como mecanismo de protección principal.

**Características**

- Cifrado AES-CCMP (128/256 bits).
- Autenticación mediante 4-Way Handshake.
- Dos modos: Personal (PSK) y Empresarial (802.1X).
- Compatible con la mayoría de dispositivos modernos.

### Modos de operación

- WPA2 Personal (PSK): Contraseña compartida. Ideal para hogares.
- WPA2 Enterprise (802.1X): Servidor RADIUS, credenciales individuales. Ideal para empresas y universidades.

### Funcionamiento

El usuario introduce una contraseña (PSK) o credenciales de una empresa.

**Proceso de autenticación con 4-Way Handshake**

- ANonce: El AP envía un número aleatorio (ANonce) al cliente para iniciar la negociación.
- SNonce + MIC: El cliente responde con su SNonce y un código de integridad (MIC).
- GTK + MIC: El AP envía la clave de grupo (GTK) cifrada y verifica autenticidad.
- Confirmación: El cliente confirma y se establece la sesión cifrada con AES-CCMP.

### Vulnerabilidades

**KRACK Attack (2017)**

Key Reinstallation Attack: explota el 4-Way Handshake para reinstalar claves ya en uso, permitiendo descifrar el tráfico Wi-Fi sin conocer la contraseña.

**PMKID Attack**

Permite capturar un identificador (PMKID) del AP sin cliente conectado, habilitando ataques offline de fuerza bruta contra la clave.

**Ataque de diccionario**

Si la contraseña PSK es débil, puede ser descifrada capturando el handshake y probando contraseñas con herramientas como Hashcat o Aircrack-ng.

**Sin protección entre clientes**

WPA2-Personal no protege el tráfico entre dispositivos del mismo AP, facilitando ataques Man-in-the-Middle en redes compartidas.

## Seguridad WPA3

### Definición

WPA3 (Wi-Fi Protected Access 3) fue lanzado en 2018 por la Wi-Fi Alliance como sucesor de WPA2.
Aborda las vulnerabilidades conocidas e introduce mejoras significativas de seguridad para redes personales, empresariales y abiertas.

**Características**

- Protocolo SAE - Simultaneous Authentication of Equals.
- Protección contra ataques de diccionario offline.
- Forward Secrecy: cada sesión genera claves únicas.
- Cifrado individualizado por dispositivo (OWE).
- Suite de seguridad de 192 bits para entornos críticos.

**Tecnologías clave**

- SAE (Dragonfly): Reemplaza PSK, resiste ataques offline.
- OWE (Enhanced Open): Cifra redes abiertas sin contraseña.
- PMF: Protege marcos de administración 802.11.

### Funcionamiento - Protocolo SAE

SAE utiliza el protocolo Dragonfly para negociar claves de forma segura.

- Commit: Cliente y AP intercambian compromisos criptográficos basados en la contraseña, sin revelarla. Se trabaja sobre curva elíptica.
- Confirm: Ambas partes demuestran que conocen la contraseña sin transmitirla. Se verifica la autenticidad mutua.
- PMK derivada: Se deriva la PMK (Pairwise Master Key) única para esa sesión, generando Forward Secrecy.
- Sesión AES-256: La comunicación se establece con AES-256, protegida contra espionaje y ataques de repetición.
