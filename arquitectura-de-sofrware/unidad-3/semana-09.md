# Semana 9: Cloud Application Architecture

## Sesión 1: Cloud Architecture Intro

### Traditional vs Cloud (App Architecture)

1. Cambio mis gastos de capital por gastos variables. Además, solo pago por la cantidad que consumo.
2. Economías de escala. Se distribuyen los costos y se logran precio menores. Del 2017 a la fecha esos costos se redujeron en 74%.
3. Evito las estimaciones sobre capacidad. Estos cambios se realizan en minutos.
4. Más velocidad y agilidad.
5. No hay gastos de mantenimiento / actualización de centros de datos.

### Cloud Computing

- Es una experiencia de usuario y un modelo de negocio:
  - Ofertas estandarizadas
  - Provisionamiento rapido
  - Flexibilidad de precios
- Un metodo para gestion de infraestructura y entrega de servicios
  - Recursos virtualizados
  - Se gestiona como un unico gran recurso
  - Entrega de servicios con escalamiento elastico
 
#### Usos de Cloud Computing

- Infraestructura como Servicio (IaaS)
  -  Servidores, software, equipos.
  -  Asignación dinámica de recursos.
- Plataforma como Servicio (PaaS)
  - Facilita el servicio al proceso de construir y desarrollar aplicaciones y servicio web.
- Software como Servicio (SaaS)
  - Licenciar software a medida.

### AWS

- Low Ongoing Cost:, pay-as-you-go pricing with no up-front expenses or long-term commitments.
- Instant Elasticity & Flexible Capacity: (scaling up and down) Eliminate guessing on your infrastructure capacity needs.
- Speed & Agility: Develop and deploy applications faster Instead of waiting weeks or months for hardware to arrive and get installed.
- Apps not Ops: Focus on projects. Lets you shift resources away from data center investments and operations and move them to innovative new projects.
- Global Reach: Take your apps global in minutes.
- Open and Flexible: You choose the development platform or programming model that makes the most sense for your business.
- Secure: Allows your application to take advantage of the multiple layers of operational and physical security in the AWS data centers to ensure the integrity and safety of your data.

## LAB: Creación de Máquinas Virtuales

### Crear una Máquina Virtual Alpine

- En Virtual Box, presionar el botón NUEVA.
- En el campo VM Name, digitar el nombre de la máquina virtual (para este lab, es el Alpine).
- En el campo VM Folder, apuntar a la carpeta donde se almacenará la VM.
- En el campo ISO Image, elegir la imagen descargada.
- En el campo OS, elegir Linux (para Alpine).
- En el campo OS Distribution, elegir Other Linux si no aparece Alpine.
- A continuación, se especifica el Hardware de la VM:
  - Para memoria, utilizar 4096 MB.
  - Para número de CPUs (núcleos), elegir 4.
  - Para Disco Duro, elegir 6 GB.
- Revisar la configuración utilizada, y presionar TERMINAR.

### Verificar la creación

- Acceder a Configuración.
- Ir a Almacenamiento.
- Verificar que exista la Imagen y el Disco Duro con la imagen elegida.

### Lista de comandos

- clear: limpiar la consola.
- setup-alpine: para iniciar el instalador.
- poweroff: para apagar el SO.
- reboot: para reiniciar el SO.

### Iniciar y acceder a la VM

- La contraseña del alpine descargado es root.
- Ejecutar el instalador.
- Se pide la distribución del teclado. Elegir 'latam'.
- Luego, se pide por una variante. Se puede elegir cualquiera o pone 'latam'.
- Ingresar el system hostname. Ejemplo: server1.empresa. Para elegir localhost, solo presionar enter.
- Luego, sigue la configuración de la tarjeta de red de la VM. Como esta VM solo tiene 1 tarjeta, presiona enter para eth0.
- A continuación, configurar la IP Address para eth0. Elegir dhcp para autoasignación, que está por defecto.
- Ahora, se le pregunta si desea configurar manualmente algo más de la tarjeta de red. Confirmar "n" para no realizar configuración manual.
- Se pide asignar una contraseña para el usuario root. Asignar cualquiera como Passw0rd. Luego, se pide reescribir la contraseña.
- Ahora, se le pide elegir la zona horaria para el Sistema Operativo. Por defecto, está como Universal Time Coordinated (UTC). Para Linux, usar Eastern Standard Time (EST).
- Después, se pregunta por el URL del proxy (proceso intermedio) sea para HTTP o FTP. Por defecto, se deja en 'none'. Si se deja habilitado, habría que abrir puertos.
- Ahora, se pide qué cliente Network Time Protocol (NTP) ejecutar en el SO. Por defecto, está en chrony.
- Luego, elegir qué número de Mirror usar para el SO que trae actualizaciones del sistema operativo.
- Ahora, se debe setear usuarios para la máquina virtual. Para development, se usa root, para production se debe crear otro usuario con menos privilegios.
- Ahora, se debe configurar el Servidor ssh (es una consola remota) para la máquina virtual. Por defecto está en open-ssh.
- Ahora se pregunta si desea que root se logee como ssh.
- Ahora, se debe configurar un SSH Key (firma digital) para conectarse. Por defecto, está en 'none'.
- A continuación, se pregunta por cuál disco usar (se creó con la imagen). Elegir el disco creado 'sda'.
- Ahora, se pregunta por cómo se quiere usar el disco elegido. 'sys': ahí se instala el SO. Elige sys.
- Ahora, se pregunta si hay algo en el disco. Para formatear, elegir 'y' para dejar en 0 ese disco elegido.
- Ahora, ir a Configuracion, Almacenamiento. Se marca el ISO de la maquina virtual. Buscar el boton con la equis para Remove Atachment.
- Con esto, la maquina virtual al iniciarse, ya no iniciara el proceso de descarga desde el ISO nuevamente. Con ello, levanta desde el disco y no desde el ISO.

### Copiar la Maquina Virtual

- Se crea un archivo VDI. Este archivo se puede copiar e iniciar en otras Maquinas o PCs para crear mas maquinas virtuales con Alpine.
