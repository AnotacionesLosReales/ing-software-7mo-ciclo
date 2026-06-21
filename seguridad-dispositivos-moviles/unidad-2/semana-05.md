# Semana 5: Permisos y paquetes en dispositivos Android

## Gestión de permisos

### Ejemplos de permisos

<table>
  <tr>
    <th>Permiso</th>
    <th>Qué hace</th>
  </tr>
  <tr>
    <td>INTERNET</td>
    <td>Permite a la aplicación conectarse a internet para enviar o recibir datos.</td>
  </tr>
  <tr>
    <td>ACCESS_NETWORK_STATE</td>
    <td>Permite a la aplicación leer el estado actual de la conexión del usuario, tanto como sus cambios y el tipo de conexión (Wi-Fi o datos móviles).</td>
  </tr>
  <tr>
    <td>READ_SMS</td>
    <td>Permite a la aplicación leer los SMS almacenados en el dispositivo del usuario.</td>
  </tr>
  <tr>
    <td>RECEIVE_SMS</td>
    <td>Permite a la aplicación leer los SMS entrantes del usuario.</td>
  </tr>
  <tr>
    <td>SEND_SMS</td>
    <td>Permite a la aplicación enviar SMS en segundo plano sin necesidad de usar la aplicación de mensajería del dispositivo.</td>
  </tr>
  <tr>
    <td>RECORD_AUDIO</td>
    <td>Permite a la aplicación el acceso al uso del micrófono del dispositivo para grabar audio.</td>
  </tr>
  <tr>
    <td>CAMERA</td>
    <td>Permite a la aplicación el acceso a la cámara del dispositivo.</td>
  </tr>
  <tr>
    <td>READ_CONTACTS</td>
    <td>Permite a la aplicación la lectura de información de contactos del dispositivo (números, nombres, etc.).</td>
  </tr>
  <tr>
    <td>SYSTEM_ALERT_WINDOW</td>
    <td>Permite a la aplicación generar elementos flotantes (como las burbujas de Messenger) por sobre otras aplicaciones.</td>
  </tr>
  <tr>
    <td>QUERY_ALL_PACKAGES</td>
    <td>Permite a la aplicación listar las otras aplicaciones instaladas en el dispositivo del usuario.</td>
  </tr>
  <tr>
    <td>READ_EXTERNAL_STORAGE</td>
    <td>Permite a la aplicación el acceso y lectura de multimedia de otros almacenamientos privados de otras aplicaciones.</td>
  </tr>
  <tr>
    <td>WRITE_EXTERNAL_STORAGE</td>
    <td>Permite modificar o sobreescribir archivos dentro del almacenamiento externo compartido del dispositivo.</td>
  </tr>
  <tr>
    <td>ACCESS_FINE_LOCATION</td>
    <td>Permite a la aplicación acceder a la ubicación geográfica precisa del dispositivo.</td>
  </tr>
  <tr>
    <td>REQUEST_IGNORE_BATTERY_OPTIMIZATIONS</td>
    <td>Permite a la aplicación solicitar al usuario que se la excluya de las funciones de ahorro de energía del dispositivo.</td>
  </tr>
</table>

### Tipos de permisos

- Permisos de tiempo de ejecución: Son aquellos que la app te solicita mientras la estás usando (por ejemplo, cuando abres un mapa y te pide permiso para acceder a tu ubicación).
- Permisos normales: Acciones que suponen un riesgo mínimo para tu privacidad.
- Permisos especiales: Operaciones avanzadas que requieren ser gestionadas de forma manual en la configuración del dispositivo.

## Gestión de paquetes

La gestión de paquetes en Android es el sistema que automatiza la instalación, actualización y eliminación de aplicaciones (archivos APK). 
A diferencia de Linux (en lo que está basado Android), Android no utiliza un gestor de comandos por terminal de forma nativa, sino que opera principalmente a través de la interfaz de la Google Play Store.

### Sistema Nativo (Google Play Store)

- Es el administrador oficial y predeterminado.
- Se encarga de la Instalación y actualización automática de tus aplicaciones.
- Verificación de seguridad mediante Google Play Protect.
- Desinstalación de apps desde el perfil del usuario.

### Instalador de Paquetes del Sistema

- Android incluye una herramienta oculta que procesa y despliega las aplicaciones.
- Se activa automáticamente al pulsar sobre un archivo APK o AAB.
- Solicita los permisos necesarios antes de instalar la aplicación en el almacenamiento interno

## Modo Desarrollador

- El Modo Desarrollador de Android es un menú oculto en el sistema operativo diseñado para programadores y usuarios técnicos. 
- Permite probar aplicaciones, optimizar el rendimiento del dispositivo y modificar configuraciones avanzadas del sistema.

### Herramientas principales que desbloquea

- Depuración USB: Esencial para conectar tu dispositivo a un ordenador y usar herramientas de desarrollo como ADB, permitiendo instalar aplicaciones directamente, hacer root, o recuperar el sistema.
- Aceleración de animaciones: Muchos usuarios acceden a este menú simplemente para cambiar la escala de las animaciones a 0.5x o desactivarlas por completo, haciendo que el teléfono se sienta mucho más rápido.
- Ubicación del puntero / Mostrar toques: Muestra en la pantalla un punto visual que indica dónde estás pulsando, muy útil para grabar videotutoriales.
- Límite de procesos en segundo plano: Permite restringir cuántas aplicaciones pueden ejecutarse al mismo tiempo en la memoria, lo que puede ayudar a ahorrar batería o mejorar el rendimiento en móviles de gama baja
- Ajustes de Bluetooth: Permite forzar códecs de audio de mayor calidad (como aptX o LDAC) si usas auriculares inalámbricos de alta gama.
