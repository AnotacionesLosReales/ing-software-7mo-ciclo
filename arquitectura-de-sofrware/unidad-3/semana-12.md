# Semana 12: On-Premise / Cloud Integration

## Patrones de Arquitectura de Microservicios

- Permite la entrega y despliegue continuos de aplicaciones grandes y complejas:
  - Mejor capacidad de prueba - los servicios son más pequeños y rápidos de probar.
  - Mejor capacidad de implementación - los servicios pueden implementarse de forma independiente.
  - Permite organizar el esfuerzo de desarrollo en torno a múltiples equipos.
  - Cada equipo es propietario y responsable de uno o más servicios individuales. Cada equipo puede desarrollar, desplegar y escalar sus servicios independientemente de todos los demás equipos.

### Patrones relacionados

- Hay muchos patrones relacionados con el patrón de microservicios. La arquitectura monolítica es una alternativa a la arquitectura de microservicios.
- Los otros patrones abordan los problemas que encontrará al aplicar la arquitectura de microservicios

<img src="https://i.imgur.com/C8zVyUk.png">

#### Patrones de descomposición

**Descomposición por capacidad de negocio**

- Defina los servicios correspondientes a las capacidades empresariales.
- Una capacidad empresarial es un concepto del modelado de arquitectura empresarial.
- Es algo que una empresa hace para generar valor. Una capacidad de negocio a menudo corresponde a un objeto de negocio, por ejemplo.

<img src="https://i.imgur.com/OWPpKn8.png">

**Descomposición por dominio**

- Los subdominios se pueden clasificar de la siguiente manera:
  - Núcleo - diferenciador clave para el negocio y la parte más valiosa de la aplicación.
  - Apoyo - relacionado con lo que hace el negocio, pero no un diferenciador. Estos pueden ser implementados internamente o externalizados.
  - Genérico - no específico para el negocio y se implementan idealmente utilizando el software fuera de la estantería.

<img src="https://i.imgur.com/URxoV1c.png">

#### Patrones de despliegue (Infrastructure Patterns)

<img src="https://i.imgur.com/nxWeZCJ.png">

- Múltiples instancias de servicios por host - despliega múltiples instancias de servicios en un sólo host.
- Una instancia de servicio por host - despliega cada instancia de servicio en su propio host.
- Una instancia de servicio por máquina virtual - despliega cada instancia de servicio en su propia máquina virtual.
- Una instancia de servicio por contenedor - despliega cada instancia de servicio en su propio contenedor.
- Despliegue sin servidor (BaaS) - despliega un servicio en una plataforma de "BaaS" (Backend-As-A-Service).
- Plataforma de despliegue de servicios - despliega servicios usando una plataforma de despliegue altamente automatizada que provee abstracción de servicios.
- Sidecar (Acompañamiento) - un componente o proceso auxiliar (el sidecar) se acopla a una aplicación principal para ampliar o mejorar sus funcionalidades sin modificar su código original.
- Service Mesh (Red de servicios) - sesacopla la lógica de red de la aplicación, permitiendo manejar el enrutamiento, la seguridad y la observabilidad sin modificar el código de los servicios.

**Despliegue Serverless**

- Problema: ¿Como se empaquetan y despliegan los servicios?
- Solucion: Use una infraestructura de implementación que oculte cualquier concepto de servidores (es decir, recursos reservados o preasignados): hosts físicos o virtuales, o contenedores. La infraestructura toma el código de su servicio y lo ejecuta. Se le cobrará por cada solicitud en función de los recursos consumidos.
- Condiciones:
  - Los servicios se escriben usando una variedad de idiomas, marcos y versiones de marcos
  - Cada servicio consta de múltiples instancias de servicio para rendimiento y disponibilidad
- Proveedores: AWS Lambda, Google Cloud Functions, Azure Functions.

**Servicio Plataforma de Despliegues**

- Problema: ¿Cómo se empaquetan e implementan los servicios?
- Solucion: Utilice una plataforma de implementación, que es una infraestructura automatizada para la implementación de aplicaciones. Proporciona un conjunto de abstracción de servicio, que es un conjunto con nombre, de instancias de servicio de alta disponibilidad (por ejemplo, balanceado de carga).
- Condiciones:
  - Los servicios se escriben utilizando una variedad de lenguajes, marcos y versiones de marco
  - Cada servicio consta de varias instancias de servicio para el rendimiento y la disponibilidad
- Proveedores: Docker Swarm Mode, Kubernetes, Plataformas Serverless, PaaS incluyendo Cloud Foundry y AWS Elastic Beanstalk.

#### Patrones de Intereses Transversales (Application Infrastructure Patterns)

<img src="https://i.imgur.com/0qvmks3.png">

- Chasis de microservicios - un framework que maneja intereses transversales y simplifica el desarrollo de servicios.
- Externalized configuration - externaliza todas las configuraciones, como la dirección de la base de datos, y credenciales

**Chasis de microservicios**

- Configuración externalizada: incluye credenciales y ubicaciones de red de servicios externos, como bases de datos y corredores de mensajes
- Registro: configuración de un marco de registro como log4j o logback
- Verificaciones de estado: una URL que un servicio de monitoreo puede "hacer ping" para determinar el estado de la aplicación
- Métricas: mediciones que proporcionan información sobre lo que está haciendo la aplicación y cómo está funcionando
- Seguimiento distribuido: servicios de instrumentos con código que asigna a cada solicitud externa un identificador único que se pasa entre los servicios.
- Solucion: Cree sus microservicios utilizando un marco de chasis de microservicios, que maneja preocupaciones transversales.
- Uso: Spring Boot y Spring Cloud, Dropwizard (Java), Go (Gizmo, Micro, Go Kit).

**Externalized configuration**

- Problema: ¿Cómo habilitar un servicio para ejecutarse en múltiples entornos sin modificación?
- Contexto: Se debe proporcionar un servicio con datos de configuración que le indiquen cómo conectarse a los servicios externos / de terceros. Por ejemplo, la ubicación de red de la base de datos y las credenciales
- Solucion: Externalice toda la configuración de la aplicación, incluidas las credenciales de la base de datos y la ubicación de la red. Al inicio, un servicio lee la configuración desde una fuente externa, p. Variables de entorno del sistema operativo, etc.

#### Patrones de Comunicación

<img src="https://i.imgur.com/ehtdFdp.png">

##### Estilos de Comunicación

¿Qué mecanismos de comunicación usan los servicios para comunicarse entre ellos y con sus clientes externos?

<img src="https://i.imgur.com/yWlFLOY.png">

- Llamada a procedimiento remoto - usa un protocolo orientado a RPC para la comunicación entre servicios.
- Mensajería - usa mensajes asíncronos para la comunicación entre servicios.
- Protocolo específico del dominio - usa un protocolo especificado por el dominio.

**Remote Procedure Invocation (RPI)**

- Solucion: Usar RPI para intercomunicación Intereservicios. El cliente usa un protocolo request/reply- para hacer pedidos al servicio.
- Ejemplos: REST, gRPC, Apache Thrift.

**Mensajería**

- Solucion: Utilice la mensajería asincrónica para la comunicación entre servicios. Servicios de comunicación mediante el intercambio de mensajes a través de canales de mensajería.
- Ejemplos: Apache Kafka, ActiveMQ, RabbitMQ

**Domain –Specific Protocol**

- Solucion: Use un protocolo específico de dominio para la comunicación entre servicios.
- Ejemplos: Protocolos de correo electrónico como SMTP e IMAP y Protocolos de transmisión de medios como RTMP, HLS y HDS.

##### External API

¿Cómo se comunican los clientes con los servicios?

- API Gateway (Puerta de enlace) - un servicio que provee a todos los clientes con una interfaz única hacia los servicios.
- Backend para el front-end - una puerta de enlace por cada tipo de cliente

**API Gateway**

- Problema: ¿Cómo acceden los clientes de una aplicación basada en microservicios a los servicios individuales?
- Contexto: La granularidad de las API proporcionadas por microservicios a menudo es diferente de lo que necesita un cliente.
- Uso: Un único punto de entrada, APIs específicas para clientes en la comunicación, Traducción de protocolos.

**Backend for Front-end**

- Problema: ¿Cómo acceden los clientes de una aplicación basada en microservicios a los servicios individuales?
- Contexto: Diferentes clientes necesitan diferentes datos. Por ejemplo, la versión del navegador de escritorio del escritorio de una página de detalles del producto suele ser más elaborada que la versión móvil.
- Uso: Es una variación del API Gateway. Se construye un API Gateway para cada aplicación cliente.

#### Patrones de Arquitectura de Bases de Datos

**Database per service Pattern**

<img src="https://i.imgur.com/UVlUD7T.png">

#### Patrones de Descubrimiento

**Service Registry Pattern**

<img src="https://i.imgur.com/lA0zHBd.png">

#### Patrones de Confiabilidad (Confiability)

**Circuit Breaker Pattern**

<img src="https://i.imgur.com/qfeCVh2.png">

**Bulkhead Pattern**

<img src="https://i.imgur.com/CzYoRKU.png">

#### Patrones para Mantener la Consistencia de la Información

**Saga Pattern**

<img src="https://i.imgur.com/D1Obzwd.png">

#### Patrones de Consultas

**CQRS Pattern**

<img src="https://i.imgur.com/uUYRU5v.png">

**API Composition Pattern**

<img src="https://i.imgur.com/3KD1UKj.png">

#### Otros patrones

**Event-driven Architecture Pattern**

<img src="https://i.imgur.com/edgRgqK.png">

**Retry Pattern**

<img src="https://i.imgur.com/yj9F8UV.png">

**Strangler Fig Pattern**

<img src="https://i.imgur.com/MbACHT9.png">

**Leader Election Pattern**

<img src="https://i.imgur.com/F6UjfDO.png">
