# Semana 3: Testing Overview

## Pruebas de Integración

### Tipos de pruebas de integración

- **Pruebas de integración de Big Bang**: Se integran todos los módulos a la vez y se prueban como un sistema completo. Es difícil identificar la causa de los errores.
- **Pruebas ascendentes**: Se integran los módulos de abajo hacia arriba, comenzando con los módulos más bajos y avanzando hacia los módulos superiores.
- **Pruebas descendentes**: Se integran los módulos de arriba hacia abajo, comenzando

## Pruebas de sistemas

- Buscan probar a la aplicación (o sistema) como un todo.
- Están basadas en requisitos (funcionales y no funcionales).
- Se realizaran dentro del ámbito de testing.

## Pruebas de aceptación

Su objetivo es validar que el software cumple con los requisitos del cliente y es apto para su uso. Se realizan pruebas funcionales basadas en casos de uso y escenarios reales.

## Estrategias de pruebas

- Las historias se utilizan para recopilar, definir y priorizar los requisitos de nivel de servicio y los acuerdos de nivel de servicio.
  - Historias de Operación: Comprobar que los despliegues funcionan correctamente y se pueden operar.
  - Historias de Test: Comprobar que las entregas funcionan: casos de aceptación y criterios de aceptación.
  - Historias de Usuario: Razón y valor de negocio, funcionalidades y condiciones de uso

### Se puede atomatizar todo?

No, no se puede automatizar todo. Algunas pruebas requieren la intervención humana, como las pruebas de usabilidad o las pruebas exploratorias. Además, algunas pruebas pueden ser demasiado complejas o costosas para automatizar, y en esos casos, es más eficiente realizarlas manualmente. Es importante evaluar cada caso y decidir qué pruebas son adecuadas para la automatización y cuáles deben realizarse manualmente.
En ese caso, se podrían usar pruebas hibridas, donde se combinan pruebas automatizadas para tareas repetitivas y pruebas manuales para aspectos que requieren juicio humano. Esto permite aprovechar lo mejor de ambos enfoques y garantizar una cobertura de pruebas efectiva.

### Proceso de una pruebas

- Arrange: Configurar el entorno de prueba y preparar los datos necesarios.
- Act: Ejecutar la funcionalidad que se desea probar.
- Assert: Verificar que los resultados obtenidos coinciden con los resultados esperados.
