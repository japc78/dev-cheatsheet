---
title: "Python"
tags: ""
---

## Links
- [Doc Python 2.7](https://docs.python.org/2.7/)
- [Doc Python 3.8](https://docs.python.org/3.8/)
- [Python para principiantes](https://uniwebsidad.com/libros/python)
- [Algoritmos de Programación con Python](https://uniwebsidad.com/libros/algoritmos-python)
- [Excepciones](https://sodocumentation.net/es/python/topic/1788/excepciones)


- [Ejercicios de Python: Tipos de datos simples](https://aprendeconalf.es/python/ejercicios/tipos-datos.html)
- [retos en Python](https://www.hackerrank.com/domains/python)


## Operadores aritméticos importantes
### Operadores Matemáticos
Existen muchos operadores básicos,
- (+) Suma
- (-) Resta
- (asterisco) Multiplicación  `5*4'
- (/) División `21/5 = 4.2`
- (//) División de enteros `21//5 = 4`
- (%) Operador de módulo `21%5 = 1`
- (doble asterisco) Potencias `2**3 = 8`
- Raiz cuadrada `9**0.5 = 3` o `math.sqrt(9)`para python3 con `import math`
- (>) Mayor que
- (<) Menor que
- (==) Igual
- (>=) Mayor igual
- (<=) Menor igual

Python respeta la separaciónde términos, por lo que si escribimos 5 + 5 * 2 multiplicará primero 5 x 2.
En el caso deque quisiéramos que primero sume 5 + 5 ponemos paréntesis: 
(5 + 5) * 2.

### Orde de las operaciones
Orden de las operaciones en álgebra y en Python utilicen el orden PEMDAS:

1. Paréntesis
2. Exponentes o raíces
3. Multiplicaciones
4. Divisiones
5. Adiciones y sustracciones

## Tipos de datos
- Input("") para pedirle al usuario que introduzca datos.
- int() con datos o variables dentro de parentesis para convertirlo en número entero.
- str() para convertir números tanto decimales como enteros a strings.

### Valores y Tipos
Los tipos le permiten a Python saber cuál es el resultado de aplicar determinada
operación,
los tipos básicos son:

- Integer `<int>`
- Float `<float>`
- String `<str>`
- Boolean `<bool>`

Para revisar de qué tipo es un dato puedes usar la función type.

**Ejemplos:**
- `type(2)` - retorna int
- `type('Hola')` - retorna str


## Definir funciones en Python

Las funciones son un concepto fundamental en programación, una función es una
secuencia de comandos que realizan un computo.
En Python las funciones se definen usando la palabra reservada o keyword
**`def`** y luego el nombre de la función con paréntesis y dos puntos que indican
que lo que sigue son los comandos, una función debe retornar un valor, para esto
se usa la palabra reservada return.

### Recuerda:
- Si usas Python 3, debes usar la función input() para recibir datos del usuario.
- Para definir dónde comenzar el código usamos la línea `if __name__ == '__main__'`
- Para definir un bloque dentro de la función debemos indentar con 4 espacios.
- Las funciones nos permiten ejecutar determinado código con diferentes valores.

**Ejemplo:** 
```python
def suma (num1,num2)
	return num1 + num2

suma(2,3) #Resultado es 5
```

## Funciones con parámetros
Limites al declarar funciones

- Los nombres no pueden comenzar con digitos
- No pueden utilizar una palabra reservada
- Las variables deben tener diferentes nombres
- Los nombres de las funciones deben ser descriptivas de lo que hacen las funciones

### Imprimir valor de variable
Para poder imprimir el valor de una variable dentro de un string podemos hacerlo así:
```python
'${} pasos mexicanos son ${} pesos mexicanos'.format(ammount, result)
```

### Declarar vs Ejecutar
- Declarar una función es escribir su estructura
- Ejecutar una función es llamar la función y ejecutar su código

### Donde se puede acceder a las variables
Scope de las variables, cada vez que una función se ejecuta se genera un
contenedor donde las variables de la función van a vivir, una vez se sale
de la función estas variables no van a existir.

## Estructura de condicionales
Uno de las cosas más poderosas en programación es controlar el flujo de ejecución, para esto utilizamos condicionales.

Las condicionales son sentencias que devuelven un valor booleano (True, False)

Podemos utilizar:

**Operadores relacionales:**
- `==` Es igual
- `!=` Es diferente
- `>` Es mayor
- `>=` Es mayor o igual
- `<` Es menor
- `<=` Es menor o igual

**Operadores lógicos:**
- and
- or
- not

## Zen Python
- Hermoso es mejor que feo.
- Explícito es mejor que implícito.
- Simple es mejor que complejo.
- Complejo es mejor que complicado.
- Sencillo es mejor que anidado.
- Escaso es mejor que denso.
- La legibilidad cuenta.
- Los casos especiales no son lo suficientemente especiales para romper las reglas.
- Lo práctico le gana a la pureza.
- Los errores no debe pasar en silencio.
- A menos que sean silenciados.
- En cara a la ambigüedad, rechazar la tentación de adivinar.
- Debe haber una - y preferiblemente sólo una - manera obvia de hacerlo.
- Aunque esa manera puede no ser obvia en un primer momento a menos que seas holandés.
- Ahora es mejor que nunca.
- Aunque “nunca” es a menudo mejor que “ahora mismo”.
- Si la aplicación es difícil de explicar, es una mala idea.
- Si la aplicación es fácil de explicar, puede ser una buena idea.
- Los espacios de nombres son una gran idea ¡hay que hacer más de eso!

## Comparacion de strings y unicode
Los strings tienen una característica muy importante: **son inmutables,** esto
quiere decir que no se pueden cambiar después de que se han declarado.

Si quieres modificar el texto de un string debes definir un nuevo string y
modificarlo usando funciones como slice.
```python
nombre = 'Xuan'
nombre = 'J' + nombre[1:]
```

### Comparación de strings

Se pueden realizar operaciones con strings, por ejemplo comparar si son iguales o
mayores o menores.

### Diferencia entre ASCII y Unicode

Los caracteres también son números, para esto existen estándares que asignan un
número a cada carácter, para generar un estándar se creó el ASCII pero esta solo
toma en cuenta los caracteres en inglés, para dar soporte a más lenguajes se crea
UNICODE.

Python codifica en ASCII por default, para cambiarlo por UNICODE debemos colocar
u antes del string.

### Operaciones con Strings en Python
Los strings tienen varios métodos que nosotros podemos utilizar.

- `upper`: convierte todo el string a mayúsculas
- `lower`: convierte todo el string a minúsculas
- `find`: encuentra el indice en donde existe un patrón que nosotros definimos
- `startswith`: significa que empieza con algún patrón.
- `endswith`: significa que termina con algún patrón
- `capitalize`: coloca la primera letra en mayúscula y el resto en minúscula
- `in` y `not in` nos permite saber con cualquier secuencia sin una subsecuencia o substrings se encuentra adentro de la secuencia mayor.
- `dir`: Nos dice todos los métodos que podemos utilizar dentro de un objeto.
- `help`: nos imprime en pantalla el docstrings o comentario de ayuda o instrucciones que posee la función. Casi todas las funciones en Python las tienen.

## Recursión o recursividad.
Una función está siendo recursiva cuando dentro de el bloque de instrucciones que
la conforma se usa a sí misma.

```python
5*fac(4)
4*fac(3)
3*fac(2)
2*fac(1)
1*fac(0)
```

**Nota importante:** Cuándo estes trabajando con recursividad siempre debes
pensar en el caso base, es decir debes definir el momento en el que la función
dejará de llamarse a si misma, para que no hagas un loop infinito, por ejemplo en
el caso del factorial terminas la ejecución cuando llegas a cero.


## Manejo de strings
Un string es una secuencia de caracteres, donde cada caracter tiene un indice que
inicia en cero, por ejemplo

```python
my_string = 'platzi'

my_string[0] # p
my_string[1] # l
my_string[2] # a
my_string[3] # t
my_string[4] # z
my_string[5] # i
```

Para conocer la longitud de un string podemos usar la funcion `len`
```python
len(my_string) # 6
```
Los string tienen algunos métodos útiles cómo:
```python
my_string.upper() # retorna el string en máyusculas
my_string.lower() # retorna el string en minúscula
my_string.find('F') # retorna el índice donde se encuentra
```

### Separar cadenas de texto. Función `slice`
La función slice de python nos permite separar los strings en substrings generando nuevas secuencias.

```python
my_string = 'platzi'
my_string[1:3] # la
my_string[1:] # latzi
my_string[1:6:2] # lti
my_string[::-1] # iztalp

```
## Ciclos en Python con for

Cuando necesitamos realizar operaciones sobre una serie de datos podemos utilizar
iteraciones.

Función range

La función range nos permite generar un rango a partir de un número
```python
range(5) # [0,1,2,3,4]
range(5, 40, 3) # [5, 8, 11, 14, 17, 20, 23, 26, 29, 32, 35, 38]
```
Iteraciones con for
`for` nos permite recorrer un arreglo, asignando cada valor a una variable que
decidas
```python
for i in range(5):
    print(i)
```
Podemos operar los valores usando también condiciones, en este caso solo queremos
elevar al cuadrado, los valores que sean divisibles por 3
```python
for i in range(30):
  if i % 3 != 0:
    continue
  else:
    print(i**2)
```    
La palabra reservada `continue` permite saltar a la siguiente iteración del ciclo
y `break` permite salirse del ciclo.

## Introducción a las listas en Python

Los strings son una secuencia de caracteres, cuando hablamos de listas podemos
hablar de secuencias de cualquier cosa, por ejemplo listas de números, listas de
strings, listas de objetos mas complejos con tipos propios etc.

Una lista es una secuencia de elementos, para crearlas usamos corchetes [] o con
la función list, por ejemplo:

Las listas se pueden acceder a través de indices, éstos indices inician en cero (0)
```python
amigos = list()
numeros = [1,2,3,4,5]
```
Las listas son mutables, para añadir elementos a una lista podemos utilizar el método append

Las listas se pueden acceder con indices, que inician en cero.

```python
amigos=list()
amigos.append('Pedro')
amigos[0]
'Pedro'

amigos.append('Enrique')
amigos[1]
'Enrique'
```

### Operaciones con listas en Python
Cuando trabajamos con listas podemos también hacer operaciones por ejemplo,

#### Unir listas

```python
my_lista = [1]

my_lista2 = [2,3,4]

my_lista3 = my_lista + my_lista2

my_lista3 # [1,2,3,4]
```

#### Multiplicar elementos
```python
my_lista = ['a']
my_lista2 = my_lista * 5
my_lista2 # ['a','a','a','a','a']
```

#### Dividir listas

```python
my_lista = [1,2,3,4,5]
my_lista_reversed = my_lista[::-1]
my_lista_reversed # [5,4,3,2,1]
```
#### Eliminar último elemento de la lista
```python
my_lista = [1,2,3,4,5]
my_lista = my_lista.pop()
my_lista # [1,2,3,4]
```
#### Ordenar la lista
```python
my_lista = [2,1,5,4,3]
my_lista = my_lista.sort()
my_lista # [1,2,3,4,5]
```

#### Eliminar un elemento
```python
my_lista = [1,2,3,4,5]
del my_lista[0]
my_lista # [2,3,4,5]
```

## Diccionarios en Python
Un diccionario es un mapa de valores, los cuales deben tener una llave. Los
diccionarios se declaran con (llaves) `{}` o con la función `dict()`

Cuando iteramos en diccionarios podemos hacerlo a través de las llaves, valores o ítems.

#### Declarar diccionarios

```python
mi_diccionario = {}
mi_diccionario['primer_elemento'] = 'hola'
mi_diccionario['segundo_elemento'] = 'adios'
```
### Iterar en llaves
```python
for key in calificaciones.keys():
    print(key)
```
### Iterar en valores
```python
for value in calificaciones.values():
    print(value)
```
### Iterar en ítems
```python
#python2
for key, value in calificaciones.iteritems():
    print('llave: {}, valor: {}'.format(key, value))
    
#python3
for key, value in calificaciones.items():
    print('llave: {}, valor: {}'.format(key, value))
```

## Tuplas
- Las tuplas son una secuencia de valores indexada por enteros.
- Similares a la listas, con la gran diferencia que son inmutables.
- Las tuplas se crean separando los valores con comas (es práctica común encerrar
  los valroes en paréntesis).
- Se pueden utilizar para devolver mas de un valor en una función o crear estructuras de datos ligeras.

```python
mi_tupla = 1, 2, 3, 4
mi_tupla = (1, 2, 3, 4)
```

## Uso de sets en Python. Conjuntos.
Los sets son muy similares a las listas, pero estas no permiten elementos repetidos.

Cuando trabajamos con sets, podemos realizar las operaciones básicas de
conjuntos, esto quiere decir que se puede calcular los valores de intercepción,
diferencia, unión.

### Declarar sets
```python
s = set([1,2,3])
t = set([3,4,5])
```
### Operaciones con sets
```python
s.union(t) # set([1,2,3,4,5])
s.intersection(t) # set([3])
s.difference(t) # set([1,2])
t.difference(s) # set([4,5])
s.symmetric_difference(t) # set([1,2,4,5]) 

#python3
s = {1,2,3}
t = {3,4,5}

print(s | t) #union {1,2,3,4,5}
print(s & t) #interseccion {3}
print(s-t) #diferencia {1,2}
print(s ^ t) #diferencia simétrica {1,2,4,5} 

#Los sets son conjuntos por los que se les aplica teoria de conjuntos
#siempre que no nos interese si se repite un elemento es mas eficiento usar sets que lists
s = {1, 2, 3} # s = set([1, 2, 3])
t = {3, 4, 5}

print(s)
print(t)

print(s | t) # | union                  s.union(t)
print(s & t) # & interseccion           s.intersection(t)
print(s - t) # - diferencia             s.difference(t)
print(s ^ t) # ^ diferencia simetrica   s.symmetric_difference(t)
print(s <= t) # <= subconjunto          s.issubset(t)
print(s >= t) # >= superconjunto        s.issuperset(t)

```
## Dictionary comprehension - list comprehension
Dictionary comprehension y list comprehension nos permite escribir listas o
diccionarios de forma más sencilla.

>### Nota. Sugar sintactica.
>El azúcar sintáctico es un término acuñado por Peter J. Landin en 1964 para
 referirse a los añadidos a la sintaxis de un lenguaje de programación diseñados
 para hacer algunas construcciones más fáciles de leer o expresar.


Las Comprehensions son constructos que nos permiten generar una secuencia a
partir de otra secuencia.

### Existen tres tipos de comprehensions:

- List comprehensions
```python
[element for element in element_list if element_meets_condition]
```
- Dictionary comprehensions
```python
{key: element for element in element_list if element_meets_condition}
````
- Sets comprehensions
```python
{element for element in element_list if elements_meets_condition}
````



### Ejemplos

#### Números pares
```python
pares = []

for num in range(1,31):
    if num % 2 == 0:
        pares.append(num)
        
```
Esto mismo lo podemos expresar con una list comprehension

```python
pares = [num for num in range(1,31) if num % 2 == 0]
```


#### Para cuadrados

```python
cuadrados = {}

for num in range(1,11):
    cuadrados[num] = num ** 2
```

Esto mismo con sugar sictactico con comprehensions.

```python
squares = {num: num**2 for num in range(1,11)}
```


## Manjejo de Errores

[Excepciones](https://sodocumentation.net/es/python/topic/1788/excepciones)

```python
try:
	# Código a ejecutar
except:
	# Código para 'cachar' o 'recibir' el error y hacer algo
else:
	# Código cuando el try SÍ sirva y NO se ejecute el except
finally:	
	# Código que SIEMPRE se va a ejecutar, independientemente se ejecute el except o el else
```

## Manejo de archivos en Python
Con Python también podemos leer y escribir archivos del sistema.

Existen varios modos en los que podemos manejar archivos

- `r` = leer. Abre un arhcivo para escribir información
- `w` = escribir
- `a` = añadir. Abre un archivo para añadir informacion
- `r+` = leer y escribir
- `w+` = Escribir y leer
- `x` =  Crea el fichero, retorna error si el fichero existe.
- `t` = Modo texto
- `b` = Modo binario(ej. imagenes)


Siempre recuerda cerrar el archivo.

El keyword with nos permite manejar el contexto al trabajar con archivos


Nota. Context manager.
En muchos lenguajes de programación, existen ciertos procesos en los que las
instrucciones se usan estrictamente en parejas, con el fin de evitar errores. Por
ejemplo, para manejar archivos, se suele usar un comando para abrir el archivo, y
otro para cerrar el archivo y liberar los recursos asociados a este. Si no se
ejecutaran ambas instrucciones, los datos almacenados en el archivo podrían
perderse, o podrían generarse fugas de memoria o fallos del sistema


Justamente es para este tipo de situaciones es en las que python usa los context
manager (administradores o manejadores de contexto). Para continuar con el 
ejemplo, usando el context manager with, python se asegura de que una vez se 
termine la operación en la que está involucrada la apertura del archivo,
automáticamente el archivo sea cerrado y los recursos liberados (sin necesidad de
que el programador lo indique explícitamente)


### Links
- [python-docx Word](https://python-docx.readthedocs.io/en/latest/)
- [openpyxl - A Python library to read/write Excel 2010](https://openpyxl.readthedocs.io/en/stable/)


## Clases y métodos.

### Links 

- [Tipos de métodos en Python](https://blog.nearsoftjobs.com/tipos-de-m%C3%A9todos-en-python-cls-vs-self-d6da1e08efa8)
- [Properties vs. Getters and Setters](https://www.python-course.eu/python3_properties.php)

Los atributos/métodos privados son precedidas por dos guiones bajos, los
atributos/métodos protegidos son precedidos por un guion bajo (protegidas y
privadas NO son lo mismo en Python), abajo una explicación sencilla.


### MODO PROTEGIDO
Está precedido por un guion bajo.
Solamente puede ser accedido por esa clase y sus sub-clases.
Es una buena práctica para uso interno y para evitar colisiones de los mismos
nombres de métodos o atributos que puedan ser causados por herencia (tema que se
tratará después en otros videos o cursos).

```python
self._miatributoprotegido = x
```

### MODO PRIVADO
Precedido por DOBLE guion bajo.
Solo puede ser accedido o modificado si se especifica la respectiva clase.

```python
self.__miatributoprivado = x
```

Ejemplo de atributo privado y protegido y como éstos deben ser accedidos.

```python
class Usuario:
	def__init__(self, nombre, clave):
		self.nombre = nombre
		self.__clave = clave

usuario1 = Usuario(“Roberto”, “qwerty”)
print(usuario1.nombre, usuario1._Usuario__clave)

class Usuario2:
	def__init__(self, nombre, clave):
		self.nombre = nombre
		self._clave = clave

usuario2 = Usuario2(“Gerardo”,“asdfgh”)
print(usuario2.nombre, usuario2._clave)

```

## Decoradores
Decoradores
Python es un lenguaje que acepta diversos paradigmas como programación orientada
a objetos y la programación funcional, siendo estos los temas de nuestro 
siguiente módulo.


Los decoradores son una función que envuelve a otra función para modificar o
extender su comportamiento.

En Python las funciones son ciudadanos de primera clase, first class citizen,
esto significan que las funciones pueden recibir funciones como parámetros y
pueden regresar funciones. Los decoradores utilizan este concepto de manera ç
fundamental.


Un decoradores una función que recibe otra función y regresa una tercera función.
Para reconocer un decorador, puedes ver que tienes un arroba sobre la declaración
de una función.


-[Argumentos en funciones (*args y **kwargs)](https://recursospython.com/guias-y-manuales/argumentos-args-kwargs/)
-[Curso Python. Decoradores I. Vídeo 73](https://www.youtube.com/watch?v=DQXm6bIZgvk)


## Entorno virtual en Python
- [Tutorial de Python virtualenv](https://rukbottoland.com/blog/tutorial-de-python-virtualenv/)

En Python la comunidad comparte su código usando PyPi (python package index), es
un repositorio para instalar módulos de la comunidad.

Con `pip install [nombre]` se puede instalar el paquete que deseas.

Podemos utilizar `requirements.txt` para ordenar los paquetes que requiere tu proyecto.

### Ambiente virtual
Nos permite encapsular un proyecto para poder instalar las versiones de los
paquetes que se requieran sin tenerlos que instalar en todo el sistema operativo.

### Crear un entorno virtual
Dentro de la carpeta de tu proyecto ejecutas
```python
virtualenv venv
```

### Encender un entorno virtual
```python
source venv/bin/activate

#python3
source venv/scripts/activate

```

### Ver las dependencias instaladas en el entorno virtual
```python
pip freeze
```

### Instalar dependencias del archivo requirements
```python
pip install -r requirements.txt
```

## Web Scrapping
- [Qué es el web scraping](https://aukera.es/blog/web-scraping/)
