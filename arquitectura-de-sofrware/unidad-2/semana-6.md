# Semana 6: Testing Microservices

## Sesión 1: Event-Driven Architecture (EDA), Event Sourcing & CQRS

### Event-Driven Architecture (EDA)

- Es un patrón arquitectónico que facilita la producción, detección, consumo y reacción a eventos.

#### Razones para enviar un mensaje

- Command: I want the system to do something.
- Event: Something has happened.
- Query: I want to know something.

### Event Sourcing

<img src="https://i.imgur.com/gAmChyl.png" alt="">

#### ¿Por qué Event Sourcing?

- **Razones para negocio:** Auditoría / Cumplimiento / Transparencia. Minería de datos y analíticas.
- **Razones técnicas:** Completitud garantizada de eventos levantados. Una sola fuente de la verdad. Concurrencia. Debug más fácil. CQRS.

### Command Query Responsibility Segregation

<img src="https://i.imgur.com/HZMRnde.png" alt="">

#### ¿Por qué CQRS?

- Tecnologías mixtas (SQL, no SQL).
- Complejidad de queries.
- Event Sourcing.
- Microservicios.

## Sesión 2: Clean Architecture

### Layers

- Presentation -> Service -> Domain -> Persistence
- UI -> API -> Business Logic -> Data Access

### Patrones

#### Patrones de la Capa de Negocio

- Transaction Script
- Table Module
- Active Record
- Domain Model

### Arquitectura Limpia

- Independiente de frameworks: Usa frameworks como herramientas, no para llenar tu sistema de sus restricciones.
- Fácil de probar: Las reglas de negocio pueden probarse sin:
  - UI (interfaz de usuario)
  - Base de datos
  - Servidor web
  - o cualquier otro elemento externo
- Independiente de la UI: La UI puede cambiar fácilmente, sin cambiar el resto del sistema. Por ejemplo, la interfaz web puede ser reemplazada por una interfaz de consola, sin cambiar las reglas del negocio.
- Independiente de la base de datos: Puede intercambiar MySQL por Oracle, o SQL Server por MongoDB / CosmosDB / Big Table o por cualquier otra base de datos. Las reglas de negocio no están ligadas a la base de datos.
- Independiente de agentes externos: Las reglas de negocio no saben nada de las interfaces con el mundo exterior.
