# Semana 4: Monolithic Decomposition

## Sesión 1: Patrones para la descomposición de una aplicación en servicios

### Intro

- Un servicio es un componente de software autónomo e implementable de forma independiente que presenta algunas funciones útiles.
- Los patrones de descomposición que se pueden utilizar para definir la arquitectura de una aplcación son:
  - **Decompose by business capability (Descomposición por capacidad empresarial):** organiza los servicios en torno a las capacidades empresariales.
  - **Decompose by subdomain (Descomposición por subdominio):** organiza los servicios en torno a subdominios Domain-Driven Design.

### Decompose by business capability

- Un concepto de modelado de la arquitectura empresarial, se denomina capacidad empresarial es algo que hace la empresa para generar valor.
- El conjunto de capacidades empresariales determinada depende del tipo de empresa.

**Ejemplos:** 

- Compañía de seguros: Cumplimiento, Suscripción, Gestión de reclamaciones y Facturación.
- Tienda en línea: Devoluciones, Pedidos, Inventarios y Envíos.

- Las capacidades empresariales capturan lo que una organización hace y, por lo general, son estables.

#### Identificar capacidades empresariales

- Contiene propósito, estructura y procesos comerciales.
- Su especificación consta de varios componentes, que incluyen entradas, salidas y acuerdos de nivel de servicio.
- Una capacidad empresarial a menudo se centra en un objeto empresarial en particular. Por ejemplo, el objeto empresarial "Reclamación" es el foco de la capacidad empresarial de "Reclamaciones".
- A menudo, una capacidad se puede descomponer en subcapacidades. Por ejemplo, la capacidad de gestión de reclamaciones tiene varias subcapacidades, incluidas:
  - La gestión de información de reclamaciones.
  - La revisión de reclamaciones.
  - La gestión de pagos de reclamaciones.
 
#### De capacidades empresariales a servicios

- Una vez definidas las capacidades empresariales, se define un servicio para cada capacidad o grupo de capacidades relacionadas.
- Algunas capacidades se identifican a nivel superior y otras se identifican como subcapacidades mapeadas a servicios.

<div align="center">
  <img src="https://i.imgur.com/J8jrUjk.png" alt="Conversión de capacidades empresariales a servicios">
</div>

#### Beneficios

- Debido a la estabilidad de las capacidades empresariales, la arquitectura resultante, también, será relativamente estable.
- Los componentes indivuales de la arquitectura pueden evolucionar a medida que cambia el aspecto del negocio, pero la arquitectura permanece sin cambios.
