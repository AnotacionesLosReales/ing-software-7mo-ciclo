# Semana 11: Navegación segura en dispositivos móviles

## Software malicioso

- El software malicioso (malware) en dispositivos móviles es un programa diseñado para robar información, espiar o dañar el teléfono.
- Suele disfrazarse de aplicaciones legítimas o llegar mediante enlaces fraudulentos, provocando un consumo rápido de batería, sobrecalentamiento, aumento en los datos móviles y publicidad excesiva.

### Tipos de Malware Más Comunes

- Spyware: Supervisa en secreto tu actividad, ubicación y contraseñas.
- Troyanos bancarios: Se hacen pasar por aplicaciones o páginas de bancos para robar tus credenciales financieras.
- Ransomware: Cifra tus archivos y exige un pago (rescate) para poder recuperarlos.
- Adware: Inunda el dispositivo con anuncios no deseados y puede forzar la descarga de otras aplicaciones.

### Señales de Alerta

- Descarga rápida de batería: El malware se ejecuta en segundo plano constantemente.
- Consumo inusual de datos: Puede estar transmitiendo tu información o descargando archivos ocultos.
- Aplicaciones desconocidas: Programas que no recuerdas haber instalado aparecen en el menú.
- Anuncios emergentes: Ventanas publicitarias que aparecen incluso fuera del navegado.

## Navegación segura

- La navegación segura en dispositivos móviles implica proteger la información personal y financiera contra amenazas como el phishing, el malware y el robo de datos.
- Para una protección efectiva, utiliza un navegador actualizado, evita conectarte a redes Wi-Fi públicas sin una VPN y activa herramientas de ciberseguridad móvil.

### Recomendaciones

- Actualiza tus sistemas: Mantén siempre actualizados tu sistema operativo (iOS o Android) y tus aplicaciones, ya que incluyen parches de seguridad críticos.
- Configura tu navegador: Asegúrate de activar funciones de protección proactiva en tus aplicaciones de navegación web (por ejemplo, activa los niveles de protección en Google Chrome).
- Descargas oficiales: Descarga aplicaciones únicamente desde tiendas oficiales como App Store o Google Play.
- Bloqueo del dispositivo: Protege tu teléfono utilizando métodos biométricos (huella dactilar, reconocimiento facial) o un PIN seguro para evitar accesos no autorizados en caso de pérdida o robo.
- Evita Wi-Fi públicas: No navegues en sitios donde necesites ingresar contraseñas o datos financieros al estar conectado a redes públicas, ya que son vulnerables a interceptaciones.

## Comandos de red en Kali Linux

- Comando ping: Su función es la de verificar la conectividad y latencia entre el dispositivo host y un dispositivo de destino en la red. Con ello, se puede verificar si el host de destino está disponible o no. Además, funciona mediante el protocolo Internet Control Message Protocol (ICMP) para enviar un paquete y esperar una respuesta.
- Comando nslookup: Su función es la de verificar los servidores DNS para obtener nombres de dominio y viceversa para saber si se está realizando una búsqueda correcta.
- Comando dig: Su función es similar al comando nslookup. Sin embargo, este comando ofrece información más detallada de la búsqueda. Además, sirve para analizar detalles adicionales del servidor DNS y solucionar problemas de configuración DNS.
- Comando whois: Su función es la de realizar una búsqueda en la base de datos donde se registran los dominios en internet. Además, proporciona información sobre el dominio como la empresa, el contacto del dueño, fechas de registro, etc.

### Diferencias entre nslookup y dig

- La principal diferencia que encontramos es el formato de respuesta.
- Mientras que al usar nslookup solo entregó una única sección en la respuesta, el comando dig entregó la respuesta en formato de divisiones por secciones (cabecera, pregunta, respuesta y detalles adicionales de la consulta).
- Otra diferencia se centra en la información brindada por ambos comandos, nslookup solo te brinda dirección IP y del servidor que a veces puede redundar, mientras que dig responde con más detalles sobre la información del servidor como qué otros servidores únicos están relacionados y el tiempo que tomó en realizar la consulta.

### Comando whois

- El comando whois proporciona información administrativa, de propiedad y del ciclo de vida del dominio a consultar.
- Proporciona información del propietario del dominio como nombre, organización y dirección de correo electrónico.
- Por parte del ciclo de vida del dominio, proporciona la fecha de registro del dominio, la fecha de expiración y la última actualización que recibió.

## Hardening de dispositivos móviles

- El hardening de dispositivos móviles es el proceso de fortalecer la seguridad de teléfonos y tabletas para reducir su superficie de ataque.
- Consiste en aplicar configuraciones estrictas, cifrado y control de accesos para mitigar vulnerabilidades y proteger los datos contra accesos no autorizados o ingeniería inversa.

### Técnicas

- Cifrado de datos: Asegura que los datos sean ilegales sin la clave de acceso. En sistemas Android modernos, esto está habilitado por defecto si utilizas un bloqueo de pantalla fuerte.
- Control de accesos y permisos: Otorga permisos estrictos solo a las aplicaciones que los necesitan. Revoca los permisos de "acceso a ubicación" o "micrófono" si una app no los requiere para funcionar.
- Gestión de actualizaciones: Mantener tanto el sistema operativo como las aplicaciones actualizadas es vital para parchear vulnerabilidades descubiertas recientemente.
- Bloqueo biométrico y contraseñas: Configura un PIN complejo o utiliza autenticación biométrica (huella dactilar/rostro) para el desbloqueo y para acceder a aplicaciones críticas (bancos, correos).
- Protección de aplicaciones: Conocido como Mobile App Hardening, implica utilizar herramientas que ofuscan el código y evitan que los atacantes realicen ingeniería inversa.

## OWASP Mobile TOP 10

- El OWASP Mobile Top 10 es un documento de concienciación reconocido mundialmente que destaca los riesgos de seguridad más críticos para las aplicaciones móviles.
- Actualizada en 2024 para reflejar el panorama actual de amenazas, la lista sirve de guía para desarrolladores, profesionales de la seguridad y CISO en la mitigación de vulnerabilidades que frecuentemente provocan filtraciones de datos.

### Riesgos del Top 10

- M1 - Improper Credential Usage: Una gestión deficiente o la codificación fija de contraseñas, claves API y tokens de autenticación los hace vulnerables a la exposición e interceptación.
- M2 - Inadequate Supply Chain Security: Riesgos derivados de la integración de bibliotecas, marcos de trabajo o servicios externos de terceros no verificados que pueden contener vulnerabilidades o código malicioso.
- M3 - Insecure Authentication and Authorization: Fallos en la verificación de la identidad del usuario o en la aplicación de los permisos de acceso adecuados, lo que permite a los atacantes secuestrar sesiones o eludir la seguridad.
- M4 - Insufficient Input/Output Validation: La falta de saneamiento de los datos procedentes del usuario o de fuentes externas puede dar lugar a ataques como la inyección de código o la corrupción de datos.
- M5 - Insecure Communication: Un cifrado deficiente o la falta de SSL/TLS durante la transmisión de datos permite a los atacantes interceptar información confidencial mediante ataques de intermediario (Man-in-the-Middle, MitM).
- M6 - Inadequate Privacy Controls: Mecanismos inexistentes o débiles para proteger los datos de los usuarios, lo que a menudo conlleva violaciones de los marcos de privacidad o el intercambio no autorizado de datos.
- M7 - Insufficient Binary Protections: La falta de protección, ofuscación o medidas antimanipulación en la aplicación permite a agentes malintencionados descompilarla, realizar ingeniería inversa o inyectar malware en ella.
- M8 - Security Misconfiguration: Una configuración predeterminada incorrecta o una configuración de seguridad incompleta en la plataforma móvil o en el servidor exponen la aplicación a diversos ataques.
- M9 - Insecure Data Storage: Almacenar información confidencial (como datos en caché, cookies o credenciales) en ubicaciones no cifradas o de fácil acceso en el sistema de archivos del dispositivo.
- M10 - Insufficient Cryptography: El uso de algoritmos de cifrado débiles o la implementación incorrecta de claves criptográficas permiten a los atacantes descifrar datos confidenciales almacenados o transmitidos.

