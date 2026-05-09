# Semana 4: Testing Agile Approaches

## Testing Agile Approaches: TDD, BDD y ATDD

### Pruebas Automatizadas para las metodologías agiles

- Un equipo de testing le es muy dificultoso realizar pruebas de regresión, cada vez que los programadores realizan una integración se genera un proceso muy lento y pesado.
- Un conjunto de pruebas automatizadas va a permitir validar el producto de manera mas rápida, acá es donde se debe de aplicar una plataforma de **Integración Continua**.

### ¿Cuándo automatizar?

- El aspecto primordial que permite determinar si es mejor o no automatizar responde a la pregunta: **“¿Cada cuánto hacemos nuevas versiones de nuestro software?”**.

### Pirámide de Cohn

- Muchos test unitarios automatizados, porque de esa manera validamos que los métodos se encuentren estables.
- Bastantes tests a nivel de API, integración de componentes, servicios, que son los más estables y candidatos a automatizar.
- Menos test de interfaces graficas.

### TDD (Test-Driven Development)

- Desarrollo guiado por pruebas.
- Primero pensar en los datos de entrada y los datos de salida esperados para empezar a programar.
- Cambio de mentalidad.

#### Beneficios

- Escribir el código necesario para que las pruebas pasen.
- Probar la funcionalidad previa a la integración.
- Comprobar que una funcionalidad sigue trabajando de manera adecuada después de un cambio.

#### Problemas al aplicar TDD

- Dificultad al probar funcionalidad complejas.
- Creación de test que sean innecesarios.
- Trabajo extra porque aparte de desarrollar el código de nuestra aplicación también debemos de arreglar los test.
- Cambio de mentalidad en el equipo de desarrollo.

### BDD (Behavior-Driven Development)

- Desarrollo guiado por el comportamiento .
- Complementa a TDD con escenarios de negocios.
- Busca un lenguaje común para unir la parte técnica con la del negocio.
- Se utiliza al momento de realizar Pruebas de Integración.
- Ejemplo de BDD: Dado (contexto inicial), cuando (se produce el evento), entonces (resultados).
- Pasos para BDD: Escribir las Historias de Usuarios, Escribir los Escenarios de Negocios, Automatizar las pruebas.

### ATDD (Acceptance Test Driven Development)

- Discutir, Destilar, Desarrollar, Demostra.

#### Discutir

- ¿Qué es una contraseña válida?
- ¿Qué personajes son obligatorios?
- ¿Cuándo deberían cambiar?
- ¿Se pueden repetir las contraseñas?
- ¿Cómo sabremos que funciona?
- ¿Cuáles son algunos ejemplos específicos?

#### Destilar

- Definir casos de prueba.
- Asignarle una accion de uso al caso de prueba.
- Definir un argumento de prueba.

#### Desarrollar

<div align="center">
  <img src="https://i.imgur.com/J6EdxRL.png" alt="Fase de desarrollo del Acceptance Test Driven Development">
</div>

## Functional & Non-Functional Requirements Testing

### Pruebas Funcionales

- Una prueba funcional es una prueba basada en la ejecución, revisión y retroalimentación de las funcionalidades previamente diseñadas para el software.
- Las pruebas funcionales se hacen mediante el diseño de modelos de prueba que buscan evaluar cada una de las opciones con las que cuenta el paquete informático.

#### Pruebas basadas en escenarios

- Los escenarios reflejan casos del uso real del software.
- Los escenarios son desarrollados desde el punto de vista de usuarios experimentados. Deben reflejar interacciones complejas y reales.
- Basadas en: entrevistas a los stekeholders, casos de uso, historias de usuarios y guiones.
- Se utilizan instancias de uno o más casos de uso para probar algo útil, interesante y complejo de la aplicación.

#### Diseño de Casos de Pruebas

- El diseño de los casos de pruebas son una parte de las Pruebas de Sistemas, que es la herramienta básica para realizar las pruebas de una aplicación.
- Se tiene que especificar correctamente los valores de entrada para saber cuales serán los valores esperados.
- Para diseñar un caso de prueba, se tiene que seleccionar un modulo o característica del sistema ha probar. En función a eso se genera la suite de datos.

#### Ejemplo: Retirar Dinero

- Flujo Básico
  - Permite retirar dinero
- Flujos Alternativos
  - Insuficiente dinero en el cajero.
  - Monto a retirar excede el saldo de la cuenta.
  - Monto a retirar excede del monto máximo de retiro.
  - Cliente sobrepasó el monto máximo de retiro diario en una cuenta.

### Pruebas Regresión

- Se denominan Pruebas de regresión a cualquier tipo de pruebas de software que intentan descubrir las causas de nuevos errores, carencias de funcionalidad, o divergencias funcionales con respecto al comportamiento esperado del software, inducidos por cambios recientemente realizados en partes de la aplicación que anteriormente al citado cambio no eran propensas a este tipo de error.
- Esto implica que el error tratado se reproduce como consecuencia inesperada del citado cambio en el programa.

#### Tipos de Pruebas Regresión

- Clasificación de ámbito
  - Local -los cambios introducen nuevos errores.
  - Desenmascarada -los cambios revelan errores previos.
  - Remota -Los cambios vinculan algunas partes del programa (módulo) e introducen errores en ella.
- Clasificación temporal
  - Nueva característica -los cambios realizados con respecto a nuevas funcionalidades en la versión introducen errores en otras novedades en la misma versión del software.
  - Característica preexistente -los cambios realizados con respecto a nuevas funcionalidades introducen errores en funcionalidad existente de previas versiones.

### Pruebas no Funcionales

- Hablar de pruebas NO funcionales es hablar de la verificación de los requisitos no funcionales de una aplicación.
- Las diferentes pruebas no funcionales son comúnmente confundidas y sus alcances tienden a sobreponerse.

#### Pruebas de rendimiento

- Este tipo de pruebas no se realiza para encontrar defectos en una aplicación, sino para eliminar cuellos de botella y establecer una línea base que pueda ser utilizada en un futuro para comparar el incremento en el rendimiento de la aplicación bajo pruebas.
- Este servicio comúnmente incluye las pruebas de carga, pruebas de estrés y pruebas de resistencia entre otras.

#### Pruebas de disponibilidad

- Las pruebas de disponibilidad verifican que sus procesos de negocio están funcionando de forma correcta, al margen del estado de sus recursos hardware.
- Nuestras pruebas de disponibilidad incluyen la implantación de herramientas para verificar de manera continua que su entorno está funcionando como espera y su disponibilidad está dentro de los límites que han sido previamente establecidos.

#### Pruebas de seguridad

- Las pruebas de seguridad cubren el proceso de evaluar la seguridad de sus sistemas desde un punto de vista externo y sin conocimiento previo de los mismos.
- Los sistemas y políticas de seguridad son analizados exhaustivamente con el fin de encontrar fallos de seguridad, tanto en el diseño, como en la implementación de la aplicación.

#### Pruebas OAT

- Las pruebas de Aceptación Operacional (OAT) se realizan como paso inmediatamente anterior a la puesta en producción de un sistema, una vez finalizadas las pruebas de UAT (Pruebas de aceptación del usuario).
- El objetivo general de este tipo de pruebas es comprobar que la aplicación dispone de la fiabilidad y el soporte necesarios para su puesta en marcha en producción.

#### Pruebas de carga

-  Este es el tipo más sencillo de pruebas de rendimiento. Una prueba de carga se realiza generalmente para observar el comportamiento de una aplicación bajo una cantidad de peticiones esperada.
-  Esta carga puede ser el número esperado de usuarios concurrentes utilizando la aplicación y que realizan un número específico de transacciones durante el tiempo que dura la carga.

#### Pruebas de estrés

- Esta prueba se utiliza normalmente para romper la aplicación. Se va doblando el número de usuarios que se agregan a la aplicación y se ejecuta una prueba de carga hasta que se rompe.
- Este tipo de prueba se realiza para determinar la solidez de la aplicación en los momentos de carga extrema y ayuda a los administradores para determinar si la aplicación rendirá lo suficiente en caso de que la carga real supere a la carga esperada.

#### Pruebas de estabilidad

- Esta prueba normalmente se hace para determinar si la aplicación puede aguantar una carga esperada continua.
- Generalmente esta prueba se realiza para determinar si hay alguna fuga de memoria en la aplicación.

#### Pruebas de pico

- La prueba de picos, como el nombre sugiere, trata de observar el comportamiento del sistema variando el número de usuarios, tanto cuando bajan, como cuando tiene cambios drásticos en su carga.
- Como buena práctica, siempre es aconsejable disponer de un entorno de pruebas de rendimiento lo más parecido como se pueda al entorno de producción.

#### Pruebas de volumen

- La prueba de volumen sujeta al elemento de prueba a grandes cantidades de datos, para determinar si se alcanzan los límites que hacen fallar al software.
- También identifica la carga máxima continua o volumen que el elemento de prueba puede manejar por un período dado.

#### Pruebas de escabilidad

- Analizan consumo de recursos durante diferentes cargas de la aplicación.
- Recursos: Velocidad de CPU, Velocidad de disco, Velocidad de red.
- También someten aplicaciones a escenarios de negocios comunes.
- Usan medidores de CPU, disco, red, instalados en la aplicación bajo prueba.
