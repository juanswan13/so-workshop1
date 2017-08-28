### Taller 1
**Universidad ICESI**  
**Curso:** Sistemas Operativos  
**Docente:** Daniel Barragán C.  
**Tema:** Comandos de Linux, Estructura de directorio, Virtualización  
**Correo:** daniel.barragan at correo.icesi.edu.co

**Estudiante:** Juan Camilo Swan Rada   /   **Código:** A00054620



### Objetivos
* Conocer y emplear comandos de Linux para la realización de tareas administrativas

### Prerrequisitos
* Virtualbox o WMWare
* Máquina virtual con sistema operativo CentOS7

### Descripción
El primer taller del curso sistemas operativos trata sobre el sistema operativo Linux, la estructura de sus directorios y virtualización 

### Actividades

1. Explique la función de los directorios en la raíz de sistema operativo Linux-CentOS.
Proporcione ejemplos de los archivos que se encuentran en cada directorio (explique al menos un
archivo por directorio).

| Directori   | Archivo ejemplo | Descripción del contenido del directorio   |
|------|------|------|
| /etc | /etc/shadow | Se encuentran archivos de configuración y arranque del sistema, base de datos de usuarios, contraseñas, mensaje del día, configuración del login, etc. | 
|------|------|------|
| /bin | /bin/chmod | Contiene una serie de comandos utiles que pueden ser usados tanto por el adminstrador del sistema como por los demás usuarios. Entre estos comandos se encuentran por ejemplo bash, csh, cat, chmod, mkdir |
|------|------|------|
| /dev | /dev/MAKEDEV | Contiene los archivos de dispositivos especiales para todos los dispositivos hardware. Los archivos de dispositivos se nombran utilizando convenciones especiales. |
|------|------|------|
| /lib | /lib/firmware | Contiene los módulos del kernel y las imágenes de la biblioteca compartida necesarios para arrancar el sistema y ejecutar los comandos en el sistema de archivos raíz. |
|------|------|------|
| /usr | /usr/bin | Contiene de lejos la mayor parte de los datos de un sistema. Por lo tanto, este es uno de los directorios más importantes en el sistema, ya que contiene todos los binarios del usuario, su documentación, bibliotecas, archivos de cabecera, etc. |
|------|------|------|
| /var | /var/cache | Contiene datos variables como archivos de registro del sistema, directorios de cola de correo e impresora, y archivos pasajeros y temporales |

2. En una tabla como se muestra a continuación escriba 10 comandos de Linux no visto en clase. Puede incluir comandos que funcionan una vez han sido instalados con yum

| Comando   | Usuario | Descripción   |     Foto     |
|------|------|------|------|
| rmdir | juan | Elimina un directorio. |![][1]|
|------|------|------|------|
| find fichero | juan | muestra todo lo contenido en un fichero. | ![][2] |
|------|------|------|------|
| who -a | juan | mostrar quien está registrado, e imprimir hora del último sistema de importación, procesos muertos, procesos de registro de sistema, procesos activos producidos por init, funcionamiento actual y últimos cambios del reloj del sistema.| ![][3] |
|------|------|------|------|
| printenv | juan | Imprime variables del ambiente que tiene el sistema. |![][4]|
|------|------|------|------|
| top | juan | Muesta las tareas de linux usando la mayoria de la CPU. |![][5]|
|------|------|------|------|
| ps -eafw | juan | Muestra todas las tareas que se estan ejecutando.|![][6]|
|------|------|------|------|
| free -m | juan | Muestra el estado de la RAM en megabytes. |![][7]|
|------|------|------|------|
| more archivo | juan | Muestra el contenido de un fichero.|![][8]|
|------|------|------|------|
| sed ‘/^$/d’ archivo.txt | juan | Elimina todas las lineas en blanco de un archivo.|![][9]|
|------|------|------|------|
| jtar -cvf comprimido.tar archivo.txt paquete | juan | crear un archivo llamado comprimido.tar conteniendo archivo.txt y paquete.|![][10]|
|------|------|------|------|

3. ¿Cuál es la utilidad del comando printenv en Linux?, Investigue acerca de la creación de variables de ambiente en Linux y como hacerlas permanentes. Cree una variable de ambiente, hágala permanente y muestre evidencias del funcionamiento.

**a)** printenv permite visualizar las variables del ambiente que tiene el sistema operativo.
                        ![][4]
 **b)** Una variable de entorno es un nombre asociado a una cadena de caracteres. Dependiendo de la variable, su utilidad puede ser distinta. Algunas son útiles para no tener que escribir muchas opciones al ejecutar un programa, otras las utiliza el propio shell (PATH, PS1,…). 
 Y si tecleo un comando, lo cual llama a un programa ejecutable (un binario), como por ejemplo “ls” que lista los directorios y archivos que hay en ese directorio, ¿cómo sabe el sistema operativo dónde está ese binario para ejecutarlo?. La respuesta es, gracias al PATH.

 El PATH (el camino, la ruta) es una variable de entorno. Las variables de entorno contienen información a la que se accede a través del      nombre de la variable (al igual que ocurre en los lenguajes de programación).
Por ejemplo, PWD es una variable de entorno.

  Para crear una variable de entorno utilizaremos el comando **export**. 
  Para hacer que la variable de entorno sea **permanente** debemos guardarla en el fichero /etc/environment
 
#### Muestra del proceso:
 **1** Se crea la variable VARIABLETALLER1 con el comando export, y se demuestra que esta si fue creada de forma correcta. Luego se reinicia la maquina virtual para en el siguiente paso demostrar que al reiniciar no se encuentra guardada nuestra variable que habiamos creado antes del reinicio. 
       ![][11]
       
  **2** Se vuelve a crear la variable VARIABLETALLER1 con el comando export y además se guarda en el fichero /etc/environment para hacer que esta variable este siempre en nuestro sistema. luego se reinicia la maquina virtual para observar que al volver a iniciar si encontramos la variable VARIABLETALLER1.
       ![][12]
       ![][13]
       ![][14]

### Nota

El informe debe ser entregado en formato README.md y debe ser subido a un repositorio de github. El repositorio de github debe ser un fork de https://github.com/ICESI-Training/so-workshop1 y para la entrega deberá hacer un Pull Request (PR) respetando la estructura definida. El código fuente y la url de github deben incluirse en el informe. 

## Referencias

* https://github.com/ICESI/so-commands/tree/master/centos7
* https://cmdchallenge.com  
* https://www.gutenberg.org
* https://blog.desdelinux.net/mas-de-400-comandos-para-gnulinux-que-deberias-conocer/
* https://rootsudo.wordpress.com/2014/04/06/el-path-la-ruta-de-linux-variables-de-entorno/
* http://linuxemb.wikidot.com/variables-entorno


[1]: rmdir.PNG
[2]: find.PNG
[3]: who-a.PNG
[4]: Printenv.PNG
[5]: top.PNG
[6]: ps-eafu.PNG
[7]: free-m.PNG
[8]: more.PNG
[9]: sedBlanco.PNG
[10]: tar.PNG
[11]: exportVariable.PNG
[12]: permanenteAmbiente.PNG
[13]: guardoVarialbe.PNG
[14]: variableSolida.PNG
