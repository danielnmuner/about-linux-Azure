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



