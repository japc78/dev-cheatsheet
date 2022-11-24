---
title: "MySQL"
tags: ""
---

## Comandos.
```bash
mysql -u root -h localhost -p #entrar en mysql desde consola

#Ejecutar estar posicionado en la carpeta
#Ejecutar un script desde la terminal SQL (Unix)*/
mysql -u root -p -h localhost < name_script.sql


#Ejecutar el script diciendole a que bases de datos debe ejecutarse
mysql -u root -p -h localhost -D name_data_bases < name_script.sql
```

```mysql
show databases; #Lista las BD existentes.
use tmp; # Usar una bd
show tables; # Muestra las tablas de la bd
select database(); # Muestra la bd seleccionada
CREATE DATABASE nombre; #crea la base de datos
CREATE DATABASE IF NOT EXISTS nombre; #Crea la bd sino existe
SHOW WARNINGS; # Muestra las advertencias
DESCRIBE nombre_tabla; #Muestra las columns de las tablas
DESC nombre_tabla; #Muestra las columns de las tablas
SHOW FULL COLUMNS FROM nombre_tabla; #Muestra todas las columnas de la tabla, incluso los comentarios.

-- Comando ON DUPLICATE 
/* 🚫Nunca usa ON DUPLICATE KEY IGNORE ALL⛔
PROHIBIDISIMOOOOOOOOOOOOOOOOOOOO */
INSERT INTO clients(name, email, birthdate, gender, active) 
VALUES('Royer G', 'royjuni3431@gmail.com', '2002-02-16', 'M', 0)
ON DUPLICATE KEY IGNORE All;

#INSERTA LA TUPLA Y SI ES DUPLICADA ACTUALIZA el calor de la columna indicada.
INSERT INTO clients(name, email, birthdate, gender, active) 
VALUES('Royer G', 'royjuni3431@gmail.com', '2002-02-16', 'M', 0)
ON DUPLICATE KEY UPDATE active = VALUES(active);

-- Truco para la presentacion de los datos \G (Mas legible)
SELECT * FROM clients WHERE client_id = 101\G
SELECT * FROM clients\G


-- Listar todas la tuplas de la tabla clients
SELECT * FROM clients;

-- Listar todos los nombres de la tabla clients
SELECT name FROM clients;

-- Listar todos los nombres, email y género de la tabla clients
SELECT name, email, gender FROM clients;

-- Listar los 10 primeros resultados de la tabla clients
SELECT name, email, gender FROM clients LIMIT 10;

-- Listar todos los clientes de género Masculino
SELECT name, email, gender FROM clients WHERE gender = 'M';

-- Listar el año de nacimientos de los clientes, con la función YEAR()
SELECT YEAR(birthdate) FROM clients;

-- Mostrar el año actual
SELECT YEAR(NOW());

-- Listar los 10 primeros resultados de las edades de los clientes
SELECT YEAR(NOW()) - YEAR(birthdate) FROM clients LIMIT 10;

-- Listar nombre y edad de los 10 primeros clientes
SELECT name, YEAR(NOW()) - YEAR(birthdate) FROM clients LIMIT 10;

-- Listar clientes que coincidan con el nombre de "Saave"
SELECT * FROM clients WHERE name LIKE '%Saave%';

-- Listar clientes (nombre, email, edad y género). con filtro de genero = F y nombre que coincida con 'Lop'
--Usando alias para nombrar la función como 'edad'
SELECT name, email, YEAR(NOW()) - YEAR(birthdate) AS edad, gender FROM clients WHERE gender = 'F' AND name LIKE '%Lop%';



```
Existen dos principales tipos de tablas (motores en su core):

- MyISAM
	- Bloqueo de tabla
	- Aumento del rendimiento si nuestra aplicación realiza un elevado número de consultas “Select”.
	- Las tablas pueden llegar a dar problemas en la recuperación de datos.
	- Permite hacer búsquedas full-text
	- Menor consumo memoria RAM
	- Mayor velocidad en general a la hora de recuperar datos.
	- Ausencia de características de atomicidad ya que no tiene que hacer comprobaciones de la integridad referencial, ni bloquear las tablas para realizar las operaciones, esto nos lleva como los anteriores puntos a una mayor velocidad.
- InnoDB
	- Bloqueo de registros
	- Soporte de transacciones
	- Rendimiento
	- Concurrencia
	- Confiabilidad
	- Permite hacer búsquedas full-text (mysql >= 5.6)

[MyISAM vs InnoDB (Ventajas y diferencias)](https://foro.elhacker.net/bases_de_datos/myisam_vs_innodb_ventajas_y_diferencias-t362611.0.html)
[InnoDB y MyISAM: El ying yang de MySQL](https://platzi.com/tutoriales/1272-sql-mysql/4484-innodb-y-myisam-el-ying-yang-de-mysql/)

## TIPOS DE JOIN

Existen diferentes formas en las que se pueden unir las tablas en nuestras consultas y de acuerdo con esta unión se va a mostrar información, y es importante siempre tener clara esta relación. En esta clase te voy a mostrar gráficamente 7 diferentes tipos de uniones que puedes realizar.

Usar correctamente estas uniones puede reducir el tiempo de ejecución de tus consultas y mejorar el rendimiento de tus aplicaciones.

Como yo lo veo cuando hacemos uniones en las consultas para seleccionar información, estamos trabajando con tablas, estas tablas podemos verlas como conjuntos de información, de forma que podemos asimilar los joins entre tablas como uniones e intersecciones entre conjuntos.

Supongamos que contamos con dos conjuntos, el conjunto A y el conjunto B, o, la tabla A y la tabla B. Sobre estos conjuntos veamos cuál es el resultado si aplicamos diferentes tipos de join.

### 1. Inner Join
Esta es la forma mas fácil de seleccionar información de diferentes tablas, es tal vez la que mas usas a diario en tu trabajo con bases de datos. Esta union retorna todas las filas de la tabla A que coinciden en la tabla B. Es decir aquellas que están en la tabla A Y en la tabla B, si lo vemos en conjuntos la intersección entre la tabla A y la B.

![](http://drive.google.com/uc?export=view&id=1q83tReToSZoLcgD_q7t4lkDcwFO7-DEC)

Esto lo podemos implementar de esta forma cuando estemos escribiendo las consultas:

```sql
SELECT <columna_1> , <columna_2>,  <columna_3> ... <columna_n> 
FROM Tabla_A A
JOIN Tabla_B B
	ON A.pk = B.pk
```

### 2. Left Join
Esta consulta retorna todas las filas que están en la tabla A y ademas si hay coincidencias de filas en la tabla B también va a traer esas filas.
![](http://drive.google.com/uc?export=view&id=1hYPkt8jpgSIKfYievWhTnbGVF90iHLIt)


Esto lo podemos implementar de esta forma cuando estemos escribiendo las consultas:

```sql
SELECT <columna_1> , <columna_2>,  <columna_3> ... <columna_n> 
FROM Tabla_A A
LEFT JOIN Tabla_B B
	ON A.pk = B.pk
```

### 3. Right Join
Esta consulta retorna todas las filas de la tabla B y ademas si hay filas en la tabla A que coinciden también va a traer estas filas de la tabla A.
![](http://drive.google.com/uc?export=view&id=1xE4cPU1pcMTehx4ceUzRaFhHSEfwlnKP)

Esto lo podemos implementar de esta forma cuando estemos escribiendo las consultas:

```sql
SELECT <columna_1> , <columna_2>,  <columna_3> ... <columna_n>
FROM Tabla_A A
RIGHT JOIN Tabla_B B
	ON A.pk = B.pk
```

### 4. Outer Join
Este join retorna TODAS las filas de las dos tablas. Hace la union entre las filas que coinciden entre la tabla A y la tabla B.
![](http://drive.google.com/uc?export=view&id=10pAyJRtJXxVPlj5ZLbhtMtQ1CMTV7L9N)

Esto lo podemos implementar de esta forma cuando estemos escribiendo las consultas:

```sql
SELECT <columna_1> , <columna_2>,  <columna_3> ... <columna_n>
FROM Tabla_A A
FULL OUTER JOIN Tabla_B B
ON A.pk = B.pk
```

Respecto a “FULL OUTER JOIN”, esta sintaxis no es soportada por MySQL y arroja el Error 1046.
Para obtener un “FULL OUTER JOIN”, se pueden unir un “LEFT JOIN” y un “RIGHT JOIN” usando la palabra clave “UNION”. 

Por ejemplo, la siguiente consulta muestra los autores sin libros (LEFT JOIN) y los libros sin autores (RIGHT JOIN), obteniendo los mismos resultados que un “FULL OUTER JOIN”:

```sql
SELECT *
FROMauthorsas a
LEFTJOIN books as b 
	ON a.author_id = b.author_id
WHERE b.author_id ISNULL
UNION
SELECT *
FROMauthorsas a
RIGHTJOIN books as b 
	ON a.author_id = b.author_id
WHERE a.author_id ISNULL;
```

### 5. Left excluding join
Esta consulta retorna todas las filas de la tabla de la izquierda, es decir la tabla A que no tienen ninguna coincidencia con la tabla de la derecha, es decir la tabla B.
![](http://drive.google.com/uc?export=view&id=1fM67rCdQ1iaFrldByV30ad9mTI-24ldz)

Esto lo podemos implementar de esta forma cuando estemos escribiendo las consultas:

```sql
SELECT <columna_1> , <columna_2>,  <columna_3> ... <columna_n>
FROM Tabla_A A
LEFT JOIN Tabla_B B
ON A.pk = B.pk
WHERE B.pk IS NULL
```

### 6. Right Excluding join
Esta consulta retorna todas las filas de la tabla de la derecha, es decir la tabla B que no tienen coincidencias en la tabla de la izquierda, es decir la tabla A.

![](http://drive.google.com/uc?export=view&id=10VQXBc9BJK6b7SEFSSnT8eXQPdagqOkp)

Esto lo podemos implementar de esta forma cuando estemos escribiendo las consultas:

```sql
SELECT <columna_1> , <columna_2>,  <columna_3> ... <columna_n>
FROM Tabla_A A
RIGHT JOIN Tabla_B B
ON A.pk = B.pk
WHERE A.pk IS NULL
```

### 7. Outer excluding join
Esta consulta retorna todas las filas de la tabla de la izquierda, tabla A, y todas las filas de la tabla de la derecha, tabla B que no coinciden.

![](http://drive.google.com/uc?export=view&id=1cuubpRPDrIea5vtY1lfTQ5aasT3-H08v)

Esto lo podemos implementar de esta forma cuando estemos escribiendo las consultas:

```sql
SELECT <select_list>
FROM Table_A A
FULL OUTER JOIN Table_B B
ON A.Key = B.Key
WHERE A.Key IS NULL OR B.Key IS NULL
```
### Resumen
![](http://drive.google.com/uc?export=view&id=1Hmd8CsT4xcnf9qTGBMQJw_4xQKyepJnb)
![](http://drive.google.com/uc?export=view&id=1FW4rIiAipFsslCKrlFpqW9FjkfOsYSMG)
![](http://drive.google.com/uc?export=view&id=16V6ekiplEJhdlApTrqJvsjG8P3uo9qbJ)
![](http://drive.google.com/uc?export=view&id=16V6ekiplEJhdlApTrqJvsjG8P3uo9qbJ)
![](http://drive.google.com/uc?export=view&id=1QmCEsMNPWoc8kW8hdcHFbMVpAw7b_x7r)


## Comandos mas usados en el curso
```sql
SHOW databases; -- muestra las bases de datos existentes.
USE database_name; -- selecciona una base de datos específica.
SHOW tables; -- muestras las tablas de la base de datos.
SELECT database(); -- me muestra el nombre de la base de datos seleccionada.
CREATE database database_name; -- crea una nueva base de datos.
CREATE DATABASE IF NOT EXISTS database_name; -- crea una base de datos si no existe.
SHOW warnings; -- muestra las advertencias.
DROP table table_name; -- Elimina permanentemente una tabla.
DESCRIBE table_name; -- Nos indica las columnas que tenemos en una tabla.
SHOW FULL COLUMNS FROM table_name; -- es parecido al comando DESCRIBE pero muestra mas datos.
INSERT INTO table_name(columns) VALUES(values); -- inserta una tupla.
ON DUPLICATE KEY IGNORE ALL -- esta sentencia ignora las resticciones al insertar una tupla con un valor repetido y que esta restringido en una columna con UNIQUE (Nota: nunca utilizarlo).
ON DUPLICATE KEY UPDATE column = VALUES(value) -- al insertar una tupla con un campo duplicado actualiza un el valor de un campo específico con un nuevo valor tomado de los datos insertados.
SELECT * FROM table_name WHERE column_value = 1\G -- en lugar de cerrar la sentencia con ;se utiliza \G, lo cual muestra los datos de una manera mas legible.
mysql -u root -p < all_schema.sql -- con este comando podemos ejecutar un script SQL inmediatamente despues de acceder a la base de datos.
mysql -u root -p -D database_name < all_schema.sql -- este comando es parecido al anterior solo que con la bandera -D indicamos el nombre de la base de datos sobre la que queremos ejecutar el script.
SELECT YEAR(NOW()); -- esta sentencia me muestra el año de la fecha actual utilizando las funciones YEAR() y NOW().
SELECT * FROM table_name WHERE column_value like ‘%value%’; -- esta sentencia nos muestra las tuplas que en un campo específico contengan un valor, el wildcard % indica que no nos importa que valor existan antes o despues del dato que especificamos.
SELECT COUNT(*) FROM table_name; -- devuelve el número de tuplas de una tabla.
SELECT * FROM table_name WHERE column_value BETWEEN value AND value; -- nos devuelve las tuplas que se encuentren en medio de los valores indicados.
DELETE FROM table_name WHERE column_value = value; -- elimina una tupla de una tabla.
UPDATE table_name SET [column_value = value, …] WHERE column_value = value; -- actualiza una tupla de una tabla.
TRUNCATE table_name; -- borra todo el contenido de una tabla.
mysqldump -u user -p database_name > esquema.sql -- guarda el esquema de una base de datos con todo y datos en un archivo sql.
mysqldump -u user -p -d database_name --es parecido al comando anterior solo que aquí no se guardan los datos.
```
