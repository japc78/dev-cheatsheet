---
title: "Java Spring"
tags: ""
---

# Java Spring

## Links
[Spring official website](https://spring.io/projects)

## ¿Qué es y qué usaremos de Spring?

Spring es el framework más usado de Java. Nos ofrece herramientas que nos permite crear proyectos más avanzados, con mejores prácticas y en menor tiempo. También posee una gran comunidad, lo que nos brinda muchísima documentación y ayuda.

Spring tiene una estructura modular y flexible, lo que nos hace usar solo lo que necesitemos.

Vamos a usar 4 subproyectos de Sping:

- Spring Framework: Permite crear aplicaciones empresariales. Es transversal, ya que todos lo usan. 
- Spring Boot: Con el que podemos crear aplicaciones autocontenidas y autoconfigurables.
- Spring Data: Gestionar e integrar bases de datos.
- Spring Security: Gestionar la seguridad de la aplicación.


## Conocer qué es una aplicación autocontenida

![](http://drive.google.com/uc?export=view&id=1GWtXqom0HLM28Wo4KVXuIx8pC_5GwAtF)

Spring Boot es el proyecto de Spring para aplicaciones autocontenidas, esto nos permite olvidarnos completamente de la infraestructura y centrarnos en el desarrollo, delegandole a spring boot tareas como configuración de dependencias,  
o despliegue de servicios. 

Spring Boot utiliza un servidor de aplicaciones embebido, por defecto, utiliza Tomcat pero tb es posible utilizar Jetty o Undertow.

Spring Boot tb nos ofrece un gestor completo de dependencias con Maven Upgrade, configuraciones automaticas y más.

## Crear nuestra aplicación con Spring Initializr
Spring Initializr es el sitio oficila de spring para crear aplicaciones autocontenidas. Desde aqui podemos crear nuestra propia aplicación utilizando las dependencias que necesitemos con muy pocos clicks.

## Configurar Spring Boot
[Common Application properties](https://docs.spring.io/spring-boot/docs/current/reference/html/appendix-application-properties.html)

application.properties es el archivo que nos permite gestionar la configuracion del proyecto. Tambien se puede utilizar de forma alternativa el archivo application.yml o desde la linea de comandos cuando se lance la aplicación.

Es posible añadir variables y atributos personalizadas para la configuración. 

Estos archivos nos ofrecen la capacidad de crear distintos perfiles acorde a los entornos donde se encuentre el proyecto, por ejemplo uno para desarrollo y otro para producción.


## Crear la estructura del proyecto

La estrcutrura usada en el proyecto Market es por capas y orientada al dominio, de la siguiente manera:
![](http://drive.google.com/uc?export=view&id=1tD65TSBV9IQl2w8euvLE1jxO3iXKOwsk)
![](http://drive.google.com/uc?export=view&id=1O3kW2aeSvKiaXM8O7YmXB45Oc8sGMBIr)



### 1. DOMINIO:
- DTO y objetos del dominio (Contexto de la aplicación)
- Servicios: Puente entre los controladores y la capa de persistencia.
- Especificación de repositorios: Interfaces que determinan las reglas que debe cumplir la persistencia para actuar entre los objetos de dominio y la DB.


### 2. WEB:
Controladores de API Rest.


### 3. PERSISTENCIA:
- Repositorios: Implementan las especificaciones que tiene la capa de DOMINIO.
- Entities: Mapean y actúan como tablas de la DB.

## ¿Qué es JPA?
Jpa es una especificación de Java, standar, para un framework ORM. Quiere decir que son uan serie de reglas que Java define para que cualquier framework que quierea interactura con la BD de Java, tenga que seguir.

Los frameworks mas populares de Java para este fin son:
- Hibernate
- TopLink
- EclipseLink
- ObjectDB

### Anotaciones JPA
JPA utiliza anotaciones para conectar clases a tablas de la BD y asi evitar hacerlo de manera nativa con SQL.

- `@Entity`. Indica a una clase de java que esta representando una tabla de nuestra BD.
- `@Table`. Recibe el nombre de la tabla a la cual esta mapeando la clase.
- `@column`. Se le pone a los atributos de la clase, no es obligatoria, se indica sólo cuando el nombre de la columna es diferente al nombre del atributo de la tabla.
- `@id` amd `@EmbededID`. Es el atributo como clave primaria de la tabla dentro de la clase. `@id` se utiliza cuando es clave primaria sencilla y `@EmbededID` cuando es una clave primaria compuesta.
- `@GeneratedValue`. Permite generar automáticamente generar valores para las clases primarias en nuestras clases
- `@OneToMany` and `@MatyToOne`. Representar relaciones

## Conocer qué es Spring Data
**Spring Data** NO es una implementacion de JPA, sino mas bien es un proyecto que usa JPA para ofrecer funcionalidaes extra en la gestion de tareas desde JAVA a las base de datos.

Spring Data internamente tiene varios subproyectos, entre ellos: **Spring Data JPA y Spring Data JDBC,** para conectarnos a BD relacionales (SQL). Spring Data MongoDB y Spring Data Cassandra, son proyectos para conectarnos a BD no relacionales.

La tarea principal de Spring Data es optimizar tareas repitivas. 

Spring data nos provee de respositorios sin codigo, nos permiten hacer todo tipo de operaciones en BD (CRUD) sin utilizar una linea de código.

También nos provee de auditorías transparentes, por ello, posee un motor de auditorias que nos permite saber cuadno se insertó un registro, cuando se borró, cuando se actualizo en la BD, etc.

### Implementación en el proyecto Market.
Se busca en MAVEN el repositorio Spring Boot Starter Data JPA, se copia el group y el name en las dependencias del archivo build.gradle de nuestro proyecto quedando de la siguiente manera.

```java
dependencies {
    //Dependencia agregada
	implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
	
    implementation 'org.springframework.boot:spring-boot-starter-web'
	testImplementation('org.springframework.boot:spring-boot-starter-test') {
		exclude group: 'org.junit.vintage', module: 'junit-vintage-engine'
	}
}
```

## Spring Data Repositories
Tres tipos de repositorios:

- **CrudRepository:** realizar el crue
- **PagingAndSortingRepository:** incluye lo de Crud repository ademas de paginación y ordenamiento.
- **JPARepository:** Ademas de tener CrudRepository y PagingAndSortingRepository nos permite tareas específicas como Flush (Combina o guarda todo en memoria sin que otras entidades o entornos vean esos cambios en la BD).

## Query Methods
[Query Methods](https://docs.spring.io/spring-data/jpa/docs/current/reference/html/#jpa.query-methods)
En ocaciones, necestiamos consultas que el Repository de Spring Data no nos puede ofrecer. Los Query Methods proveen la posibilidad de generar consultas mediante el nombre de los métodos. Tienen la posibilidad de retornar `Optional<T>`

Ejemplo
```sql
SELECT * FROM productos WHERE id_categoria = ? ORDER BY nombre ASC;
```

Con Query Methods
```java
findByIdcategoriaOrderByNombreAsc(int idCategoria)
```

Anotacion en la clase que interactura con la base de datos.

- @Repository: le indicamos a la clase que es la encarga de interactuar con la base de datos.
- @Component: le indicamos que es un componente de spring.

El primero es mejor porque indicamos el tipo de componente que es.
