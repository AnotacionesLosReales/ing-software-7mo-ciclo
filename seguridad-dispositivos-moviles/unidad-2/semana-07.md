# Semana 7: Seguridad en dispositivos iOS

## Arquitectura de seguridad

- Seguridad a Nivel de Hardware: Cada dispositivo cuenta con claves AES de 256 bits (UID y GID) fusionadas directamente en el procesador. Esto hace que el cifrado sea rápido y físicamente imposible de extraer mediante software externo.
- Secure Enclave: Un coprocesador dedicado que aísla la información biométrica (Face ID/Touch ID), los datos del llavero (keychain) y las operaciones criptográficas críticas del resto del sistema operativo.
- Arranque Seguro (Secure Boot): En cada encendido, el hardware de Apple verifica de forma criptográfica la integridad del código a nivel de componentes (firmware, kernel), garantizando que el sistema no haya sido manipulado.
- Aislamiento de Aplicaciones (Sandboxing): Todas las aplicaciones y extensiones operan en entornos aislados y restringidos. Esto evita que una aplicación acceda a los datos de otra o modifique el sistema operativo.
- Cifrado de Archivos: Todo el sistema de archivos utiliza un cifrado por bloques integrado por hardware. Las claves se vinculan directamente al código de acceso del dispositivo y al hardware mencionado.
- Protección del Ecosistema: Apple revisa y firma criptográficamente cada aplicación antes de ser distribuida, lo que evita la inyección de malware y la instalación de software no autorizado.

## Uso de software autorizado en iOS

- Para autorizar y gestionar el uso de software en iOS, se debe garantizar que las aplicaciones provengan de fuentes confiables.
- Autorizar también implica controlar qué permisos de privacidad (cámara, ubicación, contactos) y uso de red otorgas a cada programa instalado en tu dispositivo.
- En iOS, los permisos de las aplicaciones se otorgan principalmente respondiendo a las alertas que aparecen al usarlas por primera vez, o de forma manual desde el menú de configuración del dispositivo.

## Uso de software no autorizado en iOS

- Vulnerabilidad ante ataques: Las modificaciones deshabilitan los controles de seguridad diseñados por Apple. Esto facilita que el software malicioso acceda a datos cifrados y al procesador principal.
- Riesgo de ejecución remota: Ciertas fallas pueden permitir que atacantes ejecuten comandos arbitrarios, lo que facilita el robo de información o la instalación de programas ocultos.
- Pérdida de soporte y garantía: Apple advierte que la instalación de software no autorizado anula el soporte técnico. Además, los dispositivos modificados pueden quedar inutilizables al intentar instalar futuras actualizaciones del sistema.
