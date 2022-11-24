---
title: "Databases"
tags: ""
---

# Database

- [12 reglas del modelo relacional](https://www.mindmeister.com/es/1079684487/las-12-reglas-de-codd-del-modelo-relacional?fullscreen=1)
- [¿Qué es DDL, DML, DCL y TCL? + Integridad Referencial](https://platzi.com/blog/que-es-ddl-dml-dcl-y-tcl-integridad-referencial/)
- [generatedata.com - Generar datos en tablas, dummy data](https://www.generatedata.com/)
- [¿Que tipos de base de datos existes actualmente?](https://platzi.com/tutoriales/1566-bd/2282-que-tipos-de-base-de-datos-existes-actualmente/)


### Bases de datos relacionales (RBD)

Es importante que sea fácil de guardar y extraer, anteriormente se usaban bases de datos basadas en archivos, el cuál era texto plano fácil de guardar, pero difícil de extraer, por esto se inventaron las bases de datos relacionales. En 1990 Codd se preocupó porque los sistemas de gestión de bases de datos (SGBD) que decían ser relacionales, no lo eran. En la práctica es difícil cumplir las 12 pero, un SGBD es más relacional cuantas más reglas cumpla

## Las Reglas y mandamientos de Edgar Frank Ted Codd

- Regla 0: Regla de fundación.
	- Cualquier sistema que se proclame como relacional, debe ser capaz de gestionar sus bases de datos enteramente mediante sus capacidades relacionales.

- Regla 1: Regla de la información.
	- Todos los datos deben estar almacenados en las tablas
	- Esas tablas deben cumplir las premisas del modelo relacional
	- No puede haber información a la que accedemos por otra vía

- Regla 2: Regla del acceso garantizado.
	- Cualquier dato es accesible sabiendo la clave de su fila y el nombre de su columna o atributo
	- Si a un dato no podemos acceder de esta forma, no estamos usando un modelo relacional

- Regla 3: Regla del tratamiento sistemático de valores nulos.
    - Esos valores pueden dar significado a la columna que los contiene
    - El SGBD debe tener la capacidad de manejar valores nulos
    - El SGBD reconocerá este valor diferenciándolo de cualquier otro
    - El SGBD deberá aplicársele la lógica apropiada
    - Es un valor independiente del tipo de datos de la columna

- Regla 4: Catálogo dinámico en línea basado en el modelo relacional.
	- El catálogo en línea es el diccionario de datos
	- El diccionario de datos se debe de poder consultar usando las mismas técnicas que para los datos
	- Los metadatos, por tanto, se organizan también en tablas relacionales
	- Si SELECT es una instrucción que consulta datos, también será la que consulta los metadatos

- Regla 5: Regla comprensiva del sublenguaje de los datos completo.
	- Al menos tiene que existir un lenguaje capaz de hacer todas las funciones del SGBD
	- No puede haber funciones fuera de ese lenguaje
	- Puede haber otros lenguajes en el SGBD para hacer ciertas tareas
	- Pero esas tareas también se deben poder hacer con el “lenguaje completo”

- Regla 6: Regla de actualización de vistas.
    - Las vistas tienen que mostrar información actualizada
    - No puede haber diferencias entre los datos de las vistas y los datos de las tablas base

- Regla 7: Alto nivel de inserción, actualización, y cancelación.
    - La idea es que el lenguaje que maneja la base de datos sea muy humano
    - Eso implica que las operaciones del lenguaje de manipulación de los datos (DML) trabajen con conjuntos de filas a la vez
    - Para modificar, eliminar o añadir datos, no hará falta programar de la forma en la que lo hacen los lenguajes de tercera generación como C o Java

- Regla 8: Independencia física de los datos.
    - Cambios en la física de la BD no afecta a las aplicaciones ni a los esquemas lógicos
    - El acceso a las tablas (elemento lógico) no cambia porque la física de la base de datos cambie

- Regla 9: Independencias lógicas de los datos.
    - Cambios en el esquema lógico (tablas) de la BD no afectan al resto de esquemas
    - Si cambiamos nombres de tabla, o de columna o modificamos información de las filas, las aplicaciones (esquema externo) no se ven afectadas
    - Es más difícil de conseguir

- Regla 10: Independencia de la integridad.
	- Las reglas de integridad (restricciones) deben de ser gestionadas y almacenadas por el SGBD

- Regla 11: Independencia de la distribución.
    - Que la base de datos se almacene o gestione de forma distribuida en varios servidores, no afecta al uso de esta ni a la programación de las aplicaciones de usuario
    - El esquema lógico es el mismo independientemente de si la BD es distribuida o no

- Regla 12: La regla de la no subversión.
	- La base de datos no permitirá que exista un lenguaje o forma de acceso, que permita saltarse las reglas anteriores

### Entidades y atributos
Una entidad es algo similar a un objeto (programación orientada a objetos) y representa algo en el mundo real, incluso algo abstracto. Tienen atributos que son las cosas que los hacen ser una entidad y por convención se ponen en plural.

Los **atributos compuestos** son aquellos que tienen atributos ellos mismos.

**Los atributos llave** son aquellos que identifican a la entidad y no pueden ser repetidos. Existen:

- Naturales: Son inherentes al objeto como el número de serie
- Clave artificial: No es inherente al objeto y se asigna de manera arbitraria.

**Entidades débiles:** No pueden existir sin una entidad fuerte y se representan con un cuadrado con doble línea.

- Identidades débiles por identidad: No se diferencian entre sí más que por la clave de su - identidad fuerte.
- Identidades débiles por existencia: Se les asigna una clave propia.

![notaciones chen](http://drive.google.com/uc?export=view&id=1W2GLGepzXcwF5hjq8upg3WNHo8mle1r7)

## Relaciones
Las relaciones, representadas por un rombo, sirven para crear relaciones entre entidades. Por convención las relaciones son verbos que conectan entidades. Existen entidades multivaluadas o compuestas que tienen vida propia y se relacionan con otras entidades, por lo que se pueden normalizar (concepto que se explicará luego)

### Cardinalidad

Es una propiedad de las relaciones que indica la cantidad y correspondencia con la que puede estar relacionada una entidad y puede ser uno a uno, uno a varios, varios a uno y varios a varios.

![](http://drive.google.com/uc?export=view&id=1SMwvRXiHWGo1GG_TWnCKhdgWeagSRAhy)

## Diagrama físico: tipos de datos y constrains
Para llevar a la práctica un diagrama debemos ir más allá y darle detalle con parámetros como:

### Tipos de dato:

- Texto: 
	- CHAR(n) Char(n) Permite almacenar caracteres y cadenas de texto. Este tipo de dato reserva un espacio de memoria del número de caracteres que va a ser ocupado.
	- VARCHAR(n) Varchar(n) Al igual que char, este reserva espacio en la memoria. Su diferencia radica en que este reserva un mínimo espacio de memoria, y a partir de esta va creciendo o encogiéndose, es eficiente cuando desconocés cual será el tamaño de tu cadena de texto (Su limite es de 255 caracteres).
	- TEXT. Text Su función es guardar cadenas de texto que sean muuuuuy grandes.
- Números: 
	- INTEGER. Número que no tiene punto decimal, se usa para declarar un tipo de dato entero que puede ser usado para hacer operaciones.?Al usar este tipo de dato nuestra base de datos sabrá que estamos hablando de número y no solo de un simple carácter.
	- BIGINT. Es un subtipo de integer, nos sirve para declarar números muy grandes.
	- SMALLINT. Subtipo de integer, nos para declarar números muy pequeños (99 o menos).
	- DECIMAL(n,s), NUMERIC(n,s) Tiene dos parámetros (n y s, en este ejemplo). La primera entrada es para números enteros, y la segunda entrada es para números decimales.?Nos sirve para hacer operaciones mas precisas.
- Fecha/hora: 
	- DATE. Solo contiene la fecha (año, mes y día)
	- TIME. Solo contiene la hora.
	- DATETIME.  Es una mezcla de los dos primeros, contiene fecha y hora.
	- TIMESTAMP.  Es el número de segundos que ha transcurrido desde que tu archivo fue creado.?En otras palabras, podría decirse que es un medidor de tiempo.
- Lógicos:
	-  BOOLEAN. Este solo puede tener dos valores, funciona como un tipo de dato binario.?Es usado de manera discriminatoria para hacer validaciones.

### Constraints (Restricciones)
- NOT NULL: Se asegura que la columna no tenga valores nulos
- UNIQUE: Se asegura que cada valor en la columna no se repita
- PRIMARY KEY: Es una combinación de NOT NULL y UNIQUE
- FOREIGN KEY: Identifica de manera única una tupla en otra tabla
- CHECK: Se asegura que el valor en la columna cumpla una condición dada
- DEFAULT: Coloca un valor por defecto cuando no hay un valor especificado
- INDEX: Se crea por columna para permitir búsquedas más rápidas

![](http://drive.google.com/uc?export=view&id=13RtLjdz13AThUEODu7qWYB5Rv3WKlU_a)

## Normalización
La normalización como su nombre lo indica nos ayuda a dejar todo de una forma normal. Esto obedece a las 12 reglas de Codd y nos permiten separar componentes en la base de datos:

- Primera forma normal (1FN): Atributos atómicos (Sin campos repetidos)
- Segunda forma normal (2FN): Cumple 1FN y cada campo de la tabla debe depender de una clave única.
- Tercera forma normal (3FN): Cumple 1FN y 2FN y los campos que NO son clave, NO deben tener dependencias.
- Cuarta forma normal (4FN): Cumple 1FN, 2FN, 3FN y los campos multivaluados se identifican por una clave única.
![](http://drive.google.com/uc?export=view&id=1Rws3RwkEkgYd6pKWbTcr9KDOwYbkqDdM)
![](http://drive.google.com/uc?export=view&id=1lvK2VdVCOGrNmrgU-O17cW9l38k67-vY)
![](http://drive.google.com/uc?export=view&id=1QdEnG_ebuOFNZyLos0y44fvNsFPBCoFP)
![](http://drive.google.com/uc?export=view&id=1cGPyUEKkWiaRGKQbXbxlj3GgXP-Ohh2M)

## RDB ¿Qué?
RDB (relational database)
RDBMS significa Relational Database Management System o sistema manejador de bases de datos relacionales. Es un programa que se encarga de seguir las reglas de Codd y se puede utilizar de manera programática. Ej. MySQL, PostgreSQL, Etc... Todas toman un lenguaje base, pero cada uno lo apropia, imponiéndole diferentes reglas y características.

La diferencia entre ambos es que las BBDD son un conjunto de datos pertenecientes ( o al menos en teoría) a un mismo tipo de contexto, que guarda los datos de forma persistente para un posterior uso, y el Sistema de gestión de BBDD o sistema manejador, es el que nos permite acceder a ella, es un software, herramienta que sirve de conexión entre las BBDD y el usuario (nos presenta una interfaz para poder gestionarla, manejarla).

## Historia de SQL
SQL es un lenguaje de acceso a bases de datos que explota la flexibilidad y potencia de los sistemas relacionales y permite así gran variedad de operaciones.

- SQL es un estándar aceptado por ANSI (Instituto Nacional Estadounidense de Estándares)
- PL/SQL es un lenguaje de programación de la base de datos de Oracle, el nombre viene de Procedural Language/Structured Query Language
- T-SQL es un lenguaje de programación de la base de datos de Microsoft SQL Server y el nombre viene de TRANSACT-SQL

## DDL y DML
**SQL** tiene dos grandes sublenguajes:

### DDL o Data Definition Language que nos ayuda a crear la estructura de una base de datos. Existen 3 grandes comandos:

- Create: Nos ayuda a crear bases de datos, tablas, vistas, índices, etc.
- Alter: Ayuda a alterar o modificar entidades.
- Drop: Nos ayuda a borrar. Hay que tener cuidado al utilizarlo.

#### 3 objetos que manipularemos con el lenguaje DDL:
- Database o bases de datos
- Table o tablas. Son la traducción a SQL de las entidades
- View o vistas: Se ofrece la proyección de los datos de la base de datos de forma entendible.

### DML
DML trata del contenido de la base de datos. Son las siglas de Data Manipulation Language y sus comandos son:

- Insert: Inserta o agrega nuevos registros a la tabla.
- Update: Actualiza o modifica los datos que ya existen.
- Delete: Esta sentencia es riesgosa porque puede borrar el contenido de una tabla.
- Select: Trae información de la base de datos.

## CREACION DE TABLAS
### Foreing Key:
- On update: Significa qué pasará con las relaciones cuando una de estas sea modificada en sus campos relacionados, Por ejemplo, pueden utilizarse los valores:
	- cascade: Si el id de un usuario pasa de 11 a 12, entonces la relacion se actualizará y el post buscará el id nuevo en lugar de quedarse sin usuario.
	- restrict: _Si el id de un usuario pasa de 11 a 12, no lo permitirá hasta que no sean actualizados antes todos los post relacionados.
	- set nullSi el id de un usuario pasa de 11 a 12, entonces los post solo no estará relacionados con nada.
	- no action: Si el id de un usuario pasa de 11 a 12, no se hará nada. Solo se romperá la relación.
- On delete
	- cascade: Si un usuario es eliminado entonces se borrarán todos los post relacionados.
	- restrict: No se podrá eliminar un usuario hasta que sean eliminados todos su post relacionados.
	- set null: Si un usuario es eliminado, entonces los post solo no estará relacionados con nada.
	- no action: Si un usuario es eliminado, no se hará nada. Solo se romperá la relación.

### tablas transitivas
Las tablas transitivas sirven como puente para unir dos tablas. No tienen contenido semántico.

### Reverse Engineer
Nos reproduce el esquema del cual nos basamos para crear nuestras tablas. Es útil cuando llegas a un nuevo trabajo y quieres entender cuál fue la mentalidad que tuvieron al momento de crear las bases de datos.

Las consultas en una base de datos juegan un papel muy fundamental, puesto que facilitan de manera considerable los procesos en cualquier empresa.
ETL
La palabra ETL correspondería al acrónimo de:
Extract (Extraer)
Transform (Transformar)
Load (Cargar)
ETL hace parte del proceso de integración de datos, mas aun es un componente muy importante que completa el resultado final en la relación de aplicaciones y sistemas.

### Estructura básica de un Query
Los queries son la forma en la que estructuramos las preguntas que se harán a la base de datos. Transforma preguntas en sintaxis.

El query tiene básicamente 2 partes: `SELECT` y `FROM` y puede aparecer una tercera como `WHERE`.

La estrellita o asterisco `*` quiere decir que vamos a seleccionar todo sin filtrar campos.

### SELECT
SELECT se encarga de proyectar o mostrar datos.

El nombre de las columnas o campos que estamos consultando puede ser cambiado utilizando AS después del nombre del campo y poniendo el nuevo que queremos tener:
```sql
SELECT titulo AS encabezado
FROM posts;
```
Existe una función de SELECT para poder contar la cantidad de registros. Esa información (un número) será el resultado del query:
```sql
SELECT COUNT(*)
FROM posts;
```

### FROM
`FROM` indica de dónde se deben traer los datos y puede ayudar a hacer sentencias y filtros complejos cuando se quieren unir tablas. La sentencia compañera que nos ayuda con este proceso es `JOIN`.

Los diagramas de Venn son círculos que se tocan en algún punto para ver dónde está la intersección de conjuntos. Ayudan mucho para poder formular la sentencia `JOIN` de la manera adecuada dependiendo del query que se quiere hacer.


![](http://drive.google.com/uc?export=view&id=15lpq2jkxbLi0drTZEK9qwc8BvliPBfcG)
![](http://drive.google.com/uc?export=view&id=1Z6PKdVc3BAYXm5brm3MOc5oOL6nHnF9J)

![](http://drive.google.com/uc?export=view&id=1qIUDqADmrl0Vbtyq4uy2qS_gdppcWb_I)

### WHERE
`WHERE` es la sentencia que nos ayuda a filtrar tuplas o registros dependiendo de las características que elegimos.

La propiedad `LIKE` nos ayuda a traer registros de los cuales conocemos sólo una parte de la información.
La propiedad `BETWEEN` nos sirve para arrojar registros que estén en el medio de dos. Por ejemplo los registros con id entre 20 y 30.

#### Utilizando la sentencia WHERE nulo y no nulo
El valor nulo en una tabla generalmente es su valor por defecto cuando nadie le asignó algo diferente. La sintaxis para hacer búsquedas de datos nulos es `IS NULL`. La sintaxis para buscar datos que no son nulos es `IS NOT NULL`


### GROUP BY
`GROUP BY` tiene que ver con agrupación. Indica a la base de datos qué criterios debe tener en cuenta para agrupar.

- COUNT Cuenta los registros de un campo
- SUM Suma los valores de un campo
- MAX Devuelve el maximo de un campo
- MIN Devuelve el mínimo de un campo


### ORDER BY y HAVING
La sentencia `ORDER BY` tiene que ver con el ordenamiento de los datos dependiendo de los criterios que quieras usar.

- `ASC` sirve para ordenar de forma ascendente.
- `DESC` sirve para ordenar de forma descendente.
- `LIMIT` se usa para limitar la cantidad de resultados que arroja el query.

`HAVING` tiene una similitud muy grande con `WHERE`, sin embargo el uso de ellos depende del orden. Cuando se quiere seleccionar tuplas agrupadas únicamente se puede hacer con `HAVING`.
`HAVING` remplaza al `WHERE` cuando se usa un `GROUP BY`

### El interminable agujero de conejo (Nested queries) Consultas anidadas
Los Nested queries significan que dentro de un query podemos hacer otro query. Esto sirve para hacer join de tablas, estando una en memoria. También teniendo un query como condicional del otro.

Este proceso puede ser tan profundo como quieras, teniendo infinitos queries anidados.
Se le conoce como un producto cartesiano ya que se multiplican todos los registros de una tabla con todos los del nuevo query. Esto provoca que el query sea difícil de procesar por lo pesado que puede resultar.

### ¿Cómo convertir una pregunta en un query SQL?

De pregunta a Query

- SELECT: Lo que quieres mostrar
- FROM: De dónde voy a tomar los datos
- WHERE: Los filtros de los datos que quieres mostrar
- GROUP BY: Los rubros por los que me interesa agrupar la información
- ORDER BY: El orden en que quiero presentar mi información
- HAVING: Los filtros que quiero que mis datos agrupados tengan
- LIMIT: La cantiad de registros a mostrar

### Preguntándole a la base de datos
`GROUP_CONCAT` toma el resultado del query y lo pone como campo separado por comas.

GROUP_CONCAT. Sirve para concatenar todos los registros afectados por un GROUP BY en un solo campo.
'
Criterios.

- DISTINCT. Evita duplicidad en los valores.
- ORDER BY. Sirve para decidir el orden de concatenación del campo.
- SEPARATOR. Es el separador a utilizar para separar los valores (por defecto, el separador es una coma “,”).

```sql
SELECT posts.titulo, GROUP_CONCAT(DISTINCT etiquetas.nombre ORDERBY etiquetas.nombre SEPARATOR " - "), posts.id, COUNT(*) AS num_etiquetas
FROM posts
INNERJOIN posts_etiquetas
ON posts.id = posts_etiquetas.post_id
INNERJOIN etiquetas
ON etiquetas.id = posts_etiquetas.etiqueta_id
GROUPBY posts.id
ORDERBY num_etiquetas;
```

Función `CASE` permite agregar un campo virtual con información generada a partir de condiciones múltiples.
Mostrar el idioma, precio de todos los libros, así como agregar una columna de informe que indique si el libro es caro, módico o barato basado en el precio

```sql
SELECT  idioma, precio, 
CASE
	WHEN precio > 1000THEN"Muy caro"
	WHEN precio > 500THEN"Precio módico"
	ELSE"Muy barato"
ENDAS"informe"
FROM libros;
```

### Resumen
![](http://drive.google.com/uc?export=view&id=1-22vW4IEdww2NRSLfck5iKjfehuCT_CM)


## BD no realacionales.

- [¿Qué son las bases de datos no relacionales? Ventajas de NoSQL](https://agustinducca.com/blog/que-son-las-bases-de-datos-no-relacionales-ventajas-de-nosql/)


Dentro de las bases de datos relacionales tenemos diferentes niveles de datos. En primer lugar tenemos las Bases de Datos o Esquemas como repositorios donde vivirán los datos que nos interesa guardar. Dentro del esquema existen las Tablas que provienen del concepto de entidades; y a su vez dentro de las tablas tenemos las tuplas o renglones.

Cuando trabajamos con bases de datos basadas en documentos como Firestore, aún existe la figura de la base de datos, sin embargo cambiaremos las tablas en favor de las colecciones y las tuplas en lugar de los documentos.

**Recuerda:**
- Tabla -> Colección
- Tupla -> Documento

Dentro de las Colecciones existen 2 grandes tipos. Las **Top level collection** o colecciones de nivel superior y las **subcollections** o subcolecciones. Estas últimas viven únicamente dentro de un documento padre.

### ¿Cómo saber cuál escoger?

Para determinar si tu colección debe ser top level o subcolección no hay una regla escrita en piedra y más bien tiene que ver con el caso de uso en particular y con la experiencia que hayas ganado como desarrollador.

Lo cierto es que no hay una sola forma de estructurar nuestra DB basada en documentos, y por tanto no existe una respuesta correcta, sin embargo a continuación te ofrezco un par de reglas guía que puedes utilizar para transformar tu proyecto que ya trabajaste en bases de datos relacionales en un proyecto no relacional.

### Regla 1. Piensa en la vista de tu aplicación

La primera pista que te puedo dar es que pienses en un inicio en la manera en que los datos serán extraídos. En el caso de una aplicación, la mejor forma de pensarlo es en términos de las vistas que vas a mostrar a un momento determinado en la aplicación.

Es decir, al armar la estructura en la base de datos que sea un espejo o que al menos contenga todos los datos necesarios para llenar las necesidades que tiene nuestra parte visual en la aplicación.

En el caso de Platziblog por ejemplo si tienes una vista de un blog post individual, generalmente conviene mostrar además de los datos inherentes al post como el contenido, datos adicionales como las etiquetas que tiene o por ejemplo el autor (o autores si es colaborativo), en este caso tal vez convenga guardar estas dos “entidades” (autores y etiquetas) como subcolecciones de cada documento blog post.

### Regla 2. La colección tiene vida propia

Esta regla se refiere a que la excepción a la regla 1 es cuando tenemos un caso en que la “entidad” que tiene necesidad de vivir y modificarse constantemente de manera independiente a las otras colecciones. Por ejemplo en Platziblog podemos en el ejemplo anterior hacer una excepción a autores porque nos conviene tenerlas como top level collection en el sentido que se añadan, borren, cambien o listen los usuarios sin depender del blog post.

Experimenta aplicando estas dos reglas a un proyecto que ya conozcas en una base de datos relacional y trata de convertirla en un proyecto de Firestore y comentanos los retos a los que te enfrentaste.

### Tipos de BD no relacionales

Respecto a las bases de datos no relacionales, no existe un solo tipo aunque se engloben en una sola categoría.

Tipos de bases de datos no relacionales:

- **Clave - valor:** Son ideales para almacenar y extraer datos con una clave única. Manejan los diccionarios de manera excepcional. Ejemplos: DynamoDB, Cassandra.
- **Basadas en documentos:** Son una implementación de clave valor que varía en la forma semiestructurada en que se trata la información. Ideal para almacenar datos JSON y XML. Ejemplos: MongoDB, Firestore.
- **Basadas en grafos:** Basadas en teoría de grafos, sirven para entidades que se encuentran interconectadas por múltiples relaciones. Ideales para almacenar relaciones complejas. Ejemplos: neo4j, TITAN.
- **En memoria:** Pueden ser de estructura variada, pero su ventaja radica en la velocidad, ya que al vivir en memoria la extracción de datos es casi inmediata. Ejemplos: Memcached, Redis.
- **Optimizadas para búsquedas:** Pueden ser de diversas estructuras, su ventaja radica en que se pueden hacer queries y búsquedas complejas de manera sencilla. Ejemplos: BigQuery, Elasticsearch.


### Servicios administrados y jerarquía de datos
**Firebase** es un servicio de Google donde puedes tercerizar muchos elementos en la nube.
Jerarquía de datos:
- Base de datos
- Colección
- Documento


#### Top level collection con Firebase
El modelo de bases de datos no relacionales es un poco más cercano al mundo real en su comportamiento.

- Las top level collections son las colecciones que se tienen de inmediato o entrada en el proyecto.
- Firebase es un servicio que tiene múltiples opciones y está pensado principalmente para aplicaciones móviles y web.

#### Tipos de datos en Firestore:

- String: Cualquier tipo de valor alfanumérico
- Number: Soporta enteros y flotantes.
- Boolenan: Los clásicos valores True y False
- Map: Permite agregar un documento dentro de otro.
- Array: Permite agregar un conjunto de datos (soporte multi type) sin nombre e identificador.
- Null: Indica que no se ha definido un valor.
- Timestamp: Permite almacenar fechas (guarda el año, mes, día y hora).
- Geopoint: Guarda una localización geográfica (coordenadas latitud-longitud).
- Reference: Permite referencia un documento (relaciona dos documentos, no importa su colección).

## Base de datos en la vida real
Hoy en dia, se utilizan diversos tipos de bases de datos segun el problema que se quiera resolver:
- Las bases de datos relacionales, durante mucho tiempo, fueron utilizadas para resolver todo tipo de situaciones, pero al aumentar enormemente el numero de datos a manejar, se volveron ineficientes en muchos casos.
- Firestore o MongoDB nos permiten obtener los datos actuales de la aplicacion de manera simple. Sin embargo, no nos permite hacer, por ejemplo, queries muy complejos.
En una misma disciplina, es probable que haya que utilizar mas de un tipo de bases de datos.

### Bid data
**Big Data** es un concepto que nace de la necesidad de manejar grandes cantidades de datos. La tendencia comenzó con compañías como YouTube al tener la necesidad de guardar y consultar mucha información de manera rápida.

Es un gran movimiento que consiste en el uso de diferentes tipos de bases de datos.

### Data warehouse
Data Warehouse trata de guardar cantidades masivas de datos para la posteridad. Allí se guarda todo lo que no está viviendo en la aplicación pero es necesario tenerlo.

Debe servir para guardar datos por un largo periodo de tiempo y estos datos se deben poder usar para poder encontrar cuestiones interesantes para el negocio.

### Data mining
El Data Mining se dedica a minar datos, a extraerlos de donde sea que estén (archivos muertos, base de datos actual, etc…) y hacer sentido de ellos para darles un uso.


### ETL
ETL son las siglas de Extract, Transform, Load (extraer, transformar y cargar). Se trata de tomar datos de archivos muertos y convertirlos en algo que sea de utilidad para el negocio.
También ayuda a tomar los datos vivos de la aplicación, transformarlos y guardarlos en un data warehouse periódicamente.


![](http://drive.google.com/uc?export=view&id=1i6II57jRvNSPlz6Kb2EwS5kinFy5lPA5)

### Business intelligence

Business Intelligence es una parte muy importante de las carreras de datos ya que es el punto final del manejo de estos. Su razón de ser es tener la información lista, clara y que tenga todos los elementos para tomar decisiones en una empresa.
Es necesario tener una buena sensibilidad por entender el negocio, sus necesidades y la información que puede llevar a tomar decisiones en el momento adecuado al momento de realizar business intelligence.

#### ejemplo: Peluquería local

Una peluquería de Santiago de Compostela llevaba dos años abierta al público. Durante todo ese tiempo, las dueñas, dos chicas jóvenes y emprendedoras, habían trabajado todos los días de la semana (a excepción, naturalmente, de los domingos) para sacar adelante su negocio.

Al haber estabilizado su cartera de clientes decidieron descansar un día más a la semana. Su primera opción fue cerrar los lunes, como las demás peluquerías de la zona. No obstante, decidieron basar su decisión en la información histórica que habían recogido en su pequeña aplicación de citas.

Los resultados obtenidos fueron contudentes, ya que el lunes resultó ser el cuarto día más rentable de la semana (probablemente como consecuencia del cierre de la competencia). Finalmente el día elegido para descansar fue el martes.


### Machine Learning
Machine Learning tiene significados que varían. Es una serie de técnicas que involucran la inteligencia artificial y la detección de patrones.
Machine learning para datos tiene un gran campo de acción y es un paso más allá del business intelligence.

Nos ayuda a hacer modelos que encuentran patrones fortuitos encontrando correlaciones inesperadas.

Tiene dos casos de uso particulares:
- Clasificación
- Predicción


### Data Science
Data Science es aplicar todas las técnicas de procesamiento de datos. En su manera más pura tiene que ver con gente con un background de estadísticas y ciencias duras.


### Resumen
Hoy en dia no existen bases de datos ‘one size fits all’, es decir, hoy en dia en las aplicaciones modernas se utilizan distintas bases de datos ya sean relacionales, no relacionales, etc en una sola aplicacion. Las bases de datos relacionales servian muy bien por un tiempo para cumplir con varias demandas pero a medida que llego el Big Data estas no pudieron manejar bien toda esta carga con lo cual fueron creando otras.

- Big Data: Grandes cantidades de datos, el reto que empezo a cerrar las puertas fueron que se estuvieron manejando cada vez mas grandes, grandes volumenes de datos. Se refiere a que en este momento en milesimas de segundos vamos a guardar grandes cantidades de datos. Es un gran movimiento que surgio con Youtube y Facebook ya que necesitaban guardar muchoos datos rapido. Data Warehouse: Guardar grandes cantidades masivas de datos, la diferencia con Big Data es guardar mas datos que en Big Data pero que son datos historicos, es decir, que no se extraen muy a menudo. Ejemplo de Google que usa eso es Bigtable, otra solucion es BigQuery.
- Data Mining: Es literal picar piedra, es decir, debido a que el orden en que se guardaban estos datos no era el mas optimo o el mas eficaz nos toca como data miners intentar buscar en todos esos datos y sacar informacion util que ayude en las decisiones de negocio. En si no se refiere a una base de datos sino a un conjunto de tecnicas para extraer informacion valiosa para las empresas.
- ETL: Son las siglas de Extract, Transform, Load. Se trata de tomar datos de archivos muertos y convertirlos en algo que sea de utilidad para el negocio. Tambien ayuda a tomar los datos viveos de la aplicacion, transformarlos y guardarlos en un data warehouse periodicamente. Esta tecnica tiene dos grandes usos: Para el datamining cuando tenemos una base de datos sin orden, sacamos la info, la limpiamos y la guardamos en un data warehouse y ahora si esta ordenada y podemos sacarle provecho a ella. Otro gran caso de uso es mas o menos similar pero cuando lo tenemos que hacer en tiempo real que sirve para hacer etl, es decir, guardamos el estado en bases de datos no relacional que no son muy buenas manejando queries complejos y si tenemos muchas relaciones y con ETL podemos aprovechar la informacion aunque este asi y obtener informacion valiosa. Aunque no existen tecnologias que hagan todo el proceso existen los data pipelines para manejar todas estas fases.
- Business Intelligence: Como el nombre lo dice inteligencia para el negocio, que se refiere a tener los datos de manera oportuna y datos correctos que los ayuden a dar informacion necesaria para hacer las decisiones correctas. Con esto tratamos de hacer sentido a toda la info obtenida y nos ayuda a saber digamos que tipo de audiencia tenemos, el historico de como han ido las ventas en ciertos periodos, es decir, nos permite visualizar las relaciones que tiene nuestro sistema y aplicacion y los clientes entre si. Herramientas para esto: Tableau, QlikView, PowerBI.
- Machine Learning: Son una serie de tecnicas que involucran la inteligencia artificial y deteccion de patrones. A diferencia de Business Intelligence que queremos buscar un patron en especifico con la informacion que ya tenemos, mientras que con Machine Learning dado un conjunto de datos buscamos encontrar patrones que no esperas o no eran obvios para un ser humano, ademas que busca saber en un futuro como se comportarian nuestros usuarios. Una bd muy buena para esto es BigQuery que nos sirve como warehouse y ademas nos permite hacer queries que nos podrian ayudar con BusinessIntelligence como son Data Studio. Entre los dos casos de uso principales de ML son: clasificacion y prediccion. Con la clasificacion nos referimos a que si tenemos varios datos historicos y queremos conocer por ejemplo cuales temas fueron mas interesantes durante un periodo en especifico, no serviria con buscar palabras claves, para este tipo de casos se utiliza la tecnica de ML denominada Procesamiento de Lenguaje Natural lo que hace es tomar un texto o reconocimiento de voz que utiliza el lenguaje natural humano nada estructurado, lo empieza a procesar y nos devuelve los patrones que encontro. Por ejemplo con el Platziblog: Si tenemos un modelo muy bien entrenado, es decir, que le hayamos pasado una buena cantidad de articulos que si sabemos que son de politica y reconoce estos patrones. Cuando le pasamos toda la informacion de Platziblog nos devuelve articulos que no especificaban por ninguna parte que se trataban de politica pero gracias al modelo pudimos identificarlos. Con la prediccion nos ayuda a la toma de decisiones. Por ejemplo le damos las ventas de unos años pasados, procesa las ventas y genera un modelo, que cuando le pasemos las ventas actuales nos ayuda a identificar las relaciones y patrones que nos ayuda a visualizar a donde nos dirigimos, es decir, si le pasamos ventas proyectadas a futuro este nos dice que va a pasar, si se va a comportar igual, etc.
- BigQuery es una buena herramienta debido a que con un lenguaje similar a SQL pero con mas funcionalidades nos permite ademas de hacer consultas, almacenarla y alimentarla a un algoritmo de modelos de ML que con el mismo lenguaje SQL al ejecutarlo estamos creando modelos que nos ayudaran a predecir valores futuros.
- Data Science: Es aplicar todo lo que hemos visto, tecnicas de ETL, Data Mining, Business Intelligence. Aunque esta mas dirigida a personas con background de estadisticas, hoy en dia tambien participan personas con el perfil de Data Engineering. Al hacer Data Science estamos aplicando todo lo visto en los temas anteriores, no solo a nivel tecnico sino que desarrollamos la experiencia y conocimientos sobre las distintas tecnologias, en que parte del desarrollo de nuestro proyecto tenemos que utilizarlas, etc. Con lo cual el Data Science juega el papel de manager dentro de un equipo de profesionales de datos.
