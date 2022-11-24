---
title: "Linux"
tags: ""
---

## Links 
[Creando Alias en GNU/Linux](https://blog.desdelinux.net/creando-alias-en-gnulinux/)
[TMUX: La navaja suiza de la terminal](https://platzi.com/blog/tmux-navaja-suiza-terminal/)
[Usa TMUX para mejorar tu ambiente de trabajo](https://platzi.com/tutoriales/1748-terminal/2158-usa-tmux-para-mejorar-tu-ambiente-de-trabajo/)
[Tmux Cheat Sheet & Quick Reference](https://tmuxcheatsheet.com/)
[Ejemplos Para El Comando Sed De Linux En La Manipulación De Texto](https://likegeeks.com/es/sed-de-linux/)
[Vim](https://vim-adventures.com/)

## Comandos
```bash
wsl --list --verbose # ver la lista de wsl instalada

.. # directorio padre
. # directorio actual
ls # Listar archivos ocultos
ls -a # Listar archivos ocultos
ls -ltra # Listar archivos en orden por fecha.
ls -t #Ordena los archivos por fecha de modificacion
ls -x #Ordena los elementos primero por nombre y depues por extension
ls -X #Ordena primero por extesion y luego por nombre
ls -l #Muestra toda la informacion: usuario, grupo, permisos, tamaño, fecha y hora de creación
ls -lh #la misma información que ls -l pero con las unidades de tamaño en KB, MB
ls -R #Muestra el contenido de todos los subdirectorios de forma recursiva:
ls -S #Ordena los resultados por tamaño de archivo
ln -s source_file myfile #Symbolic link


pwd #Identificar el directorio
cd #Cambiar de directorio
mkdir #Crear un directorio
cp [archivo que se va a copiar] [directorio hacia el que se va a mover] #Copiar un archivo 
rm #Borrar un archivo
rm -d # borrar directorio
rm -R # borrar directorio de forma recursiva
mv [ruta del archivo] [directorio hacia el que se va a mover] #Mover un archivo
rmdir #Borrar un directorio
touch #Crear fichero
cat #Nos muestra el contenido completo de un archivo
head #Nos muestra las primeras lineas (También podemos escoger cuantas lineas queremos utilizando el modificador [-n #]).
tail #Muestras las ultimas lineas del final (Inverso a head, tambien le funciona modificadores)
grep #Permite trabajar con expresiones regulares, funciona como un buscador dentro del archivo.
sed #Screem Editor, tratamiento de flujos de caracteres. Este comando nos permite reemplazar una expresión por otra. SED no modifica el archivo, lo que hace es crear un nuevo flujo con la modificación
awk #Trataminento de texto delimitado, este comando sirve para trabajar con archivos de textos delimitados por comas.
comando < archivo #ejecutar archivo descrito
comando > archivo #la salida se guarde en un archivo
comando >> archivo #agregar el resultado al archivo existente
ls -l >> archivo.txt
ls -l | more #el pipe encadena el resultado al siguiente comando
wc #Cuenta cuantas lineas tiene el archivo
cat archivo.txt | wc -l

# Cuenta cuantas lineas tiene el archivo + cuantas palabras hay + cuantos caracteres.
wc -c <fichero> # Muestra el numero de bytes
wc -m <fichero> # Muestra el numero de caracteres
wc -l <fichero> # Muestra numero de lineas
wc -L <fichero> # Muestra la linea mas larga, maximo display
wc -w <fichero> # Muestra el numero de palabras.

```


## ¿Qué es y cómo funciona la terminal?
La terminal es un programa que recibe instrucciones, las traduce a lenguaje del computador, las ejecuta y muestra resultados.

Utiliza un entorno 100% texto por lo tanto es muy eficiente.

Permite la automatización de tareas repetitivas.

#### Se compone de:
1. El prompt: que es un conjunto de caracteres al principio de cada línea y muestra información propia del sistema en que se esté utilizando.
2. El cursor: es un “underscore” que titila en la pantalla del terminal, y en conjunto con el prompt, indican que están a la espera de recibir ordenes.

En la terminal se ingresan instrucciones, también conocidas como “comandos”.
Estos comandos, a su vez, se componen de: nombre programa parámetro modificadores.

#### La terminal también cuenta con otras utilidades, tales como:
- Comodines.
- Combinación de teclas.
- Sustitución de comandos.

#### Los comando se componen de:
- Nombre del programa
- Parámetros
- Modificadores

```bash
comando -flag1 -flag2 arg1 arg2
```
## Manejo de archivos de texto y utilidades interactivas

### Archivos Binarios:
Son archivos que solo pueden ser entendidos por computadoras, algunos ejemplos son:
- Programas Ejecutables
- Archivos de Datos

### Archivos de Texto:
Son archivo también binarios pero estos tienen caracteres que los hacen legible para el ser humano. Ejemplos:
- Paginas Web
- Código fuente

### Utilidades Interactivas:
Programas que se ejecuta inmediatamente al ejecutar el comando. en tiempo real.

- `vim`: Es un comando que permite escribir sobre un archivo. Al estar en el VIM podemos escribir, tecleando la tecla **‘i’** (Insert) y podemos guardar lo editado tecleando, **dos puntos 😃 y escribiendo w (writen).** Para salir del VIM: (Dos puntos [:], y luego la letra 'q´)

- `nano`: Es otro comando que permite editar un archivo igual que en vim, pero la diferencia es que este entra en modo edición, de una vez y nos muestra un listado de comandos que podemos utilizar.

para poder salir de el utilizamos `CTRL + X` (Guardamos antes de salir)
	- Crear un Archivo Nuevo:
    ingresamos con VIM sguido del nombre del archivo (nuevo.txt) Editamos. Luego con la tecla ESC se pasa directamente a la linea de comandos. y escribimos x (Grabar y salir a la vez)


## Tratamiento de Texto
Vamos a estudiar algunos comandos para procesar texto y emitir un resultado. Te recomiendo que no solo te quedes con la lectura, sino que experimentes todo lo que quieras con estos comandos, ya que más adelante los necesitarás para completar los desafíos.

### Trabajo fundamental con archivos de texto
En clases anteriores estudiamos cómo crear y organizar nuestras carpetas. Ahora vamos a trabajar archivos que, por supuesto, debemos guardar en estos directorios que previamente creamos.

`touch`: nos permite crear archivos.

```bash
touch archivo.txt
```

`cat`: nos permite visualizar todo el contenido de nuestros archivos.

```bash
cat archivo.txt
```

`head`: es muy parecido al comando cat. También nos permite visualizar el contenido de nuestros archivos, pero debemos indicarle cuántas líneas nos debe mostrar. Por defecto nos mostrará las primeras 10.
```bash
# primeras 10 líneas
head archivo.txt

# primeras 20 líneas
head -n 20 archivo.txt
```

`tail`: funciona igual que el comando head, pero al revés. También debemos indicarle cuántas líneas nos debe mostrar, la diferencia es que no las mostrará de abajo hacia arriba. Por defecto nos mostrará las últimas 10.
```bash
# últimas 10 líneas
tail archivo.txt

# últimas 5 líneas
tail -n 5 archivo.txt
```
Búsqueda y tratamiento de texto
No solo podemos visualizar nuestros archivos (o parte de nuestros archivos) tal cual como escribimos, también podemos filtrar y cambiar el contenido que podemos ver en los archivos.

Por ejemplo: imagina que tenemos un archivo gigante, con cientos o incluso miles de líneas. Si imprimieramos el contenido de todo el archivo sería muy difícil encontrar el nombre de una persona o elemento específico.

Y se vuelve aún más complicado si necesitamos que las palabras que buscamos cumplan ciertas condiciones, como solo mayúsculas o minúsculas, que la siguiente o anterior palabra cumpla ciertas condiciones, etc.

En estos casos podemos utilizar el comando `grep` para filtrar las líneas que queremos visualizar utilizando (o no) expresiones regulares:

```bash
grep “palabra-clave” archivo_gigante.txt
```

Si nos da igual si la palabra clave incluye mayúsculas o minúsculas podemos utilizar el flag `-i`:

```bash
grep -i “pAlaBra-cLAvE” archivo_gigante.txt
```

También podemos verificar si la línea incluye esta palabra clave al final:
```bash
grep “palabra-clave$” archivo_gigante.txt
```

O si la incluye al principio:

```bash
grep “^palabra-clave” archivo_gigante.txt
```

También hay situaciones donde necesitamos modificar un poco la información que obtenemos de un archivo de texto.

Por ejemplo, imagina que nuestro archivo contiene un poema, frase o saludo para responderle a los usuarios de nuestra aplicación. El problema es que cada usuario tiene un nombre diferente.

¡Hola, NOMBRE_USUARIO! Felicitaciones por completar tu desafío con PUNTOS_USUARIO puntos.
No queremos editar este archivo. Solo necesitamos cambiar los caracteres NOMBRE_USUARIO por el verdadero nombre del usuario.

Para esto podemos utilizar el comando `sed`. Solo debemos indicarle que queremos realizar una sustitución (`s/`), la palabra que vamos a cambiar (NOMBRE_USUARIO), la nueva palabra que vamos a incluir (Ana) y cerrar con el símbolo /.
[Ejemplos Para El Comando Sed De Linux En La Manipulación De Texto](https://likegeeks.com/es/sed-de-linux/)


```bash
sed ‘s/NOMBRE_USUARIO/Ana/’ archivo-saludo.txt
```

Ahora imagina que, además del nombre, debemos cambiar también la puntuación que obtuvo el usuario:
```bash
sed ‘s/NOMBRE_USUARIO/Ana/; s/PUNTOS_USUARIO/35/’ archivo-saludo.txt
```


## Comunicación entre procesos: Qué son y cómo se utilizan los flujos estándar
Flujos estandar: entrada, salida, error.

## Introducción a la terminal y línea de comandos
Diferencias entre la estructura de archivos de Windows, Mac o Linux.

- La ruta principal en Windows es C:\, en UNIX es solo `/`.
- Windows no hace diferencia entre mayúsculas y minúsculas pero UNIX sí.

Recuerda que GitBash usa la ruta `/c` para dirigirse a `C:\` (o `/d` para dirigirse a `D:\`) en Windows. Por lo tanto, la ruta del usuario con el que estás trabajando es /c/Users/Nombre de tu usuario


## Administración de procesos en background y foreground
- **Procesos en primer plano:** Son aquellos que mientras estén en ejecución, la terminal no permitirá realizar ninguna otra acción.
- **Procesos en segundo plano:** Son aquellas actividades que se están ejecutando mientras nosotros estamos realizando otras actividades en la terminal.

Para colocar un proceso en segundo plano desde el inicio de su ejecución, se coloca al final del toda la línea de comando, el simbolo de ampersand `&`.

Para colocar un proceso en segundo plano durante su ejecución, se debe utilizar la combinación teclas: `Ctrl + Z`.

Para volver a colocar un proceso en primer plano, se debe ingresar el comando `fg`.
Comando para ver procesos que se estén ejecutando: `ps` o con modificador para ver tambien procesos del sistema: `ps ax`.

Comando para ver procesos ejecutando en el sistema en tiempo real: `top`. Para salir de la ejecución del comando se debe oprimir la tecla `q`.

Cuando sea necesario detener un proceso mientras está en ejecución: Se debe usar la combinación de teclas `Ctrl + C`.

Si el proceso está en segundo plano y se requiere detener o es un proceso que está colgado y se debe detener: ejecutar el comando `ps ax` para averiguar el numero del comando (Campo PID) y después se ejecuta el comando: `kill -9 #proceso`, lo cual detendrá obligatoriamente el proceso indicado.

- `&` al final de un comando nos permite seguir trabajando mientras un proceso se ejecuta.
- `ctrl + z` Me permite poner un proceso en background y poder seguir utilizando la linea de comandos.
- `fg` Me permite poder volver a ese proceso.

#### Herramientas:
- `ps` Me permite ver los procesos que se estan ejecutando.
- `top`Me permite ver en tiempo real como los procesos van cambiando.

#### Como detener procesos:
- `ctrl + c` nos permite terminar un programa en ejecucion en la consola.
- `ps ax` nos permite ver los procesos y con el numero de id del procesos lo podemos eliminar.

#### Para eliminarlos por el id del proceso:
- `kill` => elimina el proceso por el id. `kill -9 #proceso` elimina el procesos inmediatamente.
- `killall` => elmina el proceso por el nombre del ejecutable.

## Permisos sobre archivos: El sistema de permisos octal
Todos los archivos de Unix tienen un: Dueño, grupo, otros

Las operaciones que pueden hacerse sobre un archivo son: Escribir [w], leer [r], Ejecutar [x]

Para alterar los permisos asociados se tienen los siguientes comandos:
- `chmod`: Cambia individualmente los permisos
ejemplo: [chmod ][o (Indica ‘others’)][-(menos quita el permiso)]
[w (Cual es el permiso que se desea quitar)]
Para dar el permiso: chmod +x hello.php (Esto dará el permiso de ejecutar a los tres grupos)

- `chown`: Cambia quien es el propietario del archivo.
ejemplo: [chown] [nombre del usuario] [nombre del archivo]
“chonw www-data hello.php”

- `chgrp`: Cambia quien es el grupo de usuarios que pueda acceder al archivo.
ejemplo: [chgrp] [nombre del usuario] [nombre del archivo]
“chgrp www-data hello.php”

- Para ejecutar un archivo: [./ (punto, barra es donde estamos actualmente)] [hello.php (El nombre del archivo)].

### Permisos
- 7 = 111 = rwx = Todos los permisos.
- 6 = 110 = rw- = Permiso de lectura y escritura.
- 5 = 101 = r-x = Permiso de lectura y ejecución.
- 4 = 100 = r-- = Permiso de lectura.
- 3 = 011 = -wx = Permiso de escritura y ejecución.
- 2 = 010 = -w- = Permiso de escritura.
- 1 = 001 = --x = Permiso de ejecución.
- 0 = 000 = — = Sin permisos.

|r|w|x| |
|-|-|-|-|
|1|0|0|4|
|1|1|0|6|
|1|1|1|7|

|Dueño|||Grupo|||Otros|||     |
|-|-|-|-|-|-|-|-|-|-|
|r|w|x|r|w|x|r|w|x||
|1|1|0|1|0|0|0|0|0|640|
|1|0|0|0|0|0|0|0|0|400|
|1|1|1|1|1|1|1|1|1|777|

### Super usuario - root:
Este usuario puede leer y escribir cualquier archivo del sistema, y ejecutar algunos archivos. y también hay otras operaciones que están reservadas para el.

Podemos utilizarlo con el comando `sudo`


### WSL Ubuntu sermisos sobre archivos: El sistema de permisos octal
Para los que están usando WSL Ubuntu o alguna otra distro y no pudieron cambiar los permisos de rx es porque Windows no permite cambiar los permisos porque no se ha autorizado la metadata para que Linux pueda hacerlo.

Sigan este tutorial para configurar un archivo wsl.conf para crear los permisos:

[Automatically Configuring WSL](https://devblogs.microsoft.com/commandline/automatically-configuring-wsl/)

Peguen este código en el wsl.conf:

```ini
# Enable extra metadata options by default
[automount]
enabled = true
root = /windir/
options = "metadata,umask=22,fmask=11"
mountFsTab = false

# Enable DNS – even though these are turned on by default, we’ll specify here just to be explicit.
[network]
generateHosts = true
generateResolvConf = true
```

Terminando reinicien Windows y listo. Prueben de nuevo cambiar permisos en Linux y Windows.

#### Fuentes:
- [File Permissions for WSL](https://docs.microsoft.com/en-us/windows/wsl/file-permissions)
- [WSL commands and launch configurations](https://docs.microsoft.com/en-us/windows/wsl/wsl-config)

## Sistemas de manejo de paquetes
Existen programas que se descargan e instalan sus archivos de programa en lugares ya indicados y se configuran para que dicho programa pueda correr en la computadora. Los paquetes de software se encargan de realizar todo lo anterior dicho.

### Administradores de Paquetes:
Estos son los que conocen de donde realizar las descargas, que otros paquetes ya están instalados en nuestro sistema y como configurar todo, a medida que no haya conflicto.

### Paquetes Binarios
Son archivos que ya son ejecutables. Dependiendo del sistema operativo, se pueden utilizar diferentes manejadores de paquetes.
- `apt`: Se utiliza en las distribuciones de Linux basadas en Devian como Ubuntu.
- `zypper`: Se utiliza en las distribuciones de Suse linux
- `rpm`: El universal…

```bash
sudo apt update #actualiza el sistema operativo
sudo apt upgrade #Se aplican las actualizaciones.
sudo apt update && sudo apt-upgrade #Actualiza y aplica las actualizaciones del s.o.
sudo apt install <nombre_paquete>
```
Ejemplo: [APT][INSTALL][ LYNX] (lynx es un navegador de linea de comandos. )

### Paquetes de Lenguajes

Estos son librerías escritas en el mismo lenguaje que vas a utilizar.
- `pip`: Es para Python
ejemplo: [sudo][pip][install][pandas] = pandas es el nombre de la librería.
- `composer`: PHP
- `npm`: NODE JS

#### Otros:
Existen unos nuevos manjadores de paquetes que pretenden ser mas genéricos instalando tanto paquetes binarios como de lenguajes.
- conda
- homebrew


## Herramientas de compresión y combinación de archivos
### Comprensión de Archivos
Los archivos en una transmisión de datos pueden perderse para esto lo comprimimos haciendo uso del comando gzip. Un archivo comprimido no podrá utilizarse como en clases pasadas pero para el envío y almacenamiento es ideal.

#### Ejemplo:
- Para ver el tamaño del archivo a comprimir es: `ls dump4.sql -lh`
- Para comprimir: `gzip dump4.sql`
- Para verificar la extensión del archivo: `ls dump4*`
- Para verificar la compresión aplicar el punto 1

Si quisiéramos volver al archivo original, debemos descomprimirlo. Al descomprimirlo. esto volverá la extensión y el tamaño del archivo original.
Ejemplo: `gzip -d (Descomprimir) dump4.sql.gz`

### Combinación de Archivos
Si quisiéramos enviar un grupo de archivos y no solo uno. Utilizaremos la herramienta tar solamente para agrupar solamente y para agrupar y comprimir utilizaremos el tar csf

Ejemplo:

[tar] [cf (create file, este creará unnuevo archivo donde combinará los otros)] [backup.tar (Luego nombre de este archivo creado)][backup/ (aquí todos los archivos que están dentro del dir. backup)]*

Para ver el contenido de TAR es: **[tar] [tf (es un parametro) backup.tar]

Para agrupar y comprimir: [tar] [czf (Crea un archivo comprimido usando internamente la utilidad del gzip )] [backup.tgz] [backup/*]

Para volver a recuperar los archivos: [tar] [xzf] [backup.tgz]

> Nota: Hay que recordar que al mover el archivo a otra carpeta. este se mantendrá comprimido. para usarlo hay que descomprimir


## Herramientas de búsqueda de archivos
### LOCATE
Busqueda en todo el sistema de archivos
Ojo: Para ello debe tener la BD actualizada
tienes que usar: sudo updatedb
*se demorara bastante la primera vez, ojo con ese detalle.

Ejemplo: `locate prueba.txt`

`locate -c <archivo>` [Mostrara el conteo de los archivos]

### WHEREIS
Para buscar archivos binarios (Osea Comandos)

Ej: `whereis echo`
echo: /bin/echo /usr/share/man/man1/echo.1.gz

/bin/echo -> la primera ruta encontrada
/usr/share/man/man1/echo.1.gz ->la segunda ruta encontrada

### FIND
Busqueda compleja segun una serie de criterios

`find /ruta -name archivo*`
[buscara todos los archivos que comiencen con el nombre archivo]

`find . -user <nombreusuario> -perm XXX`
- [. el punto es directorio actual]
- [-user nombre del usuario a que pertenece]
- [-perm = Permisos XXX puede ser 777 644 etc]

`find . -name <archivo> -delete`
- [. el punto es directorio actual]
- [-delete ->Eliminara el archivo encontrado]

Find un comando con mucho poder 💪
```bash
find [ruta][expresión_de_búsqueda][acción]
``` 
#### Ruta
Si no se indica una ruta se toma en cuenta entonces el directorio donde se este actualmente, es decir el directorio de trabajo actual, que es lo mismo que indicar con un punto “.”.
 
Es posible asignar mas de una ruta de búsqueda también como por ejemplo

```bash
find /etc /usr /var -groupadmin
 ```

#### Búsquedas básicas 👍
Algunas banderas que podemos utilizar para buscar:
- `name` = Busca nombre de un archivo
- `iname` = Igual que name pero este no toma en consideración si tiene alguna mayúscula
- `user` = El usuario propietario
- `group` = El grupo propietario
- `type` = tipo de archivo, `f` para directorios

#### Búsquedas a través del tiempo ⏰
- `mmin` = Tiempo en minutos
- `mtime` = Periodos de 24 horas

#### exec; El poder aumenta 👊
`exec` Permite ejecutar acciones sobre el resultado de cada línea o archivo devuelto por `find`, ejemplo:

```bash
find . -type f -mtime +7 -exec cp {} ./backup/ \;
```
## Herramientas para interactuar a través de HTTP

### CURL (Abreviatura de «Client URL»)
Esta diseñada para funcionar como una forma de verificar la conectividad a las URL y como una herramienta para transferir datos.

Estos son los protocolos compatibles más importantes: HTTP y HTTPS, FTP y FTPS, IMAP e IMAPS, POP3 y POP3S, SMB y SMBS, SFTP, SCP, TELNET, GOPHER,  LDAP y LDAPS, SMTP y SMTPS

```bash
curl --version #Verificar la version de curl, *Mostrara la lista de protocolos compatibles
curl https://platzi.com
curl -v https://platzi.com | more #*Al aparecer el detalle, puedes apretar = y te dira en que linea estas parado.

curl -v https://platzi.com > /dev/null *Mostrara el encabezado y lo enviara a un archivo de mentira en la ruta /dev/null

#Para guardar el resultado:
curl -O https://platzi.com/<nombredelarchivo>.tar.gz #-O guardará el archivo en el directorio de trabajo actual con el mismo nombre de archivo que el remoto.

curl -o NUEVONOMBRE.tar.gz https://platzi.com/<nombredelarchivo>.tar.gz #-o permite especificar un nombre de archivo o ubicación diferente.
```


### WGET
Puedes usarlo para recuperar contenido y archivos de varios servidores web. Admite descargas a través de FTP, SFTP, HTTP y HTTPS.

```bash
wget --version #Verificar la version de wget

wget https://wordpress.org/latest.zip #Podemos descargar archivos
wget -O <nombredelarchivo>.zip https://wordpress.org/latest.zip #Podemos descargar archivos y dejarlos con otro nombre
wget -b https://platzi.com/<nombredelarchivo>.tar.gz #Obtener archivos demasiado grandes, y dejarlo en 2do plano trabajando


nano ejemplo.txt #Podemos crear un archivo con varias URL para descargar posteriormente.

# Elejimos las URL y las copiamos dentro del archivo creado “ejemplo” y guardamos el archivo.
# https://wordpress.org/latest.zip
# https://downloads.joomla.org/cms/joomla3/3-8-5/Joomla_3-8-5-Stable-Full_Package.zip
# https://ftp.drupal.org/files/projects/drupal-8.4.5.zip

wget -i ejemplo.txt #Ojo dependiendo del peso de los archivos, el tiempo puede variar mucho mas.
```

## Acceso seguro a otras computadoras
### SSH, Secure shell (Terminal segura)

Con este comando ingresamos a un servidod de manera segura. ejemplo: `ssh leeway -prod`

Funcionalidad para conectarse por consola a un equipo remoto y ejecutar comando como si fuera nuestra terminal. Para ejecutar el comando se usa de la siguiente forma:
`ssh user@host`

Donde user es el nombre del usuario o la cuenta a la que queremos conectarnos en la maquina remota. En cuanto al host, puede ser la dirección IP del equipo remoto o el nombre del dominio asignado en esa maquina.

También se pueden usar otros métodos de autenticación tales como las llaves públicas y privadas.



### Comando `mail`

[Enviar correo desde la línea de comandos con “mail”](https://victorhckinthefreeworld.com/2014/04/23/enviar-correo-desde-la-linea-de-comandos-con-mail/)

Nos permite enviar un email desde el servidor. Para que este comando funcione hay que tener algunas cosas configuradas. Ejemplo: 
```bash
echo “Probando” | mail -s(-s: es el asunto del correo) “Probando para platzi” mchojrin1@hotmail.com"
```
Permite enviar mensajes de correo electrónico desde consola. Para hacerlo, se deben agregar las siguientes líneas al archivo `/etc/mail.rc` del sistema desde donde la vayamos a envíar. Las líneas son las siguientes:

```ini
set smtp-use-starttls
set ssl-verify=ignore
set smtp-auth=login
set smtp=smtp://smtp.tu_proveedor_de_correo.com:587
set from="tu.direccion.de.correo@tu.proveedor"
set smtp-auth-user=tu.direccion.de.correo@tu.proveedor
set smtp-auth-password=tu.contraseña
set ssl-verify=ignore
```
En las líneas anteriores, se debe cambiar los datos de tu proveedor, tu dirección, y tu contraseña por los tuyos propios. Después de realizada esta configuración, se ejecuta el comando de la siguiente manera:

```bash
echo “contenido-correo” mail -s “asunto” correo@dominio.com
```

## Qué son y cómo se utilizan las variables de entorno
Es un definición global a la que todos los procesos tienen acceso. esta toma mas información de lo que se este typeando.

Ejemplo: `echo $PATH` se encuentran la ubicacion de todos los comandos ejecutables

### Asignación de las variables de entorno
- `export` Este comando se utiliza para asignar a toda la sesión
Ejemplo: `export MI_VAR = mauro`, si luego escribimos echo $MI_VAR se mostrará mauro en la terminal. (Este permanecerá miestras dure mi sesión)

- `var` Este comando solo asigna el valor para el proximo proceso que se va a ejecutar. este no es muy usual. Ejemplo: `MI_VAR=/home php env.php`

## Cómo y para qué escribir scripts en Bash
El Bash es un interprete de comandos y a su vez un lenguaje de programación. Permitiéndonos hacer ciertos scripts usando la sintaxis Bash. Estos Scripts lo que haran será llamar a otros comandos, evaluar condiciones y ejecutar en base a eso.
Lo que nos da la posibilidad de crear nuestros propoios comandos. Esto lo podemos usar para automatizar tareas muy repetitivas y que usamos a menudo, poniendo todos los comandos utilizados en un mismo script.

Las funciones Bash puede ser:
- Eliminar tareas repetitivas
- Ahorrar tiempo
- Proporciona una secuencia de actividades bien estructurada, modular y formateada
- Con scripts, podemos proporcionar valores dinámicos a comandos usando argumentos de línea de comando
- Puede simplificar comandos complejos en una sola unidad en ejecución
- Una vez creado, se puede ejecutar cualquier cantidad de veces por cualquier persona. Construye una vez y ejecuta muchas veces.
- Los flujos lógicos se pueden construir utilizando funciones bash
- Las funciones Bash se pueden ejecutar al inicio del servidor o agregando un cron job programado
- Los comandos pueden ser depurados
- Puede tener comandos de shell interactivos

Bash es definitivamente una gran herramienta para facilitar tu trabajo y mejorar tus proyectos.

```sh
#Script platzi.sh
#!/bin/bash

NEW_DIR = platzi

#Si no existe el directorio, entonces crealo.
if [ ! -d "/root/$NEW_DIR"]; then
	mkdir /root/$NEW_DIR
fi

# Se copoia un archivo cualquiera hacia el direcotrio creado
cp backup_code.sh /root/$NEW_DIR/

#Por ultimo se muestra un echo
echo "`date` : Todo listo jefe!"

```

## Cómo y para qué dejar tareas programadas
Para realizar tareas programadas, se puede hacer de dos formas:

### at
`at` permite realizar la programación de tareas unicas en un momento especifico.
- `at now +2 minutes` (instrucción para ejecución de tarea en 2 min)
echo “hola mundo!” > /home/user/hola.txt (se ingresa la tarea a ejecutar)
se oprime Ctrl + D para finalizar el ingreso de tareas en at.

### cron
el comando cron permite a demás de programar tareas, también que estás sepuedan hacer de forma periodica. Este comando se apoya en un archivo `crontab` donde se guardar las tareas que se programan en el sistema.

para modificar el archivo mencionado, se ingresa: `crontab -e`. al principio saldrá un texto con instrucciones; las tareas a programar deben ir al final de este texto.
Las tareas a realizar se deben ingresar de la siguiente manera:
![](http://drive.google.com/uc?export=view&id=1mGAYHzx9ZoJffr6U47R5hey3Exr0ja3n)

Minuto Hora DiaDelMes Mes DiaDeLaSemana Usuario Comando

Un asterisco * como valor en los primeros cinco campos, indicará inicio-fin del campo, es decir todo. Un * en el campo de minuto indicará todos los minutos.



## Comandos básicos en la terminal:

- `pwd` Nos muestra la ruta de carpetas en la que te encuentras ahora mismo.
- `mkdir`: Nos permite crear carpetas (por ejemplo, mkdir Carpeta-Importante).
- `touch`: Nos permite crear archivos (por ejemplo, touch archivo.txt).
- `rm`: Nos permite borrar un archivo o carpeta (por ejemplo, rm archivo.txt). Mucho cuidado con este comando, puedes borrar todo tu disco duro.
- `cat`: Ver el contenido de un archivo (por ejemplo, cat nombre-archivo.txt).
- `ls`: Nos permite cambiar ver los archivos de la carpeta donde estamos ahora mismo. Podemos usar uno o más argumentos para ver más información sobre estos archivos (los argumentos pueden ser -- + el nombre del argumento o - + una sola letra o shortcut por cada argumento).
	- `ls -a`: Mostrar todos los archivos, incluso los ocultos.
	- `ls -l`: Ver todos los archivos como una lista.
- `cd`: Nos permite navegar entre carpetas.
	- `cd /`: Ir a la ruta principal:
	- `cd` o `cd ~`: Ir a la ruta de tu usuario
	- `cd carpeta/subcarpeta`: Navegar a una ruta dentro de la carpeta donde estamos ahora mismo.
	- `cd ..` (cd + dos puntos): Regresar una carpeta hacia atrás.
	- Si quieres referirte al directorio en el que te encuentras ahora mismo puedes usar cd . (cd + un punto).

- `history`: Ver los últimos comandos que ejecutamos y un número especial con el que podemos repetir su ejecución.
- `! + número`: Ejecutar algún comando con el número que nos muestra el comando history (por ejemplo, !72).
- `clear`: Para limpiar la terminal. También podemos usar los atajos de teclado Ctrl + L o Command + L.


Todos estos comandos tiene una función de autocompletado, o sea, puedes escribir la primera parte y presionar la tecla Tab para que la terminal nos muestre todas las posibles carpetas o comandos que podemos ejecutar. Si presionas la tecla Arriba puedes ver el último comando que ejecutamos.

Recuerda que podemos descubrir todos los argumentos de un comando con el argumento `--help` (por ejemplo, `cat --help`).

## ¿Qué es el staging y los repositorios? Ciclo básico de trabajo en Git

Para iniciar un repositorio, o sea, activar el sistema de control de versiones de Git en tu proyecto, solo debes ejecutar el comando `git init`.

Este comando se encargará de dos cosas: primero, crear una carpeta `.git`, donde se guardará toda la base de datos con cambios atómicos de nuestro proyecto; y segundo, crear un área que conocemos como Staging, que guardará temporalmente nuestros archivos (cuando ejecutemos un comando especial para eso) y nos permitirá, más adelante, guardar estos cambios en el repositorio (también con un comando especial).

### Ciclo de vida o estados de los archivos en Git:

Cuando trabajamos con Git nuestros archivos pueden vivir y moverse entre 4 diferentes estados (cuando trabajamos con repositorios remotos pueden ser más estados, pero lo estudiaremos más adelante):

- Archivos Tracked: son los archivos que viven dentro de Git, no tienen cambios pendientes y sus últimas actualizaciones han sido guardadas en el repositorio gracias a los comandos git add y git commit.
- Archivos Staged: son archivos en Staging. Viven dentro de Git y hay registro de ellos porque han sido afectados por el comando git add, aunque no sus últimos cambios. Git ya sabe de la existencia de estos últimos cambios, pero todavía no han sido guardados definitivamente en el repositorio porque falta ejecutar el comando git commit.
- Archivos Unstaged: entiéndelos como archivos “Tracked pero Unstaged”. Son archivos que viven dentro de Git pero no han sido afectados por el comando git add ni mucho menos por git commit. Git tiene un registro de estos archivos, pero está desactualizado, sus últimas versiones solo están guardadas en el disco duro.
- Archivos Untracked: son archivos que NO viven dentro de Git, solo en el disco duro. Nunca han sido afectados por git add, así que Git no tiene registros de su existencia.
Recuerda que hay un caso muy raro donde los archivos tienen dos estados al mismo tiempo: staged y untracked. Esto pasa cuando guardas los cambios de un archivo en el área de Staging (con el comando git add), pero antes de hacer commit para guardar los cambios en el repositorio haces nuevos cambios que todavía no han sido guardados en el área de Staging (en realidad, todo sigue funcionando igual pero es un poco divertido).
Comandos para mover archivos entre los estados de Git:
- `git status`: nos permite ver el estado de todos nuestros archivos y carpetas.
- `git add`: nos ayuda a mover archivos del Untracked o Unstaged al estado Staged. Podemos usar git nombre-del-archivo-o-carpeta para añadir archivos y carpetas individuales o git add -A para mover todos los archivos de nuestro proyecto (tanto Untrackeds como unstageds).
- `git reset HEAD`: nos ayuda a sacar archivos del estado Staged para devolverlos a su estado anterior. Si los archivos venían de Unstaged, vuelven allí. Y lo mismo se venían de Untracked.
- `git commit`: nos ayuda a mover archivos de Unstaged a Staged. Esta es una ocasión especial, los archivos han sido guardado o actualizados en el repositorio. Git nos pedirá que dejemos un mensaje para recordar los cambios que hicimos y podemos usar el argumento -m para escribirlo (`git commit -m "mensaje"`).
- `git rm`: este comando necesita alguno de los siguientes argumentos para poder ejecutarse correctamente:
- `git rm --cached`: Mueve los archivos que le indiquemos al estado Untracked.
- `git rm --force`: Elimina los archivos de Git y del disco duro. Git guarda el registro de la existencia de los archivos, por lo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

![](http://drive.google.com/uc?export=view&id=1HHBBzeVIfV07X6Q600qHOuxWv7ORhqYl)


## ¿Qué es un Branch (rama) y cómo funciona un Merge en Git?
Git es una base de datos muy precisa con todos los cambios y crecimiento que ha tenido nuestro proyecto. Los commits son la única forma de tener un registro de los cambios. Pero las ramas amplifican mucho más el potencial de Git.

**Todos los commits se aplican sobre una rama.** Por defecto, siempre empezamos en la rama master (pero puedes cambiarle el nombre si no te gusta) y creamos nuevas ramas, a partir de esta, para crear flujos de trabajo independientes.

Crear una nueva rama se trata de copiar un commit (de cualquier rama), pasarlo a otro lado (a otra rama) y continuar el trabajo de una parte específica de nuestro proyecto sin afectar el flujo de trabajo principal (que continúa en la rama master o la rama principal).

Los equipos de desarrollo tienen un estándar:
- Todo lo que esté en la rama master va a producción
- Las nuevas features, características y experimentos van en una rama **“development”** (para unirse a master cuando estén definitivamente listas)
- Los issues o errores se solucionan en una rama `“hotfix”` para unirse a master tan pronto como sea posible.

Crear una nueva rama lo conocemos como `Checkout`.
Unir dos ramas lo conocemos como `Merge`.

Podemos crear todas las ramas y commits que queramos. De hecho, podemos aprovechar el registro de cambios de Git para crear ramas, traer versiones viejas del código, arreglarlas y combinarlas de nuevo para mejorar el proyecto.

Solo ten en cuenta que combinar estas ramas (sí, hacer “merge”) puede generar conflictos. Algunos archivos pueden ser diferentes en ambas ramas. Git es muy inteligente y puede intentar unir estos cambios automáticamente, pero no siempre funciona. En algunos casos, somos nosotros los que debemos resolver estos conflictos “a mano”.

## Flujo de trabajo en Git flow

GitFlow es una una guía que nos da cierto estándares para manejar la ramificación de nuestros proyectos, es decir, que ramas debemos tener, cuándo y de dónde debemos crear nuevas ramas, cómo debemos nombrar dichas ramas y muchos otros conceptos que nos ayudaran a manejar mucho mejor nuestro repositorio; siendo esto muy importante cuando trabajamos en conjunto con varios desarrolladores.

Flujo de Gitflow es así:

En la rama master tendremos solo lo que se ha liberado.

1. Se crea la rama develop, es la rama en la que estamos trabajando (lo que vamos a liberar).
2. Liberar a producción con tu equipo de trabajo se crea una release desde develop.
No se pasa directo de develop a master, Git Flow crea la nueva rama de release.
3. Por cada petición o tarea se genera una rama llamada feature a partir de develop.
4. Por ejemplo una pantalla nueva, se crea y está completa el feature de pantalla se cierra y se afusiona con develop.
5. Cuando tienes la rama release terminada, fusionas con develop y master.
6. Si hay problema en master se crea hotfix que son los cambios sobre algo que está en producción.
7. Se crea una nueva rama se trabaja y se reintegra. Una vez que hotfix se completa, se fusiona a ambos develop y master.

![](http://drive.google.com/uc?export=view&id=1i2kwux3cjEcUiCCZ86EBOyyWlvhoZol-)


- La rama **MASTER **es el branch principal del proyecto o llamada también la rama de producción.
- La rama **DEVELOPMENT **es el branch de desarrollo donde se realizan los ajustes requeridos al desarrollo y crecimiento de los archivos.
- La rama **HOTFIX **es el branch donde se corrigen los errores de archivos que ya se encuentran en producción.
- Los archivos de las ramas DEVELOPMENT y HOTFIX son **checkout **de la rama MASTER. Una vez se haya terminado de trabajar con un archivo ya sea en DEVELOPMENT o HOTFIX se debe hacer _**merge **_con la rama MASTER.
- Lo ideal de trabajar con las ramas DEVELOPMENT y HOTFIX por separado es que se pueden trabajar los cambios en los archivos por requerimientos a la medida de desarrollo del archivo y corregir errores puntuales de producción por separado.

### Links
- [Que es Git Flow](https://www.youtube.com/watch?v=G_iTZtnlf_U)

## Crea un repositorio de Git y haz tu primer commit

*Si quieres ver los archivos ocultos de una carpeta puedes habilitar la opción de Vista > Mostrar u ocultar > Elementos ocultos (en Windows) o ejecutar el comando `ls -a.`*

Le indicaremos a Git que queremos crear un nuevo repositorio para utilizar su sistema de control de versiones. Solo debemos posicionarnos en la carpeta raíz de nuestro proyecto y ejecutar el comando `git init`.

Recuerda que al ejecutar este comando (y de aquí en adelante) vamos a tener una nueva carpeta oculta llamada .git con toda la base de datos con cambios atómicos en nuestro proyecto.

Recuerda que Git está optimizado para trabajar en equipo, por lo tanto, debemos darle un poco de información sobre nosotros. No debemos hacerlo todas las veces que ejecutamos un comando, basta con ejecutar solo una sola vez los siguientes comandos con tu información:

```bash
git config --global user.email "tu@email.com"
git config --global user.name "Tu Nombre"
```

Existen muchas otras configuraciones de Git que puedes encontrar ejecutando el comando `git config --list` (o solo `git config` para ver una explicación más detallada).

## Analizar cambios en los archivos de tu proyecto con Git
El comando `git show` nos muestra los cambios que han existido sobre un archivo y es muy útil para detectar cuándo se produjeron ciertos cambios, qué se rompió y cómo lo podemos solucionar. Pero podemos ser más detallados.

Si queremos ver la diferencia entre una versión y otra, no necesariamente todos los cambios desde la creación del archivo, podemos usar el comando `git diff commitA commitB`.

Recuerda que puedes obtener el ID de tus commits con el comando `git log`.


## Volver en el tiempo en nuestro repositorio utilizando reset y checkout

El comando `git checkout + ID` del commit nos permite viajar en el tiempo. Podemos volver a cualquier versión anterior de un archivo específico o incluso del proyecto entero. Esta también es la forma de crear ramas y movernos entre ellas.

También hay una forma de hacerlo un poco más “ruda”: usando el comando `git reset`. En este caso, no solo “volvemos en el tiempo”, sino que borramos los cambios que hicimos después de este commit.

Hay dos formas de usar `git reset`: con el argumento `--hard`, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento `--soft`, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

## Git reset vs. Git rm
`Git reset` y `git rm` son comandos con utilidades muy diferentes, pero aún así se confunden muy fácilmente.

### git rm
Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

Recuerda que `git rm` no puede usarse así nomás. Debemos usar uno de los flags para indicarle a Git cómo eliminar los archivos que ya no necesitamos en la última versión del proyecto:
- `git rm --cached`: Elimina los archivos del área de Staging y del próximo commit pero los mantiene en nuestro disco duro.
- `git rm --force`: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

### git reset
Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Este comando es muy peligroso y debemos usarlo solo en caso de emergencia. Recuerda que debemos usar alguna de estas dos opciones:

Hay dos formas de usar `git reset`: con el argumento `--hard`, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento `--soft`, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

- `git reset --soft`: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.
- `git reset --hard`: Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.

### ¡Pero todavía falta algo!

`git reset HEAD`: Este es el comando para sacar archivos del área de Staging. No para borrarlos ni nada de eso, solo para que los últimos cambios de estos archivos no se envíen al último commit, a menos que cambiemos de opinión y los incluyamos de nuevo en staging con `git add`, por supuesto.


### ¿Por qué esto es importante?

Imagina el siguiente caso:

Hacemos cambios en los archivos de un proyecto para una nueva actualización. Todos los archivos con cambios se mueven al área de staging con el comando `git add`. Pero te das cuenta de que uno de esos archivos no está listo todavía. Actualizaste el archivo pero ese cambio no debe ir en el próximo commit por ahora.

#### ¿Qué podemos hacer?

Bueno, todos los cambios están en el área de Staging, incluido el archivo con los cambios que no están listos. Esto significa que debemos sacar ese archivo de Staging para poder hacer commit de todos los demás.

¡Al usar `git rm` lo que haremos será eliminar este archivo completamente de git! Todavía tendremos el historial de cambios de este archivo, con la eliminación del archivo como su última actualización. Recuerda que en este caso no buscábamos eliminar un archivo, solo dejarlo como estaba y actualizarlo después, no en este commit.

En cambio, si usamos `git reset HEAD`, lo único que haremos será mover estos cambios de Staging a Unstaged. Seguiremos teniendo los últimos cambios del archivo, el repositorio mantendrá el archivo (no con sus últimos cambios pero sí con los últimos en los que hicimos commit) y no habremos perdido nada.

Conclusión: Lo mejor que puedes hacer para salvar tu puesto y evitar un incendio en tu trabajo es conocer muy bien la diferencia y los riesgos de todos los comandos de Git.

## Resumen de comandos
- `git init`: lo usamos para determinar la carpeta en la que vamos a trabajar.
- `git status`: lo usamos para saber si tenemos un archivo añadido o borrado en nuestro proyecto, para saber en la rama en la que estamos y si tenemos commits.
- `git add`: es para añadir un archivo a nuestra rama seguidamente ponemos entre comillas el nombre de nuestro archivo o poner un punto para añadir todos los archios de nuestra carpeta.
- `git rm`: lo usamos para borrar un archivo que hayamos añadido, para eliminarlo por completo de nuestra rama usamosgit rm --cached.
- `git commit`: se usa para añadir un commit a nuestra rama, también podemos ponerle un `-m` seguidamente ponemos entre comillas nuestro ensaje.
- `git config`: muestra configuraciones de git también podemos usar `–list` para mostrar la configuración por defecto de nuestro git y si añadimos `--show-origin` nos muestra las configuraciones guardadas y su ubicación.
- `git config --global user.name`: cambia de manera global el nombre del usuario, seguidamente ponemos entre comillas nuestro nombre.
- `git config --global user.email`: cambia de manera global el email del usuario, seguidamente ponemos entre comillas nuestro nombre.
- `git log`: se usa para ver la historia de nuestros archivos, los commits, el usuario que lo cambió, cuando se realizaron los cambios etc. seguidamente ponemos el nombre de nuestro archivo.
- `git mv`: Para renombrar archivos o cambiarlos de ubicación dentro del repositorio.
