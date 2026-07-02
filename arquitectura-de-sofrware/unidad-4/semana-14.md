# Semana 14: Serverless Architecture

## Intro

### Definición de Serverless

- Cubre una variedad de técnicas y tecnologías.
- Se agrupan estas ideas en dos áreas: Backend as a Service (BaaS), Functions as a Service (FaaS).

### Backend as a Service

- BaaS se trata de reemplazar los componentes del lado del servidor que codificamos y/o administramos nosotros mismos con servicios listos para usar.
- En concepto, está más cerca de ser un SaaS que de ser una instancia virtual o un contenedor.
- Los servicios BaaS son componentes remotos genéricos de dominio que podemos incorporar a nuestros productos.

### Functions as a Service / Serverless Compute

- FaaS es otra forma de Computación como servicio, un entorno genérico dentro del cual podemos ejecutar nuestro software.
- Implementamos software del lado del servidor con una instancia de host (máquina virtual o contenedor).
- Si nuestro host en una VM o un contenedor, entonces nuestra aplicación es un procesos del sistema operativo

## Serverless

### Non-Serverless Architecture

- Una aplicación móvil nativa para iOS o Android.
- Un backend escrito en Java, que se ejecuta en un servidor de aplicaciones, como JBoss o Tomcat.
- Una base de datos relacional, como MySQL.

### Serverless Architecture

- La interfaz de usuario seguirá siendo parte de la aplicación móvil nativa, la autenticación y la administración de los usuarios pueden ser manejadas por un servicio BaaS como AWS Cognito.
- USar el componente, AWS API Gateway, para manejar el enrutamiento de las solicitudes HTTP entre la aplicación móvil y la lógica del backend de una manera segura y escalable.
- Cada operación distinta se puede encapsular como una función FaaS.
