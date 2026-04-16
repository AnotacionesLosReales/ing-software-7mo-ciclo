# Semana 2: Attribute-Driven Design (ADD)

## Sesión 1: Estilos arquitectónicos

### Video Datacenter

- Todos esos servidores se comunican mediante un rack.
- Juniper: Permite cargar caracteristicas de seguridad o de fallos.
- Fortinet es una marca que ofrece equipos de seguridad e información.
- Cuadrante de Garner: Es una herramienta de análisis de mercado que evalúa a los proveedores en función de su capacidad de ejecución y su visión estratégica. Se divide en cuatro cuadrantes: líderes, visionarios, jugadores de nicho y retadores.
- Se detalla la elección de un lenguaje de programación mediante papers.
- Soluciones de Storage: Son sistemas de almacenamiento de datos que pueden ser utilizados para guardar y gestionar grandes cantidades de información.

### Elementos Clave 

- **Componentes:** Encapsula parte de la funcionalidad.
- **Conectores:** Efectua y regula las interacciones entre los componentes.
- **Configuración:** También llamada topología. Es un conjunto de asociaciones específicas entre los componentes y conectores.
- **Patrones arquitectónicos:** Conjunto de decisiones de diseño de alto nivel aplicables a un **problema** de diseño repetitivo.

### Estilos de Arquitectura

- Es un patrón de arquitectura que define uso, componentes, restricciones e interacciones.
- Conformado por:
    - Un conjunto de tipos de elementos.
    - Un diseño topológico de los elementos y sus relaciones.
    - Un conjunto de restricciones semánticas.
    - Un conjunto de mecanismos de interacción.
- Algunos estilos arquitectónicos incluyen:
    - Despliegue: Cliente/Servidor, N-Tier/3-Tier.
    - Estructura: Component-Based, Layered Architectura.
    - Dominio: Domain-Driven Design.
    - Comunicación: SOA, Message-Bus, Micro Services.

#### Cliente / Servidor

- Cliente y servidor separados. Por ejemplo, un web browser.
- Variaciones: Peer-to-peer, servidores de aplicaciones.
- Beneficios: seguridad (información en el servidor), acceso centralizado y mantenimiento (servidor oculto ante el cliente).

#### Component-Based

- Se descompone en componentes lógicos y/o funcionales y se definen interfaces.
- Principios: Reusable, reemplazable, no depende del contexto, extensible, encapsulado e independiente.
- Beneficios: Facilidad de desarrollo y de evolución.

#### Domain-Driven Design (DDD)

- Basado en dominios de negocio.
- Desarrollo y negocio deben compartir un lenguaje en común (Ubiquitous language).

#### Layered

- Separación de funcionalidad.
- Capa lógica.
- Promueve la separación de ámbitos.
- Comunicación mediante interfaces bien definidas.
- Principios: Defición funcional clara, alta cohesión y bajo acoplamiento.
- Beneficios: Abstracción, reusabilidad y facilidad de pruebas.

#### Message-Bus

- Permite desacoplar los componentes que forman una aplicación y se acoplan a través de un intermediario (Message-Bus).
- Intercambio de mensajes, generalmente asíncronos.
- Tipos: Enterprise Service Bus e Internet Service Bus (Cloud).
- Beneficios: Extensibilidad, simplicidad y flexibilidad.

#### N-Tier / 3-Tier

- Separación de funcionalidad.
- Nivel físico.
- Basado en componentes.
- Capas independientes, una capa solo se comunica con sus adyacentes.
- Beneficios: Mantenibilidad, escalabilidad, flexibilidad y disponibilidad.

#### Service-Oriented Architecture (SOA)

- Provee servicios interoperables y expone funcionalidad de negocio.
- Bajo acoplamiento: interfaces definidas (XML, JSON).
- El alcance es de aplicación, no de componente.
- Principios: Autonomía, distribuibilidad, bajo acoplamiento, contratos de comunicación y políticas.
- Beneficios: Alineamiento a negocio, abstracción, localizables e interoperabilidad.

#### Micro Services

- Conjunto de pequeños servicios livianos y especializados.
- Implementados y desplegados de forma independiente.
- Beneficios: fácil de entender, escalable, reemplazable, fácil de desplegar y resistente.

### Requisitos funcionales

- Especifica lo que el sistema debe hacer.
- Se expresan en términos funcionales del sistema.

### Restricciones

- Decisión de diseño con cero grados de libertad.
- Características que no pueden ser negociadas (lenguaje de programación, protocolo) y son impuestas por el cliente.
- Ejemplo: Se debe usar C#, se debe usar el protocolo TCP/IP y debe estar hecho en 4 meses.
- Alcance, Costo, Tiempo y Calidad.

### Atributos de calidad

- Es una propiedad medible o probable de un sistema, que es usada para indicar que satisface necesidades de los stakeholders.
- Son las características esperables de un sistema.
- Ejemplos: Disponibilidad, modificabilidad y performance.
- Son necesarios para definir una correcta arquitectura.

#### Problemas para definir atributos de calidad

- Un atributo no siempre se puede medir o probar por su definición. Ejemplo: "El sistema debe ser modificable".
- No es claro lo que pretende dicha cualidad. Ejemplo: "¿Una falla en el sistema es un aspecto de disponibilidad, performance o seguridad?".
- Cada comunidad tiene su propio vocabulario.

#### Escenarios de atributos de calidad

- Un requisito de atributo de calidad debería ser no ambiguo y probable. Para lograrlo, se usan los escenarios de atributos de calidad como una forma de caracterizarlos.
- Es un mecanismo que permite caracterizar/capturar aspectos de atributos de calidad de una forma que pueda ser evaluado y usado en diseño.
- Existen dos tipos de escenarios de atributos de calidad:
    - General: Son independientes del sistema y pueden pertenecer a cualquier sistema. Ejemplo: Llega un requisito para hacer un cambio en la funcionalidad, y el cambio debe ser hecho en un momento particular dentro del proceso de desarrollo y dentro de un periodo de tiempo específico.
    - Concreto: Son específicos para un determinado sistema de consideración. Ejemplo: Llega un requisito para agregar soporte a un nuevo browser para un sistema web y el cambio debe ser hecho en, como máximo, 2 semanas.

#### Partes de un Escenario de atributo de calidad

<table border="1">
  <tr>
    <th rowspan="2"> ENTRADAS </th>
    <td> Fuente de estímulo </td>
    <td> Es la entidad (humano, otro sistema u otro actor) que generó el estímulo. </td>
    <td> Ejemplo: un alumno, el blackboard. </td>
  </tr>
  <tr>
    <td> Estímulo </td>
    <td> Es la condición a ser considerada al presentarse al sistema. </td>
    <td> Ejemplo: matricularse a un curso. </td>
  </tr>
  <tr>
    <th rowspan="2"> CONDICIONES </th>
    <td> Entorno </td>
    <td> Condiciones en las que se encuentra el sistema al presentarse al estímulo. </td>
    <td> Ejemplo: el día de matrícula regular o complementaria. </td>
  </tr>
  <tr>
    <td> Artefacto </td>
    <td> Componente o destinatario que recibe el estímulo (tiene que ser una parte del sistema). </td>
    <td> Ejemplo: el producto de software que te permite implementar el atributo de calidad. </td>
  </tr>
  <tr>
    <th rowspan="2"> RESULTADOS ESPERADOS </th>
    <td> Respuesta </td>
    <td> Define las acciones que se realizan frente al estímulo. </td>
    <td> Ejemplo: un mensaje de confirmación al presionar "Matricular". </td>
  </tr>
  <tr>
    <td> Medida de respuesta </td>
    <td> Métrica definida para el tipo de estímulo, de tal manera que resulte en un valor cuantificable. </td>
    <td> Ejemplo: Cuántos cursos han recibido matriculas por hora, en cuántos milisegundos demoró en llegar el mensaje de confirmación. </td>
  </tr>
</table>

### Tácticas

- Es una decisión de diseño.
- Influye en la respuesta de un atributo de calidad.
- Son formas de alcanzar atributos de calidad deseados.
- Un patrón de arquitectura empaqueta un conjunto de tácticas.

### Guía para las decisiones de diseño de calidad

#### Allocation of Responsabilities

- Identificar las responsabilidades más importantes.
    - Funcionamiento básico del sistema.
    - Infraestructura.
    - Cumplimiento de Atributos de Calidad.
- Determinar cómo dichas responsabilidades se asignan.
    - Elementos que no son Runtime.
    - Elementos de Runtime.

#### Coordination Model

- Identificar qué elementos del sistema DEBEN/NO DEBEN coordinar.
- Determinar las propiedades de la coordinación.
    - Timeliness -> puntualidad
    - Accuracy -> precisión
    - Completeness -> completitud
    - Correctness -> exactitud
    - Consistency -> consistencia
- Seleccionar los mecanismos de coordinación:
    - Sin Estado / Con Estado.
    - Síncrono / Asíncrono.
    - Entrega garantizada / Entrega no garantizada.

#### Data Model

- Selecciona las mayores abstracciones de los datos, sus operaciones y propiedades
- Determina la METADATA (datos altamente estructurados) que describe la información.
- Selecciona la tecnología con la que se organizan los datos.

#### Management of Resources

- Balancear el uso de recursos compartidos.
- Determinar los recursos a ser manejados y ver sus límites.
- Determinar las estrategias cuando haya contención de recursos.
- Determinar los elementos a ser afectados cuando haya saturación de recursos.

#### Mapping among architectural elements

- Mapeo entre los elementos en diferentes tipos de estructuras arquitectónicas.
- Mapeo entre elementos de software con elementos del entorno.

#### Binding time decisions

- Introduce un rango de variación.
- La variación puede ser circunscrita en las diferentes etapas en el ciclo de vida del software para diferentes entidades.
- Considera los costos de implementar una decisión y los costos de hacer una modificación después que se tiene implementada la decisión.

#### Choice of technology

- Si la tecnología es seleccionada por otros, se convierte en una restricción para la arquitectura.
- El arquitecto debe seleccionar un conjunto de tecnologías posibles que permitan realizar decisiones en cada una de las categorías anteriores.

### Atributos Relacionados con la Calidad del Sistema

- Disponibilidad: es la probabilidad que tiene el Sistema de estar operativo cuando se lo necesita.
- Interoperabilidad: es la capacidad en que dos o más sistemas pueden intercambiar información significativa.
- Modificalidad: relacionada con el costo de los cambios. Es uno de los atributos de calidad más difíciles de expresar.
- Performance: relacionada con el tiempo que le lleva al sistema responder a un evento que ocurre.
- Seguridad: habilidad de un sistema para resistir usos no autorizados y seguir proveyendo sus servicios a usuarios legítimos.
- Testeabilidad: facilidad que presenta un sistema para que se ejecuten las actividades de testing.
- Usabilidad: facilidad con la cual un usuario puede cumplir una tarea o utilizar un servicio ofrecido por el sistema.

### Drivers Arquitectónicos

- Son el subconjunto de requisitos que tienen una gran importancia para la arquitectura de un sistema.
- Drivers funcionales: relevancia en la satisfacción del negocio, complejidad técnica, escenario relevante para la arquitectura.
- Drivers de atributos de calidad: relevancia en la satisfacción de los objetivos de negocio, complejidad técnica.
- Drivers de restricciones: todas las restricciones son consideradas drivers de restricciones.

### Tácticas

- Método empleado con el fin de tener un objetivo.
- Más simples que patrones, un patrón puede englobar tácticas.

<table border="1">
    <tr>
        <th> Tipo de táctica </th>
        <th colspan="2"> Descripción </th>
    </tr>
    <tr>
        <td> Disponibilidad </td>
        <td> Diseñadas para habilitar resistencia a fallas. </td>
        <td> Categoría de fallas: Detección, Recuperación y Prevención </td>
    </tr>
    <tr>
        <td> Interoperabilidad </td>
        <td> Diseñadas para apoyar la integración entre sistemas. </td>
        <td> Categorías: Localización y Manejo de interfaces </td>
    </tr>
    <tr>
        <td> Modificabilidad </td>
        <td> Controlar la complejidad de realizar cambios. </td>
        <td> Acoplamiento: responsabilidades y módulos (BAJO). Cohesión: Unidad de propósito (ALTO). </td>
    </tr>
    <tr>
        <td> Performance </td>
        <td colspan="2"> Generar una respuesta para un evento con una restricción de tiempo. </td>
    </tr>
    <tr>
        <td> Seguridad </td>
        <td colspan="2"> Detectar, Reaccionar, Resistir y Recuperar </td>
    </tr>
    <tr>
        <td> Capacidad dePrueba </td>
        <td> Permitir facilidad de pruebas cuando aumente funcionalidad. </td>
        <td> Categorías: Añadir control yobservabilidad y Limitar complejidad de diseño. </td>
    </tr>
    <tr>
        <td> Usabilidad </td>
        <td> Relacionadas a qué tan fácil es para un usuario realizar una tarea. </td>
        <td> Iniciativa de usuario, de sistema, y mixta (Ej: cancelar e indicador de progreso). </td>
    </tr>
</table>

---

## Laboratorio 02: Nginx y Wildfly

### Configuración de nginx

- Abrir archivo nginx.conf para editar el puerto en el que escucha las solicitudes del servidor.
- Abrir cmd en la misma carpeta donde están los archivos de nginx.
- Ejecutar el comando 'nginx' para levantar el servidor.
- Ir al buscador y escribir la url '127.0.0.1:90' para acceder.
- Para editar la vista html, puede colocar una página propia en la carpeta 'html' donde debe colocar todos los archivos de su página web.
- Para bajarse el servidor nginx **desde otra ventana**, ejecuta 'nginx -s stop'.

### Wildfly

- Para bajarse Wildfly, accede a C:\wildfly\wildfly-39.0.1.Final\bin y abre una ventana de comandos.
- Luego, ejecutar el siguiente -> 'jboss-cli.bat --connect command=:shutdown'.

#### Wildfly Standalone
- SO -> Runtime (JDK 25) -> Middleware (Wildfly: servidor empresarial Jakarta).
- Jakarta es una especificación para servidores empresariales.
- Wildfly levanta una JVM que ejecuta todos los archivos .war para aplicaciones.
- Si se cae la máquina virtual, se cae todo.

#### Wildfly Domain
- SO -> Runtime (JDK 25) -> Middleware (Wildfly).
- En esta versión, se crean varias JVM.
- Se pueden correr varios archivos .war y se pueden replicar entre las máquinas virtuales.
- Se crea un balanceador en una de las JVM donde puede mandar a una de las copias de cada archivo (Redundancia activa).

#### Levantar Wildfly Standalone
- Ingresar a C:\wildfly\wildfly-39.0.1.Final\bin y abrir un cmd.
- Escribir 'dir *.bat'.
- Ejecutar 'standalone.bat'.
- Acceder a '127.0.0.1:8080' para visualizar el servidor levantado.
- Esto genera que corra en consola no como servicio (servicio significa que se instala en el SO).

#### Desplegar una aplicación .war en Standalone
- Buscar el archivo .war y arrastrarlo a la página de despliegues.
- Name: donde va a vivir la aplicación (Lab03 para 127.0.0.1:8080/Lab03).
- Runtime name: el nombre del archivo con el codigo (Lab03.war).

#### Levantar Wildfly Domain
- En el puerto 8080 está el balanceador.
- Para visualizar la consola, se debe acceder a '127.0.0.1:9990'.
- Repositorio de contenidos: aqui se cargan los archivos .war y desde ahi se distribuye a los servidores.

#### Desplegar una aplicación .war en Domain
- Buscar el archivo .war y arrastrarlo a la página de repositorio de contenidos.
- Name: donde va a vivir la aplicación (Lab03 para 127.0.0.1:8080/Lab03).
- Runtime name: el nombre del archivo con el codigo (Lab03.war).
- Buscar el archivo y elegir la opcíón Deploy, elegir "application-group".

#### Hacer caer un servidor en Domain
- Buscar en Runtime la sección Hosts.
- Buscar el servidor que deseas hacer caer.
- Elegir el tiempo para bajarse el servidor (0 segundos para que sea instantáneo).

#### Arquitectura y Comandos

NGNIX: Usa el puerto 80 y es un proxy que recibir un request desde el puerto 80 y esto lo traduce a hacia otro puerto.

http://127.0.0.1:90/ -> ip para acceder a la landing page por el puerto 90

Comando para levantar NGinx: nginx

Comando para bajar: nginx -s stop

Middleware: Es un software que se instala en servidores

Amazon -> OpenJDK Correto

J2EE
Jakarta: Es una especificacion
Wildfly cumple con la especificacion Jakarta

#### Arquitectura

Estructura Standalone: Levanta una JVM y usar .WAR - Una sola maquina virtual donde se despliega una aplicación

Estructura Standalone

JVM
Middleware -> Wildfly
Runtime -> JDK 25
Sistema Operativo

Estructura Domain

Varias JVM -> Corren varios archivos .WAR y un Balancer
Middleware -> Wildfly
Runtime -> JDK
SO

Wildfly Usa una arquitectura monolitica


#### Usando Wildfly

Wildfly: 
	- http://127.0.0.1:8080/ (Standalone)
	- comando: standalone

Wildfly: 
	- http://127.0.0.1:9990/ (Domain)
	- comando: domain

Por temas didactico se corre en consola, pero en producción se corre como servicio

Repositorio de contenido: Primero se sube los .WAR aqui para hacer el deployment.
Primero se sube y luego lo distribuye

En arquitectura: ¿Cual es el unico punto de falla?

Reglas de balance:
- Availability: Direcciona quien tiene mayor recursos
- Round Robin: Hace un request hasta que alguno se cae

---

## Sesión 2: Introducción a ADD

### Attribute-Driven Design

- El diseño de la arquitectura es llevada a cabo mediante una serie de rondas a través del proyecto de desarrollo de software.
- Dentro de las rondas de diseño, una serie de iteraciones de diseño es ejecutada.

#### Pasos

- Paso 1: Revisar las entradas.
- Paso 2: Establecer el objetivo de la iteración por medio de la selección de drivers.
- Paso 3: Escoger uno o más elementos del sistema para ser refinados.
- Paso 4: Escoger uno o más conceptos de diseño para satisfacer los drivers seleccionados.
- Paso 5: Instanciar los elementos arquitecturales, asignar responsabilidades y definir interfaces.
- Paso 6: Boceto de las vistas y registro de las decisiones de diseño.
- Paso 7: Ejecutar el análisis del diseño actual, revisar el objetivo de la iteración y logros del diseño.

### Tacticas

La tactica es la forma de conseguir un atributo

Alta Disponibilidad: 
## Detectar y prevenir la falla

### Detección

Echo Test
Monitoring: Applicaciones como ServersAlive sirven para monitorear hasta 10 servidores
Availability index: Verifica que servidor esta mas sobrecarga para enviar a otro que no lo este
Timestamp:
Voting: Usa Round Robin o Round Robin Balanceado

- Reduncacia Activa: Tener mas de una instancia. Es mucho mas costoso
- Redundancia Pasiva: Se prepara otra instancia (segundo servidor)
- Repuesto: Repuesto de Hardware
- Rollback: Hacer un punto de restauración
- Software Updgrade
- Retry
- Degradación
- Reconfiguración

Para bases de datos:

En SQL Server cuando se hace un query se deja en log y luego se ejecuta en la base de datos. Esto se denomina como Two face commit 

- Shadow: Sincronización de base de datos en caso falle un disco donde se encunter la BD. 
- Non Stop Forwarding: Estrategia de backup en donde se recupera desde el log en caso de que un backup hecho no cobra toda la data a restaurar.
