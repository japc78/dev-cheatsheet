---
title: "POO"
tags: ""
---

## ¿Por qué aprender Programación Orientada a Objetos?

- Vas a programar más rápido. Tener un análisis previo de lo que estás realizando te ayudará a generar código mucho más veloz

- Dejas de ser Programador Jr. Podrás responder preguntas como ¿Qué es encapsulamiento?, ¿Qué es Abstracción?, ¿Qué es Herencia?, ¿Qué es Polimorfismo? en futuras entrevistas de trabajo

- Dejar de Copiar y Pegar Código.

## ¿Qué resuelve la Programación Orientación a Objetos?
La programación Orientada a Objetos nace de los problemas creados por la programación estructurada y nos ayuda a resolver cierto problemas como:

- Código muy largo: A medida que un sistema va creciendo y se hace más robusta el código generado se vuelve muy extenso haciéndose difícil de leer, depurar, mantener.

- Si algo falla, todo se rompe: Ya que con la programación estructurada el código se ejecuta secuencialmente al momento de que una de esas líneas fallara todo lo demás deja de funcionar.

- Difícil de mantener.

## Paradigma Orientado a Objetos
La Programación Orientada a Objetos viene de una filosofía o forma de pensar que es la Orientación a Objetos y esto surge a partir de los problemas que necesitamos plasmar en código.

Es analizar un problema en forma de objetos para después llevarlo a código, eso es la Orientación a Objetos.

Un paradigma es una teoría que suministra la base y modelo para resolver problemas. La paradigma de Programación Orientada a Objetos se compone de 4 elementos:

- Clases
- Propiedades
- Métodos
- Objetos

Y 4 Pilares:
- Encapsulamiento
- Abstracción
- Herencia
- Polimorfismo

## Lenguajes Orientados a Objetos
Algunos de los lenguajes de programación Orientados a Objetos son:

- Java:
	- Orientado a Objetos naturalmente
	- Es muy útilizado en Android
	- Y es usado del lado del servidor o Server Side
- PHP
	- Lenguaje interpretado
	- Pensado para la Web
- Python
	- Diseñado para ser fácil de usar
	- Múltiples usos: Web, Server Side, Análisis de Datos, Machine Learning, etc
- Javascript
	- Lenguaje interpretado
	- Orientado a Objetos pero basado en prototipos
	- Pensado para la Web
- C#
- Ruby
- Kotlin

## Diagramas de Modelado
- OMT: Object Modeling Techniques. Es una metodología para el análisis orientado a objetos.

- UML: Unified Modeling Language o Lenguaje de Modelado Unificado. Tomó las bases y técnicas de OMT unificándolas. Tenemos más opciones de diagramas como lo son Clases, Casos de Uso, Objetos, Actividades, Iteración, Estados, Implementación. [aprender UML en 24 horas](https://es.slideshare.net/still01/aprendiendo-uml-en-24-horas-16815956)

## UML
Como ya viste UML significa Unified Modeling Language el cual es un lenguaje estándar de modelado de sistemas orientados a objetos.

Esto significa que tendremos una manera gráfica de representar una situación, justo como hemos venido viendo. A continuación te voy a presentar los elementos que puedes utilizar para hacer estas representaciones.

Las clases se representan así:
![](http://drive.google.com/uc?export=view&id=13gXDGbb4_50w2zvtM1IFVeQevGJ5Fg08)

En la parte superior se colocan los atributos o propiedades, y debajo las opera ciones de la clase. Notarás que el primer caracter con el que empiezan es un símbolo. Este denotará la visibilidad del atributo o método, esto es un término que tiene que ver con Encapsulamiento y veremos más adelante a detalle.

Estos son los niveles de visibilidad que puedes tener:
- \- private
- \+ public
- \# protected
- ~ default

Una forma de representar las relaciones que tendrá un elemento con otro es a través de las flechas en UML, y aquí tenemos varios tipos, estos son los más comunes:

### Asociación
![](http://drive.google.com/uc?export=view&id=1nX06giUh7PCRwwB1dJwLS_UhDqPmPYf3)

Como su nombre lo dice, notarás que cada vez que esté referenciada este tipo de flecha significará que ese elemento contiene al otro en su definición. La flecha apuntará hacia la dependencia.

![](http://drive.google.com/uc?export=view&id=1Ek85X4XAg4zo7cjHXHBgHYn7FHl0feNG)


Con esto vemos que la ClaseA está asociada y depende de la ClaseB.

### Herencia

![](http://drive.google.com/uc?export=view&id=1PVt_U4QU0EPEW-nB4_dB6w8UlAjIBek5)

Siempre que veamos este tipo de flecha se estará expresando la herencia.
La dirección de la flecha irá desde el hijo hasta el padre.

![](http://drive.google.com/uc?export=view&id=1rPpwT3pxbXjfq3mcksZbEeM9PRew-fJ2)

Con esto vemos que la ClaseB hereda de la ClaseA

### Agregación

![](http://drive.google.com/uc?export=view&id=1AwSjnjjHAvJH82mEz57b0eGMRgpKau6z)

Este se parece a la asociación en que un elemento dependerá del otro, pero en este caso será: Un elemento dependerá de muchos otros. Aquí tomamos como referencia la multiplicidad del elemento. Lo que comúnmente conocerías en Bases de Datos como Relaciones uno a muchos.

![](http://drive.google.com/uc?export=view&id=1zCbYmzxOiuhtYIa5c9Msv8505bRyejOR)

Con esto decimos que la ClaseA contiene varios elementos de la ClaseB. Estos últimos son comúnmente representados con listas o colecciones de datos.

### Composición

![](http://drive.google.com/uc?export=view&id=1KElwmhgBSWpfKlQ5WqdKDIGTvdexpNUD)
Este es similar al anterior solo que su relación es totalmente compenetrada de tal modo que conceptualmente una de estas clases no podría vivir si no existiera la otra.

![](http://drive.google.com/uc?export=view&id=1MO_DXfKMiv7JQiKGLGvNTvUZsSByl2Co)

Con esto terminamos nuestro primer módulo. Vamos al siguiente para entender cómo podemos hacer un análisis y utilizar estos elementos para construir nuestro diagrama de clases de Uber.



## Objetos
Los Objetos son aquellos que tienen propiedades y comportamientos, también serán sustantivos.

- Pueden ser Físicos o Conceptuales

Las **Propiedades** también pueden llamarse atributos y estos también serán sustantivos. Algunos atributos o propiedades son nombre, tamaño, forma, estado, etc. Son todas las características del objeto.

Los **Comportamientos** serán todas las operaciones que el objeto puede hacer, suelen ser verbos o sustantivos y verbo. Algunos ejemplos pueden ser que el usuario pueda hacer login y logout.


## Abstracción y Clases
Una Clase es el modelo por el cual nuestros objetos se van a construir y nos van a permitir generar más objetos.

Analizamos Objetos para crear Clases. Las Clases son los modelos sobres los cuales construiremos nuestros objetos.

Abstracción es cuando separamos los datos de un objeto para generar un molde.

## Modularidad
La modularidad va muy relacionada con las clases y es un principio de la Programación Orientado a Objetos y va de la mano con el Diseño Modular que significa dividir un sistema en partes pequeñas y estas serán nuestros módulos pudiendo funcionar de manera independiente.

La modularidad de nuestro código nos va a permitir

- Reutilizar
- Evitar colapsos
- Hacer nuestro código más mantenible
- Legibilidad
- Resolución rápida de problemas

Una buena práctica es separando las clases en archivos diferentes.

## ¿Qué es la herencia?
Don’t repeat yourself es una filosofía que promueve la reducción de duplicación en programación, esto nos va a inculcar que no tengamos líneas de código duplicadas.

Toda pieza de información nunca debería ser duplicada debido a que incrementa la dificultad en los cambios y evolución

La herencia nos permite crear nuevas clases a partir de otras, se basa en modelos y conceptos de la vida real. También tenemos una jerarquía de padre e hijo.

## Objetos, método constructor y su sintaxis en código
Los objetos nos ayudan a crear instancia de una clase, el objeto es el resultado de lo que modelamos, de los parámetros declarados y usaremos los objetos para que nuestras clases cobren vida.

Los **métodos constructores** dan un estado inicial al objeto y podemos añadirle algunos datos al objeto mediante estos métodos. Los atributos o elementos que pasemos a través del constructor serán los datos mínimos que necesita el objeto para que pueda vivir.

### Metodo constructor
- Dar un espacio inicial al objeto.
- Tiene el mismo nombre de la clase.
- Son los parámetros mínimos que necesita el objeto para que pueda vivir.

### Java
```java
//Metodo constructor
public Person(String name) {
	this.name = name;
}

//Instaciar un objeto
Person person = new Person();
```
### Python
```python
#Metodo constructor
def __init__(self, name):
    self.name = name

#Instanciar un objeto
person = Person()
```
### JavaScript
```js
//Metodo constructor
function Person(name) {
	this.name = name;
}

//Instanciar un objeto
var person = new Person();
```
### PHP
```php
//Metodo constructor
public function __construct($name) {
	$this->name = name;
}

//Instanciar un objeto
$person = new Person();
```

## Herencia

- Java. `class Stundent extends Person`
- Python. `class Student(Person):`
- JavaScript `student.prototype = new Person();`
- PHP. `class Student extends Person`


## Encapsulamiento:
Es hacer que los datos sean inviolables, inalterable o hacer que se esconda, cuando se le asigne un Modificador de Acceso.

Modificadores de Acceso:
- Public: Es el mas permisivos de todos, Accede a todo.
- Protected: Podrá ser accedido por la clase, paquetes y subclases.
- Default: Permite el acceso a nivel de clses de internas y paquetes (No podremos ver las herencias si ha detener (Osea subclases))
- Private: Solo podrá ser modificado dentro de la clase.

Se puede encapsular: elementos o atributos, clases o incluso métodos; El encapsulamiento nos permite tener dicho elemento inalterable en la POO.

![](http://drive.google.com/uc?export=view&id=1w-N6CrPaoYzuFKH1XLd3Xh747d1cUt1f)





## En Resumen
En la POO hay 5 cosas fundamentales:

Clases: Son el molde más genérico y del cual podemos instanciar muchos objetos.
Objetos: Son creados de las clases y tienen datos y funcionalidad.
Atributos: Son las características especificas del objeto (Son las variables dentro del código)
Métodos: Son las funciones o acciones que puede hacer este objeto.
**Instaciar:**Es la creación de un objeto desde una clase a eso se le llama instancia o instancias.
Los pilares de la POO son:
Abstracción: Es separar cada uno de los datos de un objeto para poder crear su molde (clase)
Encapsulamiento: Es aislar un dato para que este sea privado y no pueda ser visto o modificado.
Herencia: Es crear una o más clases a partir de una clase que ya existe. Y se les llaman subclases.
**Polomorfismo:**Es construir métodos con el mismo nombre pero con comportamiento diferente.
