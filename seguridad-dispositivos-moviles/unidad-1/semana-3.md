# Semana 3: Historia de la seguridad en dispositivos móviles

## Sesión 1: Seguridad en dispositivos Android y iOS

### El caso Android

#### Modelo de permisos en Android

- Pueden dividirse en:
  - Permisos de API.
  - Permisos de sistema.
  - Permisos de IPC.
- En aplicaciones Android, se declaran en el archivo AndroidManifest.xml y se solicitan en runtime.
- Se utilizan ActivityCompat.requestPermissions y onRequestPermissionsResult para manejar la respuesta del usuario, garantizando la privacidad y seguridad de los datos.

**Declaración en AndroidManifest.xml**
```
<uses-permission android:name="android.permission.CAMERA" />
```

**Verificación y solicitud en runtime**
```
if (ContextCompat.checkSelfPermission(this, Manifest.permission.CAMERA)
    != PackageManager.PERMISSION_GRANTED) {
    // Solicitar permiso
    ActivityCompat.requestPermissions(this,
        arrayOf(Manifest.permission.CAMERA), REQUEST_CODE)
} else {
    // Permiso ya concedido, ejecutar acción
}
```

**Manejar la respuesta**
```
override fun onRequestPermissionsResult(requestCode: Int,
    permissions: Array<String>, grantResults: IntArray) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults)
    if (requestCode == REQUEST_CODE) {
        if (grantResults.isNotEmpty() && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
            // Permiso concedido
        } else {
            // Permiso denegado
        }
    }
}
```

#### Mejores Prácticas para uso de permisos en aplicaciones

- Solicitar permisos solo cuando sean necesarios.
- Explicar al usuario para qué se necesita el permiso antes de solicitarlo.
- Gestionar el caso de que el usuario deniegue el permiso.

#### Fichero .apk

- La mayoría de aplicaciones para Android están escritas en Java y se distribuyen mediante un APK (Android Package Kit) que, en general, tiene la siguiente estructura:

<div align="center">
  <img src="https://i.imgur.com/PoOUfzl.png" alt="Imagen de la estructura del fichero .apk">
</div>

- AndroidManifest.xml: define información crucial para el sistema operativo, como el nombre del paquete, componentes (actividades, servicios), permisos de seguridad, icono y versión de la app.
- Directorio META-INF: contiene MANIFEST.MF, CERT.RSA y CERT.SF y es un directorio dentro de los archivos APK o JAR que almacena metadatos, principalmente el archivo de manifiesto (MANIFEST.MF) y los certificados de firma digital.
- Directorio lib: almacena código compilado para el procesador y puede contener los siguientes subdirectorios: armeabi, armeabi-v7a, arm64-v8a, x86, x86_64, mips.
- Fichero resources.arsc: archivo binario esencial en los paquetes APK de Android que contiene metainformación de recursos precompilados, como tablas de ID, cadenas de texto, estilos, colores y referencias a recursos XML.

### El caso iOS

#### Reducción de superficie de ataque

- Se basa en un principio básico que indica que mientras menos código o aplicaciones relacionadas exista, será menos factible de encontrar una vulnerabilidad.

#### Reducción de aplicaciones “útiles” para un atacante

- Apple no incorpora un Shell que pudiera servir a un atacante.

#### Separación de privilegios

- iOS separa los procesos mediante usuarios, grupos y mecanismos de acceso a archivos. Por ejemplo, se tienen los usuarios mobile, root y _wireless.

#### Protección por firma de código

- Todos los binarios y librerías deben estar firmadas por una autoridad de confianza (como Apple) antes de que el núcleo permita su ejecución.

#### Sandboxing

- Se estableció como una “técnica” de seguridad bajo la sospecha de que alguna aplicación pudiera ser objeto de un ataque o pudiera estar comprometida con algún malware.
- Lo que busca el sandboxing es aislar el posible daño y evitar que éste se difumine hacia otras aplicaciones.

---

## Sesión 2: 
