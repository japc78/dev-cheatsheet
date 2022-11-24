---
title: "Git"
tags: ""
---

# Git

[Documentacion oficial](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Acerca-del-Control-de-Versiones)

Git es un software de control de versiones diseñado por Linus Torvalds, pensando en la eficiencia y la confiabilidad del mantenimiento de versiones de aplicaciones cuando estas tienen un gran número de archivos de código fuente. En su lugar GitHub es una forja para alojar proyectos utilizando el sistema de control de versiones Git. GitHub sería la red social de código para los programadores, tu propio curriculum vitae.

## ¿Por qué usar un sistema de control de versiones como Git?
Un sistema de control de versiones como Git nos ayuda a guardar el historial de cambios y crecimiento de los archivos de nuestro proyecto.

En realidad, los cambios y diferencias entre las versiones de nuestros proyectos pueden tener similitudes, algunas veces los cambios pueden ser solo una palabra o una parte específica de un archivo específico. Git está optimizado para guardar todos estos cambios de forma atómica e incremental, o sea, aplicando cambios sobre los últimos cambios, estos sobre los cambios anteriores y así hasta el inicio de nuestro proyecto.

- El comando para iniciar nuestro repositorio, o sea, indicarle a Git que queremos usar su sistema de control de versiones en nuestro proyecto, es `git init`.
- El comando para que nuestro repositorio sepa de la existencia de un archivo o sus últimos cambios es `git add`. Este comando no almacena las actualizaciones de forma definitiva, solo las guarda en algo que conocemos como “Staging Area” (no te preocupes, lo entenderemos más adelante).
- El comando para almacenar definitivamente todos los cambios que por ahora viven en el staging area es `git commit`. También podemos guardar un mensaje para recordar muy bien qué cambios hicimos en este commit con el argumento `-m "Mensaje del commit"`.
Por último, si queremos mandar nuestros commits a un servidor remoto, un lugar donde todos podamos conectar nuestros proyectos, usamos el comando `git push`.

## Flujo de trabajo básico con un repositorio remoto
No veas esta clase a menos que hayas practicado todos los comandos de las clases anteriores.

Por ahora, nuestro proyecto vive únicamente en nuestra computadora. Esto significa que no hay forma de que otros miembros del equipo trabajen en él.

Para solucionar esto están los servidores remotos: un nuevo estado que deben seguir nuestros archivos para conectarse y trabajar con equipos de cualquier parte del mundo.

Estos servidores remotos pueden estar alojados en GitHub, GitLab, BitBucket, entre otros. Lo que van a hacer es guardar el mismo repositorio que tienes en tu computadora y darnos una URL con la que todos podremos acceder a los archivos del proyecto para descargarlos, hacer cambios y volverlos a enviar al servidor remoto para que otras personas vean los cambios, comparen sus versiones y creen nuevas propuestas para el proyecto.

Esto significa que debes aprender algunos nuevos comandos:
- `git clone url_del_servidor_remoto`: Nos permite descargar los archivos de la última versión de la rama principal y todo el historial de cambios en la carpeta .git.
- `git push`: Luego de hacer `git add` y `git commit` debemos ejecutar este comando para mandar los cambios al servidor remoto.
- `git fetch`: Lo usamos para traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local (en caso de que hayan, por supuesto).
- `git merge`: También usamos el comando `git fetch` con servidores remotos. Lo necesitamos para combinar los últimos cambios del servidor remoto y nuestro directorio de trabajo.
- `git pull`: Básicamente, `git fetch` y `git merge` al mismo tiempo.

### Algunos comandos que pueden ayudar cuando colaboren con proyectos muy grandes de github:
- git log --oneline - Te muestra el id commit y el título del commit.
- git log --decorate- Te muestra donde se encuentra el head point en el log.
- git log --stat - Explica el número de líneas que se cambiaron brevemente.
- git log -p- Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
- git shortlog - Indica que commits ha realizado un usuario, mostrando el usuario y el titulo de sus commits.
- git log --graph --oneline --decorate y
- git log --pretty=format:"%cn hizo un commit %h el dia %cd" - Muestra mensajes personalizados de los commits.
- git log -3 - Limitamos el número de commits.
- git log --after=“2018-1-2” ,
- git log --after=“today” y
- git log --after=“2018-1-2” --before=“today” - Commits para localizar por fechas.
- git log --author=“Name Author” - Commits realizados por autor que cumplan exactamente con el nombre.
- git log --grep=“INVIE” - Busca los commits que cumplan tal cual está escrito entre las comillas.
- git log --grep=“INVIE” –i- Busca los commits que cumplan sin importar mayúsculas o minúsculas.
- git log – index.html- Busca los commits en un archivo en específico.
- git log -S “Por contenido”- Buscar los commits con el contenido dentro del archivo.
- git log > log.txt - guardar los logs en un archivo txt

## Introducción a las ramas o branches de Git
Las ramas son la forma de hacer cambios en nuestro proyecto sin afectar el flujo de trabajo de la rama principal. Esto porque queremos trabajar una parte muy específica de la aplicación o simplemente experimentar.

La cabecera o HEAD representan la rama y el commit de esa rama donde estamos trabajando. Por defecto, esta cabecera aparecerá en el último commit de nuestra rama principal. Pero podemos cambiarlo al crear una rama (`git branch rama, git checkout -b rama`) o movernos en el tiempo a cualquier otro commit de cualquier otra rama con los comandos (`git reset id-commit, git checkout rama-o-id-commit`).


### Fusión de ramas con Git merge
El comando `git merge` nos permite crear un nuevo commit con la combinación de dos ramas (la rama donde nos encontramos cuando ejecutamos el comando y la rama que indiquemos después del comando).

```bash
# Crear un nuevo commit en la rama master combinando
# los cambios de la rama cabecera:
git checkout master
git merge cabecera

# Crear un nuevo commit en la rama cabecera combinando
# los cambios de cualquier otra rama:
git checkout cabecera
git merge cualquier-otra-rama
```

Asombroso, ¿verdad? Es como si Git tuviera super poderes para saber qué cambios queremos conservar de una rama y qué otros de la otra. El problema es que no siempre puede adivinar, sobretodo en algunos casos donde dos ramas tienen actualizaciones diferentes en ciertas líneas en los archivos. Esto lo conocemos como un conflicto y aprenderemos a solucionarlos en la siguiente clase.

Recuerda que al ejecutar el comando `git checkout` para cambiar de rama o commit puedes perder el trabajo que no hayas guardado. **Guarda tus cambios antes de hacer git checkout.**

### Resolución de conflictos al hacer un merge
Git nunca borra nada a menos que nosotros se lo indiquemos. Cuando usamos los comandos `git merge` o `git checkout` estamos cambiando de rama o creando un nuevo commit, no borrando ramas ni commits (recuerda que puedes borrar commits con `git reset` y ramas con `git branch -d`.

Git es muy inteligente y puede resolver algunos conflictos automáticamente: cambios, nuevas líneas, entre otros. Pero algunas veces no sabe cómo resolver estas diferencias, por ejemplo, cuando dos ramas diferentes hacen cambios distintos a una misma línea.

Esto lo conocemos como conflicto y lo podemos resolver manualmente, solo debemos hacer el merge, ir a nuestro editor de código y elegir si queremos quedarnos con alguna de estas dos versiones o algo diferente. Algunos editores de código como VSCode nos ayudan a resolver estos conflictos sin necesidad de borrar o escribir líneas de texto, basta con hundir un botón y guardar el archivo.

Recuerda que **siempre debemos crear un nuevo commit para aplicar los cambios del merge.** Si Git puede resolver el conflicto hará commit automáticamente. Pero, en caso de no pueda resolverlo, debemos solucionarlo y hacer el commit.

**Los archivos con conflictos por el comando `git merge` entran en un nuevo estado que conocemos como Unmerged.** Funcionan muy parecido a los archivos en estado Unstaged, algo así como un estado intermedio entre Untracked y Unstaged, solo debemos ejecutar `git add` para pasarlos al área de **staging** y `git commit` para aplicar los cambios en el repositorio.


## Uso de GitHub
GitHub es una plataforma que nos permite guardar repositorios de Git que podemos usar como servidores remotos y ejecutar algunos comandos de forma visual e interactiva (sin necesidad de la consola de comandos).

Luego de crear nuestra cuenta, podemos crear o importar repositorios, crear organizaciones y proyectos de trabajo, descubrir repositorios de otras personas, contribuir a esos proyectos, dar estrellas y muchas otras cosas.

El `README.md` es el archivo que veremos por defecto al entrar a un repositorio. Es una muy buena práctica configurarlo para describir el proyecto, los requerimientos y las instrucciones que debemos seguir para contribuir correctamente.

Para clonar un repositorio desde GitHub (o cualquier otro servidor remoto) debemos copiar la URL (por ahora, usando HTTPS) y ejecutar el comando `it clone + la URL` que acabamos de copiar. Esto descargara la versión de nuestro proyecto que se encuentra en GitHub.

Sin embargo, esto solo funciona para las personas que quieren empezar a contribuir en el proyecto. Si queremos conectar el repositorio de GitHub con nuestro repositorio local, el que creamos con git init, debemos ejecutar las siguientes instrucciones:

```bash
# Primero: Guardar la URL del repositorio de GitHub
# con el nombre de origin
git remote add origin URL

# Segundo: Verificar que la URL se haya guardado
# correctamente:
git remote
git remote -v

# Tercero: Traer la versión del repositorio remoto y
# hacer merge para crear un commit con los archivos
# de ambas partes. Podemos usar git fetch y git merge
# o solo el git pull con el flag --allow-unrelated-histories:
git pull origin master --allow-unrelated-histories

# Por último, ahora sí podemos hacer git push para guardar
# los cambios de nuestro repositorio local en GitHub:
git push origin master
```


## Cómo funcionan las llaves públicas y privadas
Las llaves públicas y privadas nos ayudan a cifrar y descifrar nuestros archivos de forma que los podamos compartir sin correr el riesgo de que sean interceptados por personas con malas intenciones.

La forma de hacerlo es la siguiente:

1. Ambas personas deben crear su llave pública y privada.
2. Ambas personas pueden compartir su llave pública a las otras partes (recuerda que esta llave es pública, no hay problema si la “interceptan”).
3. La persona que quiere compartir un mensaje puede usar la llave pública de la otra persona para cifrar los archivos y asegurarse que solo puedan ser descifrados con la llave privada de la persona con la que queremos compartir el mensaje. El mensaje está cifrado y puede ser enviado a la otra persona sin problemas en caso de que los archivos sean interceptados.
4. La persona a la que enviamos el mensaje cifrado puede usar su llave privada para descifrar el mensaje y ver los archivos.
5. Puedes compartir tu llave pública pero nunca tu llave privada.

En la siguiente clase vamos a crear nuestras llaves para compartir archivos con GitHub sin correr el riesgo de que sean interceptados.

### Configura tus llaves SSH en local
1. Primer paso: Generar tus llaves SSH. Recuerda que es muy buena idea proteger tu llave privada con una contraseña.

```bash 
ssh-keygen -t rsa -b 4096 -C "tu@email.com"
```
2. Segundo paso: Terminar de configurar nuestro sistema.
**En Windows y Linux:**
```bash
# Encender el "servidor" de llaves SSH de tu computadora:
eval $(ssh-agent -s)

# Añadir tu llave SSH a este "servidor":
ssh-add ruta-donde-guardaste-tu-llave-privada
```
**En Mac:**
```bash
# Encender el "servidor" de llaves SSH de tu computadora:
eval "$(ssh-agent -s)"

# Si usas una versión de OSX superior a Mac Sierra (v10.12)
# debes crear o modificar un archivo "config" en la carpeta
# de tu usuario con el siguiente contenido (ten cuidado con
# las mayúsculas):
Host *
        AddKeysToAgent yes
        UseKeychain yes
        IdentityFile ruta-donde-guardaste-tu-llave-privada

# Añadir tu llave SSH al "servidor" de llaves SSH de tu
# computadora (en caso de error puedes ejecutar este
# mismo comando pero sin el argumento -K):
ssh-add -K ruta-donde-guardaste-tu-llave-privada
```


### Conexión a GitHub con SSH
Luego de crear nuestras llaves SSH podemos entregarle la llave pública a GitHub para comunicarnos de forma segura y sin necesidad de escribir nuestro usuario y contraseña todo el tiempo.

Para esto debes entrar a la Configuración de Llaves SSH en GitHub, crear una nueva llave con el nombre que le quieras dar y el contenido de la llave pública de tu computadora.

Ahora podemos actualizar la URL que guardamos en nuestro repositorio remoto, solo que, en vez de guardar la URL con HTTPS, vamos a usar la URL con SSH:
```bash
git remote set-url origin url-ssh-del-repositorio-en-github
```

### Tags y versiones en Git y GitHub
Los tags o etiquetas nos permiten asignar versiones a los commits con cambios más importantes o significativos de nuestro proyecto.

Comandos para trabajar con etiquetas:
- Crear un nuevo tag y asignarlo a un commit: `git tag -a nombre-del-tag id-del-commit`.
- Borrar un tag en el repositorio local: `git tag -d nombre-del-tag`.
- Listar los tags de nuestro repositorio local: `git tag o git show-ref --tags`.
- Publicar un tag en el repositorio remoto: `git push origin --tags`.
- Borrar un tag del repositorio remoto: `git tag -d nombre-del-tag` y `git push origin :refs/tags/nombre-del-tag`.

### Manejo de ramas en GitHub
Puedes trabajar con ramas que nunca envías a GitHub, así como pueden haber ramas importantes en GitHub que nunca usas en el repositorio local. Lo importante es que aprendas a manejarlas para trabajar profesionalmente.

Crear una rama en el repositorio local: `git branch nombre-de-la-rama o git checkout -b nombre-de-la-rama`.
Publicar una rama local al repositorio remoto: `git push origin nombre-de-la-rama`.
Recuerda que podemos ver gráficamente nuestro entorno y flujo de trabajo local con Git usando el comando `gitk`.

### Configurar múltiples colaboradores en un repositorio de GitHub
Por defecto, cualquier persona puede clonar o descargar tu proyecto desde GitHub, pero no pueden crear commits, ni ramas, ni nada.

Existen varias formas de solucionar esto para poder aceptar contribuciones. Una de ellas es añadir a cada persona de nuestro equipo como colaborador de nuestro repositorio.

Solo debemos entrar a la configuración de colaboradores de nuestro proyecto **(Repositorio > Settings > Collaborators)** y añadir el email o username de los nuevos colaboradores.

### Flujo de trabajo profesional con Pull requests
En un entorno profesional normalmente se bloquea la rama master, y para enviar código a dicha rama pasa por un code review y luego de su aprobación se unen códigos con los llamados merge request.

Para realizar pruebas enviamos el código a servidores que normalmente los llamamos **staging develop** (servidores de pruebas) luego de que se realizan las pruebas pertinentes tanto de código como de la aplicación estos pasan a el servidor de producción con el ya antes mencionado merge request.


### Pull request:
Es una funcionalidad de github (en gitlab llamada **merge request** y en bitbucket **push request**), en la que un colaborador pide que revisen sus cambios antes de hacer merge a una rama, normalmente master.

Al hacer un pull request se genera una conversación que pueden seguir los demás usuarios del repositorio, así como autorizar y rechazar los cambios.

#### El flujo del pull request es el siguiente

- Se trabaja en una **rama paralela** los cambios que se desean (`git checkout -b <rama>`)
- Se hace un **commit a la rama** (`git commit -am '<Comentario>'`)
- Se **suben al remoto los cambios** (`git push origin <rama>`)
- En GitHub se hace el **pull request comparando la rama master con la rama** del fix.
- Uno, o varios colaboradores revisan que el código sea correcto y dan feedback (en el chat del pull request)
- El colaborador hace los cambios que desea en la rama y lo vuelve a subir al remoto (automáticamente jala la historia de los cambios que se hagan en la rama, en remoto)
- Se aceptan los cambios en GitHub
- Se hace merge a master desde GitHub
    
**Importante:** Cuando se modifica una rama, también se modifica el pull request.


## Forks o Bifurcaciones
Es una característica única de GitHub en la que se crea una copia exacta del estado actual de un repositorio directamente en GitHub, éste repositorio podrá servir como otro origen y se podrá clonar (como cualquier otro repositorio), en pocas palabras, lo podremos utilizar como un git cualquiera

**Un fork** es como una bifurcación del repositorio completo, tiene una historia en común, pero de repente se bifurca y pueden variar los cambios, ya que ambos proyectos podrán ser modificados en paralelo y para estar al día un colaborador tendrá que estar actualizando su fork con la información del original.

Al hacer un fork de un poryecto en GitHub, te conviertes en dueñ@ del repositorio fork, puedes trabajar en éste con todos los permisos, pero es un repositorio completamente diferente que el original, teniendo alguna historia en común.

Los forks son importantes porque es la manera en la que funciona el open source, ya que, una persona puede no ser colaborador de un proyecto, pero puede contribuír al mismo, haciendo mejor software que pueda ser utilizado por cualquiera.

Al hacer un fork, GitHub sabe que se hizo el fork del proyecto, por lo que se le permite al colaborador hacer pull request desde su repositorio propio.

### Trabajando con más de 1 repositorio remoto
Cuando trabajas en un proyecto que existe en diferentes repositorios remotos (normalmente a causa de un fork) es muy probable que desees poder trabajar con ambos repositorios, para ésto puedes crear un remoto adicional desde consola.

```bash
git remote add <nombre_del_remoto> <url_del_remoto> 
git remote upstream https://github.com/freddier/hyperblog
```

Al crear un remoto adicional podremos, hacer pull desde el nuevo origen (en caso de tener permisos podremos hacer fetch y push)

```bash
git pull <remoto> <rama>
git pull upstream master
```

Éste pull nos traerá los cambios del remoto, por lo que se estará al día en el proyecto, el flujo de trabajo cambia, en adelante se estará trabajando haciendo pull desde el upstream y push al origin para pasar a hacer pull request.

```bash
git pull upstream master
git push origin master
```

## Ignorar archivos en el repositorio con `.gitignore`

[Git - gitignore Documentation](https://git-scm.com/docs/gitignore)

No todos los archivos que agregas a un proyecto deberían ir a un repositorio, por ejemplo cuando tienes un archivo donde están tus contraseñas que comúnmente tienen la extensión .env o cuando te estás conectando a una base de datos; son archivos que nadie debe ver.

## Readme.md es una excelente práctica
`README.md` es una excelente práctica en tus proyectos, md significa Markdown, que es una especie de código que te permite cambiar la manera en que se ve un archivo de texto.

Lo interesante de Markdown es que funciona en muchas páginas, por ejemplo la edición en Wikipedia; es un lenguaje intermedio que no es HTML, no es texto plano, es una manera de crear excelentes texto formateados.

## Git Rebase: reorganizando el trabajo realizado
**El comando rebase es una mala práctica, nunca se debe usar,** pero para efectos del curso te lo vamos a enseñar para que hagas tus propios experimentos. **Con rebase puedes recoger todos los cambios confirmados en una rama y ponerlos sobre otra.**

Cambiamos a la rama que queremos traer los cambios

```bash
git checkout experiment
# Aplicamos rebase para traer los cambios de la rama que queremos 
git rebase master
```


## Git Stash: Guardar cambios en memoria y recuperarlos después

Cuando necesitamos regresar en el tiempo porque borramos alguna línea de código pero no queremos pasarnos a otra rama porque nos daría un error ya que debemos pasar ese “mal cambio” que hicimos a stage, podemos usar `git stash` para regresar el cambio anterior que hicimos.

`git stash` es típico cuando estamos cambios que no merecen una rama o no merecen un rebase si no simplemente estamos probando algo y luego quieres volver rápidamente a tu versión anterior la cual es la correcta.


### Stashed:
El stashed nos sirve para guardar cambios para después, Es una lista de estados que nos guarda algunos cambios que hicimos en Staging para poder cambiar de rama sin perder el trabajo que todavía no guardamos en un commit

Ésto es especialmente útil porque hay veces que no se permite cambiar de rama, ésto porque porque tenemos cambios sin guardar, no siempre es un cambio lo suficientemente bueno como para hacer un commit, pero no queremos perder ese código en el que estuvimos trabajando.

El stashed nos permite cambiar de ramas, hacer cambios, trabajar en otras cosas y, más adelante, retomar el trabajo con los archivos que teníamos en Staging pero que podemos recuperar ya que los guardamos en el Stash.

### git stash
El comando `git stash` guarda el trabajo actual del Staging en una lista diseñada para ser temporal llamada **Stash,** para que pueda ser recuperado en el futuro.

Para agregar los cambios al stash se utiliza el comando: `git stash`

Podemos poner un mensaje en el stash, para asi diferenciarlos en git stash list por si tenemos varios elementos en el stash. Ésto con:

```bash 
git stash save "mensaje identificador del elemento del stashed"

```

### Obtener elelmentos del stash
El stashed se comporta como una Stack de datos comportándose de manera tipo LIFO (del inglés Last In, First Out, «último en entrar, primero en salir»), así podemos acceder al método pop.

El método pop recuperará y sacará de la lista el último estado del stashed y lo insertará en el staging area, por lo que es importante saber en qué branch te encuentras para poder recuperarlo, ya que el stash será agnóstico a la rama o estado en el que te encuentres, siempre recuperará los cambios que hiciste en el lugar que lo llamas.

Para recuperar los últimos cambios desde el stash a tu staging area utiliza el comando: `git stash pop`

Para aplicar los cambios de un stash específico y eliminarlo del stash:

```bash 
git stash pop stash@{<num_stash>}
```

Para retomar los cambios de una posición específica del Stash puedes utilizar el comando:

```bash 
git stash apply stash@{<num_stash>}

```

Donde el `<num_stash>` lo obtienes desden el git stash list

### Listado de elementos en el stash

Para ver la lista de cambios guardados en Stash y así poder recuperarlos o hacer algo con ellos podemos utilizar el comando: `git stash list`


Retomar los cambios de una posición específica del Stash || Aplica los cambios de un stash específico

### Crear una rama con el stash
Para crear una rama y aplicar el stash mas reciente podemos utilizar el comando
```bash
git stash branch <nombre_de_la_rama>
```
Si deseas crear una rama y aplicar un stash específico (obtenido desde git stash list) puedes utilizar el comando:

```bash
git stash branch nombre_de_rama stash@{<num_stash>}
```
Al utilizar estos comandos crearás una rama con el nombre `<nombre_de_la_rama>`, te pasarás a ella y tendrás el stash especificado en tu staging area.

### Eliminar elementos del stash
Para eliminar los cambios más recientes dentro del stash (el elemento 0), podemos utilizar el comando: `git stash drop`

Pero si en cambio conoces el índice del stash que quieres borrar (mediante git stash list) puedes utilizar el comando:

```bash
git stash drop stash@{<num_stash>}
```

Donde el `<num_stash>` es el índice del cambio guardado.

Si en cambio deseas eliminar todos los elementos del stash, puedes utilizar: `
git stash clear` 

### Consideraciones:
El cambio más reciente (al crear un stash) SIEMPRE recibe el valor 0 y los que estaban antes aumentan su valor.
Al crear un stash tomará los archivos que han sido modificados y eliminados. Para que tome un archivo creado es necesario agregarlo al Staging Area con `git add [nombre_archivo]` con la intención de que git tenga un seguimiento de ese archivo, o también utilizando el comando `git stash -u` (que guardará en el stash los archivos que no estén en el staging).

**Al aplicar un stash este no se elimina, es buena práctica eliminarlo**


## Git Clean: limpiar tu proyecto de archivos no deseados
A veces creamos archivos cuando estamos realizando nuestro proyecto que realmente no forman parte de nuestro directorio de trabajo, que no se deberían agregar y lo sabemos.

- Para saber qué archivos vamos a borrar tecleamos `git clean --dry-run`
- Para borrar todos los archivos listados (que no son carpetas) tecleamos `git clean -f`


## Git cherry-pick: traer commits viejos al head de un branch
Existe un mundo alternativo en el cual vamos avanzando en una rama pero necesitamos en master uno de esos avances de la rama, para eso utilizamos el comando `git cherry-pick IDCommit.`

> cherry-pick es una mala práctica porque significa que estamos reconstruyendo la historia, usa cherry-pick con sabiduría. Si no sabes lo que estás haciendo ten mucho cuidado.

## Reconstruir commits en Git con amend
A veces hacemos un commit, pero resulta que no queríamos mandarlo porque faltaba algo más. Utilizamos `git commit --amend`, amend en inglés es remendar y lo que hará es que los cambios que hicimos nos los agregará al commit anterior.

## Git Reset y Reflog: úsese en caso de emergencia
¿Qué pasa cuando todo se rompe y no sabemos qué está pasando? Con `git reset HashDelHEAD` nos devolveremos al estado en que el proyecto funcionaba.

- `git reflog`Muestra el historial  de registros de git. Podemos ver la referencia para luego utilizarlo con `git reset` y recuperar desde ese registro.
- `git reset --soft` HashDelHEAD te mantiene lo que tengas en staging ahí.
- `git reset --hard` HashDelHEAD resetea absolutamente todo incluyendo lo que tengas en staging.

**`git reset` es una mala práctica, no deberías usarlo en ningún momento; debe ser nuestro último recurso.**


## Buscar en archivos y commits de Git con Grep y log
A medida que nuestro proyecto se hace grande vamos a querer buscar ciertas cosas.

Por ejemplo: ¿cuántas veces en nuestro proyecto utilizamos la palabra color?

Para buscar utilizamos el comando `git grep color` y nos buscará en todo el proyecto los archivos en donde está la palabra color.

- Con `git grep -n color` nos saldrá un output el cual nos dirá en qué línea está lo que estamos buscando.
- Con `git grep -c color` nos saldrá un output el cual nos dirá cuántas veces se repite esa palabra y en qué archivo.
- Si queremos buscar cuántas veces utilizamos un atributo de HTML lo hacemos con `git grep -c "<p>"`.

### Ejemplo
- `git grep color` -> use la palabra color
- `git grep la` -> donde use la palabra la
- `git grep -n color` –> en que lineas use la palabra color
- `git grep -n platzi` -> en que lineas use la palabra platzi
- `git grep -c la` -> cuantas veces use la palabra la
- `git grep -c paltzi` -> cuantas veces use la palabra platzi
- `git grep -c “<p>”` -> cuantas veces use la etiqueta `<p>`
- `git log-S “cabecera”` -> cuantas veces use la palabra cabecera en todos los commits.
- `grep` –> para los archivos
- `log` --> para los commits.

## Comandos y recursos colaborativos en Git y GitHub
[Git - git-blame Documentation](https://git-scm.com/docs/git-blame)

- `git shortlog -sn` = muestra cuantos commit han hecho cada miembros del equipo.
- `git shortlog -sn --all` = muestra cuantos commit han hecho cada miembros del equipo hasta los que han sido eliminado
- `git shortlog -sn --all --no-merge` = muestra cuantos commit han hecho cada miembros quitando los eliminados sin los merges
- `git blame ARCHIVO` = muestra quien hizo cada cosa linea por linea
- `git COMANDO --help` = muestra como funciona el comando.
- `git blame ARCHIVO -Llinea_inicial,linea_final` = muestra quien hizo cada cosa linea por linea indicándole desde que linea ver ejemplo -L35,50
- **`git branch -r` **= se muestran todas las ramas remotas
- `git branch -a` = se muestran todas las ramas tanto locales como remotas

## Links
- [Aprende Git con Bitbucket Cloud](https://www.atlassian.com/es/git/tutorials/learn-git-with-bitbucket-cloud)
-[Fusión frente a reorganización](https://www.atlassian.com/es/git/tutorials/merging-vs-rebasing)
