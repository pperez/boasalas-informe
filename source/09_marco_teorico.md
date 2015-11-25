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

La literatura categoriza de distintas formas a este patrón, sus creadores, [@Burbeck1992], es presentado como un paradigma, mientras que en [@Gos2004] es tratado como un patrón arquitectónico como tal; debido a que trata un problema de diseño arquitectónico y según la definición de [@Buschmann1996] en el presente trabajo se referirá a él como un _patrón_.

En [@Buschmann1996] se define al patrón _MVC_ como un patrón arquitectónico que divide una aplicación interactiva en 3 componentes.

* **Modelo**: Contiene la funcionalidad principal y los datos. Es independiente de las representaciones de salida o comportamientos de entrada.
* **Vistas**: Muestran información al usuario. Una vista obtiene datos desde el modelo y pueden existir múltiples vistas para el mismo modelo.
* **Controladores**: Manejan la entrada del usuario, interactuando con el modelo y vistas para cumplir su función.

El _contexto_ de aplicación de este patrón es en aplicaciones interactivas con interfaces flexibles humano-computador. El problema que este patrón soluciona se origina en las interfaces de usuarios, estas son especialmente propensas a cambiar en base a peticiones del cliente. Se requiere un alto nivel de flexibilidad para cumplir con estos requerimientos, ¿esta es dificilmente alcanzada si la interfaz de usuario está altamente ligada con la funcionalidad base.

Debido a la naturaleza cambiante del modelo, nace la necesidad de refrescar el contenido de las vistas, por lo que [@Buschmann1996] menciona que es escencial contar con un _mecanismo de prograpación de cambios_, que mantenga un registro de los componentes dependientes al modelo.

<!-- [@Burbeck1992] define al patrón _MVC_ como aquel en que la entrada de usuario, el modelado del mundo exterior y la representación visual mostrada al usuario son separadas explícitamente y
manejadas por 3 tipos distintos de objetos, cada uno especializado para su tarea.

La _vista_ maneja la salida gráfica o de texto presentada al usuario. El _controlador_ se encarga de interpretar las órdenes del usuario, controlando los cambios que deban generarse en
el modelo y/o la vista. Finalmente, el modelo maneja el comportamiento de los datos del dominio de la aplicación, respondiendo a peticiones de información.
Esta descripción nos indica que cualquier tipo de objeto puede ser un modelo, incluyendo _Strings_, _Integers_, o incluso objetos complejos instanciados desde clases que utilizan composición.

[@Buschmann1996] nos menciona que los distintos usuarios presentan requerimientos conflictivos a la interfaz de usuario, es por esto que los softwares desarrollados con este patrón deberian soportar la integración de distintos paradigmas
de interfaces de usuario sin mayores problemas.

[@Supaartagorn2011] menciona que usualmente los frameworks para construir aplicaciones web implementan el modelo _MVC_.
-->

## Web Service

[@Austin2004] define un _Web Service_ como un sistema identificado por un _URI_ cuyas interfaces públicas y enlaces son descritos utilizando _XML_ (La descripción es realizada en un _Web Service Description Language_(_WSDL_). Su definición puede ser descubierta por otros sistemas, estos pueden interactuar con el _Web Service_ de acuerdo al comportamiento descrito en su definición, usando mensajes codificados en _XML_ transmitidos por protocolos de internet.

En [@Sleeper2001], el grupo Stencil define _Web Service_ como componentes de software de bajo acoplamiento y reusables, que encapsulan funcionalidad discreta y son distribuidos y accedidos mediante lenguajes de programación a través de protocolos de internet estándares. Otro aporte importante sobre la materia es aportada en este artículo, definiendo las capas de bajo nivel de esta tecnología:

* **Protocolos de transporte comunes en internet**: Aunque los _web services_ no se asocian en particular a algún protocolo de transporte, se intenta que esta elección garantize el alcance y soporte universal. Generalmente, los _web services_ utilizan el protocolo _HTTP_, utilizado principalmente por servidores web y navegadores.
* **Extensible Markup Language (XML)**: Es un formato ampliamente aceptado para el intercambio de datos y su semántica de correspondencia.
* **Simple Object Access Protocol (SOAP)**: Es un protocolo de mensajeria y de comunicación tipo _RPC_ (Remote Procedure Call o llamada de procedimiento remoto) entre aplicaciones. Se basa en _XML_ y usa protocolos de transporte de internet como el _HTTP_ para mover datos.

Tambien se definen las capas de mayor nivel:

* **Web Services Description Language (WSDL)**: Es un descriptor basado en _XML_ sobre como conectarse a un _web service_ en particular.
* **Universal Description, Discovery, and Integration (UDDI)**: Representa un conjunto de protocolos y un directorio público para la búsqueda y registro en tiempo real de _web services_ y otros procesos de negocios.
* **Web Services Flow Language**: Describe la lógica de negocios necesaria para integrar múltiples servicios en un proceso de negocios desde principio a fin.
* **Otras reglas de negocio**: Son aquellas reglas de negocio que deben implementarse para confiar en la automatización de procesos de negocios críticos, entre estas reglas encontramos mecanismos de seguridad y autenticación y calidad de servicio.

## Representational State Transfer (_REST_)

Fielding describe a _REST_ como un estilo arquitectónico para sistemas de hipermedia distribuidos en [@Fielding2000].
[@Skulason2008] asevera que la arquitectura _REST_ es un tipo de _Web Service_, sin embargo la gran diferencia está en que _REST_ fue diseñado para la web y sus protocolos, limitandose exclusivamente a esas áreas.

Continuando la comparativa, Magnus hace notar que las diferencias entre ambas tecnologias yace en la codificación y forma de enviar los mensajes: En _SOAP_ se busca canalizar toda la información necesaria en una envoltura _SOAP_, por ejemplo, al enviar mensajes _SOAP_ mediante _HTTP_, se envia el mensaje en el body del request _POST_. Mientras que en _REST_, el único método de transporte válido es _HTTP_, por lo que se aprovechan las características de este protocolo.
De esta forma, la arquitectura _REST_ es centralizada en utilizar URLs para acceder a _entidades_ y _recursos_. Teniendo definido el "donde" se accede a los datos, es necesario definir el "cómo", aquí nuevamente se aprovecha el estándar HTTP, utilizando sus verbos: _GET_, _HEAD_, _PUT_, _DELETE_ y _POST_. El uso de cada verbo puede verse en la siguiente lista:

* **GET**: Muestra el estado actual del recurso.
* **DELETE**: Elimina el recurso.
* **PUT**: Reemplaza el contenido de un recurso.
* **POST**: Crea un nuevo recurso.

_REST_ no restringe el formato de codificación de los mensajes, siendo la única limitación, que estos puedan ser contenidos en el body de un request _HTTP_.
Las estructuras que se utilizan comunmente incluyen _XML_, _Atom_, _RSS_, _XHTML_, _Schema XML_ y _JSON_ (JavaScript Object Notation, una _serialización_ de objetos Javascript en forma de texto). La última estructura es usada intensivamente en aplicaciones web que utilizan _AJAX_ (Asynchronous Javascript and XML), donde los clientes javascript presentes en navegadores son usados para extraer y actualizar contenido sin refrescar la página.

## Base de datos

Antes de poder definir una base de datos como tal, en [@Ceruti1999] se presenta una definición de _dato_, esta palabra es un sustantivo que se refiere a cosas sabidas o asumidas; hechos o figuras desde las cuales se pueden construir conclusiones, generando así _información.
Esta definición es complementada por el Departamento de defensa de los Estados Unidos [@???], diciendo que un dato es una representación de hechos, conceptos o instrucciones de una forma normalizada que es adecuada para la comunicación, interpretación o procesado, ya sea por humanos o de forma automática.

A partir de la definición de dato, es posible construir un conjunto de datos, a lo que Ceruti caracteriza como una pila de datos que estan relacionados de alguna forma.

<!-- TODO: Terminar esto, suena pajoso -->

## Programación orientada a objetos

<!-- Filler -->

## Java Persistence API

[@Boeck2011] dice que la función de la _Java Persistence API_ o _JPA_, es especificar un modelo de persistencia estándar y sencillo de usar en plataformas Java SE y Java EE.
Su principal característica es la especificación del _object relational mapping_ (Mapeo objeto-relacional) directamente en los objetos de persistencia, conocidos en este contexto como entidades.
En [@ONeil2008] vemos que un _mapeo objeto-relacional_ (_ORM_), provee un mecanismo para que sistemas orientados a objetos mantengan sus datos de forma segura en una base de datos, con manejo transaccional y controlados mediante objetos cuando sea necesario.
De esta forma, el _ORM_ se encarga de manejar en tiempo de ejecución las relaciones entre las entidades, entregando grafos de objetos que representan relaciones complejas entre objetos; tambien se encarga de seguir el ciclo de vida de los objetos, llevando la cuenta de las acciones aplicadas sobre ellos y ejecutando las queries SQL necesarias para persistir estos hechos en la base de datos.
