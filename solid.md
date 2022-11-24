---
title: "SOLID"
tags: ""
---

# Principios SOLID aplicados.

## ¿Qué son los principios SOLID?
- Principios o convenciones de diseño de Software.
- Ampliamente aceptados en la industria.
- Ayudan a hacer un código más mantenible y tolerante a cambios.
- Aplicables en términos de diseño de clases (micro-diseño), y también a nivel de arquitectura de software y estructura de [micro]servicios (macro-diseño).
- Tenemos que romper con el rol de “Arquitecto de software”. Entender el diseño de software de calidad como una habilidad y no un rol.

### SOLID
- El primero de los principios SOLID: SRP. ¿Qué quiere decir eso de “Una clase = Una responsabilidad”? ¿Cómo lo aplicamos en El Mundo Real™️?
- Principio OPEN/CLOSE de Abierto/Cerrado:
Analizamos el OCP a varios niveles de nuestro software. Tanto con el clásico ejemplo a nivel de clases, como a nivel de casos de uso gracias a eventos
- Principio de sustitución de Liskov:Quizás uno de los principios más difíciles de asimilar. Vemos ejemplos de LSP tanto de introducción (clásico rectángulo vs. cuadrado), como del mundo real. #keepItReal
- Principio de segregación de interfaces ISP: es uno de los principios más fáciles de malinterpretar y pensar que es sencillo. Nada más lejos de la realidad. Es uno de los más interesantes a nivel conceptual.
- Principio de inversión de dependencias: AKA: Santo Grial de la Arquitectura Hexagonal. 

## SOLID vs STUPID
¿Qué significa el acrónimo STUPID?

- **Singleton:**
  - Patrón de diseño ampliamente usado hace unos años. Evita exponer los colaboradores de una clase (algo negativo ya que hace más difícil de detectar el acoplamiento entre clases).
  - Además, el beneficio del que provee es básicamente mantener un estado global, algo que podemos conseguir vía inyección de dependencias como veremos en el curso.
  - Por último, derivado de los puntos anteriores, perjudica la testabilidad de nuestras clases haciéndolas más difícil de
- **Tight Coupling:** Acoplamiento entre clases que dificulta la mantenibilidad y tolerancia al cambio que proporciona la aplicación de principios SOLID
- **Untestability:** Código difícil de testear. Derivado de no inyectar dependencias vía constructor nos vemos obligados al uso de costuras en nuestro código.
- **Premature Optimization:** Anticiparnos a los requisitos de nuestro software desarrollando abstracciones innecesarias que añaden complejidad.
- **Indescriptive Naming:** Nomenclatura indescriptiva tanto a nivel de clases, como variables o atributos. ¡Hablaremos más de esto en el curso de Clean Code!
- **Duplication:** Duplicidad de código. Algo solucionable si aplicamos el Principio de Responsabilidad Única de SOLID e inyección de dependencias como veremos en este curso


## OCP. Principio de Abierto/Cerrado Open/close. 
### ntroducción conceptual
- Concepto:
  - El Software debería estar abierto a extensión y cerrado a modificación.
  - Esto aplica tanto a nuestras clases internas, servicios, microservicios, casos de usos…
- Cómo conseguirlo:
  - Evitando depender de implementaciones específicas, haciendo uso de clases abstractas o interfaces.
- Finalidad:
  - Facilidad para añadir nuevos Casos de uso en nuestra aplicación.


### Interfaces 🆚 Abstract Class
- Beneficios de Interface:
  - No modifica el árbol de jerarquía
  - Permite implementar N Interfaces
- Beneficios de Abstract Class:
  - Permite desarrollar el patrón Template Method[^1] empujando la lógica al modelo. 
    - Problema: Dificultad de trazar
  - Getters privados (Tell don’t ask)

####  Conclusión
- ¿Cuándo usamos Interfaces?: Cuando vayamos a desacoplar entre capas
- ¿Cuándo usamos Abstract?: En determinados casos para Modelos de dominios

[^1]: Patrón de diseño Template Method: Plantea que en la clase abstracta definiríamos un cuerpo de método que define qué operación vamos a realizar, pero estaríamos llamando a unos métodos definidos como abstractos (delegando la implementación a los hijos).
¡Pero cuidado! 👀 esto implica una pérdida de la trazabilidad de nuestro código.

## LSO.  Principio de sustitución de Liskov. 
- Concepto:
  - Si S es un subtipo de T, instancias de T deberían poderse sustituir por instancias de S sin alterar las propiedades del programa. 
  - Es decir, al tener una jerarquía nos supone que estamos estableciendo un contrato en el padre, por lo que, garantizar que se mantiene dicho contrato en el hijo, nos permitirá que podamos sustituir al padre y la aplicación seguirá funcionando perfectamente 👌
- Cómo:
  - El comportamiento de de las subclases debe respetar el contrato establecido en la superclase.
- Finalidad:
  - Mantener correctitud funcional para poder aplicar OCP
