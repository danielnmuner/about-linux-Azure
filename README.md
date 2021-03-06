## Curso de Administración de Servidores Linux  

### Tabla de Contenidos

- [Distribuciones más utilizadas de Linux](#distribuciones-más-utilizadas-de-linux)
- [Instalación de Ubuntu Server](#instalación-de-ubuntu-server)
- [Instrucciones para instalar Rocky](#instrucciones-para-instalar-rocky)
- [Gestión del árbol de directorios](#gestión-del-árbol-de-directorios)
- [Diferencias entre LESS CAT HEAD y TAIL para lectura de archivos](#diferencias-entre-less-cat-head-y-tail-para-lectura-de-archivos)
- [Interacción con archivos y permisos](#interacción-con-archivos-y-permisos)
- [Conociendo las terminales en linux](#conociendo-las-terminales-en-linux)
- [Manejo y monitoreo de procesos y recursos del sistema](#manejo-y-monitoreo-de-procesos-y-recursos-del-sistema)
- [Monitoreo de recursos del sistema](#monitoreo-de-recursos-del-sistema)
- [Análisis de los parámetros de red](#análisis-de-los-parámetros-de-red)
- [Administración de paquetes acorde a la distribución](#administración-de-paquetes-acorde-a-la-distribución)
- [Manejo de paquetes en sistemas basados en Debian](#manejo-de-paquetes-en-sistemas-basados-en-bebian)
- [Administración de software con YUM y RPM para CentOS](#administración-de-software-con-yum-y-rpm-para-centos)
- [Nagios: Desempaquetado, descompresión, compilación e instalación de paquetes](#nagios-Desempaquetado-descompresión-compilación-e-instalación-de-paquetes)
- [Los usuarios, una tarea vital en el proceso de administración del sistema operativo](#los-usuarios-una-tarea-vital-en-el-proceso-de-administración-del-sistema-operativo)
- [Creando y manejando cuentas de usuario en el sistema operativo](#creando-y-manejando-cuentas-de-usuario-en-el-sistema-operativo)
- [Entendiendo la membresía de los grupos](#entendiendo-la-membresía-de-los-grupos)
- [Usando PAM para el control de acceso de usuarios](#usando-pam-para-el-control-de-acceso-de-usuarios)
- [Autenticación de clientes y servidores sobre SSH](#autenticación-de-clientes-y-servidores-sobre-ssh)
- [Configurando DNS con bind](#configurando-dns-con-bind)
- [Arranque, detención y recarga de servicios](#arranque-detención-y-recarga-de-servicios)
- [NGINX y Apache en Ubuntu server](#nginx-y-apache-en-ubuntu-server)
- [Instalación y configuración de NGINX](#instalación-y-configuración-de-nginx)
- [¿Qué es NGINX Amplify?](#-¿qué-es-nginx-amplify?-)
- [Monitoreo de MySQL con Nagios](#monitoreo-de-mysql-con-nagios)
- [Configuración de Nagios](#configuración-de-nagios)
- [Los logs, nuestros mejores amigos](#los-logs-nuestros-mejores-amigos)
- [Las bases de bash](#las-bases-de-bash)
- [Automatizando tareas desde la terminal](#automatizando-tareas-desde-la-terminal)
- [Crontab](#crontab)
- [Entendiendo la gestión de vulnerabilidades](#entendiendo-la-gestión-de-vulnerabilidades)
- [¿Qué es una superficie de ataque? Principio del menor privilegio](#¿-qué-es-una-superficie-de-ataque-?-principio-del-menor-privilegio)
- [Configuración de Node.js en un ambiente productivo](#configuración-de-node-.-js-en-un-ambiente-productivo)

### **Distribuciones más utilizadas de Linux**
1. Vamos a usar dos distribuciones de Linux: Ubuntu Server en su versión 18.04 y Rocky-8.5 RedHat.
> <img src="https://static.platzi.com/media/user_upload/45009527_1925244564239156_3912908948335755264_n-61d234d0-93af-4a72-91f2-4de917b4ae5f.jpg" alt="Clouds" style="width:300px;"/>
2. Importante: Se deben instalar las versiones LTS (Long Term Support), ya que ofrecen soporte de al menos 5 años

### **Instalación de Ubuntu Server**
---
#### Instalación de Ubuntu Server

1. Descargar Virtual Box: [VirtualBox](https://www.virtualbox.org/)
2. Descargar Ubuntu Server: [Ubuntu](https://ubuntu.com/download/server)
3. Crear una nueva máquina virtual
4. En la configuración de nuestra máquina, en la sección Red cambiar de NAT a Adaptador puente. En avanzadas, colocar en el Modo promiscuo “Permitir todo”
5. En la sección Storage seleccionamos el cd que dice “Vacío”, y en el apartado de atributos a la derecha seleccionamos el icono del cd para buscar nuestra imagen ISO de Ubuntu ya descargada anteriormente. Aceptamos los cambios.
6. Iniciamos la máquina virtual
7. Si estamos trabajando en un servidor físico, deberíamos seleccionar “Comprobar memoria” Instalamos el sistema operativo


**Notes**: Si estas en windows 11/10 y _Hyper-V_ no te permite correr VirtualBox 6.1 independiente de la version LTS de Ubuntu, entonces te recomiendo usar **VirtualBox 5.2** y que desactives Hyper-V a través de `bcdedit /set hypervisorlaunchtype off`, si usas WSL2 probablemente
te aparezca el siguiente mensaje _Please enable the Virtual Machine Platform Windows feature and ensure virtualization is enabled in the BIOS._ pero no te preocupes puedes volver al estado inicial con `bcdedit /set hypervisorlaunchtype auto` no importa cuantas veces tengas que hacer este proceso solo recuerda **REINICIAR** tu pc para que los cambios se guarden correctamente. Revise muchos foros de VirtualBox y lo mejor que puedes hacer para realmente descubrir el problema es a través de los logs a los cuales puedes acceder, apagando la VM, click derecho sobre VM > Mostrar Trazas o Show Log. 👍

### Instrucciones para instalar Rocky 
---
#### Instalación de CentOS

1. Descargar [VirtualBox](https://www.virtualbox.org/)
2. Descargar [Rocky-8.5](https://rockylinux.org/download)
3. Crear una nueva máquina virtual
4. En la configuración de nuestra máquina, en la sección Red cambiar de NAT a Adaptador puente. En avanzadas, colocar en el Modo promiscuo “Permitir todo”
5. En la sección Storage seleccionamos el cd que dice “Vacío”, y en el apartado de atributos a la derecha seleccionamos el icono del cd para buscar nuestra imagen ISO de CentOS ya descargada anteriormente. Aceptamos los cambios
6. Iniciamos la máquina virtual
7. Instalamos el sistema operativo
8. En la configuración, en el apartado de NETWORK & HOST NAME, activar la interfaz con el botón “on”. Cambiamos el host name a “platzi-server” y damos click en aplicar
9. En el apartado de INSTALLATION DESTINATION seleccionamos el disco de Virtual Box
9. Configuramos la hora y damos click en done
10. Hacemos click en ROOT PASSWORD y creamos una contraseña para el usuario root
11. Creamos un usuario nuevo dando click en USER CREATION y finalizamos la instalación.

### Gestión del árbol de directorios
---
- `pwd`: nos muestra nuestra ubicación actual en el árbol de directorios (Print Working Directory).  
- `ls`: nos muestra el contenido de las carpetas de nuestro sistema operativo. Podemos especificar alguna ruta o, por defecto, listar el contenido de la carpeta donde estamos trabajando.    
- `cd`: cambiar nuestra ubicación en el árbol de directorios (Change Directory). Usamos dos puntos (..) para referirnos al directorio padre y solo uno (.) para referirnos a nuestro directorio actual.  
- `touch`: nos ayuda a crear archivos desde la terminal.  
- `mkdir`: nos ayuda a crear carpetas desde la terminal.  
- `cp`: nos permite duplicar archivos y carpetas.  
- `mv`: cambiar el nombre de nuestros archivos y carpetas.

### Diferencias entre LESS CAT HEAD y TAIL para lectura de archivos
---
- `cat`: Muestra un archivo sin paginar.  
- `less`: Muestra un archivo paginado. Pulsando “/” y escribiendo una palabra, puedo buscar las coincidencias de la misma en el archivo. Con la tecla “n” me muevo entre coincidencias hacia adelante, y con `shift + n` me muevo entre coincidencias hacia atras. Con espacio cambio de página.  
- `tail`: Muestra las últimas 10 líneas de un archivo específico. Con la opción `-n` puedo modificar la cantidad de líneas que veo. Con la opción -f puedo poner los cambios en escucha.  
- `head`: Muestra las primeras 10 lineas de un archivo específico. Con la opción `-n` puedo modificar la cantidad de líneas que veo.
- `man`: Muestra ayuda sobre comandos.  

### Interacción con archivos y permisos
---
- Con el comando `ls -l` podemos observar la lista de archivos de nuestro directorio actual con información un poco más detallada. El primer campo nos indica los diferentes permisos para cada archivo o directorio. Por ejemplo: `-rwxrw-r--`.

- El primer carácter nos indica si tenemos un archivo (-), enlace simbólico (l) o directorio (d).

- Los siguientes caracteres se dividen en grupos de 3: lectura **r**, escritura **w** y ejecución **x**. El primer grupo son los permisos del usuario que creó ese archivo, el segundo para el grupo al que pertenece este usuario y el tercero para cualquier otro usuario de tu sistema operativo.

- Los grupos nos ayudan a darle los mismos permisos a diferentes usuarios sin necesidad de asignarlos a cada uno individualmente. Todos los usuarios que pertenezcan al grupo tendrán los mismos permisos.

- Si en vez de estas letras encuentras un guion significa que ese usuario o grupo de usuarios no tiene permiso para esa acción en particular.

Por ejemplo: `-rwxrw-r--` nos indica que trabajamos con un archivo. Todos los usuarios del sistema tienen permisos de lectura. El usuario creador y su grupo tienen permiso de escritura. Y solo el usuario creador puede ejecutar el archivo.

También podemos encontrar estos permisos como 3 números del 1 al 7. Estos números son la suma de los 3 caracteres de permisos para cada usuario o grupo.

- `- = 0`
- `x = 1`
- `w = 2`
- `r = 4`
Por lo tanto, los permisos de nuestro archivo de ejemplo serían: `7 (1+2+4) 6 (0+2+4) 4 (0+0+4)`.

Para cambiar los permisos de un archivo o directorio podemos usar el comando `chmod` + a quién queremos añadir o quitar los permisos:

- El usuario propietario: `u`.
- El grupo, `g`.
- El resto de usuarios, `o`.
- Para todos, `a`.

**Por ejemplo, para añadir permisos de ejecución a nuestro usuario propietario usamos:**

- `chmod u+x nombre-del-archivo`

**También podemos cambiar al usuario propietario del archivo con el comando chown.**

- `sudo chown nuevo-usuario:grupo-usuarios nombre-del-archivo`

- Cambiar usuario `su username`

### Conociendo las terminales en linux
---
- `chvt`: Cambia de terminal
- `tty`: Muestra la terminal actual
- `who`: Muestra los usuarios conectados a nuestro sistema
- `w`: Hace lo mismo que el comando who pero muestra más información
- `ps`: Muestra los procesos corriendo. Con los modificadores -ft y tty podemos filtrar para ver las conexiones de los usuarios
- `kill`: Mata un proceso. Con el modificador -9 fuerzo el cierre del mismo

### Manejo y monitoreo de procesos y recursos del sistema
---
**Comandos**
|
- `ps`: Muestra los procesos corriendo. Modificadores:
- `aux`: Muestra todos los procesos
- `jobs`: Al igual que el comando anterior, muestra los procesos. A diferencia de ps, es un comando interno de la terminal
- `fg`: Abre un proceso que estaba pausado
- `nohup`: Genera un archivo llamado “nohup.out” que muestra toda la información que produjo un proceso
- `grep`: Nos ayuda a filtrar el resultado de un comando o el contenido de un archivo dependiendo de las palabras (o incluso expresión regular) que le indiquemo.  

**Lo que significa cada parametro al ejecutar el comando** `ps aux`

- `USER`: usuario con el que se ejecuta el proceso
- `PID`: ID del proceso
- `%CPU`: porcentaje de tiempo que el proceso estuvo en ejecución desde que se inició
- `%MEM`: porcentaje de memoria física utilizada
- `VSZ`: memoria virtual del proceso medida en KiB
- `RSS`: “resident set size”, es la cantidad de memoria física no swappeada que la tarea a utilizado (en KiB)
- `TT`: terminal que controla el proceso (tty)
- `STAT`: código de estado del proceso (información detallada más adelante)
- `STARTED`: fecha de inicio del proceso
- `TIME`: tiempo de CPU acumulado
- `COMMAND`: comando con todos sus argumentos

### Monitoreo de recursos del sistema
---
- `top`: Muestra la siguiente información del sistema:
- load average (carga promedio): Provee una representación en números del 1 al número de procesadores que tenga nuestro servidor del uso de los mismos. Uso de la memoria, Cantidad de usuarios, Uso del CPU, Procesos, Etc.

- `free`: Me muestra información sobre la memoria de mi sistema. Con el modificador -h la información es más legible para un humano
- `du`: Muestra información sobre el disco duro. Con el modificador -hsc y un directorio especificado muestra el tamaño de ese directorio
- `htop`: Funciona como top pero funciona de forma más intuitiva

**Comandos útiles**

- `cat /proc/cpuinfo | grep "processor"`: Muestra información sobre el CPU
- `sudo ps auxf | sort -nr -k 3 | head -5`: Muestra los 5 procesos que más uso hacen del CPU
- `sudo ps auxf | sort -nr -k 4 | head -5`: Muestra los 5 procesos que más uso hacen de la memoria RAM

### Análisis de los parámetros de red
---
**Comandos**

- `ifconfig`: Interface Configuration, muestra las tarjetas de red que tenemos y su direccionamiento específico
- `ip a`: IP Address Show, muestra las direcciones IP
- `hostname`: Como se identifica este equipo en la red
- `route -n`: Muestra cual es el dispositivo que me permite conectarme a internet
- `nslookup`: Muestra la dirección IP de un dominio determinado
- `curl`: Realiza consultas a un servidor
- `wget`: Permite descargar contenido de un servidor

**Comandos útiles**

- `ip -4 a`: Muestra las direcciones IPv4
- `ip -6 a`: Muestra las direcciones IPv6

### Administración de paquetes acorde a la distribución
---
**Ubuntu server**

- Repositorios: `apt`
- Extensión de paquetes: `.deb`

**Comandos:**

- `dpkg -l`: Lista todos los deb instalados en la máquina
- `dpkg -i paquete.deb`: Instala un paquete
- `dpkg -r paquete.deb`: Desinstala un paquete
- `dpkg-reconfigure paquete`: Permite configurar nuevamente un paquete
- `apt install paquete`: Instala un paquete desde un repositorio
- `apt search paquete`: Busca un paquete en un repositorio

**Rocky**

Repositorios: `yum`
Extensión de paquetes: `.rpm`

**Comandos:**

- `rpm -qa`: Lista todos los rpm instalados en la máquina
- `rpm -i paquete.rpm`: Instala un paquete
- `rpm -e paquete.rpm`: Desinstala un paquete
- `yum install paquete`: Instala un paquete desde un repositorio
- `yum search paquete`: Busca un paquete en un repositorio

#### Distribuciones Linux
---
![image](https://user-images.githubusercontent.com/60556632/161408242-9d528580-838f-490e-b306-5dd18db629e4.png)

### Manejo de paquetes en sistemas basados en Debian
---

- `sudo apt upgrade` No se trata solo de hacer el upgrade debemos verificar que que es lo que va a actlizar y que eso no valla a afectar nuestro ambiente de programacion.
- `sudo apt dist-upgrade` A diferencia del comando anterior este upgrade se realiza a nivel de Kernel, razón por lo cual se debe ser mas precavido puesto que podriamos romper algunos programas.

- [LivePatch](https://ubuntu.com/livepatch) nos permite realizar actualizaciones en e sistema sin necesidad de realizar reinicios.
- `sudo apt search mysql` Me permite buscar todos lo paquetes conformados por la keyword "mysql"
- `sudo apt search "mysql-server$"` Es mas especifico que es importante colocar el signo `$`
- `sudo apt-cache search "mysql-server$"` Es exactamente lo mismo que el comando anterior
- `dpkg -l` Lista los paquetes de mi OS
- `sudo dpkg-reconfigure tzdata` Toma el paquete `tzdata` para configurar la zona horaria, y asi podemos espesificar nuevamente que zona horario queremos usar.
- `sudo snap search aws-cli` Snap es tambien un gestor de paquetes de debian, en este caso podemos buscar la consola de amazon, Snap fue desarrollado Canonical, los mismos creadores de Ubuntu ccon el tiempo se ha ido migrando de apt a snap paulatinamente.
- `sudo snap refresh --list` Asi podemos ver todos los paquetes instalados en nuestro gestor snap
- `sudo snap info aws-cli` Asi podemos consultar un paquete de snap en especifico
- `sudo snap install canonical-livepatch` 
### Administración de software con YUM y RPM para CentOS
---

-`rpm -qa` Lista todos los paquetes de rpm `a` -> all
- `rpm -qi bash` Busca `i` informacion del paquete bash.
- `rpm -qc bash` Indica las rutas de los archivos involucrados en la configuracion `c` de Bash.
- `rpm -e curl` Borra `e` o intenta borrar un paquete del repositorio si el sistema lo permite.

### Nagios Desempaquetado descompresión compilación e instalación de paquetes
---

> No todo el software que necesitamos se encuentra en los repositorios. Debido a esto, algunas veces debemos descargar el software, realizar un proceso de descompresión y desempaquetado para finalmente instalar la herramienta.

> Instalación de algunas herramientas para manejar una base de datos MySQL 

- `sudo apt install build-essential libgd-dev openssl libssl-dev unzip apache2 php gcc libdbi-perl libdbd-mysql-perl` 
1. Build-essentials: The build-essentials packages are meta-packages that are necessary for compiling software.
2. [libgd-dev](https://packages.debian.org/sid/libgd-dev): It allows your code to quickly draw images complete with lines, arcs, text, multiple colours, cut and paste from other images, flood fills, and write out the result as a PNG file.
3. Unzip: Paradescomprimir archivos zip
4. Apache2: The goal of this project is to provide a secure, efficient and extensible server that provides HTTP services in sync with the current HTTP standards. ASi podremos soportar nagios😀
5. php: PHP is mainly focused on server-side scripting
6. gcc: GCC development is a part of the GNU Project, aiming to improve the compiler used in the GNU system including the GNU/Linux variant. 
7. [libdbi-perl](https://packages.debian.org/es/sid/libdbi-perl): Es un entorno de desarrollo en Perl que proporciona una interfaz común para acceder a varios sistemas de bases de datos de una manera uniforme. 
8. [libdbd-mysql-perl](https://packages.debian.org/stretch/libdbd-mysql-perl): DBD::mysql is the Perl5 Database Interface driver for the MariaDB/MySQL database. In other words: DBD::mysql is an interface between the Perl programming language and the MySQL programming API that comes with the MariaDB/MySQL relational database management system.

Instalación de Nagios: Nagios monitors your entire IT infrastructure to ensure systems, applications, services, and business processes are functioning properly.

- `wget https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.4.4.tar.gz -O nagioscore.tar.gz`

Descomprimir y desempaquetar archivos con tar:

- `tar xvzf nagioscore.tar.gz`

Este comando creará una carpeta nagios-4.4.4. El nombre de la carpeta puede variar dependiendo de la versión que descargaste. Entrando a esta carpeta podemos ejecutar diferentes archivos y comandos para configurar el software y realizar la instalación.

1. `sudo ./configure --with-https-conf=/etc/apache2/sites-enabled` . Permite configurar el software que vamos a instalar. `./configure` es un archivo dentro de la carpeta nagios-4.4.4. luego con el comando `--with-https-conf=` le indicamos que los queremos configurar con apache2 entregandole la ruta donde esta apache2.

#### [The magic behind configure, make, make install](https://thoughtbot.com/blog/the-magic-behind-configure-make-make-install)


3. `sudo make all` Verifica todos los archivos de configuracion anteriormente creados.
4. `sudo make install-groups-users` then `sudo usermod -a -G nagios www-data` finally `sudo make install` By definition, if you are doing make install that means you are making a local install
5. `sudo make install-init` This installs the init script in /lib/systemd/system.
6. `sudo make install-commandmode` This installs and configures permissions on the directory for holding the external command file.
7. `sudo make install-config` This installs sample config files in /usr/local/nagios/etc. Remember, these are *SAMPLE* config files.
8. `sudo make install-webconf` Permite habilitar el módulo Apache necesario para la interfaz web de Nagios -> Nagios/Apache conf file installed.
9. Por último, para administrar el servicio de nagios podemos usar los comandos `sudo systemctl (status, start, restart, reload, stop, enable, disable, list-dependencies) nagios`  

- Si queremos ver que hay en el localhost desde la terminal podemos ejecutar el comando `curl localhost` o `curl localhost | grep apache` para ver si esta relacionado con apache.
- Nagios ps si solo no es muy funcional a menos que le instalemos plugins por esta razon es importante hacerlo:

### Los usuarios una tarea vital en el proceso de administración del sistema operativo
---

- El comando `id` nos muestra el identificador único (uid) de cada usuario en nuestro sistema operativo. El ID 0 está reservado para el usuario root.
En debian Ubuntu Server los Id's inician desde 1000 y en CentOS RedHat inician desde 500.

- Con el comando `whoami` podemos ver con qué usuario estamos trabajando en este momento. Podemos ver todos los usuarios del sistema leyendo el archivo `cat /etc/passwd`. Aqui podemos ver todos los usuarios del sistema operativo que son necesarios para que el sistema operativo funcione.

- Las contraseñas de los usuarios están almacenadas en el archivo `cat etc/shadow`, pero están cifradas. Y solo el usuario `root` tiene permisos de lectura/escritura.

Para cambiar la contraseña de nuestros usuarios usamos el comando `passwd`.

### Creando y manejando cuentas de usuario en el sistema operativo
---

Comandos para administrar cuentas de usuarios:

- `sudo useradd nombre-usuario`: crea un usuario sin asignarle inmediatamente alguna contraseña ni consultar más información. Debemos terminar de configurar esta cuenta a mano posteriormente.
- `sudo adduser nombre-usuario`: crea un nuevo usuario con contraseña y algo más de información. También creará una nueva carpeta en la carpeta /home/.
- `userdel nombre-usuario`: eliminar cuentas de usuarios.
- `usermod`: modificar la información de alguna cuenta.
- `exit` para salir de un usuario y volver al inicial 
> Nunca modifiques a mano el archivo /etc/passwd. Para administrar los usuarios debemos usar los comandos que estudiamos en clase.

### Entendiendo la membresía de los grupos
---

1. Los grupos nos ayudan a darle los mismos permisos a diferentes usuarios al mismo tiempo, sin necesidad de asignar el mismo permiso a cada usuario individualmente. Todos los usuarios que pertenezcan al mismo grupo tendrán los mismos permisos.

2. Para cambiar de usuario sin necesidad de reiniciar el sistema podemos usar el comando `su - nombre-usuario`. **También podemos cambiar de usuario sin necesidad de saber su contraseña** usando el comando `sudo su - nombre-usuario`.

3. Para ver a qué grupos pertenecen nuestros usuarios usamos el comando `groups nombre-usuario`. Para **agregar usuarios a un nuevo grupo** usamos el comando `sudo gpasswd -a nombre-usuario nombre-grupo`. Los eliminamos de la misma forma con `gpasswd -d`.

4. Para esto también podemos usar el comando `sudo usermod -aG nombre-grupo nombre-usuario`. Recuerda que en este caso el orden en que escribimos el grupo y el ususario se invierte.

5. Para listar los permisos de nuestros usuarios ejecutamos el comando `sudo -l`.

### Usando PAM para el control de acceso de usuarios
---

- __PAM__ es un mecanismo para administrar a los usuarios de nuestro sistema operativo. Nos permite autenticar usuarios, controlar la cantidad de procesos que ejecutan cada uno, **verificar la fortaleza de sus contraseñas**, ver la hora a la que se conectan por SSH, entre otras.

- Con el comando `pwscore` **podemos probar qué tan fuertes son nuestras contraseñas** Donde el puntaje va de 0 a 100. Recuerda que para usar este comando en sistemas basados en Ubuntu debemos instalar el paquete `sudo apt install libpwquality-tools`. Siempre que debemos validar nuestros passwords con `pwscore` antes de asignarlas a los usuarios

- El comando `ulimit` nos ayuda a listar los permisos de nuestros usuarios. **Para limitar el número de procesos que nuestros usuarios pueden realizar ejecutamos** `ulimit -u max-numero-procesos`. Para verificar que realmente se limitoel numero de procesos entonces podemos crear un script **script.sh**

```sh
#!/bin/bash
#Imprime en pantalla 'Hola'
echo 'Hola'
#Llama el comando anterior varias veces como un loop
$0
```
- La consola ejecuta **script.sh** hasta que se han cumplido la cantidad maxima de procesos. 
- A continuacion algunos de los flags de `ulimit`
> ```sh
> ulimit -n ⟶ It will display number of open files limit
ulimit -c ⟶ It display the size of core file
umilit -u ⟶ It will display the maximum user process limit for the logged in
user.
ulimit -f ⟶ It will display the maximum file size that the user can have.
umilit -m ⟶ It will display the maximum memory size for logged in user.
ulimit -v ⟶ It will display the maximum memory size limit 
> ```

### Autenticación de clientes y servidores sobre SSH
---
**SSH** es un protocolo que nos ayuda a conectarnos a nuestros servidores desde nuestras máquinas para administrarlos de forma remota. ❌**NO** es muy recomendado usar otros protocolos como Telnet, ya que son inseguros y están deprecados.

Con el comando ``ssh-keygen`` podemos generar llaves públicas y privadas en nuestros sistemas, de esta forma podremos conectarnos a servidores remotos o, si es el caso, permitir que otras personas se conecten a nuestra máquina. Para comprobar que la llave fue creada listamos `ls .ssh` alli debe aparacer tanto `id_rsa.pub` **Llave Publica** como `id_rsa` **Lave Privada**

- Para conectarnos desde nuestra máquina a un servidor remoto debemos:

- Ejecutar el comando `ssh-copy-id -i ubicación-llave-pública nombre-usuario@dirección-IP-servidor-remoto` y escribir nuestra `contraseña` para enviar nuestra llave pública al servidor. Asi `ssh-copy-id -i ~/.ssh/id_rsa.pub danmuner@192.168.xx.xx`

- Usar el comando `ssh danmuner@192.168.xx.xx` para conectarnos al servidor sin necesidad de escribir contraseñas.

- `vim /etc/ssh/sshd_config` Asi podemos modificar otras opciones de ssh 

Las configuraciones de SSH se encuentran en el archivo `/etc/ssh/sshd_config` como 
```ssh
# To disable tunneled clear text passwords, change to no here!
PasswordAuthentication no
#PermitEmptyPasswords no
```
> Ahora siempre que realizemos cambios sera necesario reiniciar `ssh`
> `sudo systemctl stop ssh` para deneter ssh
> `sudo systemctl start ssh` para iniciar ssh.

- También podemos usar el comando `ssh -vvvv danmuner@192.168.xx.xx` para ver la información o los errores de nuestra conexión con el servidor.

### Configurando DNS con bind
---
**Contexto histórico de los DNS**
En Junio de 1983 alrededor de 70 sitios estuvieron conectados a la red de ciencias de la computación, permitiendo de esta forma la unión de algunos establecimientos gubernamentales, científicos y universitarios para que pudieran compartir datos, por esta razón los archivos de host no eran suficientes para hacer la replicación entre sitios, por este motivo en noviembre de 1983 se publicó el RFC 882 que define el servicio de nombre de dominios. Paso siguiente en octubre de 1984 se crearon 7 TLDs (Dominios de nivel superior) o también conocidos como dominios de propósito general .arpa, .com, .org, .edu, .gov, .mil y la letra de los países respetando su código ISO [1]

**Instalación de Bind**
1. Para realizar el proceso de instalación de `bind` lo primero que realizaremos es verificar que bind se encuentre en los repositorios, para esto utilizaremos otro gestor de paquetes llamado `aptitude`, para instalarlo simplemente diremos 
 - `sudo apt install aptitude`.

2. Con aptitude instalado buscaremos el paquete `bind` utilizando para ellos una expresión regular.
 - `aptitude search "?name(^bind)"`

3. Instalamos bind. El proceso de instalación se realiza con `sudo apt install -y bind9` , la opción `-y` es para confirmar que si queremos instalar el paquete en mención.

4. Validamos la instalación con `netstat` y verificaremos que el puerto 53 este escuchando asi `sudo netstat -ltnp`. Sabemos que es el puerto 53 xxx.xxx.xxx.xxx:53 porque despues de los dos puntos aparece el numero del puerto.
5. Para realizar consultas al DNS podemos utilizar varias herramientas, entre ellas `dig`, que me permiten conocer más al respecto del nombre de dominio, para ello usaremos el dominio `platzi.com` y lo buscaremos en la máquina `local`, es decir `127.0.0.1`.

- `dig www.platzi.com @127.0.0.1` Nos interesa la parte de respuesta y la de tiempo de ejecución para validar que la respuesta se dio desde localhost.

6. Paso siguiente después de instalarlo es verificar todo lo que viene incluido dentro del paquete como lo son los archivos de configuración manuales entre otros, para esto podemos hacer uso de `dpkg -L bind9`.

7. El archivo de configuración principal será `/etc/bind/named.conf`, también tenemos el archivo `/etc/bind/rndc.key` en este se puede configurar la clave que se puede usar para obtener acceso al nombre de dominio.
8. Podemos ver la versión de bind de dos formas `named -v` o una versión extendida con `named -V`

9. Si deseas adquirir tu DNS, tienes varias opciones:

   - Namecheap
   - Hover
   - Route 53

10. Como cliente tienes varias opciones para configurar tus **DNS**, lo que influirá directamente en tu velocidad, seguridad o reputación. Para eso te daré algunas opciones, el orden no significa nada:

  - OpenDns
  - Google DNS
  - Neustar UltraDNS
  - Cloudflare
  - quad
  - Public DNS
  - Yandex DNS
  
11. Existe una herramienta que nos permite seleccionar cuál será el **DNS** que debemos utilizar basados en nuestra ubicación y nuestras búsquedas, se llama `namebench`. Para ello sólo basta instalarlo y ejecutarlo en la máquina cliente y con esto obtendremos sugerencias al respecto. [namebanch](https://tools.ietf.org/html/rfc920)

### Arranque detención y recarga de servicios
---
- El comando `systemctl` nos permite manejar los procesos de nuestro sistema operativo `Gestor de Arranque`. Nuestros servicios pueden estar activos (es decir, encendidos) o inactivos (apagados). También podemos configurar si están habilitados o deshabilitados para correr automáticamente con el arranque del sistema. E.g. `sudo systemctl status apache2` dependiento el estado el servcio se va o no a iniciar junto con el sistema operativo. 
    - `stop`
    - `start`
    - `restart`
    - `enable`
    - `disable`
    - `status`
    - `list-units -t service --all` Lista unidaes de todos los servicios

- `sudo systemctl status nombre-servicio`: ver el estado de nuestros servicios.
- `sudo systemctl (enable, disable) nombre-servicio`: activar o desactivar el arranque automático de nuestros servicios.
- `sudo systemctl (start, stop, restart) nombre-servicio`: encender, apagar o reiniciar los servicios.
- `sudo systemctl list-units -t service --all`: ver todos los servicios del sistema.
- El comando `journalctl` nos permite ver los logs de los procesos de nuestro sistema operativo. Recuerda que todos ellos están almacenados en la carpeta `/var/log/`.

- `sudo journalctl -fu nombre-servicio`: ver los logs de nuestros servicios y hacer un seguimiento.
- `sudo journalctl --disk-usage`: ver la cantidad de espacio que ocupan nuestros logs.
- `sudo journalctl --list-boots`: muestra la lista de booteos de la computadora.
- `sudo journalctl -p (critic, info, warning, error)`: filtrar los logs por el tipo de mensaje.
- `sudo journalctl -o json`: ver los logs en formato JSON.

### NGINX y Apache en Ubuntu server
---
**NGINX** y **Apache** son **softwares** para montar servidores web, puedes realizar la instalación de ambos en el sistema operativo, teniendo como base que pueden estar corriendo al mismo tiempo, **siempre y cuando no estén a la espera de conexiones por el mismo puerto**.

- Para validar los puertos que tienen un proceso activo usamos:

`sudo netstat -tulpn`

- Podríamos tener una infraestructura donde **NGINX** puede servir como proxy y **Apache** como servidor web.

![nginx-apache](https://user-images.githubusercontent.com/60556632/161886398-08ae9909-c2a3-4e43-ad65-fe5de4d8c2ff.png)

- Si revisamos las estadísticas podemos ver que **Apache** aún es el líder del mercado en servidores web, seguido por **NGINX**, es por esta razón que veremos la instalación y configuración de ambos.
![nginx-vs-apache](https://user-images.githubusercontent.com/60556632/161886566-cabd0b68-4c16-408f-a969-a72bba60f682.png)
 
 - Existen en internet artículos interesantes de comparación entre ambos y el caso de uso de cada uno de ellos.
    - [Apache-vs-Nginx](https://www.digitalocean.com/community/tutorials/apache-vs-nginx-practical-considerations) y 
    - [What-is-Nginx](https://www.nginx.com/faq/what-is-nginx-how-different-is-it-from-e-g-apache/)

#### Proceso de instalación.

1. Installacion

**Apache**
Ejecuta el siguiente comando
- `sudo apt install apache2`

**NGINX**
Ejecuta el siguiente comando

`sudo apt install nginx nginx-extras`

2. Para verificar si los servicios está corriendon se debe ejecutar los siguientes comandos:
   - `systemctl status apache2`
   - `systemctl status nginx`

3. Si se siguió el orden de instalación, **NGINX** no debe estar ejecutándose, pues por defecto intentará levantarse en el puerto 80, el cual ya se encuentra ocupado por **Apache**, para ello cambiaremos el puerto de Apache al puerto alterno http 8080.

   - `sudo nano /etc/apache2/ports.conf`
   - A continuación tenemos que cambiar el puerto al _8080_, para esto se debe cambiar la instrucción `Listen _8080_` dentro del documento `ports.conf`.
   - Después abrimos nuestro archivo de configuración de *Apache* `sudo nano /etc/apache2/sites-available/000-default.conf` y cambiamos el virtualhost a `8080 <VirtualHost *:8080>`
4. Después realizamos el proceso de detener **apache2** y volverlo a encender, con los siguientes comandos.
   - `sudo systemctl restart apache2`
   - `systemctl status apache2`
   - `systemctl status nginx`
 
- Ambos sitios deberían estar activos y en ejecución.
Paso siguiente, dirígete al archivo de configuración de **NGINX** donde te asegurarás que exista una directiva en el location llamada `proxy_pass` que contenga lo siguiente: `proxy_pass http://127.0.0.1:8080`

![Location-Proxy](https://user-images.githubusercontent.com/60556632/161887494-bc55c6c7-f27e-4971-bc8b-ede07e564bbb.png)

5. Si por alguna razón el servidor **Apache** no se encuentra en la misma máquina, debemos cambiar la dirección IP y el puerto respectivo.

    - Apache tiene un comando para activar sitios que es `a2ensite` que recibe como parámetro el archivo de configuración definido en `/etc/apache2/sites-available`. **NGINX** no cuenta con este comando, motivo por el cual se tiene un enlace __blando__, es decir, cuando creemos un archivo de configuración en `/etc/nginx/sites-available` debemos ejecutar `sudo ln -s /etc/nginx/sites-available/configuracion_nginx /etc/nginx/sites-enabled/`

- **Apache** también me permite deshabilitar sitios y agregar módulos

`sudo a2dissite 000-default`

`sudo a2enmod rewrite headers env dir mime`

6. Si queremos activar `letsecrypt` en **NGINX**, debemos agregar una línea en el `.htaccess` en la ruta `/var/www/html/nombre_host/.htaccess`. La linea es `SetEnvIf X-Forwarded-Proto https`

![letsecrypt](https://user-images.githubusercontent.com/60556632/161887875-11e3ab43-ccb4-4a1f-9736-353058fff9ac.png)

7. **Conclusión**
Antes de realizar la elección de uno de los dos, deberías mirar el tipo de proyecto en el que estás trabajando y que se acople mejor a tus necesidades, es un proceso de evaluación y prueba en cada uno de los aspectos que esperamos como administradores de sistemas.
Existen múltiples diferencias entre ambos proyectos, que tienen impacto real en el rendimiento y tiempo de configuración para lograr que el servicio quede funcionando perfectamente. Algunos prefieren NGINX por la sintaxis de configuración, otros eligen basado en las estadísticas presentadas y otros por simple experiencia con trabajos anteriores. Yo te recomiendo probar ambos y elegir según el proyecto, o quizás puedes usarlos ambos y sacar lo mejor de cada uno.

### Instalación y configuración de NGINX
---
1. `sudo apt search "nginx$"` Verificamos si nginx esta en nuestro repo.
2. `sudo apt update && sudo apt install nginx` Actualizamos e Instalamos
  - Si revisamos los logs por el comando anterior es muy probable que despues de haber instalado **Apache** diaga algo como `Not attempting to start NGINX, port 80 is already in use`

3. Si no supieramos que se esta ejecutando en el puero `80`, con el comando `sudo netstat -tulpn` sabremos que puertos se estan utilisando.
4. Entonces primero apagamos **Apache**  `sudo systemctl stop apache2` luego iniciamos **NGINX** `sudo systemctl start nginx` y verificamos nuevamente el puerto `sudo netstat -tulpn` donde ahora **NGINX** debe estar usando el puerto 80.
---
**Archivos de configuracion de NGINX**
1. En Linux todos los archivos de configuracion se encuentran en la carpeta `etc`, en este caso `ls etc/nginx` donde tendremos los siguntes archivos:

```sh
conf.d          koi-win            nginx.conf       sites-enabled
fastcgi.conf    mime.types         proxy_params     snippets
fastcgi_params  modules-available  scgi_params      uwsgi_params
koi-utf    modules-enabled    sites-available  win-utf
```
Los archivos mas usados son los siguientes:

   a. `nginx.conf` Aqui podemos ver la cantidad de procesos que vamos a lanzar, cual es el Process ID, y el Usuario con el que se ejecuta nginx `www-data`.   
   b. `sites-available/default` Nos muestra toda la configuracion del servidor, aqui podemos activar PHP, el puerto.  
   c. `curl -I localhost` Head de la respuesta del Servidor.  
   d. `sites-enabled` Aquellos sitios activos en el momento.  

### ¿Qué es NGINX Amplify?
---

**NGINX Amplify** es una herramienta SaaS que permite realizar el monitoreo de NGINX y NGINX Plus. Los factores que permite monitorear son:
1. El rendimiento
2. Configuraciones con análisis estático
3. Parámetros del sistema operativo, así como PHP-FPM
4. Bases de datos y otros componentes. 

Nginx Amplify es de fácil configuración y llevar control de nuestros servidores es agradable por los tableros de administración que posee.

Con **NGINX [Amplify](https://www.nginx.com/products/nginx-amplify/)** podrás recolectar más de 100 métricas de NGINX y el sistema operativo. Amplify analiza los archivos de configuración propios del servidor, detecta configuraciones incorrectas y da recomendaciones de seguridad, también permite crear notificaciones que pueden ser enviadas por correo o a un canal de Slack con un simple clic.

Los tableros de mando de [Amplify](https://www.nginx.com/products/nginx-amplify/) sirven para verificar la disponibilidad del sitio e identificar situaciones anómalas en diferentes periodos de tiempo. Otra característica a destacar es que NGINX Amplify te permite administrar varios sitios, direcciones IP y un nombre para identificarlo.

### NGINX Amplify: Instalación y configuración de un servidor para producción
---
1. `sudo apt install pythonx.x` Instalamos python
2. Movernos a la carpeta de Nginx `cd /etc/nginx`
3. Modificar el archivo conf.d de la siguiente manera
```sh
sudo cat > conf.d/stub_status.conf
server{
	listen 127.0.0.1:80;
	server_name 127.0.0.1;
	location /nginx_status {
		stub_status on;
		allow 127.0.0.1;
		deny all;
	}
}
```
4. Matar el proceso de Nginx `sudo kill -HUP `cat /var/run/nginx.pid`
5. Reiniciar y habilitar Nginx `sudo systemctl restart nginx && systemctl enable nginx`
6. Logearnos en el sitio web de Nginx Amplify y seguir las instrucciones de instalación: [nginx](https://amplify.nginx.com), Iniciar el servicio de Nginx Amplify `service amplify-agent start`.

![login-nginx](https://user-images.githubusercontent.com/60556632/162007565-5cc22683-8510-4491-b301-45e32fb6f05f.png)

7. Se puede instalar en Ubuntu 20 de la siguiente manera: Después de darle los permisos de ejecución al archivo `install.sh` de abre con `vi o nano`
se edita la linea que dice `packages_url=` se reemplaza la url de las comillas por esta `https://packages.amplify.nginx.com/py3/`
Se ejecuta como dice en Nginx Amplify `API_KEY=#### sh ./install.sh`
![API_KEY](https://user-images.githubusercontent.com/60556632/162007896-926ed76b-73d5-4acd-a984-41ad55bb94f4.png)
8. Reiniciar Nginx `sudo systemctl restart nginx`

### Monitoreo de MySQL con Nagios
---
1. `sudo apt search "mysql-server$" buscamos si el paquete se encuentra en el repo de Ubuntu. Si la version que necesitamos no es encuentra en el repo entonces todo se debe hacer manual.
2. Instalación de MySQL `sudo apt install mysql-server`
3. Si perdemos acceso a mysql, entonces podemos ingresar a `cd /etc/mysql` donde encontraremos los siguientes archivos.
![etc/mysql-server](https://user-images.githubusercontent.com/60556632/162011767-f9e6cca0-9af8-48ea-9118-a1ab508f8b7c.png)
Abrimos `vim debian.cnf` alli encontraremos la informacion del usuario.
![debian-cnf](https://user-images.githubusercontent.com/60556632/162012668-8de120c2-4584-4948-bea2-fe6772dd113d.png)
3. Ahora si podemos conectarnos a la base de datos MySQL asi `mysql -u debian-sys-maint -p`, enter y luego colcamos el password `QEOJgXWSVq9ogcDw` 
4. Salimos de mysql `exit` luego Asegurar el server de la base de datos `sudo mysql_secure_installation` aqui nos aseguramos de usar un password fuerte, luego verificar que Apache esté funcionando `sudo systemctl status apache2`
5. Activar módulos **rewrite** y **cgi** `sudo a2enmod rewrite cgi`, asi nagios va a funcionar apropiadamente. Reiniciar Apache `sudo systemctl restart apache2`.
6.  Crear un usuario para Nagios `sudo htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin` luego reiniciamos apache `sudo systemctl restart apache2`, he iniciamos nagios `sudo systemctl start nagios`
7.  Entrar a Nagios en nuestro navegador web, escribiendo como dirección: `127.0.0.1:8080/nagios` luego de haber hecho log in con nagiosadmin, los servios aun deben aparecer detenidos solo si no hemos instalado los plugins de nagios de lo contrario deben estar en verde.
8. Nagios a diferencia de otros paquetes, tiene sus archivos de configuracion en `sudo /usr/local/nagios/bin/nagios -v /usr/loacl/nagios/etc/nagios.cfg`

### Configuración de Nagios
---
1. Nos conectamos a mysql `sudo mysql`
2. Crear un usuario 
```sql
GRANT SELECT ON *.* TO 'nagios'@'localhost' IDENTIFIED BY 'nagiosplatziS14*'; 
-- (nagiosplatziS14*) es un Password no un usuario.
FLUSH PRIVILEGES; 
```
3. Configurar Nagios
```sh
sudo vim /usr/local/nagios/etc/nagios.cfg
#Ya dentro del archivo, agregar la siguiente linea:
cfg_file=/usr/local/nagios/etc/objects/mysqlmonitoring.cfg
```
4. Crear comandos para hacer uso de Nagios
```sh
sudo vim /usr/local/nagios/etc/objects/commands.cfg
#Ya dentro del archivo, agregar las siguientes líneas:
define command {
	command_name check_mysql_health
	command_line $USER1$/check_mysql_health -H $ARG4$ --username $ARG1$ --password $ARG2$ --port $ARG5$  --mode $ARG3$
#ARG Se refiere a la posicion de los datos a ingresar como --username en la posicion 1 luego password en la posicion 2,etc.
}
```
5. Crear el archivo que nombrarmos en la configuración en el archivo `nagios.cfg`
```sh
#El archivo debe estar vacio.v 
sudo vim /usr/local/nagios/etc/objects/mysqlmonitoring.cfg
#Ya en el archivo, agregar las siguientes líneas

define service {
	use local-service
	host_name localhost
	service_description MySQL connection-time
	check_command check_mysql_health!nagios!nagiosplatziS14*!connection-time!127.0.0.1!3306!
}
```
6. Reiniciar nagios `sudo systemctl restart nagios` si algo no funciona entonces podemos apagar y encender nagios.

### Los logs nuestros mejores amigos
---
1. `find /var/log/ -name "*.log" -type f` Busca todos los `.log` en la ruta `/var/log/`

2. Comandos útiles
- find `/var/log/ -iname *.log -type f`: Muestra los archivos de log que tenemos en el sistema
- `sudo find /etc/ -mtime 10 2`: Muestra los archivos de configuración que tuvieron salidas de error en los últimos diez minutos
- `awk '{print $1}' /var/log/nginx/access.log | sort | uniq -c | sort -nr`: Muestra las IP’s que se conectaron con nuestro servidor nginx
- `awk '{print $9}' /var/log/nginx/access.log | sort | uniq -c | sort -nr`: Muestra los errores que surgieron en nuestro servidor nginx.

### Otros servicios de logs
---
1. Un servidor puede llegar a registrar millones de líneas de datos en un log. Para facilitar el monitoreo y mantenimiento podemos usar herramientas o tecnologías que nos permitan tomar esta información sin procesar y convertirla en visualizaciones fáciles de consumir y entender.

2. El primer paso para seleccionar las herramientas que usaremos. Lo primero es tener una base de conocimiento que nos identifique el servidor en circunstancias normales y de esta forma con la ayuda de estas herramientas detectar preocupaciones o incluso tendencias con una sola mirada.

Algunas herramientas que podemos tener en distribuciones Linux son:

3. **[Collectd](https://collectd.org/wiki/index.php/Table_of_Plugins)**
Es un demonio que recopila datos de rendimiento, y junto con la herramienta collectd web, es capaz de generar reportes que se pueden visualizar en un navegador WEB. Se puede establecer un servidor y a él conectarle un número ilimitado de clientes remotos.

4. **Nmon**
Obtener visualizaciones rápidas de mi sistema. Se instala con apt install nmon. Tiene una característica especial que me permite guardar en archivos de formato nmon que se pueden convertir en información que puede ser presentada en html con la herramienta nmonchart. `Nmon -f -s 15 -c 20`, se recolectará información por cinco minutos mostrados en incrementos de 15 segundos 20 veces.

5. **Munin**
Es una herramienta para analizar el rendimiento del servidor que contiene gráficos históricos para facilitar la identificación de problemas en el tiempo.

6. **Grafana**
Permite consultar, visualizar, alertar y ante todo entender las métricas de negocio sin importar dónde están almacenadas. Se puede crear, explorar y compartir tableros de mando con el equipo basados en el principio de la cultura orientada a los datos.

7. También podemos instalar agentes de monitoreo en los servidores, algunas opciones son [newrelic](https://newrelic.com/) y [datadoghq](https://www.datadoghq.com)/, podemos tener una prueba del servicio y analizar el rendimiento de nuestro servidor.
8. Cabe aclarar que también necesitará algún sistema de alarma automatizado que nos envíe alertas de forma proactiva cuando las cosas no estén funcionando bien.

### Las bases de bash
---
Como administradores de bases de datos Linux debemos saber automatizar tareas, es por esta razon que utilizaremos pyscripts.

1. **¿Qué es Bash?** Es una **shell** de **UNIX** y el intérprete de comandos por defecto en la mayoría de distribuciónes GNU/Linux. Se pueden crear scripts, los cuales por convención terminan con la extensión `.sh`
2. Creamos un script y debe tener la siguiente cabecera para el caso de bash `#!bin/bash` luego si colocamos el codigo. Ejecutamos asi `./script.sh`. Aprender a programar en bash es muy necesario para el dia a dia de los administradores de servidores Linux.

### Variables de Entorno
---
- `env`: Muestra las variables del sistema operativo
- `$PATH`: Guarda las rutas donde se ubican los archivos binarios que pueden ejecutarse directamente en la consola
- Verificar la cantidad de espacio en el S.O.
```sh
#!/bin/bash
# Verificar la cantidad de espacio en el S.O
# Desarrollado por Jhon Edison
CWD=$(pwd)
FECHA=$(date +"%F%T")
echo $FECHA
df -h | grep /dev > uso_disco_"$FECHA".txt
df -h | grep /dev/sda2 >> uso_disco_"$FECHA".txt
echo "Se ha generado un archivo en la ubicación $CWD"
```

### Automatizando tareas desde la terminal
---
En esta clase vamos a realizar un script que nos permita realizar una copia de seguridad de una base de datos **MYSQL**.  Leer [Crontab en Linux](https://geekflare.com/es/crontab-linux-with-real-time-examples-and-tools/) para automatizar otras tareas en la consola.



```sh
#!/bin/bash
# Description: Shell script to restore a backup from Mysql
#
# Desarrollado: Para platzi by Jhon Edison Castro @edisoncast
PATH=/usr/local/sbin:/usr/local/bin:/sbin:bin:/usr/sbin:/usr/bin
#La variable PATH describe las posibles rutas desde donde se podria ejecutar. 

#Set -e Sirve para detener el script en caso de que el programa falle.
set -e

readonly SCRIPT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"

readonly SCRIPT_NAME="$(basename "$0")"

run
restore_backup

function assert_is_installed {
  local readonly name="$1"

  if [[ ! $(command -v ${name}) ]]; then
    log_error "The binary '$name' is required by this script but is not installed or in the system's PATH."
    exit 1
  fi
}

function log_error {
  local readonly message="$1"
  log "ERROR" "$message"
}

function log {
  local readonly level="$1"
  local readonly message="$2"
  local readonly timestamp=$(date +"%Y-%m-%d %H:%M:%S")
  >&2 echo -e "${timestamp} [${level}] [$SCRIPT_NAME] ${message}"
}

function run {
  assert_is_installed "mysql"
  assert_is_installed "mysqldump"
  assert_is_installed "gzip"
  assert_is_installed "aws"
}

function restore_backup {
    local BAK="$(echo $HOME/restore)"
    local MYSQL="$(which mysql)"
    local GZIP="$(which gzip)"
    local NOW=$(date +"%d-%m-%Y")
    local BUCKET="xxxxx"
    local DATABASE="xxxxxxx"
    USER="xxxxxx"
    PASS="xxxxxx"
    HOST="xxxxxxxx"
    DATABASE="xxxxx"

    [ ! -d "$BAK" ] && mkdir -p "$BAK"

    FILE=$BAK/$DATABASE.$NOW-$(date +"%T").gz

    local SECONDS=0

    aws configure set s3.signature_version s3v4
    aws s3 sync "s3://$BUCKET" $BAK --exact-timestamps

    cd $BAK

    local FILE="$(find . -iname "*.gz" -type f -print0 | xargs --no-run-if-empty -0 stat -c "%y %n" | sort -r | head -n 1 |awk '{print $4}')"

    gunzip < $FILE | $MYSQL -u $USER -h $HOST -p$PASS $DATABASE

    duration=$SECONDS
    echo "$(($duration / 60)) minutes and $(($duration % 60)) seconds elapsed."
}
```
**Explicacion Víctor Macedo Becerril `estudiante platzi`**
1. El objetivo del script es hacer un backup de una base de datos, para ello primero se debe verificar que estén instalados ciertos paquetes en el sistema operativo es lo que se ve en esta clase. Antes de continuar es importante saber la definición de funciones en programación. Una vez sabiendo esto, empezamos el análisis del código:

- El profesor empezó con el comando

- `set -e` simplemente para detener la ejecución del script por si hay alguna falla.

- Después declaró dos variables de solo lectura. Estas son como variables **globales**, es decir, pueden llamarse aún estando dentro de funciones.

- Después ejecuta dos funciones **run** y **make_backup**, estas dos funciones son declaradas más abajo en realidad en esta clase solo se ve la función **run**.

- La función **run** ejecuta otra función `assert_is_insatalled`, la cual recibe como parámetro los nombres de paquetes que la función `assert_is_insatalled` se va a encargar de preguntar si están instalados.

- La función `assert_is_insatalled` inicia con la declaración de una variable **name**, la cual lee el primer argumento `$1` que recibe la función `assert_is_insatalled` que es el nombre del paquete a averiguar si está instalado. Para saber si está instalado el paquete solo hace un condicional cuya condición es si el comando `command -v "paquete"`, da respuesta, si no da respuesta el comando, significa que no está instalado y ejecuta la función `log_error` con argumento `The binario …` y después de eso marca un error con el comando:

`exit 1`

- La función `log_error` define otra variable que lee el argumento recibido y llama a otra función `log` con dos argumentos.

- La función `log` lee los dos argumentos recibidos y crea otra variable con la fecha de ese momento, para después hacer una salida `echo` especificando que es un error `>&2`. **Errores1 Errores2**

- En clonclusión se crearon las funciones `run` y `assert_is_installed` para saber si ciertos paquetes que se usarán están insatalados, y las funciones `log_error` y `log` para el manejo de errores.

### Crontab
---
Para ejecutar nuestra tarea de copia de seguridad debemos hacer uso de cron, el cual es un administrador regular de procesos en segundo plano que comprueba si existen tareas para ejecutar, teniendo en cuenta la hora del sistema.  

Las configuraciones de las tareas a ejecutar se almacenan en el archivo crontab que puede ser editado con el comando `crontab -e`, si requerimos listar las tareas que tenemos configuradas ejecutamos `crontab -l`.  

A continuación te muestro lo que se imprime en la pantalla al correr el comando `crontab -e`.

![crontab](https://user-images.githubusercontent.com/60556632/162059566-fe86b989-5e46-4eb2-b41b-d84d75d47196.png)

- Para establecer una tarea automatizada con cron se debe seguir un formato específico para definir una tarea como se muestra a continuación:

![formato-específico](https://user-images.githubusercontent.com/60556632/162059658-f5761587-9cc5-40ed-8408-64ab2f3f82d4.png)

- Lo siguiente sería definir la periodicidad de nuestro cron, para ello podemos hacer pruebas en el sitio [crontab](https://crontab.guru). Nosotros queremos que nuestra copia se ejecute todos los días a las 03:15 de la mañana, pues es el momento donde menos tráfico tenemos en nuestra base de datos.

### Entendiendo la gestión de vulnerabilidades [CVE-2017-16995](https://www.incibe-cert.es/alerta-temprana/vulnerabilidades/cve-2017-16995)
---
**Malas prácticas**

1. No desactivar el usuario root
2. Realizar un login con usuario y password (sin ssh)
3. No validar la versión de software usada
4. Utilizar comandos r* o telnet
5. No identificar los servicios y puertos abiertos en el S.O
6. No gestionar correctamente los permisos de los usuarios.  


**Buenas prácticas**

1. Verificar las actualizaciones de seguridad y realizar la instalación de las mismas.

- CentOS `yum check-update --security` y `yum update security`
- Ubuntu `apt update` y `apt upgrade`

**Recuerda que la seguridad informática no es un producto, sino un proceso constante**.

### ¿Qué es una superficie de ataque? Principio del menor privilegio
---

La **Superficie de Ataque** es el conjunto de vulnerabilidades o datos conocidos que pueden ser explotados por un atacante informático. Cada servicio de nuestras aplicaciones es un nuevo punto de entrada a nuestra red. No solo debemos proteger nuestros servidores, también debemos proteger todos los servicios que corren en él.

**Lynis** es una herramienta que analiza nuestros servidores y para darnos algunas recomendaciones. La estudiaremos más a fondo en una próxima clase. También existen frameworks o manuales como **[OWASP](https://owasp.org/)** que nos explican las características de aplicaciones web vulnerables y cómo programarlas de forma segura.

### El [firewall](https://www.youtube.com/watch?v=Dj5AJzw4HlI) y sus reglas
---
1. Los Firewalls son herramientas que monitorean el tráfico de nuestras redes para identificar amenazas e impedir que afecten nuestro sistema.

2. Recuerda que la seguridad informática es un proceso constante, así que ninguna herramienta incluyendo el **`firewall`** puede garantizarnos seguridad absoluta.

3. En Ubuntu Server podemos usar **ufw** _Uncomplicated Firewall_ para crear algunas reglas, verificar los puertos que tenemos abiertos y realizar una protección básica de nuestro sistema:

- `sudo ufw (enable, reset, status)`: activar, desactivar o ver el estado y reglas de nuestro firewall.
- `sudo ufw allow numero-puerto`: permitir el acceso por medio de un puerto específico. Recuerda que el puerto 22 es por donde trabajamos con SSH.
- `sudo ufw status numbered`: ver el número de nuestras reglas.
- `sudo ufw delete numero-regla`: borrar alguna de nuestras reglas.
- `sudo ufw allow from numero-ip proto tcp to any port numero-puerto`: restringir el acceso de un servicio por alguno de sus puertos a solo un número limitado de IPs específicas.
- `sudo ufw app list`: Para ver las apps permitidas

**Recomendación**
> Abrir al público únicamente el puerto `80 http`, `443 https`. 
> Para un conjunto de IP’s específicas, habilitar el puerto `22 ssh`.

### Escaneo de puertos con NMAP y NIKTO desde [Kali Linux](https://platzi.com/clases/1583-ethical-hacking/19725-instalacion-del-entorno-de-pruebas-kali-linux/)
---
**Comandos**
- `nmap -sV -sC -0 -oA nombre_de_archivo dirección_ip_del_servidor`: Realiza un mapeo de la red
- `nikto -h ip_del_host -o nombre_de_archivo`: Escanea vulnerabilidades en un servidor.

- Uso de [nmap](nmap.org):

> - `-sV` Service/version info (Información acerca de los puertos abiertos).
> - `-sC` Permite utilizar el motor de scripts.
> - `-O` Habilita la detección de OS.
> - `-p-` Escanea todos los puertos.
> - `-oA` Envía la salida a un archivo

### Lynis: Herramientas de auditoria de seguridad en Linux
---
**[Lynis](https://cisofy.com/documentation/lynis/)**: Herramientas de auditoria de seguridad en Linux
- `sudo lynis audit system`: Realiza un escaneo del sistema operativo, mostrándonos sugerencias y el estado de peligro de ciertos detalles en nuestra distribución.

- [Aprende a auditar-seguridad-Linux](https://www.welivesecurity.com/la-es/2014/09/01/tutorial-de-lynis-aprende-auditar-seguridad-linux/)

### Configuración de Node.js en un ambiente productivo
---
0. Que es [Node.js](https://www.luisllamas.es/que-es-node-js/)
1. `git clone https://github.com/edisoncast/linux-platzi`: Clonar el repositorio necesario para realizar la clase.
2. `sudo apt install nodejs npm`: Instalar Node.js y npm.
3. `curl -sL https://deb.nodesource.com/setup_10.x -o node_setup.sh`: Posicionados en el home, descargar Node 10.
4. `sudo bash node_setup.sh`: Instalar Node 10
5. `sudo apt install gcc g++ make`: Instalar gcc, g++ y make
6. `sudo apt install -y nodejs`: Finalizar el proceso de instalación de la versión 10 de Node.
7. `sudo adduser nodejs`: Agregar el usuario nodejs si todavía no lo creaste.
8. `node server.js`: En la carpeta de linux-platzi, ejecutar el archivo server.js.
9. Crear un archivo de configuración para el servicio de Node.

```sh
sudo vim /lib/systemd/system/platzi@.service

# Una vez creado el archivo, llenarlo con la siguiente información

[Unit]
Description=Balanceo de carga para Platzi
Documentation=https://github.com/edisoncast/linux-platzi
After=network.target

[Service]
Enviroment=PORT=%i
Type=simple
User=nodejs
WorkingDirectory=/home/nodejs/linux-platzi
ExecStart=/usr/bin/node /home/nodejs/linux-platzi/server.js
Restart-on=failure

[Install]
WantedBy=multi-user.target
```
- Ver lectura sobre [Anatomía de un archivo de configuración de systemd](https://www.digitalocean.com/community/tutorials/understanding-systemd-units-and-unit-files).

### Configuración de NGINX para la aplicación de Node.js
---

1. Cambiar el usuario a nodejs `sudo su - nodejs`.
2. Clonar el repositorio necesario para la clase `git clone https://github.com/edisoncast/linux-platzi`.
3. > Cambiar el nombre a la carpeta de linux-platzi a `server`.
   > Corregir los errores en el archivo de configuración del servicio en `/lib/systemd/system/platzi@.service`.
   > Iniciar el servicio debemos estar en la carpeta `/server/configuracion_servidor/bash`.
   > `./enable.sh`
   > ./start.sh
 4. Iniciar el servicio de Nginx Apagar antes Apache si es necesario `sudo systemctl start nginx`.
 5. Una vez en la carpeta `/etc/nginx/sites-available/` eliminar el contenido de la configuración de Nginx `sudo truncate -s0 default`.
 6.Editar el archivo de configuración.
 
 ```sh
 sudo vim default

# Una vez en el archivo, escribir lo siguiente

server  {
	listen 80 default_server;
	listen [::]:80 default_server;
	
	server_name _;
	
	location / {
		proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
		proxy_set_header Host $host;
		proxy_http_version 1.1;
		proxy_pass http://backend;
	}
}

upstream backend {
	server 127.0.0.1:3000;
	server 127.0.0.1:3001;
	server 127.0.0.1:3002;
	server 127.0.0.1:3003;
}
```
7. Validamos que la configuración establecida fue correcta `sudo nginx -t`
8. Reiniciamos nginx `sudo systemctl restart nginx`
9. Probamos todo haciendo un `curl` a localhost `curl localhost`.
10. Para que nginx pueda detectar los cambios, hay que **publicar** los cambios hechos en la carpeta `sites-enabled`, y la forma de hacer es reescribiendo el enlace simbólico, para que esto se pueda hacer, se debe eliminar primero el enlace simbólico previo creado: `sudo rm /etc/nginx/sites-enabled/default`

### Lo que aprendiste sobre servidores linux - Concluciones
---

Aprendimos a instalar paquetes desde diferentes distribuciones de Linux, utilizar comandos básicos, manejar usuarios y permisos, proteger nuestros servidores de diferentes vulnerabilidades, administrar procesos y servicios, escribir scripts en Bash para automatizar tareas, entre otras.

Te recomendamos continuar tu ruta de aprendizaje profesional con los siguientes cursos:

- [Curso de Programación en Bash Shell](https://platzi.com/cursos/bash-shell/)
- [Curso Profesional de DevOps](https://platzi.com/cursos/devops/)
- [Carrera de Administración de Servidores y DevOps](https://platzi.com/servidores/)
- [Carrera de Amazon Web Services](https://platzi.com/aws/)
- [Carrera de Seguridad Informática](https://platzi.com/seguridad-informatica/)

### Examen Curso de Administración de Servidores Linux
1. ¿Cuál es la distribución más utilizada de Linux en servidores según w3techs? `Ubuntu Server`
2. ¿Cuáles proveedores de nube me permiten lanzar instancias de Ubuntu server y CentOS como base? `Todas las mencionadas`
3. ¿Cuánto tiempo de soporte tengo con las versiones LTS de Ubuntu? `5 años.`
4. ¿Por qué debo elegir versiones LTS en Ubuntu? `Mayor tiempo de soporte en actualizaciones de seguridad y en software.`
5.¿Cuál es el mecanismo recomendado para validar la integridad de la imagen ISO descargada en la página de CentOS? `sha256`
6. ¿Cuántos tipos de descargas puedo hacer desde la página de CentOS? ¿Cuáles son? `2: DVD y Minimal`
7. Comando utilizado para concatenar y leer archivos: `cat`
8. Comando para listar los archivos en formato largo, por orden de modificación y en orden reverso: ❌`ls -lS` Nada en el Video
9. Número de líneas por defecto que leemos con head y tail en un archivo: `10`
10. Modificador del comando tail que me permite hacer seguimiento del archivo en tiempo real:`-f`
11. Como mínimo se requiere una partición para:❌`/home` Mensionan algo de Swap.
12. Qué comando debo utilizar para usar comandos que requieren privilegios de root? `sudo`
13. Archivo que contiene los usuarios del sistema: `/etc/passwd`
14. ¿Qué comando debo ejecutar para usar el usuario nodejs? `su - nodejs`
15. ¿Cuál es el grupo en CentOS que tiene permisos de administrador? `wheel`
16. Comando que permite cambiar los permisos de un archivo: `chmod`
17. Sistema numérico utilizado para cambiar permisos de forma numérica en Linux: `Octal`
18. Si un archivo tiene el valor de permisos 400 quiere decir que: `Solo el usuario propietario puede leer el archivo.`
19. Para poder ejecutar un script en bash, necesitamos el permiso de: `Ejecución para el usuario que lo quiere correr.`
20. ¿Qué comando se puede utilizar para mostrar la información de la conexión de red actual (Dirección IP y MAC) en Ubuntu y CentOS sin instalar paquetes adicionales? `ip a`
21. ¿Cuál es el protocolo que me permite conectar a otras máquinas Linux de forma segura y ejecutar comandos en un servidor remoto? `ssh`
22. ¿Con qué comando puedo ver los paquetes instalados en una máquina Ubuntu? `dpkg -l`
23. ¿Dónde se encuentra almacenada la base de datos de rpm? `var/lib/rpm/`
24. ¿Qué comando me permite ver los procesos corriendo en el servidor? `ps`
25. ¿Qué comando me muestra la lista de procesos en background? `jobs`
26. ¿Cuál es el comando que me permite editar el archivo crontab? `crontab -e`
27. Al realizar la configuración de una base de datos, ¿cuál comando puedo utilizar para proporcionar seguridad básica en una base de datos MySQL o MariaDB? `mysql_secure_installation`
28. ¿Cuál es el nombre del proceso que controla Apache y que se maneja con systemctl? `apache2`
29. Este parámetro en NGINX depende directamente de la cantidad de CPU que tengamos en nuestro servidor: `worker_processes`
30. Después de almacenar información en una variable, ¿cuál símbolo debemos incluir para poder obtener su contenido? `./`
31. ¿Cuál operador redirige la salida de pantalla a un archivo y lo concatena al final?`>>`
32. ¿Cuál es el Firewall instalado por defecto en distribuciones Ubuntu?`ufw`
33. Comando para verificar los puertos en escucha de nuestro servidor: `netstat`
34. Parámetro en nmap que hace uso de los scripts: `-sC`
35. El reporte CVE-2017-18017 corresponde a: `Vulnerabilidad en el kernel de Linux antes de la versión 4.11, 4.9.x y antes de la versión 4.9.36`

