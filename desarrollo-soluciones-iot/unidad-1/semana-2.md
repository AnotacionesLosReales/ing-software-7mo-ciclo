# Semana 2: OOP Review

## Sesion 1: C++ and Python OOP Review

### Plugins

- Git Flow Integration Plus
- Atom Material Icons
- Conventional Commit
- CodeGlance Pro
- plantuml4Idea
- JetBrains AI Assistant
- Xcode theme
- GitHub Copilot

### Comments Convention

- C++: Doxygen
- Java: JavaDocs
- C#: XML Docs
- Python: docstrings

### Proyectos en C++

- CMakeLists.txt: Tiene la configuracion de dependencias del proyecto
- Archivos .h: Header files - van en la carpeta "include".
- Archivos .cpp: Source files - van en la carpeta "src".

```
CMakeLists.txt
---------------
cmake_minimum_required(VERSION 4.2)
project(cpp_opp_review)

# Set C++ Standard to C++20
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS ON)

# Include the directories containing the header files
include_directories(${PROJECT_SOURCE_DIR}/include)

# Source files
set(SOURCES
        main.cpp)

# Define the executable target
add_executable(cpp_opp_review ${SOURCES})
```

### Header and Source files

- Nombres de clases: Upper Camelcase.
- Nombres de atributos: Lower Camelcase.
- Destructores: Libera recursos de memoria.
- ```virtual```: usado para polimorfismo.
- ```[[nodiscard]]```: atributo que indica al compilador que emita una advertencia si el valor de retorno de una función, o el resultado de un constructor, es ignorado por el llamador.
- ```default```: se utiliza para indicarle al compilador que genere automáticamente la implementación por defecto de funciones especiales de clase.
- ```std::unique_ptr```: es un puntero inteligente que gestiona recursos asignados dinámicamente con propiedad exclusiva. Se define en <memory> y elimina automáticamente la memoria al salir del ámbito. Ademas, no se puede copiar, solo mover, evitando así fugas de memoria y eliminaciones dobles.
- ```const T```: es la referencia constante. Se utiliza para pasar argumentos a funciones de manera eficiente sin copiarlos, garantizando al mismo tiempo que el objeto original no sea modificado.
- ```auto```: permite al compilador deducir automáticamente el tipo de dato de una variable a partir de su expresión de inicialización.
- ```std::move```: convierte una expresión (generalmente una variable, lvalue) en una referencia rvalue. No mueve datos por sí misma, sino que indica al compilador que un objeto puede ser "movido", permitiendo transferir recursos (como memoria dinámica) en lugar de copiarlos, mejorando el rendimiento.
- ```std::cerr```: flujo de salida estándar utilizado específicamente para mostrar mensajes de error, advertencias o diagnósticos en la consola.
- ```std::ranges::none_of```: es un algoritmo que verifica si ningún elemento de un rango cumple con una condición (predicado) dada. Devuelve true si la condición es falsa para todos los elementos o si el rango está vacío, y false en caso contrario.

### Proyectos en Python

- ```abc```: es una dependencia que ofrece las herramientas necesarias para crear una clase base abstracta.
- ```ABC```: asegura que las clases derivadas implementen métodos obligatorios.
- ```@property```: es un decorador que transforma métodos de clase en atributos de solo lectura, permitiendo acceder a ellos sin usar paréntesis.
- ```@abstractmethod```: es un decorador perteneciente a ABC que se utiliza para definir métodos en una clase base que obligatoriamente deben ser implementados por cualquier subclase concreta.

## Sesion 2: Casos IoT

## Edge Computing vs Cloud Computing

- Edge Computing: procesamiento de datos cerca de la fuente de generación, reduciendo latencia y ancho de banda.
- Cloud Computing: procesamiento de datos en servidores remotos, ofreciendo escalabilidad y recursos compartidos

### Caso: Smart Mirror

Es mucho más costoso procesar video e imágenes en la nube, por lo que es mejor hacerlo en el edge.

Dentro de edge: Recolección, filtro, agregación de datos y modelo LLM pre entrenado.

Dentro de Cloud: Análisis y dashboards.

### C4 Model y big Picture

landscape: afuera los segmentos y dentro los empleados.

Se despliega en el server y se ejecuta en el browser.

Big Picture: Los procesos de neogcio sin contar con nuestra solución. 

---

## Sesion 2: IoT Solution Components

### IoT Architecture

- Device layer.
- Network Layer.
- Edge processing Layer.
- Service and application support layer.
- Application Layer.

### IoT C4 Architecture

- Contenedores: elementos que se despliegan.
