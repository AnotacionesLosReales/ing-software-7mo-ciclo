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

---

## Sesión 2: Introducción a ADD

### Drivers Arquitectónicos

- Son el subconjunto de requisitos que tienen una gran importancia para la arquitectura de un sistema.
- Drivers funcionales: relevancia en la satisfacción del negocio, complejidad técnica, escenario relevante para la arquitectura.
- Drivers de atributos de calidad: relevancia en la satisfacción de los objetivos de negocio, complejidad técnica.
- Drivers de restricciones: todas las restricciones son consideradas drivers de restricciones.
