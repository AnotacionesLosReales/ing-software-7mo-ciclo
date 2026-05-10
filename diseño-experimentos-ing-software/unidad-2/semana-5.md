# Semana 5: Continuous Integration

## Definicion

- La integración continua requiere que cada vez que alguien realiza un cambio, se cree toda la aplicación y se ejecute un conjunto completo de pruebas automatizadas contra ella.

### Sistema Básico de Integración Continua

- No se necesita un software de integración continua para realizar una integración continua (práctica, no una herramienta).
- En realidad, sin embargo, las herramientas de CI hoy en día son extremadamente simples de instalar y poner en marcha: Hudson, Jenkins, Team Concert.
- Luego de Instalar la herramienta CI, se debe encontrar su repositorio de control de origen, qué script ejecutar para compilar, si es necesario, y ejecutar las pruebas de confirmación automatizadas.

### Modelo de Integracion Continua

1. Compruebe si la compilación ya se está ejecutando. Si es así, espere a que termine. Si falla, tendrás que trabajar con el resto del equipo para que sea verde antes de registrarte.
2. Una vez que haya terminado y hayan pasado las pruebas, actualice el código en su entorno de desarrollo desde esta versión en el repositorio de control de versiones para obtener cualquier actualización.
3. Ejecute el script de compilación y realice pruebas en su máquina de desarrollo para asegurarse de que todo sigue funcionando correctamente en su ordenador, o bien utilice la función de compilación personal de su herramienta de CI Sistema Básico de Integración Continua
4. Si su compilación local pasa, compruebe su código en el control de versiones.
5. Espere a que su herramienta CI ejecute la compilación con sus cambios.
6. Si falla, detenga lo que está haciendo y solucione el problema inmediatamente en su equipo de desarrollo; vaya al paso 3.
7. Si la construcción pasa, regocíjese y continúe con su próxima tarea.

<div align="center">
  <img src="https://i.imgur.com/X6Fl40M.png" alt="Imagen demostrando el modelo de integracion continua">
</div>

## Requisitos Previos

- **Control de versiones:** El proyecto debe estar registrado en un único repositorio y todo lo necesario para crear, instalar, ejecutar y probar su aplicación.
- **Una Construcción automatizada:** Debe ser posible que una persona o un equipo ejecute el proceso de creación, prueba e implementación de forma automatizada a través de la línea de comandos.
  - Ejecutar su proceso de construcción de forma automatizada desde su entorno.
  - Scripts de compilación deben ser probados y reformados constantemente para que sean ordenados y fáciles de entender.
  - Facilita la comprensión, el mantenimiento y la depuración de la compilación, y permite una mejor colaboración con el personal de operaciones.
- **Acuerdo del Equipo:** La integración continua es una práctica, no una herramienta. Requiere un cierto grado de compromiso y disciplina por parte de su equipo de desarrollo. Necesita que todo el mundo compruebe los pequeños cambios incrementales con frecuencia en la línea principal y esté de acuerdo en que la tarea de mayor prioridad en el proyecto es arreglar cualquier cambio que rompa la aplicación.

## Practicas Esenciales

- Don’t Check-In on a Broken Build:
  - Si la compilación se rompe, los desarrolladores responsables están esperando para arreglarla.
  - Esta estrategia, siempre estaremos en la mejor posición para averiguar qué causó la rotura y arreglarla inmediatamente.
- Ejecutar todas las pruebas de confirmación localmente antes de realizar la confirmación:
  - Ejecutar las pruebas de confirmación localmente es una comprobación de cordura antes de comprometerse con la acción.
  - Deben actualizar su copia local del proyecto desde el sistema de control de versiones.
  - Deben iniciar una construcción local y ejecutar las pruebas de confirmación. Sólo cuando esto tiene éxito.
- Espere a que pasen las pruebas de confirmación antes de seguir adelante:
  - Encontrar errores y eliminarlos lo antes posible, sin esperar perfección y sin errores.
  - Los desarrolladores que lo hicieron son responsables de monitorear el progreso de la construcción.
  - Hasta que su check-in no haya compilado y pasado sus pruebas de confirmación, los desarrolladores no deben iniciar ninguna tarea nueva.
  - Si la confirmación tiene éxito, los desarrolladores son entonces, y sólo entonces, libres para pasar a su siguiente tarea.
  - Si falla, retroceder sus cambios hasta que entiendan cómo hacerlos funcionar.
- Fijación de la caja de tiempo antes de la reversión:
  - Cuando se inicie la construcción en el momento del check-in, intente arreglarlo durante diez minutos
  - Si, después de diez minutos, no ha terminado con la solución, vuelva a la versión anterior desde su sistema de control de versiones.
