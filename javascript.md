---
title: "JavaScript"
tags: ""
---

## ¿Cómo nace Javascript?
Nace con la necesidad de generar dinamismo en las páginas web y que a su vez los usuarios y las empresas pudieran interactuar unos con otros.
### ¿Qué es Javascript?
Es un lenguaje interpretado, orientado a objetos, débilmente tipado y dinámico.
Débilmente tipado
Se pueden hacer operaciones entre tipos distintos de datos (enteros con strings, booleanos con enteros, etc). Ejemplo:
```js
4 + "7"; // 47
4 * "7"; // 28
2 + true; // 3
false - 3; // -3
```
### Dinámico
Corre directamente en la etapa de Runetime sin una etapa de compilación previa. Esto permite probar nuestro código inmediatamente; pero también es lo que hace que los errores se muestren hasta que se ejecuta el programa.

### ¿Realmente es Javascript un lenguaje interpretado?
Si, y la razón es que le navegador lee linea por linea nuestro código el cuál le indica lo que tiene que hacer, sin la necesidad de compilar. Todo esto es controlado por el motor de Javascript V8 del navegador

### Javascript es Basckwards Compatible
Todas las funciones nuevas que salen de Javascript no dañarán el trabajo ya hecho, pero no se podrá utilizar en nuestro entorno de trabajo inmediatamente. Para solucionar esto está Babel que permite utilizar las nuevas características del lenguaje pero lo transforma a una versión que el navegador pueda entender.

## ¿Por qué JavaScript?
JavaScript tiene una comunidad enorme de desarrolladores que te pueden ir ayudando a generar diferentes cosas.

Si solo estuvieras interesado en trabajar aplicaciones web tienes muchos frameworks y librerías construidas en JavaScript que te van a ayudar a hacer proyectos de forma mucho mas rápida, eficiente y robusta (Angular, Vue, React, entre otros)

Si no quieres trabajar solo en aplicaciones Web puedes utilizar JavaScript con un framework que se llama React Native para poder construir aplicaciones nativas como Android y IOS.

Puedes construir aplicaciones de escritorio con JavaScript, usando un framework llamado Electron, pueden correr en Mac o Windows.

También puedes trabajar en la parte del Back-end o **IOT **(Internet Of Things) es un concepto que se refiere a una interconexion digital de objetos cotidianos con Internet. Esto con un Framework llamado NodeJS, el cual es un entorno de ejecución de JavaScript que corre directamente en el Back-end.

![tipo de datos](https://i.ibb.co/WvW72Vv/js-tipo-datos.png)

## Variables

Dentro de JavaScript tenemos tres formas de declarar una variable las cuales son: var, const y let.

1. Var: Era la forma en que se declaraban las variables hasta ECMAScript 5. Casi ya no se usa porque es de forma global y tiene las siguientes características:

	- Se puede reinicializar: osea todas las variables se inicializan, por ejemplo: 	Var pokemonType = ‘electric’ entonces reinicializar es:	Var pokemonType = ‘grass’ osea la misma variable con diferentes datos el último dato predomina.
    - Se puede reasignar: osea la variable ya inicializada le reasignamos otro valor por ejemplo: inicializamos la variable: Var pokemonType = ‘electric’ ahora la reasignamos pokemonType = ‘grass’ ya no va var 
    - Se alcance es función global: osea inicializamos la variable, pero la podemos llamar desde cualquier bloque (una llave abierta y una cerrada {}) pero hay que tener mucho cuidado con ello ya que puede haber peligro, no es recomendable usar VAR.

2. const: sirve para declarar variables que nunca van a ser modificadas:
	- No se puede reinicilizar: es una const única no puede haber otra inicializada con el mismo nombre. const pokemonType = ‘electric’ no puede haber: const pokemonType = ‘grass’
	- No se pude re asignar: una vez que la hayamos inicializado no la podemos reasignar solo con su nombre: const pokemonType = ‘electric’ no puede ejecutarse: pokemonType = ‘grass’
	- No es inmutable: osea no puede cambiar con objetos:

3. Let: Son variables que pueden ser modificadas, se pueden cambiar:
	- No se puede reinicilizar: es una const única no puede haber otra inicializada con el mismo nombre. let pokemonType = ‘electric’ no puede haber: let pokemonType = ‘grass’
	- Se puede reasignar: Osea la variable ya inicializada le reasignamos otro valor por ejemplo: inicializamos la variable: let pokemonType = ‘electric’ ahora la reasignamos pokemonType = ‘grass’
	- Su contexto de es bloque: Solo funciona dentro de un bloque {}, fuera de ello no.
    
## Tipos de funciones
Cuando hablamos de funciones en JavaScript, tenemos dos tipos de funciones: Funciones Declarativas (function declaration / function statement) y Expresiones de función (function expression / funciones anónimas).

### Funciones Declarativas:
En las funciones declarativas, utilizamos la palabra reservada function al inicio para poder declarar la función:

```js
function saludar(nombre) {
	console.log(`Hola ${nombre}`);
}

saludar('Diego');
```
### Expresión de función:
En la expresión de función, la declaración se inicia con la palabra reservada var, donde se generará una variable que guardará un función anónima.

```js
var nombre = function(nombre){
    console.log(`Hola ${nombre}`)
}

nombre(‘Diego’);
```
En la expresión de función, la función podría o no llevar nombre, aunque es más común que se hagan anónimas.

### Diferencias:
A las funciones declarativas se les aplica hoisting, y a la expresión de función, no. Ya que el hoisting solo se aplica en las palabras reservadas var y function.

Lo que quiere decir que con las funciones declarativas, podemos mandar llamar la función antes de que ésta sea declarada, y con la expresión de función, no, tendríamos que declararla primero, y después mandarla llamar.


## Valores Truthy y Falsy
[Truthy](https://developer.mozilla.org/es/docs/Glossary/Truthy)
```js
//Ejemplos en los que Boolean devuelve Falso:
Boolean(0); //false
Boolean(null); //false
Boolean(NaN); //false
Boolean(undefined); //false
Boolean(false); //false
Boolean(true); //true
Boolean(""); //false

//Ejemplos en los que Boolean devuelve verdadero:
Boolean(1); //true para 1 o cualquier número diferente de cero (0)
Boolean(-1); //true
Boolean("a"); //true para cualquier caracter o espacio en blanco en el string
Boolean([]); //true aunque el array esté vacío
Boolean({}); //true aunque el objeto esté vacío
Boolean(function(){}); //Cualquier función es verdadera también
```

## OPERADORES: ASIGNACION, LOGICOS Y ARITMETICOS
[Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)

```js
//Operadores binarios:
3 + 2//Suma
50 - 10// Resta
10 * 20//Multiplicación
20 / 2//División

"Diego " + "De Granda"//concatenación de strings

//Operadores unitarios:
!false//negación de la negación = true

//Operadores de asignación:
var a = 1; //Asignamos un valor a la variable

//Operadores para comparar:
3 == "3"; //Compara los valores y devuelve "true" en este caso

3 === "3"; //Compara y valida los tipos y valores. Devuelve "falso" en este caso

5 < 3//Compara y valida si el 5 es menor a 3
5 > 3//Compara y valida si el 5 es mayor a 3
5 <= 6//Compara y valida si el 5 es menor o igual al 6
5 >= 6//Compara y valida si el 5 es mayor o igual al 6

a && b //Valida si ambas variables son verdaderas para que se cumpla la condición
a || b //Aquí se cumple la condición si alguna de las dos variables es verdadera

var edad = 40
edad++ //Incrementa el valor en 1

edad += 2//Incrementa el valor por 2
```

### Operador de asignacion
| símbolo  |  descripción |  
|---|---|
| = |  operador de asignacion |   


### Operadores de comparacion
| símbolo  |  descripción |  
|---|---|
|==	|igual que|
|===|estrictamente igual que|
|> or >= or >==	|mayor o mayor igual que|
|< or <= or <==	|menor o menor igual que|
|!= or !==|	diferente que|

### Operadores aritmeticos
| símbolo  |  descripción |  
|---|---|
|+	|operador suma este se utiliza para concatener dos cadenas de texto|
|-	|operador resta|
|*	|operador de multicacion|
|/	|operador de division|
|%	|operador de modulo|
|**	|operador de potenciacion. tambien se les conoce como operadores binarios. por que toman dos valores y generan un resultado.|

## Operadores logicos
| símbolo  |  descripción |  
|---|---|
|!	NOT| niega un valor|
|&&	|AND|
| \|\||	OR|

## Arrays
```js
var frutas = ["Manzana", "Plátano", "Cereza", "Fresas"];

console.log(frutas);

console.log(frutas.length); // lingitud o numero de elementos
console.log(frutas[n]); // acceder al elemento por medio de index

//Mutar o alterar Array
var masFrutas = frutas.push("Uvas") //añadir elementos al final del array
var ultimo = frutas.pop()//Eliminar el último elemento del Array
var nuevaLongitud = frutas.unshift("Uvas");//añadir elemento al inicio del array
var borrarFruta = frutas.shift();//Borrar el primer elemento
var posicion = frutas.indexOf("Cereza");//Devuelve el index o posicion del elemento```
```

## Asincronismo

JavaScript sólo puede hacer una cosa a la vez, sin embargo; es capaz de delegar la ejecución de ciertas funciones a otros procesos. Este modelo de concurrencia se llama **EventLoop.**

JavaScript delega en el navegador ciertas tareas y les asocia funciones que deberán ser ejecutadas al ser completadas. Estas funciones se llaman callbacks, y una vez que el navegador ha regresado con la respuesta, el callback asociado pasa a la cola de tareas para ser ejecutado una vez que JavaScript haya terminado todas las instrucciones que están en la pila de ejecución.

Si se acumulan funciones en la cola de tareas y JavaScript se encuentra ejecutando procesos muy pesados, el EventLoop quedará bloqueado y esas funciones pudieran tardar demasiado en ejecutarse.

## APIs
- [Public APIs](https://github.com/public-apis/public-apis)
- [The Star Wars API](https://swapi.dev/)
- [Rick & Morty API](https://rickandmortyapi.com/)


## Callbacks

### Links
- [Que es el Callback Hell y como evitarlo](https://codearmy.co/que-es-el-callback-hell-y-como-evitarlo-4af418a6ed14)

### Ventajas y Desventajas
V = Es simple una función que recibe otra función
V = Son universales
D = Composición tosca
D = Callbacks Hell
D = Flujo poco intuitivo
D = Debemos pensar que estamos haciendo código para humanos y debe ser facil de leer
D = if FecthData, if FecthData, if FecthData y se vuelve tedioso y no se maneja excepciones

## Promesas
En esta clase veremos las promesas, que son valores que aun no conocemos. Las promesas tienen tres estados:
- pending
- fullfilled
- rejected

Las promesas se invocan de la siguiente forma:

```js
new Promise( ( resolve, reject ) => {
  // --- llamado asíncrono
  if( todoOK ) {
     // -- se ejecutó el llamado exitosamente
     resolve()
  } else {
     // -- hubo un error en el llamado
     reject()
  }
} )

```
### Ventajas y desventajas
V = Fácilmente enlazable then y return, then y return y asi
V = Es poderoso // es muy recomendado para desarrolladores
D = NO maneja excepciones si no maneja un catch al final y seremos propensos a errores
D = Requiere un polyfile para ser transpilados y ser interpretados en todos los navegadores //Babbel

### Links
- [Qué son y cómo funcionan las promesas en JavaScript](https://platzi.com/blog/que-es-y-como-funcionan-las-promesas-en-javascript/)
- [Promise: Te lo prometo por JavaScript](https://medium.com/@mvtercero85/promise-te-lo-prometo-por-javascript-8b3ae2c5bbb4)

## ASYNC/AWAIT
Async/Await hace que nuestro codigo funcione como codigo sincrono.

### Vetajas y desventajas
V = El tradicional try - catch y manejar las excepciones de manera mas fluida
V = Mas fáciles de leer que sucedera que va a suceder
D = Ese poder que podemos decir es decir si queremos algo debemos esperar que algo suceda
D = Requiere un polyfile para ser transpilados y ser interpretados en todos los navegadores //Babbel

### Links
- [ASYNC y AWAIT en Javascript #ES6](https://www.youtube.com/watch?v=pywyV4pbnQQ)
- [MDN- Función async](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Sentencias/funcion_asincrona)
