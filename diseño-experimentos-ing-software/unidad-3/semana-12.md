# Semana 12: Digital Product Performance Analytics

## Intro

### Software Quality

Hay dos nociones que son distintas, pero se relacionan:
- Software functional quality.
- Software structural quality.

#### Software functional quality

- Refleja cuán bien el diseño del software se basa en los functional requirements.
- También es importante considerar cómo se compara en el mercado con productos competidores.

#### Software structural quality

- Refleja cómo satisface los non-functional requirements que brindan soporte a la entrega de los functional requirements, por ejemplo, maintenability.
- Non-functional requirements son también criterios para evaluar un sistema de software.
- Performance, security, usability, compatibility no son solo features del sistema, sino características que se requieren.
- Cuando decimos que un software es seguro, portable, escalable, estamos hablando de sus quality atributes.

#### Software Quality Attributes

- **Interoperabilidad:** La capacidad del software para conectarse con otro sistema de software y comunicarse con él.
- **Reliability:** La capacidad del software de funcionar correctamente bajo ciertas condiciones. Se incluye *fault tolerance* y *recoverability*.
- **Availability:** Cubre la necesidad de que el software se encuentre accesible para cubrir peticiones.
- **Usability:** Mide el nivel de facilidad y otros aspectos relacionados como eficiencia y manejo de errores en relación a la interacción del usuario con el software.
- **Security:** Relacionado con la confidencialidad y la autenticidad.
- **Performance:** Se mide el tiempo de respuesta, latencia, velocidad de procesamiento, consumo de recursos, throughput (rendimiento) y eficiencia.
- **Scalability:** Reacciona a los cambios del software. Toma en cuenta los factores como número de usuarios y nuevos productos en el mercado.
- **Extensibility:** La capacidad para agregar funcionalidad a un componente de software sin modificar otras partes.
- **Adaptability:** Se refiere a la capacidad de modificar con facilidad el software según requisitos.
- **Testeability:** Se hace notar en los stages de building y test automation de componentes.
- **Auditability:** Significa la capacidad de realizar auditorías del sistema de software. Dicho proceso implica que todo el software sea seguro.
- **Observability:** Hace posible que los cambios se vean reflejados en el software.
- **Operability:** Significa el nivel del sistema para ser desplegado y operado durante tiempo de ejecución.

### Quality attribute scenario

- Es una manera de documentar quality attributes que se necesita comprobar.
- Se compone de seis elementos:
  - Source of stimulus. Personas internas o externas, un sistema, que crea el stimulus.
  - Stimulus. El response que llega al software.
  - Environment. Dónde tiene lugar el sitmulus.
  - Artifact. Reacción al stimulus. Algún componente del sistema.
  - Response. El response del artifact acorde con el stimulus recibido.
  - Response measure. La medida que se debería comprobar para determinar si el requisito se satisface.

## APM

 - Application Performance Monitoring entrega real-time y trending data sobre el performance de las aplicaciones y el nivel de satisfaccción de los usuarios.
 - APM permite identificar problemas potenciales con rapidez antes que ellos afecten a los usuarios finales.

### Strategy

- User experience monitoring.
- Code-level diagnostics.
- Key business transactions.
- Application infrastructure deep dive.
- Supporting infrastructure health.

## Observability

- Es la práctica de instrumentar sistemas con herramientas para recolectar data que sea accionable y que proporcione información sobre cuándo ocurre un error o issue, sino por qué.
- Observability ayuda a los equipos de software a:
  - Entregar software de alta calidad a escala.
  - Construir una sólidad cultura de innovación.
  - Optimizar las inversiones en cloud y otras tecnologías.
  - Ver performance del negocio digital en tiempo real.
 
### MELT (Metrics, Events, Logs, and Traces)

- Metrics. Las soluciones necesitan consumir metrics de cualquier source que los equipos han adoptado en el digital business.
- Traces. Traces permiten a los ingenieros entender los journeys, encontrar bottlenecks, identificar errores para corregirlos y optimizar. Tomar en cuenta estándares como W3C Trace Context y OpenTelemetry Project.
- Logs. Logs proporcionan high-fidelity data y contexto detallado sobre un event, para que los ingenieros puedan recrear lo que sucedió a cada milisegundo.
- Events. Son registros detallados y discretos de puntos significativos de análisis. Contienen un mayor nivel de abstracción que los logs. Por ejemplo, transaction events.
