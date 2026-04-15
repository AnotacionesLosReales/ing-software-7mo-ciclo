# Semana 2: Arquitectura de Android y iOS

## Sesión 1: Sistema operativo Android

### Versiones

- Desde su lanzamiento oficial en 2008, hasta la versión 9, se le dio siempre un nombre que correspondía a una golosina o postre, cuya primera letra seguía de forma secuencial según el alfabeto.
- Las versiones incluyen:
  - Android 1.0 - 1.1
  - Android 1.5 Cupcake
  - Android 1.6 Donut
  - Android 2.0 - 2.1 Eclair
  - Android 2.2 - 2.2.3 Froyo
  - Android 2.3 - 2.3.7 Gingerbread
  - Android 3.0 - 3.2.6 Honeycomb
  - Android 4.0 - 4.0.4 Ice Cream Sandwich
  - Android 4.1 - 4.3.1 Jelly Bean
  - Android 4.4 - 4.4.4 Kit Kat
  - Android 5.0 - 5.1.1 Lollipop
  - Android 6.0 - 6.0.1 Marshmallow
  - Android 7.0 - 7.1.2 Nougat
  - Android 8.0 - 8.0.1 Oreo
  - Android 9 Pie

### Historia del bloqueo comercial a Huawei

- Tras la imposición del gobierno de Donald Trump, se quiebran las relaciones comerciales de gigantes tecnológicos estadounidenses con Huawei.
- El elemento clave es Google Play Services (el hub de soluciones de Google), por lo cual al no tener Google en Android se pierde: GoogleProtect, Google Play Store, Google Drive, Google Play Books, etc.
- En respuesta, Huawei crea HarmonyOS, un sistema operativo multiplataforma para conectar varios dispositivos en un ecosistema unificado.

### Arquitectura en Android

<table border="1">
  <tr>
    <th> Layer </th>
    <td colspan="3"> Funciones </td>
  </tr>
  <tr>
    <th> Núcleo (Kernel) </th>
    <td> Kernel basado en Linux. También se maneja la batería. </td>
    <td> Android utiliza una estructura de Generic Kernel Image (GKI) para estandarizar la base y facilitar actualizaciones, especialmente en versiones modernas. </td>
    <td> Drivers: Audio, Keypad, Shared Memory, Binder (IPC), Bluetooth, USB, Display, Camara, Wi-Fi. </td>
  </tr>
  <tr>
    <th> Hardware Abstraction Layer </th>
    <td> Permite a los fabricantes de dispositivos (OEMs) implementar componentes de hardware sin modificar el código fuente de Android de alto nivel, facilitando la portabilidad. </td>
    <td> Es una interfaz estándar de software que conecta el marco de trabajo (framework) de Android de alto nivel con los controladores (drivers) de hardware subyacentes. </td>
    <td> Audio, Bluetooth, Camara, Sensores, etc. </td>
  </tr>
  <tr>
    <th> Android Runtime (ART) </th>
    <td> Entorno de ejecución de aplicaciones (motor) de Android, situado en la segunda capa de su arquitectura que transforma el código de las apps en instrucciones nativas. </td>
    <td> Sustituye a Dalvik (Android 5.0) utilizando compilación AOT (Ahead-of-Time), instalando las apps precopiladas para mejorar el rendimiento, reducir el consumo de energía y agilizar el inicio de aplicaciones. </td>
    <td> Core Librerias: conjunto de bibliotecas base de Java que permiten a los desarrolladores utilizar el lenguaje Java para crear aplicaciones Android. </td>
  </tr>
  <tr>
    <th> Native C/C++ Libraries </th>
    <td> Conjuntos de código precompilado, creado con el Android NDK (Native Development Kit), que permiten a los desarrolladores ejecutar tareas de alto rendimiento o reutilizar bibliotecas existentes. </td>
    <td> A diferencia de Java/Kotlin, este código se compila para arquitecturas específicas (ARM, x86) y se comunica con la app a través de JNI (Java Native Interface). </td>
    <td> Webkit, Media Framework, OpenMAX AL, OpenGL ES, Libc, etc. </td>
  </tr>
  <tr>
    <th> Java API Framework </th>
    <td> Proporciona acceso a funciones del sistema operativo (botones, notificaciones, cámara, GPS) y gestiona recursos. </td>
    <td> Content Provider y View System (Herramientas para diseñar la interfaz de usuario como listas, botones y cuadros de texto). </td>
    <td> Managers: Activity, Location, Package, Notification, Resource, Telephony, Window. </td>
  </tr>
  <tr>
    <th> System Apps </th>
    <td> Es el nivel superior de la arquitectura, conformado por aplicaciones preinstaladas (navegador, correo, cámara, ajustes) ubicadas en la partición /system/app </td>
    <td> Dialer, Email, Calendar, Camera, etc. </td>
    <td> Por lo general, son aplicaciones de lectura útil para el sistema. </td>
  </tr>
</table>

---

## Sesión 2: Sistema operativo iOS

### Arquitectura del sistema iOS

<table border="1">
  <tr>
    <th> Layer </th>
    <td colspan="3"> Funciones </td>
  </tr>
  <tr>
    <th> Core OS </th>
    <td> Servicios del sistema y compatibilidad kernel </td>
    <td> Gestiona funciones de bajo nivel como el núcleo (kernel) Darwin/BSD, controladores de dispositivos, seguridad, redes y sistema de archivos, siendo fundamental para el funcionamiento de las capas superiores. </td>
    <td> Incluye frameworks para encriptación, certificados, almacenamiento seguro y autenticación. </td>
  </tr>
  <tr>
    <th> Core Services </th>
    <td> Libreta de direcciones, base principal, localización principal, red CF, SQLite, soporte XML. </td>
    <td> Ofrece infraestructura crítica como acceso a archivos, redes, persistencia de datos (Core Data), localización y manejo de la libreta de direcciones. </td>
    <td> Foundation Framework: Biblioteca base para gestión de memoria, serialización de datos y tipos de datos básicos. </td>
  </tr>
  <tr>
    <th> Media (ART) </th>
    <td> OpenGL ES, Quartz, Gráficos principales, audio principal, OpenAI, reproductor multimedia. </td>
    <td> Incluye Core Media (objetos multimedia de bajo nivel), AV Foundation (audiovisuales basados en tiempo) y Core Animation. </td>
    <td> Es el nivel de la arquitectura del sistema operativo dedicado a la gestión de contenido multimedia, proporcionando soporte para audio, video y gráficos. </td>
  </tr>
  <tr>
    <th> Cocoa Touch (App Layer) </th>
    <td> UIKit y Base. </td>
    <td> Capa de abstracción superior en la arquitectura de iOS, esencial para crear aplicaciones nativas en iPhone, iPad y iPod touch. </td>
    <td> Maneja interacciones táctiles, movimientos del dispositivo (sacudir) y eventos de control remoto. </td>
  </tr>
</table>
