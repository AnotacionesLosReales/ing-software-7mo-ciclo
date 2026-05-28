# Semana 5: Interprocess communication in a Microservice Architecture

## Sesión 1: Evolution App Structures

### ¿Qué es la Ingeniería de Software?

- La aplicación de un enfoque sistemático, disciplinado y cuantificable al desarrollo, operación y mantenimiento del software; esto es, la aplicación de la ingeniería al software.
- El propósito de la ingeniería de software es controlar la complejidad, no crearla.

### La arquitectura y el diseño difieren en tres áreas:

<table>
  <tr>
    <th></th>
    <th>Arquitectura</th>
    <th>Diseño</th>
  </tr>
  <tr>
    <td>Nivel de Abstracción</td>
    <td>Alto Nivel</td>
    <td>Bajo Nivel. Enfoque específico de detalles</td>
  </tr>
  <tr>
    <td>Entregables</td>
    <td>Planificación de Subsistemas, interfaces con sistemas externos, servicios, componentes reutilizables, prototipo arquitectónico.</td>
    <td>Diseño detallado en componentes. Especificación de Codificación.</td>
  </tr>
  <tr>
    <td>Áreas de enfoque</td>
    <td>Selección de tecnologías, requisitos no funcionales, manejo de riesgos</td>
    <td>Requisitos funcionales</td>
  </tr>
</table>

### Evolución de la Arquitectura

<img src="https://i.imgur.com/E5xM1AY.png" alt="">

## Sesión 2: Interprocess communication

### IPC technologies

- There are lots of different IPC technologies to choose from. Services can use:
  – Synchronous request/response-based communication mechanisms, such as HTTP based REST or gRPC.
  – Asynchronous: message-based communication mechanisms such as AMQP or STOMP.
- There are also a variety of different messages formats. Services can use human-readable, text-based formats such as JSON or XML. Alternatively, they could use a more efficient binary format such as Avro or Protocol Buffers.

### Interaction Styles

- The following are the different types of one-to-one interactions:
  – Request/response: A service client makes a request to a service and waits for a response. The client expects the response to arrive in a timely fashion. It might event block while waiting. This is an interaction style that generally results in services being tightly coupled.
  – Asynchronous request/response: A service client sends a request to a service, which replies asynchronously. The client doesn’t block while waiting, because the service might not send the response for a long time.
  – One-way notifications: A service client sends a request to a service, but no reply is expected or sent.
- The following are the different types of one-to-many interactions:
  – Publish/subscribe: A client publishes a notification message, which is consumed by zero or more interested services.
  – Publish/async responses: A client publishes a request message and then waits for a certain amount of time for responses from interested services.
- Each service will typically use a combination of these interaction styles.

### Evolving APIs - Use Semantic Versioning

- The Semantic Versioning specification (https://semver.org) is a useful guide to versioning APIs.
  - It’s a set of rules that specify how version numbers are used and incremented.
  - Semantic versioning was originally intended to be used for versioning of software packages, but you can use it for versioning APIs in a distributed system.
  - The Semantic Versioning specification (Semvers) requires a version number to consist of three parts: MAJOR.MINOR.PATCH. You must increment each part of a version number as follows:
    - MAJOR: When you make an incompatible change to the API.
    - MINOR: When you make backward-compatible enhancements to the API.
    - PATCH: When you make a backward-compatible bug fix.

### Message formats - Text-Based Message Formats

- The first category is text-based formats such as JSON and XML. An advantage of these formats is that not only are they human readable, they’re self describing.
- A JSON message is a collection of named properties.
- Similarly, an XML message is effectively a collection of named elements and values.
- A downside of using a text-based messages format is that the messages tend to be verbose, especially XML. Every message has the overhead of containing the names of the attributes in addition to their values.
- Another drawback is the overhead of parsing text, especially when messages are large. Consequently, if efficiency and performance are important, you may want to consider using a binary format.

### Handling partial failure using the Circuit Breaker pattern

- Whenever one service synchronously invokes another service, it should protect itself using the approach described by Netflix. This approach consists of a combination of the following mechanisms:
  - Network timeouts
  - Limiting the number of outstanding requests from a client to a service
  - Circuit breaker pattern
- Netflix Hystrix is an open source library that implements these and other patterns. If you’re using the JVM, you should definitely consider using Hystrix when implementing RPI proxies. And if you’re running in a non-JVM environment, you should use an equivalent library. For example, the Polly library is popular in the .NET community.

### Service Discovery

- In a modern cloud-based microservices application Service instances have dynamically assigned network locations.
- Moreover, the set of service instances changes dynamically because of autoscaling, failures, and upgrades.
- Consequently, your client code must use a service discovery.

### Communicating using the Asynchronous messaging pattern

- There are several different kinds of messages:
  - Document: A generic message that contains only data. The receiver decides how to interpret it. The reply to a command is an example of a document message.
  - Command: A message that’s the equivalent of an RPC request. It specifies the operation to invoke and its parameters.
  - Event: A message indicating that something notable has occurred in the sender. An event is often a domain event, which represents a state change of a domain object such as an Order, or a Customer.
 
### Communicating using the Asynchronous messaging pattern - Message Broker

- Brokerless Messaging Tools
  - ZeroMQ
- Broker-Based Messaging Tools
  - ActiveMQ
  - RabbitMQ
  - Apache Kafka
- Broker-Cloud-Based Messaging Services
  - AWS Kinesis
  - AWS SQS

- When selecting a message broker, you have various factors to consider, including the following:
  - Supported programming languages: You probably should pick one that supports a variety of programming languages.
  - Supported messaging standards: Does the message broker support any standards, such as AMQP and STOMP, or is it proprietary?
  - Messaging ordering: Does the message broker preserve ordering of messages?
  - Delivery guarantees: What kind of delivery guarantees does the broker make?
  - Persistence: Are messages persisted to disk and able to survive broker crashes?
  - Durability: If a consumer reconnects to the message broker, will it receive the messages that were sent while it was disconnected?
  - Scalability: How scalable is the message broker?
  - Latency: What is the end-to-end latency?
  - Competing consumers: Does the message broker support competing consumers?
