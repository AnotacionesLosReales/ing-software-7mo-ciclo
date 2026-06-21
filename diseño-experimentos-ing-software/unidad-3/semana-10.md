# Semana 10: Continuous Deployment and Best Practices

## Pruebas de Regresión

- Las pruebas de regresión se deben llevar a cabo cada vez que se hace un cambio en el sistema, tanto para corregir un error como para realizar una mejora.
- No es suficiente probar solo los componentes modificados o añadidos, o las funciones que en ellos se realizan, sino que también es necesario controlar que las modificaciones no produzcan efectos negativos sobre el mismo u otros componentes.
- Normalmente, este tipo de pruebas implica la repetición de las pruebas que ya se han realizado previamente, con el fin de asegurar que no se introducen errores que puedan comprometer el funcionamiento de otros componentes que no han sido modificados y confirmar que el sistema funciona correctamente una vez realizados los cambios.

## User Acceptance Testing (UAT)

- Es un proceso para obtener confirmación por un Experto en la Materia (EM), preferiblemente el cliente o el usuario final del objeto bajo pruebas.
- A través de pruebas o revisiones que demuestran que las modificaciones o adiciones cumplan requisitos mutuamente establecidos.
- En el desarrollo de software, UAT ocurre en las fases finales del desarrollo y comúnmente antes que el usuario final o cliente acepte el nuevo sistema.
- Desarrolladores de testeo delinean pruebas formales usando un rango de niveles de severidades.
- Es preferible que los diseñadores de estas pruebas no sean los testers pero en muchas situaciones esto no puede ser evitado.
- UAT actúan como un verificador final de las funciones de negocios requeridas y el comportamiento adecuado del sistema, emulando condiciones del mundo real.

### Tipos de UAT

- **Alpha testing:** Ocurre en el lugar de desarrollo por grupo desarrollador (staff interno) antes de que el producto sea entregado a usuarios.
- **Beta testing:** Ocurren en el lugar del cliente en un grupo grande de clientes que se involucran para dar feedback (recomendaciones) y reportar errores del producto justo antes de que sea público.

### Alcance

Las pruebas de aceptación involucran:

- Correr un suite de pruebas en un sistema completo
- Tienen carácter booleano. No hay grado en de éxito o falla (pasan o fallan)
- El entorno en que se realizan es lo más parecido al entorno real del software
- Acompañadas por casos de prueba con pasos de prueba y una descripción formal de los resultados
- En ciclos de Desarrollo de Software Ágil (Agile Software Development) las pruebas son creadas por clientes y expresadas en un lenguaje de dominios del negocio.

## Informes de Ejecución

- **Histórico de Pruebas:** Documenta todos los hechos relevantes ocurridos durante la ejecución de las pruebas.
- **Informe de Incidente:** Documenta cada incidente (p. ej., una interrupción en las pruebas debido a un corte de electricidad, bloqueo del teclado, etc.) ocurrido en la prueba y que requiera una posterior investigación.
- **Informe resumen:** Resume los resultados de las actividades de prueba (las reseñadas en el propio informe) y aporta una evaluación del software, basada en dichos resultados.

## Reportes de errores

Los reportes de error son los documentos/data más importantes de un esfuerzo de pruebas:

- ID de Error
- Nombre de error
- Descripción
- Prioridad
- Tipo
- Pasos para reproducir
- Solución propuesta
