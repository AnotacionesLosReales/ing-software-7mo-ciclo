# Semana 3: Monolithic Architecture

## Sesión 1: Definición de arquitectura monolítica

### Intro

- Una aplicación monolítica coloca todos sus funcionalidades en un único proceso.
- Para escalar la arquitectura monolítica se copia el monolito varias veces en distintos servidores.

### Historia

- Este estilo arquitectónico no fue ideado, sino que todas las aplicaciones estaban construidas de esta forma en un inicio.
- Al no existir internet, se constuían sistemas monolíticos de forma que puedan ser autosuficientes.

### Definición

- El estilo arquitectónico monolítico consiste en crear una aplicación autosuficiente que contenga toda la funcionalidad necesaria para realizar la tarea para la cual fue diseñada.
- Puede estar construido como una sola unidad de software o creada a partir de varios módulos, pero al compilarse se empaqueta como una sola unidad.

### Características

- Son autosuficientes.
- Realizan las operaciones de punto a punto para completar una tarea.
- Por lo general, son aplicaciones grandes.
- Por lo general, cada instalación administra su propia base de datos.
- Todo el sistema corre sobre una misma plataforma.

### Ventajas

- Fácil de desarrollar: debido a que existe un único componente, es fácil para un equipo pequeño iniciar un proyecto y ponerlo en producción rápidamente.
- Fácil de escalar: Basta con instalar la aplicación en varios servidores.
- Pocos puntos de fallo: El no depender de nadie más, mitiga gran parte de los errores.
- Autónomo: funcionan independientemente del resto de aplicaciones.
- Performance: son significativamente más rápidas debido a que todo el procesamiento lo realizan localmente.
- Fácil de probar: por ser una unidad de código, es posible realizar todas las pruebas sin depender de nada más.

### Desventajas

- Anclado de Stack tecnológico: al ser una sola pieza, implica que todo debe usar el mismo stack.
- Escalado monolítico: implica escalar toda la aplicación, gastando recursos en funcionalidades que quizás no necesiten escalar.
- El tamaño sí importa: mientras más crece la aplicación, más crece el equipo y es más difícil dividir el trabajo.
- Versión tras versión: cualquier mínimo cambio implicará realizar una compilación de todo el artefacto, generando una nueva versión para ser administrada.
- Si falla, falla todo: a menos que exista alta disponibilidad, si la aplicación monolítica falla, falla todo el sistema.
- Es fácil perder el rumbo: la naturaleza de tener todo en un mismo módulo ocasiona caer a veces en malas prácticas de programación.
- Abrumador: en proyectos muy grandes, puede ser abrumador para un nuevo programador hacer un cambio.
