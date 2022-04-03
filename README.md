## Curso de Administración de Servidores Linux  

### Tabla de Contenidos

- [Distribuciones más utilizadas de Linux](#distribuciones-más-utilizadas-de-linux)
- [Instalación de Ubuntu Server](#instalación-de-ubuntu-server)
- [Instrucciones para instalar Rocky](#instrucciones-para-instalar-rocky)
- [Gestión del árbol de directorios](#gestión-del-árbol-de-directorios)



### **Distribuciones más utilizadas de Linux**
1. Vamos a usar dos distribuciones de Linux: Ubuntu Server en su versión 18.04 y Rocky-8.5 RedHat.
> <img src="https://static.platzi.com/media/user_upload/45009527_1925244564239156_3912908948335755264_n-61d234d0-93af-4a72-91f2-4de917b4ae5f.jpg" alt="Clouds" style="width:300px;"/>
2. Importante: Se deben instalar las versiones LTS (Long Term Support), ya que ofrecen soporte de al menos 5 años

### **Instalación de Ubuntu Server**

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

`pwd`: nos muestra nuestra ubicación actual en el árbol de directorios (Print Working Directory).  
`ls`: nos muestra el contenido de las carpetas de nuestro sistema operativo. Podemos especificar alguna ruta o, por defecto, listar el contenido de la carpeta donde estamos trabajando.    
`cd`: cambiar nuestra ubicación en el árbol de directorios (Change Directory). Usamos dos puntos (..) para referirnos al directorio padre y solo uno (.) para referirnos a nuestro directorio actual.  
`touch`: nos ayuda a crear archivos desde la terminal.  
`mkdir`: nos ayuda a crear carpetas desde la terminal.  
`cp`: nos permite duplicar archivos y carpetas.  
`mv`: cambiar el nombre de nuestros archivos y carpetas.  

