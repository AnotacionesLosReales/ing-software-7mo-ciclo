# Semana 4: Seguridad en dispositivos Android

## Modelo de seguridad en Android

- Autorización multipartita: La plataforma, el desarrollador y el usuario interactúan mediante un sistema de permisos donde el usuario tienes la última palabra.
- Aislamiento de aplicaciones (Sandboxing): Cada aplicación opera en su propio entorno cerrado. No pueden acceder a los datos de otras apps ni del sistema a menos que se les otorguen permisos explícitos.
- Permisos de tiempo de ejecución: Las apps deben solicitar acceso a datos sensibles (cámara, ubicación, contactos) mientras las usas, y no al momento de instalarlas, dándote control total.

## Capas de protección

- Google Play Protect: Servicio que analiza las aplicaciones en tu dispositivo de forma automática y diaria para detectar comportamientos maliciosos.
- Cifrado de extremo a extremo: Los dispositivos Android modernos cifran los datos del usuario de forma predeterminada, haciendo inaccesible la información si el teléfono se bloquea.
- Seguridad de la cuenta de Google: El control sobre tu dispositivo está ligado a tu cuenta. Esto incluye herramientas biométricas (huella, rostro) y la Verificación en dos pasos para evitar accesos no autorizados.

## Riesgos a evitar

- Versiones de Android modificadas: Instalar ROMs no oficiales o eliminar el control del fabricante (desbloquear el bootloader) deshabilita la seguridad integrada de Google y te expone a software dañino.
- Fuentes desconocidas: Descargar archivos .apk desde sitios web o tiendas no verificadas es la principal vía de infección de malware.

## Mejores prácticas de seguridad

- Mantén el sistema actualizado: Instala siempre las últimas actualizaciones de Android y los Parches de Seguridad para cubrir vulnerabilidades recientes.
- Revisa permisos de apps: Ve a Configuración > Privacidad > Administrador de permisos y revoca el acceso a aplicaciones que no utilizas o que piden datos innecesarios.
