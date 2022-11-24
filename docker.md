---
title: "Docker"
tags: ""
---

# Docker


```bash
docker run hello-world (corro el contenedor hello-world)
docker ps (muestra los contenedores activos)
docker ps -a (muestra todos los contenedores)
docker inspect <containe ID> (muestra el detalle completo de un contenedor)
docker inspect <name> (igual que el anterior pero invocado con el nombre)
docker run –-name hello-platzi hello-world (le asigno un nombre custom “hello-platzi”)
docker rename hello-platzi hola-platzy (cambio el nombre de hello-platzi a hola-platzi)
docker rm <ID o nombre> (borro un contenedor)
docker container prune (borro todos lo contenedores que esten parados)

docker run ubuntu (corre un ubuntu pero lo deja apagado)
docker ps -a (lista todos los contenedores)
docker -it ubuntu (lo corre y entro al shell de ubuntu)
# -i: interactivo
# -t: abre la consola
# -d: deja el contenedor activo en modo


docker run -d --name proxy nginx # (corro un nginx)
docker stop proxy #(apaga el contenedor)
docker rm proxy # (borro el contenedor)
docker rm -f <contenedor> #(lo para y lo borra)
docker run -d --name proxy -p 8080:80 nginx # (corro un nginx y expongo el puerto 80 del contenedor en el puerto 8080 de mi máquina) localhost:8080 (desde mi navegador compruebo que funcione)
docker logs proxy # (veo los logs)
docker logs -f proxy #(hago un follow del log)
docker logs --tail 10 -f proxy # (veo y sigo solo las 10 últimas entradas del log)


mkdir dockerdata #(creo un directorio en mi máquina)
docker run -d --name db mongo
docker ps #(veo los contenedores activos)
docker exec -it db bash #(entro al bash del contenedor)
mongo #(me conecto a la BBDD)

shows dbs #(listo las BBDD)
use platzi #( creo la BBDD platzi)
db.users.insert({“nombre”:“guido”}) #(inserto un nuevo dato)
db.users.find() #(veo el dato que cargué)
docker run -d --name db -v <path de mi maquina>:<path dentro del contenedor(/data/db mongo)> #(corro un contenedor de mongo y creo un bind mount)


$ docker volume ls (listo los volumes)
$ docker volume create dbdata (creo un volume)
$ docker run -d --name db --mount src=dbdata,dst=/data/db mongo (corro la BBDD y monto el volume)
$ docker inspect db (veo la información detallada del contenedor)
$ mongo (me conecto a la BBDD)

shows dbs (listo las BBDD)
use platzi ( creo la BBDD platzi)
db.users.insert({“nombre”:“guido”}) (inserto un nuevo dato)
db.users.find() (veo el dato que cargué)



$ mkdir imagenes (creo un directorio en mi máquina)
$ cd imagenes (entro al directorio)
$ touch Dockerfile (creo un Dockerfile)
$ code . (abro code en el direcotrio en el que estoy)

##Contenido del Dockerfile##
FROM ubuntu:latest
RUN touch /ust/src/hola-platzi.txt (comando a ejecutar en tiempo de build)
##fin##

$ docker build -t ubuntu:platzi . (creo una imagen con el contexto de build <directorio>)
$ docker run -it ubuntu:platzi (corro el contenedor con la nueva imagen)
$ docker login (me logueo en docker hub)
$ docker tag ubuntu:platzi miusuario/ubuntu:platzy (cambio el tag para poder subirla a mi docker hub)
$ docker push miusuario/ubuntu:platzi (publico la imagen a mi docker hub)



$ git clone https://github.com/platzi/docker
$ docker build platziapp . (creo la imagen local)
$ docker image ls (listo las imagenes locales)
$ docker run --rm -p 3000:3000 platziapp (creo el contenedor y cuando se detenga se borra, lo publica el puerto 3000)


```

## Windows 10 wsl

Desde windows los volumenes son creados en:
```bash
\\wsl$\docker-desktop-data\version-pack-data\community\docker\volumes\shared_data\_data
```
Al utilizar la integración WSL, docker crea dos ubicaciones
- docker-desktop
- docker-desktop-data

Se puede acceder a ellas mediante:
```bash
\\wsl$\docker-desktop
\\wsl$\docker-desktop-data

# images
$ docker image ls (veo las imágenes que tengo localmente)
$ docker pull ubuntu:20.04 (bajo la imagen de ubuntu con una versión específica)

```
