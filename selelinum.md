---
title: "Selelinum"
tags: ""
---

# Selenium con Python
- [Top 25 Selenium WebDriver Commands That You Should Know](https://www.softwaretestinghelp.com/selenium-webdriver-commands-selenium-tutorial-17/)
- [WebDriver API](https://selenium-python.readthedocs.io/api.html?highlight=WebDriver)

## Qué es Selenium?
Es una SUIT de herramientas para la automatización de navegadores Web. 

El objetivo de Selenium NO fue para el Testing ni para el Web Scraping (aunque se puede usar para eso), por lo tanto, no es el más optimo para estas actividades.

Protocolo: WebDriver, herramienta que se conecta a un API.

**Selenium WebDriver** es la herramienta que utilizaremos en el curso.

Selenium NO es un Software, ES una SUIT de Softwares.

*DDT: Data Drive Testing: Ingresar datos para que realice varias pruebas (sin intervención humana).

## Historia de Selenium
Inicia en 2004 con Jason Huggins encontró una forma de automatizar las pruebas unitarias. Nace como JavaScriptTestRunner, hay un problema con Js y lo script que sólo funcionan para un sitio.

Shinya Katasani desarrollo el IDE de Selenium en Firefox y Chrome. Desarrolló la API WebDriver (Selenium Web Driver).

Origen del nombre, una cura para el envenamiento por mercurio. Por Mercury una competencia de Selenium

#### Selenium IDE
- No es un lenguaje, sólo funciona con clics
- Ofrece reportes de las pruebas


### Selenium IDE
####Pros
- Excelente para iniciar
- No requiere saber programar
- Exporta scripts para Selenium RC y Selenium WebDriver
- Genera reportes
#### Contras
- Disponible para Google Chrome y FireFox
- No soporta DDT. No permite colocar datos para múltiples pruebas.

### Selenium RC
#### Pros
- Soporte para
- Varias plataformas, navegadores y lenguajes.
- Operaciones lógicas y condicionales
- DDT
- Posee una API madura

#### Contras
- Complejo de instalar
- Necesita de un servidor corriendo.
- Comandos redundantes en una API
- Navegación no tan realista

### Selenium Web Driven
#### Pros
- Soporte para múltiples lenguajes
- Facil de instalar.
- Comunicación directa con el navegador.
- Interacción más realista.

#### Contra
- No soporta nuevos navegadores tan rápido.
- No genera reportes o resultados de pruebas.
- Requiere de saber programar.

## Algunas herramientas de testing y automatización:

### Puppeteer:
- PROS: Soporte por parte de Google, te brinda datos del Performance Analysis de Chrome y un mayor control de este navegador. No requiere archivos externos como lo hace Selenium con WebDriver.
- CONTRAS: Solo funciona para Google Chrome con JavaScript, tiene una comunidad pequeña así que el apoyo será poco.

### Cypress.io:
- PROS: Tiene una comunidad emergente y va creciendo a pasos acelerados, tiene muy buena documentación para implementar Cypress en los proyectos. Es muy ágil en pruebas E2E, está orientado a desarrolladores y tiene un excelente manejo del asincronismo, logrando que las esperas sean dinámicas y también se puedan manejar fácilmente.
- CONTRAS: Solo funciona en Google Chrome con JavaScript, se pueden realizar pruebas en paralelo únicamente en la versión de pago.

## Unittest (Pytest)
- Test Fixture: preparaciones para antes y despues de la prueba.
- Test Case: unidad de código a probar.
- Test suite: Colección de test Cases
- Test runner: orquestador de la ejecución.
- Test report: resumen de resultados.

## Preparar assertions y test suites

### Assertions

Metodos que permiten validar un valor esperado en la ejecución del test. Si el resultado es verdadero el test continuúa, en caso contrario "falla" y termina.

Ejemplo: `assertEqual(price.text, "300")`

### Test Suites
Conlección de test unificados en una sola prueba, permitiendo tener resultados grupales e individuales.

## Entender las clases WebDriver y WebElement
Un sitio web se construye por código HTML en forma de árbol, conteniendo distintos elementos con los que podemos interactuar según estén presentes o no en nuestra interfaz gráfica.

Selenium WebDriver nos brinda la posibilidad de poder referirnos a estos elementos y ejecutar métodos específicos para realizar las mismas acciones que un humano haría sobre los mismos, gracias a las clases WebDriver y WebElement.

### Clase WebDriver
Cuenta con una serie de propiedades y métodos para interactuar directamente con la ventana del navegador y sus elementos relacionados, como son pop-ups o alerts. Por ahora nos centraremos a las más utilizadas.

#### Propiedades de la clase WebDriver
|Propiedades/atributo | Descripcion | Ejemplo|
|--|--|--|
|current_url|Obtiene la URL del sitio en la que se encuentra el navegador|	driver.get_url|
|current_window_handle|	Obtiene la referencia que identifica a la ventana activa en ese momento|driver.current_window_handle|
name|Obtiene el nombre del navegador subyacente para la instancia activa|driver.name|
|orientation|Obtiene la orientación actual del dispositivo móvil|driver.orientation|
|page_source|Obtiene el código fuente de disponible del sitio web|driver.page_source|
|title|	Obtiene el valor de la etiqueta `<title>` del sitio web|driver.title|

### Clase WebElement
Esta clase nos permite interactuar específicamente con elementos de los sitios web como textbox, text area, button, radio button, checkbox, etc.

#### Propiedades más comunes de la clase WebElement
|Propiedades/atributo | Descripcion | Ejemplo|
|--|--|--|
size|Obtiene el tamaño del elemento|login.size|
tag_name|Obtiene el nombre de la etiqueta HTML del elemento|login.tag_name|
text|Obtiene el texto del elemento|	login.text|

#### Métodos más comunes de la clase WebElement
|Metodo/atributo | Descripcion | Ejemplo|
|--|--|--|
clear()|Limpia el contenido de un elemento input o texarea|first_name.clear()
click()|Hace clic en el elemento|send_button.click()
get_attribute(name)|Obtiene el valor del atributo de un elemento| submit_button.get_attribute(‘value’) last_name.get_attribute(max_length)
is_displayed()|	Verifica si el elemento está a la vista al usuario |	banner.is_displayed()
is_enabled()|Verifica si el elemento está habilitado |radio_button.is_enabled()|
is_selected()|Verifica si el elemento está seleccionado, para el caso de checkbox o radio button|	checkbox.is_selected()
send_keys(value)|	Simula escribir o presionar teclas en un elemento|	email_field.send_keys(‘team@platzi.com’)
submit()| Envía un formulario o confirmación en un text area|search_field.submit()
value_of_css_property(property_name)|Obtiene el valor de una propiedad CSS del elemento|header.value_of_css_property(‘background-color’)

## Demora implícita y explícita
- [Implicit, Explicit, & Fluent Wait in Selenium WebDriver](https://www.guru99.com/implicit-explicit-waits-selenium.html)

Las pausas no solo sirven para ver lo que esta ocurriendo,sino que también nos ayuda a manejar el asincronismo, una de las debilidades de Selenium y podemos encontrarlas de dos formas:

- Implicita
Busca uno o varios elementos en el DOM si no se encuentra disponibles por la cantidad de tiempo asignado. `implicitly_wait(secons)`
- Explicita
Utiliza condicona de espera determinadas y contiuna hasta que se cumplan.

`By` nos ayuda para hacer referencia a un elemento del sitio Web a través de sus selectores, NO para identificarlo, ES para interactuar de madera distinta a como lo hace `WebDriver`.

`WebDriverWait` nos ayuda para hacer uso de las ExpectedCondition junto con las Esperas Explicitas

### Condicionales esperadas
|Expected Condition|Descripción|Ejemplo|
|--|--|--|
|element_to_be_clickable(locator)|Espera a que el elemento sea visible y habilitado para hacer clic en el mismo |WebDriverWait(self.driver,10).until(expected_conditions.element_to_be_clickable((By.NAME,“accept_button”)))|
|element_to_be_selected(element)|	Espera a que un elemento sea seleccionado|	subscription = self.driver.find_element_by_name(“terms”). WebDriverWait(self.driver, 10).until(expected_conditions.element_to_be_selected(terms)))|
|invisibility_of_element_located(locator)|	Espera a que un elemento no sea visible o no se encuentre presente en el DOM|	WebDriverWait(self.driver,10).until(expected_conditions.invisibility_of_element_located((By.ID,“loading_banner”)))|
|presence_of_all_elements_located(locator)|Espera a que por lo menos uno de los elementos que se indican coincida con los presentes en el sitio	|WebDriverWait(self.driver,10).until(expected_conditions.presence_of_all_elements_located((By.CLASS_NAME,“input-text”)))|
|presence_of_element_located(locator)|	Espera a que un elemento sea visible se encuentre presente en el DOM|	|WebDriverWait(self.driver,10).until(expected_conditions.presence_of_element_located((By.ID,“search-bar”)))|
|text_to_be_present_in_element(locator,text_)|	Espera a que un elemento con el texto indicado se encuentre presente|	WebDriverWait(self.driver,10).until(expected_conditions.text_to_be_present_in_element((By.ID,“seleorder”),“high”))|
|title_contains(title)|	Espera a que la página contenga en el título exactamente como es indicado|	WebDriverWait(self.driver, 10).until(expected_conditions.title_contains(“Welcome”))|
|title_is(title)|	Espera a que la página tenga un título idéntico a como es indicado|	WebDriverWait(self.driver, 10).until(expected_conditions.title_is(“Welcome to Platzi”))|
visibility_of(element)|	Espera a que el elemento indicado esté en el DOM, sea visible, su alto y ancho sean mayores a cero|	first_name = self.driver.find_element_by_id(“firstname”) WebDriverWait(self.driver, 10).until(expected_conditions.visibility_of(first_name))|
|visibility_of_element_located(locator)|	Espera a que el elemento indicado por su selector esté en el DOM, sea visible y que su alto y ancho sean mayores a cero	|WebDriverWait(self.driver,10).until(expected_conditions.visibility_of_element_located((By.ID,“firstname”)))|


## Data Driven Testing (DDT)
- Test driven development: desarrollar código en base a pruebas para que pueda cumplirlas.
- **Data Driven Testing:** desarrollar pruebas en base a código ya existente para validar en qué escenarios pasan o fallan.

## Page Object Model (POM)
Page Object Model es un patrón de diseño utilizado en Testing, el cual, tiene beneficios para la elaboración de Tests.
Funcionamiento:
-En vez de tener nuestros Test en un solo archivo, los tendremos abstraídos en una nueva capa llamada Pages, donde tendremos los Tests en archivos independientes, haciendo referencia al sitio donde se aplica (Home, Login, etc).

A los archivos independientes se les agregará un nuevo archivo que es el Page Object, el cual se encargará de tomar los Tests que se están realizando y validarlas contra los Tests Cases.

### Beneficios
- Crea un alto nivel de abstracción para minimizar cabmios en las  pruebas si los desarrolaladores modifican el sitio.
- Crea código reutilizable que se puede utilizar en  múltiples pruebas.
- Las pruebas son más legibles, flexibles y vigentes.
