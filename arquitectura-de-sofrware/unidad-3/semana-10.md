# Semana 10: Cloud Patterns

## LAB: Implementación de Docker en Alpine Linux

### Docker

- Maneja contenedores.
- DevOps: “Crea una vez y ejecútalo donde quieras”.
- SysOps: “Configúralo una vez y ejecútalo donde quieras”.

<div align="center">
  <img src="https://i.imgur.com/SCmJzfK.png" alt="sivaasalir">
  <img src="https://i.imgur.com/k8KcQWf.png" alt="sivasalir2">
</div>

- SSH: Funciona en el puerto 22 para acceder a la VM. Por defecto la VM está cerrada.
- Por protección, se pone un puerto distinto al 22 para no exponer fácilmente el puerto. Ejemplo: 667.

### Crea VM Alpine y configurar Docker

1. Abrir VirtualBox y elegir la opción "Nueva".
2. Buscar la carpeta donde almacenar la VM.
3. Para no crear, no elegir ISO.
4. Configurar de forma normal y terminar la configuración.
5. Acceder a Configuración > Almacenamiento. Luego, borrar el disco duro existente con el ícono marcado con la X. Después, agregar nuevo disco y elegir la VDI descargada de Alpine.
6. En comando: cd /etc/apk.
7. Luego: ls -l
8. Después: cat repositories
9. Luego: vi repositories. Que abre el editor "Vi" de Linux.
10. En modo edición del archivo repositories, elimina el "#" del segundo http.
11. Luego, presionar "Esc" para salir del modo edición y escribir ":wq" para guardar y salir.
12. Después, escribir "apk add docker" para instalar Docker.
13. Luego, escribir "service docker start".
14. Luego, "docker version" para ver la versión.
15. Luego, "docker images" para ver las imagenes
16. Luego, "docker pull ubuntu" para crear una nueva imagen de ubuntu.

### Habilitar SSH en la VM

1. Ahora, escribir "cd /etc/ssh".
2. Ubicar el archivo "sshd_config", ahí se debe realizar un cambio.
3. Digitar "vi sshd_config" para abrir el modo configuración. Buscar la linea 32 que dice "PermitRootLogin" y hay que cambiar que diga "yes".
4. Presionar "Esc" y luego ":wq".
5. Luego, escribir "service sshd restart".
6. Se puede configurar alertas en IP Tables para detectar cuando alguien externo intenta acceder al SSH.

### Traducción de puertos (Decirle al Firewall: "Quiero entrar por este puerto")

1. Ir a Configuracion > Red (en modo Experto).
2. Luego, buscar la opción "Reenvío de puertos". Puerto anfitrión (lo que se expone): 222 y Puerto invitado (externo): 22.
3. Luego, abrir "PUTTY" y en HOST NAME escribir 127.0.0.1 y en PORT escribir 22 y presionar "Open".
4. Después, escribir las credenciales de la máquina virtual.

### Ejecutar Ubuntu (desde PUTTY)

1. Ejecutar "docker run -it ubuntu bash" (-it: Interactivo, bash: apenas levante ubuntu, abre el shell).
2. El shell de alpine es "sh", el de ubuntu es "shell" y el de windows es "cmd, powershell y el buscador".
3. Usar "apt-get update" para actualizar el ubuntu. Con ello, se le colocó una capa al ubuntu base con un update.
4. Instala figlet con "apt-get install figlet". Para escribir algo usar "figlet 'texto'".
5. En otro PUTTY, escribir "docker ps" para ver los contenedores que están corriendo.
6. En el otro PUTTY, escribir "docker ps -a" cuando haya cerrado la sesión de ubuntu para ver qué sesiones están almacenadas.
7. Escribir "history" para ver todos los comandos ejecutados.

### Convertir archivo modificado a otra imagen (UBUNTU 2)

1. Escribir "docker commit '4 primeros digitos del id del contenedor'".
2. Escribir "docker images" y se visualiza una nueva imagen creada a partir del ubuntu original.
3. Para cambiar el nombre de la imagen usar "docker image tag '4 primeros digitos de la id de la imagen' 'escribir_tag'.

### Uso de NGINX en Alpine (dentro de otro Alpine)

1. Escribir "docker pull alpine" y, luego, "docker pull nginx:alpine"
2. Ejecutar alpine "docker run -it alpine sh".
3. Escribir "touch hola.txt" para crear un archivo en Alpine.
4. A los cambios hechos, se les debe hacer commit para no perder la imagen cambiada.

### Redis

- Normalmente, se tiene una BD con tablas, etc. En este caso, la aplicación se conecta a la DB y ejecuta "select * from products".
- Ahí entra redis, que es un software de caché. El contenido de la tabla products, se puede cargar en el caché.
- Ahora, la aplicación cuando quiere leer productos, no lo hace de la BD, sino de redis.
- Para esto, se deben buscar las tablas más pesadas y a esas se les aplica una subida a caché por lo mismo que no cambian mucho.

### Instalar Redis

1. Escribir "docker pull redis".
2. Ejecutar redis "docker run -d -p 6379:6379 redis" (-d: detach, dejalo corriendo como proceso, -p: puerto 6379).
3. Habilitar el puerto 6379 de la VM. Ir a Config > Red (modo expert) > Redirección de puertos y escribir 6370 en puerto anfitrión y externo.
