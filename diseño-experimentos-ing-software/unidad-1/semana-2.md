# Semana 2: Software Delivery & Software Deployment.

### Flash informativo:

Se evaluará otros proyectos, en donde se decide si cada grupo pasa o no.

- Puntos para completar los Artefactos:
  - Se debe asignar roles a cada integrante del equipo
  - Jefe: Líder QA Auditor
  - Benchmarking: Evaluar hasta cuanto puedo soportar un sistema.
  - Matriz de errores: Es un documento que se hace para cada proyecto, en donde se registran los errores que se van encontrando, con el fin de tener un control de los mismos (Como un product backlog de errores).
  - UAT: User Acceptance Testing, es una fase del proceso de desarrollo de software en la que los usuarios finales prueban el software para asegurarse de que cumple con sus necesidades y requisitos antes de su lanzamiento oficial.

### SmartSheet

Es una herramienta de gestión de proyectos que permite a los equipos colaborar, planificar y ejecutar proyectos de manera eficiente. Se utiliza para organizar tareas, asignar responsabilidades, establecer plazos y realizar un seguimiento del progreso del proyecto.

Plantilla de caso de prueba de aceptación de usuarios: Se usa para la validación de las UAT

- Convertir PDF a Markdown: [https://products.aspose.app/words/es/conversion/pdf-to-md#](https://products.aspose.app/words/es/conversion/pdf-to-md#)

## Software Delivery

- Es el proceso de hacer que tu producto de software llegue al mercado.
- Incluye los siguientes grupos y acciones:
  - Negocio y Product Owners para los requisitos.
  - Tecnologia para desarrollo y despliegue de software.
  - QA para validacion y pruebas.
 
### Patron de "Pipeline de Despliegue"

- Cada cambio que se realiza en la configuracion, codigo fuente, el entorno o los datos de una aplicacion, desencadena la creacion de un nuevo release.
  
1. Compilar, pruebas unitarias, analizar y construir.
2. Pruebas de aceptacion automaticas.
3. Pruebas de capacidad automaticas.
4. Pruebas manuales y pruebas exploratorias.
5. Release.

## Antipatrones de comunes de despliegue

### Despliegue manual de software

- Documentación extensa y detallada
- Confianza en las pruebas manuales
- Llamadas frecuentes al equipo de desarrollo
- Correcciones frecuentes
- Solucion -> Despliegue automatico.

### Implementación en un entorno similar a la producción solo después de que se completa el desarrollo

- Pruebas en máquinas de desarrollo.
- Alguien de operaciones ve el software por primera vez el día del despliegue.
- Caro entorno similar al de producción.
- Poca colaboración entre el equipo de desarrollo y las personas que realizan implementaciones.
- Solucion -> Integrar las actividades de prueba, implementación y despliegue en el proceso de desarrollo.

### Gestión de configuración manual de entornos de producción

- Implementación exitosa en staging, pero en producción falla.
- Los diferentes miembros de un clúster se comportan de manera diferente.
- El equipo de operaciones tarda mucho en preparar un entorno para un lanzamiento.
- No puede volver atrás a una configuración anterior de su sistema.
- Los servidores en clústeres tienen recursos en versiones diferentes.
- La configuración del sistema se hace modificando directamente en los sistemas de producción.
- Solucion -> Proceso Automatizado.

## Despliegue correcto de aplicaciones

### Automatización de Despliegue

- Haciendo frecuentes y automatizados despliegues de software aseguramos que nuestro producto de software llegue mas rápido al cliente y pueda obtener el ROI de manera rápida.
- Se basa en dos factores:
  - Automatizados: Sino no son totalmente repetibles. Los pasos son manuales, son propensos a errores y no hay forma de revisar exactamente lo que se hizo.
  - Frecuentes: Reduce el riesgo asociado con el despliegue, hace que sea mucho más fácil retroceder. y conducen a una retroalimentación más rápida.
- Componentes a controlar: Codigo ejecutable, configuracion, entornos y datos.

### Proceso de feedback

- Debe funcionar el proceso de creación del código ejecutable. Para validar que el código es el correcto.
- Deben pasar las pruebas unitarias, de aceptación, funcionales y no funcionales, y exploratorias del software.
- El software debe cumplir con ciertos criterios de calidad.
- El software debe pasar por una demostración al cliente y una selección de usuarios.

## Principios de Entregas de Software

- Crear un proceso confiable y repetible para lanzar software
- Automatiza casi todo
- Mantener todo en control de versiones
- Si duele, hazlo con más frecuencia y adelanta el dolor
- Calidad en la construcción
- Hecho significa lanzado
- Todos son responsables del proceso de entrega
- Mejora continua

---

## DevOps

- Conjunto de practicas que trabaja para automatizar e integrar los procesos entre el desarrollo y los equipos de TI, para que puedan construir, probar y lanzar software de manera más rápida y confiable.
- Proviene de la union de las palabras "Developement" y "Operations".

## Fases del proceso DevOps

<table border="1">
  <tr>
    <th> Fase </th>
    <th> Objetivo </th>
    <th> Herramientas </th>
  </tr>
  <tr>
    <td> Plan </td>
    <td> Definir requisitos, priorizar tareas y alinear equipos. </td>
    <td> Jira y Trello (gestion de proyectos), Spring planning (en equipos agiles). </td>
  </tr>
  <tr>
    <td> Code </td>
    <td> Crear y versionar el código fuente. </td>
    <td> Uso de Git para control de versiones, revision de codigo (Pull Requests). </td>
  </tr>
  <tr>
    <td> Build </td>
    <td> Compilar y empaquetar el código en artefactos ejecutables. </td>
    <td> Jenkins (orquesta el pipeline de pruebas y builds), Docker (contenerizacion), SonarQ (escaneo de codigo) y Snyk (escaneo de dependencias). </td>
  </tr>
  <tr>
    <td> Test </td>
    <td> Validar calidad antes del release. </td>
    <td> Artifactory: Almacena artefactos probados (ej: .jar, imágenes Docker), pruebas unitarias/integración (JUnit, pytest), pruebas de seguridad (OWASP ZAP) </td>
  </tr>
  <tr>
    <td> Release </td>
    <td> Preparar artefactos estables para despliegue. </td>
    <td> Artifactory: Sirve como repositorio de artefactos versionados (ej: v1.2.0) y approvals manuales (si es necesario) antes de producción </td>
  </tr>
  <tr>
    <td> Deploy </td>
    <td> Llevar el software a entornos objetivo (stagging, production). </td>
    <td> Kubernetes (K8s): Orquesta contenedores (escalado, rollbacks), Terraform: Gestiona infraestructura como código (IaC). Estrategias de despliegue seguro (Blue-Green: Cambio instantáneo entre entornos y Canary: Liberación gradual a usuarios). </td>
  </tr>
  <tr>
    <td> Operate/Test </td>
    <td> Asegurar que el despliegue funciona correctamente. Validar en Produccion. </td>
    <td> Postman: Pruebas API post-despliegue (smoke tests), Verificación de métricas básicas (latencia, errores 5xx). </td>
  </tr>
  <tr>
    <td> Monitor </td>
    <td> Detectar problemas en tiempo real y mejorar continuamente </td>
    <td> Prometheus: Monitorea métricas (CPU, memoria, errores), Grafana: Dashboards visuales para análisis, Alertas automatizadas (ej: Slack, PagerDuty), Feedback loop: Retroalimentación al equipo de desarrollo. </td>
  </tr>
</table>

## Principales elementos de DevOps

- Implementación de una cultura sin culpabilidad.
- Proporciona aplicaciones y servicios Just-in-Time
- Asegurar la continuidad de los servicios de TI
- Gestión del ciclo de vida de las aplicaciones y servicios

## Beneficios de usar DevOps

- Velocidad
- Entrega rápida
- Confiabilidad
- Escalado
- Colaboración mejorada
- Seguridad

## Prácticas de DevOps

- Integración continua
- Entrega continua
- Microservicios
- Infraestructura como código
- Monitoreo y registro
- Comunicación y colaboración

## Marco CALMS para DevOps
