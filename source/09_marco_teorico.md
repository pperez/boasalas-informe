# Marco teórico

## Framework

Un framework es una aplicación reusable y "semi-completa" que puede ser especializada para producir aplicaciones personalizadas. [@Fayad1997]. Un framework permite disminuir los costos y esfuerzos producidos por el continuo redescubrimiento y reinvención de conceptos base y componentes transversales en la industria del software.
Los beneficios principales del uso de frameworks son la modularidad, reusabilidad, extensibilidad e inversión de control que proveen a los desarrolladores.

Por otra parte, Johnson [@Johnson1997] define frameworks como una técnica de reuso orientada a objetos, la cual difiere de la visión original basada en componentes del reuso del software. Se puede pensar en un framework como un componente en el contexto de que una aplicación puede utilizar varios frameworks, sin embargo la diferencia principal yace en el automento del nivel de personalización en comparación a la mayoria de los componentes, además de que los frameworks poseen interfaces de mayor complejitud.

[@Fayad1997] clasifica los frameworks en 3 tipos:

* **Frameworks de infraestructura de sistemas**: Su tarea es simplificar el desarrollo de infraestructuras portables y eficientes, tales como sistemas operativos, frameworks de comunicación, herramientas de procesado de lenguaje y frameworks de interfaces de usuarios.
* **Frameworks de integración middleware**: Su tarea es la integración de aplicaciones distribuidas y componentes. Su concepción responde a la necesidad de incrementar la capacidad de los desarrolladores de modularizar, reusar, y extender sus infraestructuras para trabajar sin problemas de forma distribuida.
* **Frameworks de aplicaciones empresariales**: Este tipo de framework tiene un amplio rango de aplicaciones y cuenta con alto retorno de inversión (ROI) debido a que con ellos es posible desarrollar aplicaciones de alta calidad rápidamente. Sin embargo, el costo de desarrollar este tipo de frameworks es alto, por lo que generalmente se opta por adquirir sistemas envasados y realizar integraciones con frameworks de middleware.

## Clases  de frameworks: White-box y Black-box

En su artículo [@Fayad1997] identifica dos clases de frameworks:

### Frameworks White-box

Su reuso y extensión es realizado mediante herencia y sobrecarga de métodos _hooks_ predefinidos (Utilizando patrones como el _Template Method_ o similares)

## Patrones de diseño

En las etapas de diseño, el diseñador es encasillado a las limitaciones introducidas por las decisiones de diseño implementadas en los componentes que debe reutilizar, considerando entre estas algoritmos particulares y las interfaces propias de los componentes/objetos. De esta forma Sommerville [@Sommerville2005] introduce el tópico de los patrones de diseño.

Un patrón de diseño es la descripción de un problema y la esencia de su solución, de forma que esta pueda ser reutilizada en distintas situaciones [@Sommerville2005]. Se destaca la naturaleza abstracta del patrón, mediante el no detallar la especificación, pero que, sin embargo es la descripción del conocimiento y experiencia acumulados.

En [@Gamma1994] se definen los 3 aspectos principales que un patron de diseño debe cumplir:

* Una descripción abstracta de las relaciones existentes entre objetos o clases, se requiere una abstracción debido a que describe un diseño abstracto y no uno particular.
* El problema de diseño en el sistema que será atacado por la estructura abstracta, de esta forma se determina en que escenarios es aplicable el patron.
* Las consecuencias (positivas y negativas) introducidas al aplicar la estructura abstracta a la arquitectura del sistema. Este punto ayuda a determinar si el patron debe aplicarse o no.
