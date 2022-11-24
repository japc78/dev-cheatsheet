---
title: "Angular"
tags: ""
---

https://angular.io/api/core/ElementRef

## Ciclo de vida de un componente
ngOnInit. Cuando el componente esta inicializado.
ngOnChanges. cuando la data de las propiedades realacionadas cambian.
ngDoCheck. Durante cada revision del ciclo de deteccion de cambios.


## Para realizar peticiones HTTP
Modulo `HttpClienModule`


## CLI ANGULAR
```bash
#Crear App
ng new nombre_app

#Start app de angular
ng serve -o

# Crear componentes
# Modificadores opcionales
# skipTest=True no crea el fichero de especificaciones
# -is los stilos en el componente.
# -it el template en el mismo archivo
# --flat para que no cree la carpta de la ruta, util para crear elemetnos dentro de una misma carpta del componente
# --module=nombe_modulo_donde_importarlo
ng g c component/name_component --skipTests=true -is -it

## Crear app para produccion
## Previamente comprobar los arhicvos enviroment de la aplicacion.
ng build --prod


#Crear directivas
ng g d directives/name_directive

```

## Decoradores de Modulos
