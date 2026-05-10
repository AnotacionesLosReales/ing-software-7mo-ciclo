# Semana 7: Continuous Delivery

## Entrega Continua (Continuous Delivery)

- El concepto de Entrega continua en DevOps hace referencia a la implementación automatizada de los procesos de creación, implementación, prueba y despliegue de aplicaciones.
- Los despliegues de mantenimiento posibilitan que la prestación de servicios sea tratada de la misma manera.

### Madurez

<div align="center">
  <img src="https://i.imgur.com/jaqy0Te.png" alt="Madurez en entrega continua: niveles -1 y 0">
  <img src="https://i.imgur.com/aFcKZsX.png" alt="Madurez en entrega continua: niveles 1, 2 y 3">
</div>

## Despliegue Continuo (Continuous Deployment)

- Desplegar en producción todos los cambios que pasen las pruebas automatizadas.
- Crear primero una estrategia de entrega antes de cualquier planificación de versión y antes de la primera iteración.
- Planes de iteración: Proponer desplegar en la primera iteraciónpara demostrar lo que se puede hacer y probar la implementación.

### Buenas Practicas

- Las personas que realizan la implementación deben participar en la creación del proceso de implementación.
- Registrar las actividades de despliegue.
- No eliminar los archivos antiguos. Mejor moverlos.
- El despliegue es responsabilidad de todo el equipo.
- Fallar rápido.
- No realizar cambios directamente en el entorno de producción.
- Mantener períodos de preparación para nuevas implementación.

## Metodologias de Despliegue

- JKK (Construyendo con calidad en propiedad)
  - Clara comprensión de los objetivos.
  - Garantizar la alta calidad del trabajo.
  - Los defectos nunca pasan al siguiente proceso.
  - Fundamental la definición de hecho.
- Ritmo
  - En el que el equipo de DevOps trabaja y despliega.
- Trabajo en curso (WIP)
  - Reducir el WIP reduce cuellos de botella y mejora el tiempo de ciclo.
- Flujo de una sola pieza
  - Cada equipo o individuo trabajar en un elemento a la vez para completar.
  - Ritmo rápido, flujo suave.

### Flujo basico de despliegue

<div align="center">
  <img src="https://i.imgur.com/Ox6BHuw.png" alt="Madurez en entrega continua: niveles -1 y 0">
</div>

## Practicas de Pipelines

- Solo construye tus binarios una vez.
- Implemente de la misma manera cada entorno.
- Smoke-Test antes de los Deployments.
- Implementar en una copia de producción.
- Cada cambio debería propagarse a través del pipeline al instante.
- Si falla alguna parte de la pipeline, detenga la línea.

### Preparando para el Release

- Tener un plan de lanzamiento creado y mantenido por todos los involucrados en la entrega del software, incluidos los desarrolladores y probadores, así como operaciones, infraestructura y personal de apoyo.
- Minimice el efecto de las personas que cometen errores automatizando tanto el proceso como sea posible, comenzando con las etapas más propensas a errores.
- Ensaye el procedimiento a menudo en entornos similares a la producción, para que pueda depurar el proceso y la tecnología que lo soporta.
- Tener la capacidad de retrasar un lanzamiento si las cosas no salen según el plan.
- Tener una estrategia para migrar datos de configuración y producción como parte de los procesos de actualización y retrotracción.

### Implementado el Pipeline de Despliegue

1. Modele su flujo de valores y cree un esqueleto andante.
2. Automatice el proceso de compilación e implementación.
3. Automatice las pruebas unitarias y el análisis de código.
4. Automatice las pruebas de aceptación.
5. Automatice las versiones.

## Buenas practicas de despliegue

### Buenas Practicas

- Cree una secuencia de comandos para cada etapa en su pipeline de implementación.
- Use una tecnología apropiada para implementar su aplicación
- Utilice los mismos scripts para implementar en cada entorno
- Use las herramientas de Packaging de su sistema operativo
- Evolucione su sistema de implementación de forma incremental
- Usa siempre rutas relativas
- Eliminar los pasos manuales
- Integración en la rastreabilidad desde los binarios hasta el control de versiones
- No verifique los binarios en el control de versiones como parte de su compilación
- Los objetivos de prueba no deberían fallar en la construcción
- Restringe tu aplicación con pruebas de humo integradas

## Aprendizaje Continuo (CL)

### Llevar a cabo una Reunión Post Mortem Impecable

- Los objetivos de una revisión Post Mortem son muy simples:
  ‒ Para identificar las cosas que se hicieron bien, puede realizarlas nuevamente en situaciones similares.
  - Para destacar lo que debería haberse hecho de manera diferente, puede refinar las técnicas en el futuro.
  - Destacar lo que se hizo mal y sugerir enfoques alternativos o medidas de seguridad que se deberían emplear la próxima vez que se enfrente un problema similar.

### Días de Juego

- El concepto de los días de juego proviene de la disciplina de la ingeniería de la resiliencia.
- La ingeniería de la resiliencia es "un ejercicio diseñado para aumentar la resiliencia a través de la inyección de fallas a gran escala en sistemas críticos". (Robbins).
- El objetivo de los días de juego es:
  - Ayudar a los equipos a simular y ensayar accidentes, a fin de posibilitar la practicar.
  - En primer lugar, se programa un evento catastrófico, como la destrucción simulada de un data center completo,
  - Luego, dar tiempo a los equipos para prepararse, eliminar todos los puntos únicos de falla y crear los procedimientos de supervisión necesarios, los procedimientos de conmutación por error, etc.
