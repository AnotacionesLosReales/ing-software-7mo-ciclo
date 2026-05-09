# Semana 6: Agile Project Cost Management

## Intro

- Los proyectos consumen el presupuesto del proyecto durante la ejecucion.
- Costos es lo que se estima.
- Presupuesto es un cronograma donde es estiman los gastos.

***Consideraciones para el enfoque Agile:** Los proyectos adaptables no administran el dinero de la misma manera quelo hacen os proyectos predictivos. Para estos casos, se dispone de una cantidad predeterminada de fondos (y tiempo) para el proyecto, y esta cantidad es fija.*
  
## Plan for Project Cost Management

- En un proyecto predictivo, se necesita un plan solo para los costos del proyecto.
- El plan ayuda a definir politicas de costos, documentos que determinan como se gastara el dinero y que entradas indican como se lleva a cabo la administracion de costos a lo largo del proyecto.

**Inputs:**
- Project Charter.
- Project Management Plan.

***Consideraciones para el enfoque Agile:*** 
- *Los presupuestos en proyectos adaptativos son predeterminados.*
- *Segun los cambios de las necesidades del cliente, se puede refinar el product backlog para priorizar los cambios.*
- *El mayor gasto en proyectos adaptativos es la mano de obra (horas de trabajo de conocimiento del equipo del proyecto).*
- *Punto de no retorno: dependen del estado actual de desarrollo del proyecto (por ejemplo: pedir algun cambio estructural en fase de pruebas de una funcionalidad).*

## Estimate the Project Costs

***Consideraciones para el enfoque Agile:*** 
- *En la planificacion de proyectos tradicional, el gerente del proyecto es responsable de estimar los costos del proyecto. En proyectos agiles, el equipo estima indirectamente los costos al proporcionar primero estimaciones de funcionalidades.*
- *Estimar los costos de recursos humanos para un proyecto agil deberia ser mucho menos complicado que en proyectos tradicionales.*
- *El gerente toma el costo total para los miembros del equipo y lo multiplica por el numero de iteraciones proyectadas por el equipo en el release plan.*

## Determine the Project Budget

- La presupuestacion de costos implica la agregacion de los costos estimados de las actividades individuales del cronograma o paquetes de trabajo para establecer una linea base de costos totales para medir el desempeno.
- El objetivo de cualquier linea de base es permitir que se realice un seguimiento del rendimiento a lo largo del proyecto, pero tambien se necesita un presupuesto vivo para poder actualizar los gastos reales y luego compararlos con la linea de base.

***Consideraciones para el enfoque Agile:*** 
- *En la planificacion tradicional, el trabajo del equipo no esta autorizado hasta despues de que se haya realizado el presupuesto de costos.*
- *En Agile, se debe autorizar parte del trabajo antes del inicio del proyecto para que el equipo pueda al menos participar en el release plan.*
- *En proyectos agiles, los equipos dedicados ayudan a estabilizar los costos a lo largo del ciclo de vida del proyecto.*

## Manage Project Costs Control

- Una vez financiado el proyecto, depende del gerente y el equipo trabajar efectivamente para controlar los costos. Esto significa evitar el aumento del alcance, los cambios no documentados y deshacerse de cualquier actividad sin valor agregado.
- El control de costos se enfoca en controlar la capacidad de cambio de los costos y en como el equipo de gestion del proyecto puede permitir o evitar que ocurran cambios en los costos.

***Consideraciones para el enfoque Agile:*** 
- *Los cambios en la linea de base de costos de proyectos agiles se manejan mediante el uso adecuado de la priorizacion del product backlog.*
- *Agregar o volver a priorizar una funcionalidad en el product backlog constituye lo que tradicionalmente se conoce como cambio de alcance o 'cambio esperado' en terminologia agil*

## Work with Earned Value Management (EVM)

- En la ejecucion tradicional de proyectos, se utiliza Earned Value Management. Resulta que EVM tambien se usa en agile.

- Valor planificado (PV): es lo que tu estimas realizar.
- Costo real (AC): es el dinero que realmente se ha gastado.
- Valor ganado (EV): estimacion del trabajo actual.
 
***Caso: se tiene un modulo de login, dura 10 dias su desarrollo y cuesta 10k soles. Al quinto dia se reporta un gasto de 7k soles. Al revisarse, el avance va un 40% (transformado a 4k soles en dinero).***
- PV: 10k soles.
- RC: 7k soles.
- EV: 4k soles.
- En dia 5, se espera un avance de 50%, o sea, 5k soles, por lo tanto, hay un sobrecosto de 2k soles (7k - 5k). Y en el avance, estamos mal porque hay un desbalance de 1k soles (40% real o sea 4k soles), pero deberia haber gastado 5k (50% avance esperado).

**Formulas**
- Variacion de costo (CV): **CV = EV - AC**. Si es menor a 0, esta mal (por encima del presupuesto)). Si es mayor a 0 bien (por debajo del presupuesto).
- Indice de desempeno del presupuesto (CPI): **CPI = EV / AC**. Si es menor que 1, mal (ineficiencia). Si es igual a 1, bien (eficiencia). Mayor a 1, esta muy bien.
- Valor relativo (CV): **CV% = CV / EV**.
- Variacion del cronograma (SV): **SV = EV - PV (PV se refiere a planificado para el dia a evaluar)**. Si es menor a 0, mal (retraso respecto a lo planificado). Si es mayor a 0, bien (por delante a lo planificado).
- Indice de desempeno del cronograma (SPI): **SPI = EV / PV**. Si es menor a 1, mal (ineficiencia). Si es mayor a 1, bien (eficiente).
- Valor relativo SV: **SVR = SV / EV**.
