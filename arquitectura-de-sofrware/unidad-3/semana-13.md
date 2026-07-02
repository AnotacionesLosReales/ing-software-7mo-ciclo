# Semana 13: Architecture Scenarios - Microsoft Azure, Google Cloud Platform

## Model, View, Controller (MVC)

### Intro

- Es la mas común debido a que se construye alrededor de la base de datos.
- Muchos de los marcos de software mas usados utilizan esta arquitectura: Java EE, Drupal, Express.
- El codigo se organiza en capas desde la mas externa hasta la mas interna donde se encuentra la base de datos.
- Es común que los programadores trabajen independientemente en las capas.

### Objetivos

- El patrón de arquitectura Model View Controller utiliza esta estructura, es el marco de desarrollo mas usado.
- En las capas superiores esta la capa de View con CSS, jvascript y HTML.
- En el medio está la capa Controller la cual tiene las reglas y métodos para transformar la data que se mueve entre las capas View y Model.

### Ventajas

- Cada capa es separada y aislada, enfocándose en su rol
- Fácil de mantener
- Fácil de probar
- Puede separa roles
- Fácil de actualizar separadamente

### Desventajas:

- El código se convierte en una bola de nieve si no está organizado en módulos o los roles no están bien definidos.
- Se puede caer en el anti patrón embudo, es cuando el código solo se dedica a pasar data a través de las capas sin usar ninguna lógica.
- El aislamiento de capas puede ser difícil de entender sin entender cada módulo.
- Los desarrolladores pueden saltar capas y crear acoplamientos fuertes creando una red compleja de interdependencias.
- El despliegue monolítico es inevitable, un cambio requiere desplegar toda la aplicación.

## Event-Driven Architecture (EDA)

### Intro

- Cuando los programas se mantienen mucho tiempo esperando que algo suceda, especialmente en dispositivos que trabajan directamente con humanos.
- Esta arquitectura ayuda a gestionar construyendo una unidad central que acepta toda la data y la delega a módulos separados para manejar los casos particulares.
- Este manejo se denomina “Evento” y se delega al código asignado a ese tipo de evento.
- Por ejemplo: Una pagina web contiene Javascript o css y hay varios módulos pequeños que reaccionan a eventos como clicks o acciones de teclas

### Ventajas

- Esta arquitectura se adapta a entornos complejos y caóticos
- Escala fácilmente
- Se puede extender cuando aparecen nuevos eventos
- Sistemas Asíncronos
- Interfases de usuarios
- La aplicación interactúa con pocos módulos

### Desventajas

- Las pruebas pueden ser complejas si los módulos afectan a otros, se pueden probar los módulos independientemente pero no es tan fácil probar las interacciones.
- El manejo de error es difícil de estructurar, sobre todo si varios módulos manejan el mismo evento.
- Los módulos fallan la unidad central debe tener un plan de respaldo
- El exceso de mensajes o eventos puede ralentizar el proceso
- La estructura de datos para diferentes eventos puede ser compleja
- El mantenimiento mediante mecanismos transaccionales puede ser difícil debido al bajo acoplamiento o independencia de los módulos

## Arquitectura Hexagonal

### Intro

- La arquitectura hexagonal, también conocida como arquitectura de puertos y adaptadores, es un patrón de diseño de software que pretende hacer que las aplicaciones sean más fáciles de mantener y probar.
- Fue introducida por Alistair Cockburn en 2005.

### Objetivos

- Aislar el núcleo de la aplicación de los detalles de implementación.
- Facilitar las pruebas unitarias y de integración.
- Permitir cambios en los componentes externos sin afectar el núcleo.

### Componentes principales

- Núcleo de la Aplicación: Contiene la lógica de negocio y las reglas del dominio.
- Puertos: Interfaces que definen cómo los componentes externos interactúan con el núcleo.
- Adaptadores: Implementaciones concretas de los puertos que conectan el núcleo con componentes externos como bases de datos, servicios web, etc.

### Beneficios

- Independencia de Tecnología: Permite cambiar tecnologías sin afectar el núcleo.
- Facilidad de Pruebas: Facilita la creación de pruebas unitarias y de integración.
- Mantenibilidad: Hace que el código sea más fácil de mantener y evolucionar.

### Conclusión

- La arquitectura hexagonal es un patrón poderoso que ayuda a crear aplicaciones más mantenibles y testeables.
- Al separar el núcleo de la aplicación de los detalles de implementación, permite una mayor flexibilidad y adaptabilidad a cambios futuros.

### Ejemplo de estructuración

```
src/
├── domain/
│   ├── model/
│   │   └── User.java
│   ├── port/
│   │   ├── in/
│   │   │   └── CreateUserUseCase.java
│   │   └── out/
│   │       └── SaveUserPort.java
│   └── service/
│       └── CreateUserService.java
├── adapter/
│   ├── in/
│   │   └── rest/
│   │       └── UserController.java
│   └── out/
│       └── persistence/
│           ├── UserEntity.java
│           └── UserRepositoryAdapter.java
└── application/
    └── Main.java
```
