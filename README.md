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
`pwd`: nos muestra nuestra ubicación actual en el árbol de directorios (Print Working Directory).  
`ls`: nos muestra el contenido de las carpetas de nuestro sistema operativo. Podemos especificar alguna ruta o, por defecto, listar el contenido de la carpeta donde estamos trabajando.    
`cd`: cambiar nuestra ubicación en el árbol de directorios (Change Directory). Usamos dos puntos (..) para referirnos al directorio padre y solo uno (.) para referirnos a nuestro directorio actual.  
`touch`: nos ayuda a crear archivos desde la terminal.  
`mkdir`: nos ayuda a crear carpetas desde la terminal.  
`cp`: nos permite duplicar archivos y carpetas.  
`mv`: cambiar el nombre de nuestros archivos y carpetas.

### Diferencias entre LESS CAT HEAD y TAIL para lectura de archivos
---
`cat`: Muestra un archivo sin paginar.  
`less`: Muestra un archivo paginado. Pulsando “/” y escribiendo una palabra, puedo buscar las coincidencias de la misma en el archivo. Con la tecla “n” me muevo entre coincidencias hacia adelante, y con `shift + n` me muevo entre coincidencias hacia atras. Con espacio cambio de página.  
`tail`: Muestra las últimas 10 líneas de un archivo específico. Con la opción `-n` puedo modificar la cantidad de líneas que veo. Con la opción -f puedo poner los cambios en escucha.  
`head`: Muestra las primeras 10 lineas de un archivo específico. Con la opción `-n` puedo modificar la cantidad de líneas que veo.
`man`: Muestra ayuda sobre comandos.  

### Interacción con archivos y permisos
---
- Con el comando `ls -l` podemos observar la lista de archivos de nuestro directorio actual con información un poco más detallada. El primer campo nos indica los diferentes permisos para cada archivo o directorio. Por ejemplo: `-rwxrw-r--`.

- El primer carácter nos indica si tenemos un archivo (-), enlace simbólico (l) o directorio (d).

- Los siguientes caracteres se dividen en grupos de 3: lectura **r**, escritura **w** y ejecución **x**. El primer grupo son los permisos del usuario que creó ese archivo, el segundo para el grupo al que pertenece este usuario y el tercero para cualquier otro usuario de tu sistema operativo.

- Los grupos nos ayudan a darle los mismos permisos a diferentes usuarios sin necesidad de asignarlos a cada uno individualmente. Todos los usuarios que pertenezcan al grupo tendrán los mismos permisos.

- Si en vez de estas letras encuentras un guion significa que ese usuario o grupo de usuarios no tiene permiso para esa acción en particular.

Por ejemplo: `-rwxrw-r--` nos indica que trabajamos con un archivo. Todos los usuarios del sistema tienen permisos de lectura. El usuario creador y su grupo tienen permiso de escritura. Y solo el usuario creador puede ejecutar el archivo.

También podemos encontrar estos permisos como 3 números del 1 al 7. Estos números son la suma de los 3 caracteres de permisos para cada usuario o grupo.

`- = 0`
`x = 1`
`w = 2`
`r = 4`
Por lo tanto, los permisos de nuestro archivo de ejemplo serían: `7 (1+2+4) 6 (0+2+4) 4 (0+0+4)`.

Para cambiar los permisos de un archivo o directorio podemos usar el comando `chmod` + a quién queremos añadir o quitar los permisos:

El usuario propietario: `u`.
El grupo, `g`.
El resto de usuarios, `o`.
Para todos, `a`.

**Por ejemplo, para añadir permisos de ejecución a nuestro usuario propietario usamos:**

`chmod u+x nombre-del-archivo`

**También podemos cambiar al usuario propietario del archivo con el comando chown.**

`sudo chown nuevo-usuario:grupo-usuarios nombre-del-archivo`

Cambiar usuario `su username`

### Conociendo las terminales en linux
---
`chvt`: Cambia de terminal
`tty`: Muestra la terminal actual
`who`: Muestra los usuarios conectados a nuestro sistema
`w`: Hace lo mismo que el comando who pero muestra más información
`ps`: Muestra los procesos corriendo. Con los modificadores -ft y tty podemos filtrar para ver las conexiones de los usuarios
`kill`: Mata un proceso. Con el modificador -9 fuerzo el cierre del mismo

### Manejo y monitoreo de procesos y recursos del sistema
---
**Comandos**
|
`ps`: Muestra los procesos corriendo. Modificadores:

`aux`: Muestra todos los procesos
`jobs`: Al igual que el comando anterior, muestra los procesos. A diferencia de ps, es un comando interno de la terminal
`fg`: Abre un proceso que estaba pausado
`nohup`: Genera un archivo llamado “nohup.out” que muestra toda la información que produjo un proceso
`grep`: Nos ayuda a filtrar el resultado de un comando o el contenido de un archivo dependiendo de las palabras (o incluso expresión regular) que le indiquemo.  

**Lo que significa cada parametro al ejecutar el comando** `ps aux`

`USER`: usuario con el que se ejecuta el proceso
`PID`: ID del proceso
`%CPU`: porcentaje de tiempo que el proceso estuvo en ejecución desde que se inició
`%MEM`: porcentaje de memoria física utilizada
`VSZ`: memoria virtual del proceso medida en KiB
`RSS`: “resident set size”, es la cantidad de memoria física no swappeada que la tarea a utilizado (en KiB)
`TT`: terminal que controla el proceso (tty)
`STAT`: código de estado del proceso (información detallada más adelante)
`STARTED`: fecha de inicio del proceso
`TIME`: tiempo de CPU acumulado
`COMMAND`: comando con todos sus argumentos

### Monitoreo de recursos del sistema
---
`top`: Muestra la siguiente información del sistema:
load average (carga promedio): Provee una representación en números del 1 al número de procesadores que tenga nuestro servidor del uso de los mismos. Uso de la memoria, Cantidad de usuarios, Uso del CPU, Procesos, Etc.

`free`: Me muestra información sobre la memoria de mi sistema. Con el modificador -h la información es más legible para un humano
`du`: Muestra información sobre el disco duro. Con el modificador -hsc y un directorio especificado muestra el tamaño de ese directorio
`htop`: Funciona como top pero funciona de forma más intuitiva

**Comandos útiles**

`cat /proc/cpuinfo | grep "processor"`: Muestra información sobre el CPU
`sudo ps auxf | sort -nr -k 3 | head -5`: Muestra los 5 procesos que más uso hacen del CPU
`sudo ps auxf | sort -nr -k 4 | head -5`: Muestra los 5 procesos que más uso hacen de la memoria RAM

### Análisis de los parámetros de red
---
**Comandos**

`ifconfig`: Interface Configuration, muestra las tarjetas de red que tenemos y su direccionamiento específico
`ip a`: IP Address Show, muestra las direcciones IP
`hostname`: Como se identifica este equipo en la red
`route -n`: Muestra cual es el dispositivo que me permite conectarme a internet
`nslookup`: Muestra la dirección IP de un dominio determinado
`curl`: Realiza consultas a un servidor
`wget`: Permite descargar contenido de un servidor

**Comandos útiles**

`ip -4 a`: Muestra las direcciones IPv4
`ip -6 a`: Muestra las direcciones IPv6

### Administración de paquetes acorde a la distribución
---
**Ubuntu server**

Repositorios: `apt`
Extensión de paquetes: `.deb`

**Comandos:**

`dpkg -l`: Lista todos los deb instalados en la máquina
`dpkg -i paquete.deb`: Instala un paquete
`dpkg -r paquete.deb`: Desinstala un paquete
`dpkg-reconfigure paquete`: Permite configurar nuevamente un paquete
`apt install paquete`: Instala un paquete desde un repositorio
`apt search paquete`: Busca un paquete en un repositorio

**Rocky**

Repositorios: `yum`
Extensión de paquetes: `.rpm`

**Comandos:**

`rpm -qa`: Lista todos los rpm instalados en la máquina
`rpm -i paquete.rpm`: Instala un paquete
`rpm -e paquete.rpm`: Desinstala un paquete
`yum install paquete`: Instala un paquete desde un repositorio
`yum search paquete`: Busca un paquete en un repositorio

#### Distribuciones Linux
---
![image](https://user-images.githubusercontent.com/60556632/161408242-9d528580-838f-490e-b306-5dd18db629e4.png)

