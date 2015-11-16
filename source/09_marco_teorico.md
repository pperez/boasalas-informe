# Marco teórico

## Framework

Un framework es una aplicación reusable y "semi-completa" que puede ser especializada para producir aplicaciones personalizadas. [@Fayad1997]. Un framework permite disminuir los costos y esfuerzos producidos por el continuo redescubrimiento y reinvención de conceptos base y componentes transversales en la industria del software.
Los beneficios principales del uso de frameworks son la modularidad, reusabilidad, extensibilidad e inversión de control que proveen a los desarrolladores.

Por otra parte, Johnson [@Johnson1997] define frameworks como una técnica de reuso orientada a objetos, la cual difiere de la visión original basada en componentes del reuso del software. Se puede pensar en un framework como un componente en el contexto de que una aplicación puede utilizar varios frameworks, sin embargo la diferencia principal yace en el automento del nivel de personalización en comparación a la mayoria de los componentes, además de que los frameworks poseen interfaces de mayor complejitud.

[@Fayad1997] clasifica los frameworks en 3 tipos:

* **Frameworks de infraestructura de sistemas**: Su tarea es simplificar el desarrollo de infraestructuras portables y eficientes, tales como sistemas operativos, frameworks de comunicación, herramientas de procesado de lenguaje y frameworks de interfaces de usuarios.
* **Frameworks de integración middleware**: Su tarea es la integración de aplicaciones distribuidas y componentes. Su concepción responde a la necesidad de incrementar la capacidad de los desarrolladores de modularizar, reusar, y extender sus infraestructuras para trabajar sin problemas de forma distribuida.
* **Frameworks de aplicaciones empresariales**: Este tipo de framework tiene un amplio rango de aplicaciones y cuenta con alto retorno de inversión (ROI) debido a que con ellos es posible desarrollar aplicaciones de alta calidad rápidamente. Sin embargo, el costo de desarrollar este tipo de frameworks es alto, por lo que generalmente se opta por adquirir sistemas envasados y realizar integraciones con frameworks de middleware.

## Clases  de frameworks

En su artículo [@Fayad1997] identifica dos clases de frameworks, estas se diferencian por la forma en que se extienden y se reusan sus componentes.

### Frameworks White-box

Su reuso y extensión es realizado mediante herencia y sobrecarga de métodos _hooks_ predefinidos (Utilizando patrones como el _Template Method_ [@Gamma1994] o similares).

Debido a su forma de reuso y extensión (Herencia) es necesario que el desarrollador tenga un íntimo conocimiento de cada pieza interna de estos, produciendo que el software desarrollado tenga un gran acoplamiento a la estructura jerárquica de herencia del framework.

### Frameworks Black-box

La extensión en esta clase de frameworks es realizada definiendo interfaces compatibles con el framework e inyectandolas a este mediante composición.

Por otra parte, el reuso de funcionalidades es realizado mediante la definición de componentes que cumplan con ciertas interfaces e inyectando estos componentes al framework con patrones como _Strategy_ y _Functor_ [@Gamma1994].

Su estructura basada en composición y delegación permite que sea más sencillo su uso y extensión (En comparación a los frameworks White-box). Este beneficio incurre en un elevado costo de desarrollo, debido en que las etapas de diseño deben definirse interfaces y hooks que anticipen un amplio espectro de casos de uso [@Hermann1995].

## Patrones de diseño

En las etapas de diseño, el diseñador es encasillado a las limitaciones introducidas por las decisiones de diseño implementadas en los componentes que debe reutilizar, considerando entre estas algoritmos particulares y las interfaces propias de los componentes/objetos. De esta forma Sommerville [@Sommerville2005] introduce el tópico de los patrones de diseño.

Un patrón de diseño es la descripción de un problema y la esencia de su solución, de forma que esta pueda ser reutilizada en distintas situaciones [@Sommerville2005]. Se destaca la naturaleza abstracta del patrón, mediante el no detallar la especificación, pero que, sin embargo es la descripción del conocimiento y experiencia acumulados.

En [@Gamma1994] se definen los 3 aspectos principales que un patron de diseño debe cumplir:

* Una descripción abstracta de las relaciones existentes entre objetos o clases, se requiere una abstracción debido a que describe un diseño abstracto y no uno particular.
* El problema de diseño en el sistema que será atacado por la estructura abstracta, de esta forma se determina en que escenarios es aplicable el patron.
* Las consecuencias (positivas y negativas) introducidas al aplicar la estructura abstracta a la arquitectura del sistema. Este punto ayuda a determinar si el patron debe aplicarse o no.

## Patrones Arquitectónicos

En [@Buschmann1996] se define un patrón arquitectónico como la expresión de una estructura fundamental para sistemas de software. [@Malinen2013] hace una referencia similar a lo que ocurre con los patrones de diseño, diciendo que "un patrón arquitectónico no es una arquitectura; un software concreto tiene una arquitectura que es una _instancia_ de un patrón arquitectónico" y a su vez, hace enfasis en que una de las características más importantes de los patrones arquitectónicos es proveer atributos de calidad.

El patrón provee un conjunto definido de subsistemas, especificando sus responsabilidades e incluye las reglas y guias para organizar las relaciones entre ellos.

Para terminar, [@Bass2012] menciona que un patrón arquitectónico es una forma de comunicar experiencias de diseño de arquitecturas de software para generar mejores diseños; en otras palabras un patrón arquitectónico promueve la reutilización de diseños.

### Atributos de calidad

Un atributo de calidad es una característica no funcional de un componente o sistema [@Dobrica2002] y expresan el como una aplicación debe lograr una necesidad dada [@Gorton2006]. El estándar ISO-9126-1 define seis categorias de características:

* **Eficiencia**: Consiste en un conjunto de atributos que indican el nivel de rendimiento y la cantidad de recursos utilizados. La eficiencia puede ser sub-caracterizada en función del tiempo y recursos utilizados.
* **Funcionalidad**: Se refiere a al conjunto de funciones que satisfacen las necesidades requeridas. Consiste en la exactitud, interoperabilidad, seguridad y cumplimiento funcional.
* **Mantenibilidad**: Se refiere al conjunto de atributos que indican el nivel de esfuerzo requerido para realizar cambios. Los puntos escenciales en esta categoria son las capacidades de realizar cambios, análisis, pruebas, estabilidad y cumplimiento de mantenibilidad.
* **Portabilidad**: Es la capacidad del software de ser transferido de una plataforma a otra. Los atributos relacionados a esta categoria son la _adaptabilidad_, _instalabilidad_, _coexistencia_, _reemplazabilidad_ y cumplimiento de portabilidad.
* **Confiabilidad**: Se refiere a la capacidad del software para actuar bajo ciertas condiciones en un periodo de tiempo definido. Las subcaracterísticas presentes son _madurez_, _tolerancia a fallos_, _recuperabilidad_ y cumplimiento de confiabilidad.
* **Usabilidad**: Define la cantidad de esfuerzo necesario para usar el software. Posee 5 subcaracterísticas: _comprensibilidad_, _facilidad de aprendizaje_, _operabilidad_, _atractivo_ y cumplimiento de usabilidad.

### Patrón MVC

La literatura categoriza de distintas formas a este patrón, sus creadores, [@Burbeck1992], lo presentan como un paradigma, mientras que en [@Gos2004] es tratado como un patrón arquitectónico como tal; debido a que trata un problema de diseño arquitectónico y según la definición de [@Buschmann1996]
 en el presente trabajo se referirá a él como un patrón.

[@Burbeck1992] define al patrón _MVC_ como aquel en que la entrada de usuario, el modelado del mundo exterior y la representación visual mostrada al usuario son separadas explícitamente y
manejadas por 3 tipos distintos de objetos, cada uno especializado para su tarea.

La _vista_ maneja la salida gráfica o de texto presentada al usuario. El _controlador_ se encarga de interpretar las órdenes del usuario, controlando los cambios que deban generarse en 
el modelo y/o la vista. Finalmente, el modelo maneja el comportamiento de los datos del dominio de la aplicación, respondiendo a peticiones de información.
Esta descripción nos indica que cualquier tipo de objeto puede ser un modelo, incluyendo _Strings_, _Integers_, o incluso objetos complejos instanciados desde clases que utilizan composición.

[@Buschmann1996] nos menciona que los distintos usuarios presentan requerimientos conflictivos a la interfaz de usuario, es por esto que los softwares desarrollados con este patrón deberian soportar la integración de distintos paradigmas
de interfaces de usuario sin mayores problemas.

[@Supaartagorn2011] menciona que usualmente los frameworks para construir aplicaciones web implementan el modelo _MVC_.
