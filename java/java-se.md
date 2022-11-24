---
title: "Java SE"
tags: ""
---

Java es un lenguaje de programación de alto nivel (aunque no tan alto como Python o JavaScript) que nos ayuda a construir aplicaciones para diferentes dispositivos y sistemas operativos.

Fue creado en 1991 por James Gosling mientras trabajaba en Sun Microsystems, una empresa que luego fue adquirida por Oracle. Esto significa que Java tiene muy buen mantenimiento, pero también algunos cambios con los que no todos estaremos de acuerdo.

Java tiene dos categorías: Standard Edition para construir aplicaciones de escritorio o consola y Enterprise Edition para que las empresas trabajen aplicaciones web de última generación.

En este curso aprenderemos los fundamentos de Java Standard Edition: la sintaxis del lenguaje, declarar variables, trabajar con funciones, ciclos y condicionales, lógica de programación, algoritmos y muchas otras cosas.

Pero no te preocupes. Java sigue filosofía de Write Once, Run Anywhere (WORA), por lo que todo lo que aprendas en este curso lo podrás aplicar también con Java EE.

## Versiones de Java y JDK
El JDK o Java Development Kit se compone de los siguientes elementos:

- Java Runtime Environment (JRE): La máquina virtual de Java, lo que nos permite que al escribir el mismo código funcione igual en todos los dispositivos y sistemas operativos.
- Compilador de Java: El encargado de traducir nuestro código en Java a un lenguaje que puede entender e interpretar nuestra máquina virtual.
- APIs de desarrollo: Una base de código lista para ayudarnos a desarrollar.

Las APIs de desarrollo con Java han evolucionado con el tiempo, por lo que existen diferentes versiones de java que puedes utilizar. La versión que más elevo la popularidad y las ofertas de trabajo con Java fue Java SE 6.

En Java SE 9 anunciaron que las actualizaciones ocurrirían cada 6 meses, pero las versiones LTS (Long Time Support) tendrán mantenimiento por 3 años, así que las actualizaciones son necesarias, pero no urgentes.

En este curso vamos a trabajar con la versión Java SE 11 LTS, la primera versión de Java con licencia. Solo podremos usarlo gratis cuando trabajemos en ambientes de desarrollo y testing. De otra forma, debemos pagar 2.5 USD al mes por usuario de escritorio y 25 USD por procesador para aplicaciones de servidor.

Afortunadamente, OpenJDK es una versión gratis y open source de usar Java SE Platform Edition.

## Las herramientas más usadas de Java
Java 8 (LTS) es la versión más usada de Java hasta inicios del 2019, pero solo tendrá soporte hasta diciembre del 2020, luego de esta fecha tendremos que pagar una licencia para continuar con su soporte.

Java 10 introdujo algunos cambios en la forma de declarar variables, así que en este curso vamos a trabajar con las versiones 8 y 11 de Java.

La herramienta más usada para construir proyectos web con Java es Maven, pero también existen otras alternativas como Gradle. También existen frameworks como Spring para trabajar con Java EE y ORMs como Hibernate para trabajar con bases de datos.

Los IDEs son entornos de desarrollo integrados, herramientas (aplicaciones, seguramente de escritorio) que nos ayudan a escribir nuestro código con editores, compiladores, depuradores y constructores de interfaces gráficas, todo en un mismo lugar.

El IDE recomendado por Oracle es NetBeans, pero también están Eclipse e IntelliJ IDEA, este último es el que más fuerza ha tomado gracias a Kotlin. Las tres herramientas son gratuitas, pero IntelliJ IDEA también tiene una versión de pago.

## Etapas de la programación en Java
1. Escribir nuestros archivos .java.
2. Compilar, cargar y verificar nuestros archivos con javac (los IDEs nos permiten compilar con solo presionar un botón).
3. Al compilar obtenemos archivos .class con código que nuestras computadoras pueden entender (Byte Code).
4. La JVM (Java Virtual Machine) se encarga de ejecutar el código de forma que funcione en cualquier dispositivo o sistema operativo.

Java es un lenguaje compilado e interpretado al mismo tiempo.

## Variables en Java
Una variable es un espacio de memoria (RAM) que contiene un dato de tipo numérico, booleano, de texto u otros tipos de datos un poco más complejos.

Las variables en Java se componen de un nombre único y un valor que puede cambiar a lo largo de la ejecución del programa. Al declarar las variables debemos definir el tipo de dato que vamos a usar y un punto y coma al final:
```java
// Variables.java

public class Variables {
  public static void main(String[] args) {
    // Declarar la variable speed de tipo int (números enteros)
    int spped;

    // Actualizar el contenido de la variable speed:
    spped = 10; // si ya habías declarado la variable

    // Declarar una variable y asignarle un valor al mismo tiempo:
    int salary = 1000;

    // Crear una variable de tipo String:
    String eployeeName = "Anahí Salgado";
  }
}

```

## Convención de Nombres en Java
Una convención de nombres es un patrón que deben seguir los nombres de las variables para que el código esté organizado, entendible y sin repetidos.

- Java es sensible a mayúsculas y minúsculas, este punto es clave al seguir una convención.
- Las variables siempre deben comenzar con un simbolo de letra, $ o _.
- No puedes usar el simbolo - en ninguna parte de la variable.

Las variables constantes son variables cuyo valor nunca va a cambiar, por lo que se deben escribir completamente en mayúsculas y usando el caracter _.

## Técnica de Naming: Camel Case
Camel Case es una convención muy popular para nombrar nuestras variables. Podemos usarlo en modo Upper Camel Case o Lower Camel Case, la diferencia es si comenzamos el nombre de la variable con mayúscula o minúscula.
```java
// Upper Camel Case:
class SoyUnaClase {};

// Lower Camel Case
int soyUnNumeroInt = 10;
```
Debemos usar Upper Camel Case en los nombres de las clases y archivos. Y Lower Camel Case en los nombres de las variables o métodos.

## Tipos de datos numéricos
Tipos de datos para números enteros (sin decimales):

- `byte`: Ocupa 1 byte de memoria y su rango es de -128 hasta 127.
- `short`: Ocupa 2 bytes de memoria y su rango es de -32,768 hasta 32,727.
- `int`: Ocupa 4 bytes de memoria y su rango es de -2,147,483,648 hasta 2,147,483,647. Es muy cómodo de usar, ya que no es tan pequeño para que no quepan nuestros números ni tan grande como para desperdiciar mucha memoria. Puede almacenar hasta 10 dígitos.
- `long`: Ocupa 8 bytes de memoria y su rango es de -9,223,372,036,854,775,808 hasta 9,223,372,036,854,775,807. Para diferenciarlo de un tipo de dato long debemos terminar el número con la letra L.

Por ejemplo:
```java
// Int:
int n = 1234567890;

// Long:
long nL = 123456789012345L;
```
Tipos de datos para números flotantes (con decimales):
- `float`: Ocupan 4 bytes de memoria y su rango es de 1.40129846432481707e-45 hasta 3.40282346638528860e+38. Así como long, debemos colocar una letra F al final.
- `double`: Ocupan 8 bytes de memoria y su rango es de 4.94065645841246544e-324d hasta 1.79769313486231570e+308d.
    
Por ejemplo:

```java
// Double:
double nD = 123.456123456;

// Float
float nF = 123.456F;
```
## Tipos de datos char y boolean
- char: Ocupa 2 bytes y solo puede almacenar 1 dígito, debemos usar comillas simples en vez de comillas dobles.
- boolean: Son un tipo de dato lógico, solo aceptan los valores true y false. También ocupa 2 bytes y almacena únicamente 1 dígito.

> Seguro te diste cuenta que siempre debemos escribir el tipo de dato de nuestras variables antes de definir su nombre y valor. Pero esto cambia a partir de **Java 10: solo debemos escribir la palabra reservada var y Java definirá el tipo de dato de nuestras variables automáticamente:**

```java
var salary = 1000; // INT
var pension = salary * 0.03; // DOUBLE
var totalSalary = salary - pension; // DOUBLE
```
Recuerda que esto solo funciona con versiones superiores a Java 10.
   
## Operadores de Asignación, Incremento y Decremento

#### Operadores de asignación:

- \+=: a += b es equivalente a a = a + b.
- \-=: a -= b es equivalente a a = a - b.
- \*=: a *= b es equivalente a a = a * b.
- /=: a /= b es equivalente a a = a / b.
- %=: a %= b es equivalente a a = a % b.

### Operadores de incremento:

- \++: i++ es equivalente a i = i + 1.
- \--: i-- es equivalente a i = i - 1.
Podemos usar estos operadores de forma prefija (++i) o postfija (i++). La diferencia está en qué operación se ejecuta primero:

```java
// Incremento postfijo:
int vidas = 5;
int regalo = 100 + vidas++;

System.out.println("Regalo: " + regalo + ", vidas: " + vidas);
// Regalo: 105, vidas: 6

// Incremento prefijo:
int vidas = 5;
int regalo = 100 + ++vidas;

System.out.println("Regalo: " + regalo + ", vidas: " + vidas);
// Regalo: 106, vidas: 6  

```

## Operaciones matemáticas
`Math` es una clase de Java que nos ayuda a ejecutar diferentes operaciones matemáticas:

```java
Math.PI // 3.141592653589793
Math.E // 2.718281828459045

Math.ceil(2.1) // 3.0 (redondear hacia arriba)
Math.floar(2.1) // 2.0 (redondear hacia abajo)

Math.pow(2, 3) // 8.0 (número elevado a una potencia)
Math.sqrt(3) // 1.73... (raíz cuadrada)

Math.max(2, 3) // 3.0 (el número más grande)

// Área de un círculo (PI * r^2):
Math.PI * Math.pow(r, 2)

// Área de una esfera (4 * PI * r^2):
4 * Math.PI * Math.pow(r, 2)

// Volumen de una esfera ( (4/3) * PI * r^3):
(4/3) * Math.PI * Math.pow(r, 3)
   
```

## Cast en variables: Estimación y Exactitud
En la programación hay situaciones donde necesitamos cambiar el tipo de dato de nuestras variables, esto lo conocemos como Cast.

Estimación:

```java
double monthlyDogs = dogsQuantity / 12.0;
// monthlyDogs: 2.5 (pero no es posible, ¡no rescatamos medio perrito!)

int estimatedMonthlyDogs = (int) monthlyDogs;
// estimatedMonthlyDogs: 2

// Recuerda que el casteo no redondea, solo quita los decimales:
Math.sqrt(3) // 1.7320508075688772
(int) Math.sqrt(3) // 1
``` 
Exactitud:

```java
int a = 30;
int b = 12;

a / b // 2
(double) a / b // 2.5
```

## Casteo entre tipos de datos
Java nos ayuda a realizar casteo automático de los tipos de datos más chicos a otros más grandes.

Sin embargo, en algunos casos vamos a necesitar realizar un cast manualmente, así como aprendimos en la clase anterior ((dataType) variableOperación).

Por ejemplo: supongamos que declaramos dos variables a y b de tipo int y una variable c de tipo double que es igual a la división de las primeras dos variables.

En este caso, aunque definimos que el tipo de dato de c es double, Java automáticamente convertirá el resultado de la división a tipo int, ya que este es el tipo de datos de las dos variables que dividimos, pero seguirá respetando que la variable c es de tipo double y añadirá un decimal al final (.0).

Esto significa que muchas de nuestras operaciones pueden verse afectadas. Por ejemplo:

```java

int a = 30;
int b = 12;

double c = a / b;
System.out.println(c); // 2.0 (??)

```
En este caso, ya que Java convierte nuestras variables automáticamente, debemos indicarle a nuestra variable c (de tipo double) que debe hacer cast de su valor para que Java no altere los valores de las variables y el resultado de la operación sea correcto:

```java
int a = 30;
int b = 12;

double c = (double) a / b;
System.out.println(c); // 2.5
```
Es decir, como a y b son de tipo int, el resultado de una operación entre ambas variables será de tipo int, por lo que no tendrá decimales, pero si guardamos el resultado de esta división en una variable de tipo double añadiremos un .0.

Esto podemos solucionarlo si indicamos que además de que la variable c es de tipo double, el valor de esta variable también debe ser de tipo double. Esto significa que Java ejecutará la división entre a y b como si fueran de tipo double, por lo que tendrán decimales a pesar de haber sido definidas inicialmente como números enteros.

## Archivos .JAR
Los archivos JAR (Java Archive) son archivos de Java con el código compilado de los archivos .class y comprimido con el formato ZIP para que más adelante sean interpretados y ejecutados por la máquina virtual de Java (JVM).

Para generar estos archivos podemos entrar a `File > Project Structure > Artifacts` y seleccionar la opción de `JAR > From modules with dependencies`. Luego de esto podemos compilar nuestro proyecto desde `Build > Build Artifacts > Build` y podremos nuestros archivos ejecutables en la carpeta `out/artifacts/`.


## Sentencia if
Los condicionales son la forma en que las computadoras toman decisiones, evaluaran si la condición para ejecutar una parte del código se cumple. Si el resultado de la operación es verdadero ejecutarán esta parte del código, en caso de que no, seguirán con las siguientes instrucciones.

La forma de programar condicionales es usando la sentencia IF (hay más, pero las veremos más adelante) de la siguiente manera:
```java
if (condición) {
  // instrucciones
}
```
En el siguiente ejemplo vamos a guardar algunas instrucciones dentro del condicional IF, Java solo ejecutará esta parte del código si se cumple la condición, en este caso, que la variable isBluetoothEnabled sea igual a true:
```java
boolean isBluetoothEnabled = true; // también podría ser false
int filesSended = 3;

if (isBluetoothEnabled) {
  fileSended++;
  System.out.println("Archivo enviado");
}
```


## Alcance de las variables y Sentencia ELSE
**Mientras más crecen nuestros programas, más lógica, complejidad y niveles añadimos. Estos niveles son el alcance que tienen nuestras variables, es decir, los lugares dónde pueden ejecutarse o no.

Estos niveles (en parte) son representados por las llaves ({ ... }) que envuelven nuestro código. Por lo tanto, entre más llaves envuelvan nuestro código, estaremos más niveles dentro y el alcance de las variables que definimos será un poco más limitado.

Solo podemos usar una variable si la definimos antes, en el mismo nivel o alguno anterior. Pero si declaramos una variable en un nivel posterior al resto de nuestro código, no podremos modificarla a menos que el código esté en su mismo nivel.

Por ejemplo:
```java
// Primer nivel:
boolean condicion = true;
int numero1 = 1;

// Segundo nivel:
if (condicion) {
  // podemos modificar variables del primer nivel,
  // incluso desde el segundo nivel:
  numero1++;

  // También podemos crear y modificar 
  // nuevas variables en este nivel:
  int numero2 = 10;
  numero2++;
}

// Si volvemos al primer nivel, podemos seguir usando
// y modificando las primeras variables:
numero1--;

// Pero si salimos del segundo nivel no podemos volver a acceder
// a las variables que creamos allí:
System.out.println(numero2); // ERROR!

```
La sentencia ELSE es todo lo contrario a la sentencia IF: en vez de ejecutar una parte del código si la condición es verdadera, solo lo hará si la condición NO se cumple:

```java
boolean isBluetoothEnabled = false;
int filesSended = 3;

if (isBluetoothEnabled) {
  fileSended++;
  System.out.println("Archivo enviado");
} else {
  System.out.println("El Bluetooth no está activado");
}
```

## Operadores Lógicos y Expresiones booleanas
Nuestros condicionales no solo pueden evaluar variables booleanas, también pueden evaluar si el resultado de una operación es verdadero o falso.

Por ejemplo:
```java
boolean condicionA = true; // verdadero
boolean condicionB = false; // falso

boolean condicionC = 2 + 2 == 4; // verdadero
boolean condicionD = 2 + 2 == 5; // falso

boolean condicionE = "Pepito" == "Pepito"; // verdadero
boolean condicionF = "Pepito" == "Pepe"; // falso
```
Para esto debemos usar los operadores lógicos:

#### Operadores de equidad:

- Igualdad: ==
- Desigualdad: !=

#### Operadores Relacionales:

- Menor que: <
- Mayor que: >
- Menor o igual que: <=
- Mayor o igual que: >=

#### Operadores lógicos:

- &&: AND (evaluar si dos o más condiciones son verdaderas).
- ||: OR (evaluar si al menos una de las condiciones es verdadera).
- !: NOT (evaluar que la condición NO sea verdadera).

Recuerda que además de las sentencias IF y ELSE, también podemos usarELSE IF. Esta la usamos cuando queremos evaluar alguna condición diferente a la condición del IF pero no exactamente al revés.

Por ejemplo:

```java
if (noHayInternet) {
  System.out.println("No hay Internet");
} else if (hayInternetPeroMuyPoquito) {
  System.out.println("Tienes muy poquito Internet");
} else if (hayBuenInternetPeroNoEsSuficiente) {
  System.out.println("Casi casi, falta solo un poquito más");
} else {
  System.out.println("¡Tienes suficiente Internet!");
}
```


## Sentencia Switch
La sentencia Switch nos ayuda a tomar decisiones con base en una o más condiciones, pero funciona un poco diferente:

#### Switch hasta Java 11:

```java
switch (profe) {
  case "Anahí":
    System.out.println("¡Profesora de Java!");
    break;
  case "Leonidas":
    System.out.println("¡Profesor de React.js!");
    break;
  case "JuanDC":
    System.out.println("Oye niño, ¿qué haces aquí?");
    break;
  default:
    System.out.println("¡Un nuevo profe!");
    break;
}
```
#### Switch desde Java 12:

```java
switch (edad) {
  case 1 -> System.out.println("¡Tienes 1 año!");
  case 20 -> System.out.println("Tienes 20 años!");
  default -> System.out.println("Tu edad no es 1 ni 20");
}
```
Recuerda que esta nueva sintaxis está deshabilitada por defecto, debemos hacer algunas configuraciones en nuestro IDE para que podamos utilizarla.

## ¿Para qué sirven las funciones?
Las funciones nos ayudan a ejecutar código que dependiendo de las opciones que le enviemos, transformará y devolverá un cierto resultado. Gracias a las funciones podemos organizar, modularizar, reutilizar y evitar repetidos en nuestro código.

Todas nuestras funciones deben tener un nombre. Opcionalmente, pueden recibir argumentos y devolver un resultado. También debemos especificar el tipo de dato de nuestros argumentos y el resultado final de nuestra función.

Por ejemplo:

```java
public int suma(inta, int b) {
  return a + b;
}
```
Si nuestra función NO devuelve ningún tipo de dato podemos usar la palabra reservada void.

Para utilizar nuestras funciones solo debemos asignar el resultado de la función y sus parámetros a una variable con el mismo tipo de dato de la función:

```java
int c = suma(5, 7);
```

## Java Docs
Los Java Docs son una herramienta usada por muchas otras herramientas y aplicaciones porque nos ayuda a documentar todo nuestro código usando comentarios. Además, nos permite visualizar la documentación en formato HTML.

```java
// Comentarios de una sola línea 
 
/* Comentario 
* en múltiples 
* líneas */ 
 
/** 
* Comentario para Java Docs 
* */ 
```

### Javadoc en funciones
Vamos a documentar la función convertToDolar. Recuerda que esta función devuelve un número double y recibe dos argumentos: quantity (de tipo double) y currency (de tipo String):

```java
/**
 * Descripción general de nuestra función.
 * 
 * @param quantity Descripción del parámetro quanity.
 * @param currency Descripción del parámetro currency (MXN o COP).
 * @return Descripción del valor que devolvemos en esta función.
 * */
```
Para que el IDE muestre la descripción y documentación de las funciones debemos entrar a `IntelliJ IDEA > Preferences > Editor > General > Code Complettion` y habilitar la opción de `Show the documentarion popup`.

![](http://drive.google.com/uc?export=view&id=1-HkR9zdW2RVoevefXqCc9L3Vd3io8lte)

## Bucle do While
Los bucles (ciclos) nos ayudan a ejecutar una parte de nuestro código una cantidad de veces hasta que se cumpla alguna condición y podamos continuar con la ejecución de nuestro código.

Existen diferentes bucles. Por ejemplo, el buble do while:
```java
do {
  // instrucciones
} while (condición);
```
Los ciclos evaluarán si la condición se cumple y cuando deje de hacerlo no ejecutarán más el código del ciclo. Las instrucciones son las encargadas de que esta condición cambie de verdadero a falso. De otra forma, si las instrucciones nunca cambian la condición, el ciclo no se detendrá nunca, lo que conocemos como un ciclo infinito.

La clase Scanner le permite a los usuarios contestar algunas preguntas para que nuestro programa actúe de una forma u otra. Para usarla solo debemos importar la clase Scanner de las APIs de desarrollo de Java:

```java
import java.util.Scanner;

int response = 0;

Scanner sc = new Scanner(System.in);
response = Integer.valueOf(sc.nextLine());
```

## Operador Ternario y Bucle While
Vamos a crear el algoritmo con la lógica necesaria para encender una lampara, emitir un mensaje y detener las luces en algún momento.

El Bucle While nos ayuda a ejecutar una parte del código mientras una condición se cumpla. Recuerda tener mucho cuidado y asegurarte de que la condición del ciclo while cambie en algún momento, de otra forma, el ciclo no se detendrá nunca y sobrecargarás tu programa:
```java
while (isTurnOnLight) {
  printSOS();
}
```
Los operadores ternarios son otra forma de evaluar condiciones, así como los condicionales IF y ELSE`:
```java
// Operador Ternario:
isTurnOnLight = (isTurnOnLight) ? false : true;

// IF y ELSE:
if (isTurnOnLight) {
  isTurnOnLight = false;
} else {
  isTurnOnLight = true;  
}
```

## Bucle For
El Ciclo For también nos ayuda a ejecutar una parte de nuestro código las veces que sean necesarias para que se cumpla una condición. De hecho, el ciclo FOR nos da muchas ayudas para lograr este resultado de la forma más fácil posible:

```java
// Estructura:
for (inicialización; condición; incremento o decremento;) {
  // Instrucciones
}

// En este ejemplo el mensaje de printSOS se
// ejecutará 10 veces:
for (int i = 1; i <= 10; i++) {
  printSOS();
}

```
## Break, Continue y Return
### Break
En Java esta sentencia la verás en dos situaciones especificamente:

1. En un Switch: en esta situación break hace que el flujo del switch no continúe ejecutándose a la siguiente comparación, esto con el objetivo de que solo se cumpla una sola condición:
```java
switch (colorModeSelected){
	case "Light":
                System.out.println("Seleccionaste Light Mode");
                break;
        case "Night": //Ambar
                System.out.println("Seleccionaste Night Mode");
                break;
        case "Blue Dark":
                System.out.println("Seleccionaste Blue Dark Mode");
                break;
}
```
2. Para salir de un bucle: Como acabamos de ver un break es capaz de detener el flujo en el código, en este caso detendremos el ciclo como tal terminándolo y haciendo que saltemos a la siguiente instrucción después del ciclo.

### Continue
Continue en cierto modo también nos va a servir para detener un ciclo pero en lugar de terminarlo como en el caso de break, este volverá directo a la condición.

### Return
Aunque en algunos lenguajes esta sentencia sirve como un tipo goto, dónde se rompe el flujo del programa la mejor forma de usarlo en Java es en Funciones, cuando lo usamos aquí siempre viene acompañado de un valor, el cuál indica el dato que se estará devolviendo en la función.

## Arrays
Los arreglos o arrays son objetos en los que podemos guardar más de una variable, una lista de elementos. Los arrays son de una sola dimensión, pero si guardamos arrays dentro de otros arrays podemos obtener arrays multidimensionales.

Los arrays se definen en código de las siguientes maneras:
```java
// 1. Definir el nombre de la variable y el tipo de datos
//  que va a contener, cualquiera de las siguientes dos
// opciones es válida:
TipoDato[] nombreVariable;
TipoDato nombreVariable[];

// 2. Definir el tamaño del array, la cantidad de elementos
// que podemos guardar en el array:
TipoDato[] nombreVariable = new TipoDato[capacidad];

// Array de dos dimensiones:
TipoDato[][] cities = new String[númeroFilas][númeroColumnas];
```
Ya que los arrays pueden guardar multiples elementos, la convención es escribir los nombres de las variables en plural.

## Ciclos For anidados
Los ciclos FOR nos ayudan a ejecutar una parte de nuestro código todas las veces que sean necesarias hasta que una condición se cumpla, por ejemplo, que un número supere o iguale cierta cantidad.

Eso es exactamente lo que necesitamos para trabajar con índices. En vez de escribir todos los números a mano, vamos a utilizar un ciclo para imprimir el valor de cada posición de nuestros arreglos, incluso si estos son multidimensionales:

```java

// Array de una sola dimensión:
for (int i = 0; i <= 3; i++) {
  System.out.println(i);
}
// El resultado será: 0, 1, 2, 3

// Array de dos dimensiones:
for (int row = 0; row < cities.length; row++) {
  for (int col = 0; col < cities[row].length; col++) {
    System.out.println(cities[row][col]);
  }
}
// El resultado será:
// Colombia
// Bogotá
// México
// Guadalajara
// España
// Madrid

```
El ciclo FOREACH también nos ayuda a recorrer los elementos de un array posición por posición, solo que no tenemos control sobre el índice, el ciclo se encarga de recorrer todo el array automáticamente:
```java
for (TipoDato elemento : coleccion) {
  // Instrucciones
}
```

## Programación orientada a objetos en Java
¡Te damos la bienvenida al Curso de Java SE Orientado a Objetos!

Los paradigmas de programación son una teoría que nos suministra una base y modelo estandarizado para resolver problemas con nuestro código.

La Programación Orientada a Objetos (POO) nos ayuda a analizar y entender todos estos problemas para resolverlos de la forma más sostenible en el futuro. Java surgió con este paradigma y es uno de los lenguajes que define en gran manera el rumbo que sigue la POO.

Este paradigma se compone de 4 elementos (que analizaremos a fondo más adelante):

- Clases
- Propiedades
- Métodos
- Objetos

Además, se basa en los siguientes 4 pilares:

- Encapsulamiento
- Abstracción
- Herencia
- Polimorfismo


## Abstracción: ¿Qué es una Clase?
La Abstracción se trata de analizar objetos de forma independiente, sus propiedades, características y comportamientos, para abstraer su composición y generar un modelo, lo que traducimos a código como clases.

Las Clases son los modelos sobre los cuales construimos nuestros objetos, es decir, las clases son los “moldes” que nos permiten generar objetos. Cada clase debe tener identidad (con un nombre de clase único usando Upper Camel Case), estado (con sus atributos) y comportamiento (con sus métodos y operaciones).

Por ejemplo:

```bash
El ejemplo de clase más típico en Internet:
Nombre de la clase: Person
Atributos: Name, Age
Operaciones: Walk()
```

### Atributos:
Los atributos o características de una Clase pueden ser de tres tipos, definen la visibilidad:
- Public (+): Indica que el atributo será visible tanto dentro como fuera de la clase, es decir, es accesible desde todos lados.
- Private(-): Indica que el atributo sólo será accesible desde dentro de la clase (sólo sus métodos lo pueden acceder).
- Protected (#): Indica que el atributo no será accesible desde fuera de la clase, pero si podrá ser accedido por métodos de la clase además de las subclases que se deriven (herencia).
- Sin modificador de acceso ( ): Indica que el atributo será accesible desde cualquier clase que se encuentre en el mismo paquete de la clase que contiene al atributo sin modificador de acceso.

### Métodos:
Los métodos u operaciones de una clase son la forma en cómo ésta interactúa con su entorno, éstos pueden tener las características:
- Public (+): Indica que el método será visible tanto dentro como fuera de la clase, es decir, es accesible desde todos lados.
- Private (-): Indica que el método sólo será accesible desde dentro de la clase (sólo otros métodos de la clase lo pueden acceder).
- Protected (#): Indica que el método no será accesible desde fuera de la clase, pero si podrá ser accedido por métodos de la clase además de métodos de las subclases que se deriven (herencia).
- Sin modificador de acceso ( ): Indica que el método será accesible desde cualquier clase que se encuentre en el mismo paquete de la clase que contiene al método sin modificador de acceso.


## Modularidad
La Modularidad consiste en dividir nuestro programa en diferentes módulos de forma que puedan unirse o separarse sin romperse entre ellos o perder alguna funcionalidad.

La Modularidad en Programación Orientada a Objetos nos ayuda a:

- Reutilizar código.
- Evitar colapsos.
- Que nuestro código sea mantenible.
- Mejorar la legibilidad.
- Resolución rápida de problemas.

## Creando nuestra primera Clase
Nuestro proyecto en este curso es construir un sistema que nos permita listar y agendar nuestras citas médicas, por lo que debemos crear algunas clases para cada integrante del sistema: doctores, pacientes, entre otras.

Así vamos a crear nuestra primer clase con sus métodos y atributos:
```java
// Clases:
public class Doctor {
  // Atributos:
  int id;
  String name;
  String speciality;

  // Comportamientos (métodos):
  public void showName() {
    // Instrucciones...
  }
}
```

Declarar un Objeto:
```java
// Tipo de Objeto ---- Nombre del Objeto
Doctor myDoctor;

// Otro objeto del mismo tipo Doctor:
Doctor anotherDoctor;
```

Instanciar un Objeto:
```java
// Nombre del Objeto ---- Clase base para crear algún tipo de objetos
myDoctor = new Doctor();

// Otro objeto
anotherDoctor = new Doctor();
```
Declarar e instanciar un objeto en la misma línea:
```java
// Declarar el objeto ---- Instanciar el objeto
Doctor myDoctor = new Doctor();
```
Utilizar el objeto:

```java
// Declarar el objeto ---- Instanciar el objeto
Doctor myDoctor = new Doctor();
myDoctor.name = "Anahí Salgado";
myDoctor.showName();
```

## Método constructor
El Método Constructor es el primer método que se ejecuta por defecto cuando creamos una clase, nos permite crear nuevas instancias de una clase. Lo invocamos con la palabra reservada new seguida del nombre con el que inicializamos la clase y paréntesis.

```java
// nombreDeLaInstancia = new MétodoConstructor();
myDoctor = new Doctor();
```


El compilador de Java crea un método constructor en caso de que no definamos uno, pero de todas formas es muy buena idea programarlo nosotros, ya que nos permite definir y/o configurar el comportamiento de nuestros objetos usando argumentos.

```java
public class Doctor {
  // Atributos...

  // Método Constructor:
  Doctor(/* parámetros */) {
    // Instrucciones que se ejecutan al crear/instanciar
    // un nuevo objeto con la clase Doctor...
  }
}
```
El método constructor no debe regresar ningún valor (no necesitamos un return). Más adelante estudiaremos un poco más a fondo cómo funcionan la sobrecarga de métodos y sobrecarga de constructores.


## Static: Variables y Métodos Estáticos
Los métodos y variables estáticos nos ayudan a ejecutar o conseguir algún código desde clases no han sido instanciadas, ya que sus valores se guardan en la memoria de nuestro programa, no en diferentes objetos instanciados a través de una clase.

Las variables estáticas mantienen su valor durante todo el ciclo de vida de nuestro programa, por lo tanto, podemos alterar los valores de una variable estática desde una clase y consumir su valor alterado desde otra sin necesidad de conectar ambas clases.

También podemos importar los métodos estáticos de una clase para usarlos sin necesidad de escribir el nombre de la clase:

```java
import static com.anncode.operaciones.Calculadora.*
import static java.lang.Math.*

public class Principal {
  public static void (String[] args) {
    int number = suma(3, 5);
    System.out.println(number + PI);
  }
}
```


### Creando elementos estáticos
En muchos casos nuestro código necesita ejecutar métodos que no necesariamente deben pertenecer a un objeto o instancia en concreto, ya que pueden ser muy generales (así como Math.Random) o los valores que almacenamos deben ser los mismos, sin importar si los consumimos desde una o más clases.

En todos estos casos vale la pena usar variables y métodos estáticos.


## Variable vs. Objeto: Un vistazo a la memoria
**Un objeto es una referencia a un espacio en memoria.** Cuando creamos objetos, Java los guarda en la memoria y nos devuelve coordenadas con las que podremos acceder a la información que almacenamos.

Existen dos tipos de memoria: **Stack y Heap.**

La memoria **Stack** es mucho más rápida y nos permite almacenar nuestra información de forma “ordenada”. Aquí se guardan las variables y sus valores de tipos de datos primitivos (booleanos, números, strings, entre otros).

Los objetos también usan la memoria Stack, pero no para guardar su información, sino para guardar las coordenadas a la verdadera ubicación del objeto en la memoria **Heap,** una memoria que nos permite guardar grandes cantidades de información, pero con un poco menos de velocidad.


## Sobrecarga de métodos y constructores
A veces necesitamos que dos o más métodos de una misma clase tengan el mismo nombre, pero con diferentes argumentos o distintos tipos de argumentos/valores de retorno.

Afortunadamente, Java nos permite ejecutar código y métodos diferentes dependiendo de los argumentos que reciba nuestra clase.
```java
public class Calculadora {
  // Los dos parámetros y el valor de retorno son de tipo int
  public int suma(int a, int b) {
    return a + b;
  }

  // Los dos parámetros y el valor de retorno son de tipo float
  public float suma(float a, float b) {
    return a + b;
  }

  // Un parámetro es de tipo int, mientras que el otro parámetro
  // y el valor de retorno son de tipo float
  public float suma(int a, float b) {
    return a + b;
  }
}

```
El uso más común de la sobrecarga de métodos es la sobrecarga de constructores para instanciar objetos de formas distintas dependiendo de la cantidad de argumentos que enviamos.

```java
public class Doctor {
  static int id = 0;
  String name;
  String speciality;

  public Doctor() {
    this.name = "Nombre por defecto";
    this.speciality = "Especialidad por defecto";
  }

  public Doctor(String name, String speciality) {
    this.name = name;
    this.speciality = speciality;
  }
}
```

## Encapsulamiento: Modificadores de acceso
Los Modificadores de Acceso nos ayudan a limitar desde dónde podemos leer o modificar atributos especiales de nuestras clases. Podemos definir qué variables se pueden leer/editar por fuera de las clases donde fueron creadas. Esto lo conocemos como Encapsulamiento.

![](http://drive.google.com/uc?export=view&id=1Ow9zL58ebuqYj54JmTx8ycUjeK4scaj5)
Encapsulamiento: Modificadores de acceso

## Getters y Setters
Los Getters y Setters nos permiten leer y escribir (respectivamente) los valores de nuestras variables privadas desde fuera de la clase donde fueron creadas. Con los Getters obtenemos los datos de las variables y con los Setters asignamos o cambiamos su valor.

También puedes usar los atajos de tu IDE favorito para generar los métodos getters y setters de todas o algunas de tus variables.

```java
public class Patient {
  private String name;

  public String getName() {
    return "Patient name is " + this.name;
  }

  public void setName(String newName) {
    this.name = newName;
  }
}
```

## Variable vs. Objeto
Las Variables son entidades elementales muy sencillas, pueden ser números, caracteres, booleanos, entre otras. Los Objetos son entidades complejas que pueden estar formadas por la agrupación de diferentes variables y métodos.

Los Objetos Primitivos o Clases Wrapper son variables primitivas que trabajan con algún tipo de dato y también tienen las características de los objetos.

Por ejemplo: Byte, Short, Integer, Long, Float, Double, Character, Boolean o String.

## Clases Anidadas
Las Clases Anidadas o Clases Helper son clases dentro de otras clases que agrupamos por su lógica y/o características en común.

Podemos encontrar clases estáticas anidadas, clases internas que son locales a un método o clases internas anónimas. Las clases anidadas pueden llamar a cualquier tipo de elemento o método de nuestras clases.

Las Clases Estáticas no necesitan ser instanciadas para poder ser llamadas y ejecutadas, aunque debes recordar que solo permiten llamar a los métodos estáticos de sus clases padre.
![](http://drive.google.com/uc?export=view&id=1Vhhrwj2i2AzPp7vE3Jo_YD11oKGWEyKY)

## Enumerations

Los enumerations son tipos de datos muy especiales pues este, es el único en su tipo que sirve para declarar una colección de constantes, al ser así estaremos obligados a escribirlos con mayúsculas.

Usaremos enum cada vez que necesitemos representar un conjunto fijo de constantes. Por ejemplo los días de la semana.

Así podemos declarar un enumeration usando la palabra reservada enum.
```java
public enum Day {
	SUNDAY, MONDAY, TUESDAY, WEDNESDAY,
	THURSDAY, FRIDAY, SATURDAY
}
```
Puedo crear referencias de enumerations de la siguiente forma:
```java
Day day;
switch (day) {
	case MONDAY:
		System.out.println(“Mondays are good.”);
		break;
	case FRIDAY:
		System.out.println(“Fridays are nice”);
		break;
	case SATURDAY: case: SUNDAY:
		System.out.println(“Weekends are the best”);
		break;
	default:
		System.out.println(“Midweek are so-so”);
		break;

}
```
Y puedo llamar un valor del enumeration así:
```java
Day.MONDAY;
Day.FRIDAY;
Day.SATURDAY
```
Los enumerations pueden tener atributos, métodos y constructores, como se muestra:
```java
public enum Day {
  MONDAY("Lunes");
  TUESDAY("Jueves");
  FRIDAY("Viernes");
  SATURDAY("Sábado");
  SUNDAY("Domingo");

  private String spanish;
  private Day(String s) {
    spanish = s;
  }

  private String getSpanish() {
    return spanish;
  }
}
```
Y para utilizarlo lo podemos hacer así:
```java
System.out.println(Day.MONDAY);
```
Imprimirá: MONDAY
```java
System.out.println(Day.MONDAY.getSpanish());
```
Imprimirá: Lunes

## ¿Qué es la Herencia? Don\'t repeat Yourself
**Don’t repeat yourself (DRY)** consiste en detectar cuando estamos repitiendo el mismo código una y otra vez para crear algún método o función que nos ayude a evitar estos repetidos.

Esta es una de las bases de la programación que siempre debemos tener en cuenta, ya que nos ayuda a reducir la dificultad de nuestro código para implementar cambios y/o mejoras en nuestra aplicación.

La **Herencia** consiste en crear nuevas clases a partir de otras clases, establecemos una relación padre e hijo entre nuestras clases. Es diferente a las clases anidadas, ya que, en vez de crear clases dentro de clases, le indicamos a nuestras subclases de qué superclase pueden heredar (extends) para reutilizar el código de algunos de sus métodos.

Recuerda que nuestras clases no pueden heredar de más de una clase.
```java
public class SuperClass {
  // ...
}

public class SubClass extends SuperClass {
  // ...
}
```

## Super y This
Super indica que una variable o método es de la clase padre, la superclase de cual heredan nuestras subclases, solo la usamos cuando aplicamos herencia.

Además, podemos llamar al constructor de la clase padre desde sus diferentes subclases usando `super()`; y enviando los argumentos que sean necesarios.

Por otro lado, `this` nos permite especificar que nuestras variables están señalando a la misma clase donde estamos trabajando, ya sea una clase normal, anidada, *subclase* o *superclase*.

```java
public class User {
  int age = 1;

  public int getAge() {
    return this.age;
  }
}

public class Doctor extends User {
  String speciality = "Dentist";

  Doctor() {
    super.getAge(); // 1
    this.getSpeciality(); // Dentist
  }

  public int getSpeciality() {
    return this.speciality;
  }
}
```

## Polimorfismo: Sobreescritura de Métodos
El Polimorfismo es una característica de la programación orientada a objetos que consiste en sobrescribir algunos métodos de la clase de la cual heredan nuestras subclases para asignar comportamientos diferentes.

Además de los métodos de las superclases, también podemos redefinir el comportamiento de los métodos que “heredan” todos nuestros objetos, así como `.toString`, `hashCode`, `finalize`, `notify`, entre otros.

La sobreescritura de constructores consiste en usar los miembros heredados de una supreclase pero con argumentos diferentes.

Recuerda que no podemos sobrescribir los métodos marcados como `final` o `static`.

## Interfaces
Las Interfaces son un tipo de referencia similar a una clase con solo constantes y definiciones de métodos, son de gran ayuda para definir los comportamientos que son redundantes y queremos reutilizar un más de una clase, incluso cuando tenemos muchas clases y no todas pertenecen a la misma “familia”.

Las interfaces establecen la forma de las clases que la implementan, así como sus nombres de métodos, listas de argumentos y listas de retorno, pero NO sus bloques de código, eso es responsabilidad de cada clase.


## Creando una interfaz para definir si una fecha es agendable
**Composición de Interfaces en Clases:** abstraer todos los métodos/comportamientos de una clase para modularizarlos (comprimirlos, encapsularlos) en una *interfaz* y reutilizar su código en diferentes clases.

Las interfaces se crean utilizando la palabra reservada interface y se implementan en nuestras clases con implements.

Recuerda que podemos heredar (implementar) más de una interfaz, pero no podemos hacerlo de las clases padres o superclases.

```java
public interface ISchedulabe {
  void schedule(Date date, String Time);
}

public class AppointmentDoctor implements ISchedulable {
  @Override
  public void schedule(Date date, String Time) {
    // ...
  }
}
```
## Collections

Otras interfaces que son muy importantes en Java son los llamados Collections

Los Collections nos van a servir para trabajar con colecciones de datos, específicamente y solamente con objetos, para esto recuerda que tenemos disponibles nuestras clases Wrapper que nos ayudan a convertir datos primitivos a objetos.

Los collections se diferencian de los arrays en que su tamaño no es fijo y por el contrario es dinámico.

A continuación te muestro un diagrama de su composición:
![](http://drive.google.com/uc?export=view&id=1wxveeR-PQ25ww5vkD6W89dTvthv9ig0a)

Como podemos observar el elemento más alto es la interfaz `Collection`, para lo cual, partiendo de su naturalidad de interface, entendemos que tiene una serie de métodos “básicos” dónde su comportamiento será definido a medida que se vaya implementando en más elementos. De ella se desprenden principalmente las interfaces `Set` y `List`.

La interface `Set` tendrá las siguientes características:

- Almacena objetos únicos, no repetidos.
- La mayoría de las veces los objetos se almacenarán en desorden.
- No tenemos índice.

La interface `List` tiene éstas características:

- Puede almacenar objetos repetidos.
- Los objetos se almacenan en orden secuencial.
- Tenemos acceso al índice.

#### Si seguimos analizando las familias tenemos que de `Set` se desprenden:

- Clase `HashSet`
- nterfaz `SortedSet` y de ella la clase `TreeSet`.

`HashSet` los elementos se guardan en desorden y gracias al mecanismo llamado hashing (obtiene un identificador del objeto) permite almacenar objetos únicos.

`TreeSet` almacena objetos únicos, y gracias a su estructura de árbol el *acceso es sumamente rápido.

#### Ahora si analizamos la familia `List`, de ella se desprenden:
- Clase `ArrayList` puede tener duplicados, no está sincronizada por lo tanto es más rápida
- Clase `Vector` es sincronizada, los datos están más seguros pero es más lento.
- Clase `LinkedList`, puede contener elementos duplicados, no está sincronizada (es más rápida) al ser una estructura de datos doblemente ligada podemos añadir datos por encima de la pila o por debajo.

![](http://drive.google.com/uc?export=view&id=18YJHopXReeftHTHLgrlYsrrssId24Dfn)

### Sigamos con Map
Lo primero que debes saber es que tiene tres implementaciones:
- HashTable
- LinkedHashMap
- HashMap
- SortedMap ➡️ TreeMap

![](http://drive.google.com/uc?export=view&id=1TKRj-UV3FAInd-Gou983uaNWXH5jnHxx)

La interfaz `Map` no hereda de la interfaz Collection porque representa una estructura de datos de Mapeo y no de colección simple de objetos. Esta estructura es más compleja, pues cada elemento deberá venir en pareja con otro dato que funcionará como la llave del elemento.

### Map

- Donde K es el key o clave
- Donde V es el value o valor

Podemos declarar un map de la siguiente forma:

```java
Map<Integer, String> map = new HashMap<Integer, String>();
Map<Integer, String> treeMap = new TreeMap<Integer, String>();
Map<Integer, String> linkedHashMap = new LinkedHashMap<Integer, String>();
```

Como observas solo se puede construir el objeto con tres elementos que implementan de ella: `HashMap`, `TreeMap` y `LinkedHashMap` dejando fuera `HashTable` y `SortedMap`. `SortedMap` estará fuera pues es una interfaz y `HashTable` ha quedado deprecada pues tiene métodos redundantes en otras clases. Mira la funcionalidad de cada uno.

Como te conté hace un momento Map tiene implementaciones:

- `HashMap`: Los elementos no se ordenan. No aceptan claves duplicadas ni valores nulos.
- `LinkedHashMap`: Ordena los elementos conforme se van insertando; provocando que las búsquedas sean más lentas que las demás clases.
- `TreeMap`: El Mapa lo ordena de forma “natural”. Por ejemplo, si la clave son valores enteros (como luego veremos), los ordena de menos a mayor.

Para iterar alguno de estos será necesario utilizar la interface `Iterator` y para recorrerlo lo haremos un bucle `while` así como se muestra:

#### Para HashMap
```java
// Imprimimos el Map con un Iterador
Iterator it = map.keySet().iterator();
while(it.hasNext()){
  Integer key = it.next();
  System.out.println("Clave: " + key + " -> Valor: " + map.get(key));
}
```
#### Para LinkedHashMap
```java
// Imprimimos el Map con un Iterador
Iterator it = linkedHashMap.keySet().iterator();
while(it.hasNext()){
  Integer key = it.next();
  System.out.println("Clave: " + key + " -> Valor: " + linkedHashMap.get(key));
}
```
### Para TreeMap
```java
// Imprimimos el Map con un Iterador
Iterator it = treeMap.keySet().iterator();
while(it.hasNext()){
  Integer key = it.next();
  System.out.println("Clave: " + key + " -> Valor: " + treeMap.get(key));
}
```

#### Deque
El objetivo de las estructuras de datos es el de facilitar la organización de los datos para una manipulación eficiente de los mismos con el mínimo de recursos (tiempo de proceso y espacio de memoria) . Tenemos las siguientes estructuras: Listas, pilas, colas, arboles, etc., la cual deberemos de seleccionar de acuerdo al tipo de problema que queremos resolver.

Deque es una cola de doble extremo. Una cola de doble extremo es una colección lineal de elementos que admite la inserción y eliminación de elementos en ambos puntos finales. La interfaz Deque es un tipo de datos abstractos más rico que una pila (Stack) y una cola (Queue) porque implementa ambas (pilas y colas) al mismo tiempo. La interfaz Deque define métodos para acceder a los elementos en ambos extremos de la instancia de Deque. Se proporcionan métodos para insertar, eliminar y examinar los elementos. Clases predefinidas como ArrayDeque y LinkedList implementan la interfaz Deque

![](http://drive.google.com/uc?export=view&id=1NyPCAoBv9gIm0wzlUyCCI0Q-IFqQsRzg)


La Deque interfaz define métodos para acceder a los elementos en ambos extremos de la Deque instancia. Esto es importante porque significa que pone el práctica los conceptos de FIFO(first in, first out) y LIFO (last in, first out), lo que significa que es más eficiente porque implementa las estructuras de datos pilas y colas al mismo tiempo.

Es una interface, es una cola de dos extremos, es decir, una colección lineal de elementos que permite insertar y elimiinar desde los puntos finales. Implementa colas y pilas al mismo tiempo; y las clases ArrayDeque y LikenList implementar la Deque interface.

![](http://drive.google.com/uc?export=view&id=1R0BkP7sbJKaKEKD9IU_EKepfWmHB50IR)


## Clases Abstractas
A veces NO necesitamos implementar todos los métodos de una clase heredada o interfaz. No siempre necesitamos crear instancias o implementar todos los métodos heredados de una clase padre, así como tampoco podremos necesitamos algún método de nuestras interfaces, pero estas nos obligan a escribir el código de todos los métodos que definimos genéricamente.

Afortunadamente, las Clases Abstractas resuelven todos estos problemas. Son una combinación entre interfaces y herencia donde no implementaremos todos los métodos ni tampoco crearemos instancias.

```java
public abstract class Figura {
  // ...
}

class Triangulo extends Figura {
  // ...
}
```

## Miembros abstractos
Los Métodos Abstractos son los métodos que debemos implementar obligatoriamente cada vez que usemos nuestras clases abstractas, mientras que los métodos que no sean abstractos van a ser opcionales.

```java
public abstract class Figura {
  abstract void dibujar(); // obligatorio
  void dibujar3D(); // no es obligatorio
}

class Triangulo extends Figura {
  void dibujar() {
    // Instrucciones para dibujar el triángulo...
  }
}
```
Recuerda los métodos abstractos solo se pueden implementar en clases abstractas. Y las clases abstractas no necesitan ser instanciadas para ser implementadas.

## Clases Anónimas
Las Clases Anónimas son una forma de instanciar clases abstractas sin necesidad de usar sus clases hijas. Pero este tipo de instanciación tiene algunas restricciones: el ciclo de vida de estas instancias NO es duradero, no las tendremos disponibles durante toda la ejecución del programa.

```js
// Clase Abstracta:
public abstract class Figura {
  abstract void dibujar();
}

// Clase Anónima:
User user = new User() {
  @Override
  public void showDataUser() {
    // Instrucciones...
  }
};
```

## Interfaces en Java 8 y 9
Las Interfaces nos permiten usar métodos abstractos y campos constantes para implementar herencia/polimorfismo de forma muy similar a las clases abstractas.

A partir de Java 8 podemos tener implementación en métodos para heredar y reutilizar diferentes comportamientos. No todos los métodos de nuestras interfaces deben ser abstractos, ahora podemos usar el modificador de acceso default y desde Java 9 también private.

Recuerda que el nivel de acceso de default y private son los mismos que estudiamos en clases anteriores.
```java
public interface MyInterface {
  // Métodos default: nos permite heredar la definición
  // de la función y también su implementación...
  default void defaultMethod() {
    privateMethod("Hello from the default method!");
  }

  // Métodos private: nos permiten definir comportamiento,
  // pero solo se puede usar desde otras clases de esta
  // interfaz, no se hereda a la clase hija....
  private void privateMethod(final String message) {
    System.out.println(message);
  }

  // Métodos abstractos: recuerda que todos los métodos
  // son abstractos por defecto...
  void normalMethod();
}
```

## Herencia en interfaces
Las interfaces pueden heredar de otras interfaces utilizando la palabra clave extends, el concepto de herencia se aplicará como naturalmente se practica en clases, es decir, la interfaz heredará y adquirirá los métodos de la interfaz padre.

Una cosa interesante que sucede en caso de herencia con interfaces es que, aquí sí es permitido la herencia múltiple como ves a continuación:

```java
public interface IReadable {
	public void read();
}


public interface Visualizable extends IReadable, Serializable {
	public void setViewed();
	public Boolean isViewed();
	public String timeViewed();
}
```
Además siguiendo las implementaciones de métodos default y private de las versiones Java 8 y 9 respectivamente podemos sobreescribir métodos y añadirles comportamiento, si es el caso.

```java
public interface Visualizable extends IReadable, Serializable {
	public void setViewed();
	public Boolean isViewed();
	public String timeViewed();
	
	@Override
	default void read() {
	// TODO Auto-generated method stub
	}
}
```
