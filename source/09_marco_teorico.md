# Marco teórico

## Framework

Un framework es una aplicación reusable y "semi-completa" que puede ser especializada para producir aplicaciones personalizadas [@Fayad1997].
Un framework permite disminuir los costos y esfuerzos producidos por el continuo redescubrimiento y reinvención de conceptos base y componentes transversales en la industria del software.
Los beneficios principales del uso de frameworks son la modularidad, reusabilidad, extensibilidad e inversión de control que proveen a los desarrolladores.

Por otra parte, un framework es una técnica de reuso orientada a objetos, la cual difiere de la visión  basada en componentes del reuso del software [@Johnson1997].
Se puede pensar en un framework como un componente en el contexto en que una aplicación puede utilizar varios frameworks, sin embargo la diferencia principal radica en el mayor niel de personalización en comparación a la mayoría de los componentes, además de que los frameworks poseen interfaces de mayor complejidad.

Existen 3 tipos de frameworks [@Fayad1997]:

* **Frameworks de infraestructura de sistemas**: Su tarea es simplificar el desarrollo de infraestructuras portables y eficientes, tales como sistemas operativos, frameworks de comunicación, herramientas de procesado de lenguaje y frameworks de interfaces de usuarios.
* **Frameworks de integración middleware**: Su tarea es la integración de componentes entre aplicaciones distribuidas.
Su concepción responde a la necesidad de incrementar la capacidad de los desarrolladores de modularizar, reusar, y extender sus infraestructuras para trabajar sin problemas de forma distribuida.
* **Frameworks de aplicaciones empresariales**: Este tipo de framework tiene un amplio rango de aplicaciones y cuenta con alto retorno de inversión (ROI) debido a que con ellos es posible desarrollar aplicaciones de alta calidad rápidamente; sin embargo, el costo de desarrollar este tipo de frameworks es alto, por lo que generalmente se opta por adquirir sistemas envasados y realizar integraciones con frameworks de middleware.

## Clases  de frameworks

Hay dos clases de frameworks, estas se diferencian por la forma en que sus componentes son reutilizados y extendidos (Para añadir funcionalidad no ofrecida) [@Fayad1997].

### Frameworks White-box

Su reuso y extensión es realizado mediante herencia y sobrecarga de métodos _hooks_ predefinidos (Utilizando patrones como _Template Method_ [@Gamma1994] o similares).

Debido a su forma de reuso y extensión (Herencia) es necesario que el desarrollador tenga un íntimo conocimiento de cada pieza interna de estos, produciendo que el software desarrollado tenga un gran acoplamiento a la estructura jerárquica de herencia del framework.

### Frameworks Black-box

La extensión en esta clase de frameworks es realizada definiendo interfaces compatibles con el framework e inyectándolas a este mediante composición.

Por otra parte, el reuso de funcionalidades es realizado mediante la definición de componentes que cumplan con ciertas interfaces e inyectando estos componentes al framework con patrones como _Strategy_ y _Functor_ [@Gamma1994].

Su estructura basada en composición y delegación permite que sea más sencillo su uso y extensión (En comparación a los frameworks White-box).
Este beneficio incurre en un elevado costo de desarrollo, debido en que las etapas de diseño deben definirse interfaces y hooks que anticipen un amplio espectro de casos de uso [@Hermann1995].

## Patrones de diseño

Una de las grandes problemáticas que enfrentan los diseñadores en la etapa de diseño de un sistema, son las limitaciones generadas por las decisiones de diseño tomadas en componentes que se desean reutilizar, entre estas decisiones encontramos algoritmos e interfaces propias de componentes u objetos.

Esta problemática es compartida por diseñadores, generalmente con distintos contextos y componentes, la que finalmente lleva a la creación de los _patrones de diseño_, siendo estos una solución general a problemas encontrados en la etapa de diseño [@Sommerville2005].

Un _patrón de diseño_ es la descripción de un problema y la esencia de su solución, de forma que esta pueda ser reutilizada en distintas situaciones [@Sommerville2005].
Se destaca la naturaleza abstracta del patrón, al no entrar en los detalles de su especificación;, sin embargo un patrón es una expresión de conocimiento y experiencia acumulada.

Hay 3 aspectos principales que todo patrón de diseño debe incluir [@Gamma1994]:

* Una _descripción abstracta_ de las relaciones existentes entre objetos o clases, la abstracción es requerida debido a que describe un diseño general y no uno particular.
* El _problema de diseño_ que será abordado por la estructura abstracta, de esta forma se determina en que escenarios es aplicable el patrón.
* Las _consecuencias_ (positivas y negativas) introducidas al aplicar la estructura abstracta a la arquitectura del sistema. Este punto ayuda a determinar si el patrón debe aplicarse o no.

## Patrones Arquitectónicos

Un _patrón arquitectónico_ es la expresión de una estructura fundamental para sistemas de software [@Buschmann1996].

"Un patrón arquitectónico no es una arquitectura; un software concreto tiene una arquitectura que es una _instancia_ de un patrón arquitectónico" [@Malinen2013]. Este concepto tiene una íntima relación a la función de los _patrones de diseño_, debido al nivel de abstracción que ambos tipos de patrones deben presentar.
Una de las características más importantes de los patrones arquitectónicos es proveer atributos de calidad [@Malinen2013].

El patrón provee un conjunto definido de subsistemas, especificando sus responsabilidades e incluye las reglas y guías para organizar las relaciones entre ellos.

Un patrón arquitectónico es una forma de comunicar experiencias de diseño de arquitecturas de software, produciendo así softwares de mejor calidad; en otras palabras un patrón arquitectónico promueve la reutilización de diseños [@Bass2012].

### Atributos de calidad

Un atributo de calidad es una característica no funcional de un componente o sistema [@Dobrica2002] y expresa el cómo una aplicación debe lograr una necesidad dada [@Gorton2006].
El estándar ISO-9126-1 define seis categorías para los atributos de calidad:

* **Eficiencia**: Consiste en un conjunto de atributos que indican el nivel de rendimiento y la cantidad de recursos utilizados.
La eficiencia puede ser sub-caracterizada en función del tiempo y recursos utilizados.
* **Funcionalidad**: Se refiere al conjunto de funciones que satisfacen las necesidades requeridas.
Consiste en la exactitud, interoperabilidad, seguridad y cumplimiento funcional.
* **Mantenibilidad**: Se refiere al conjunto de atributos que indican el nivel de esfuerzo requerido para realizar cambios.
Los puntos esenciales en esta categoría son las capacidades de realizar cambios, análisis, pruebas, estabilidad y cumplimiento de mantenibilidad.
* **Portabilidad**: Es la capacidad del software de ser transferido de una plataforma a otra.
Los atributos relacionados a esta categoría son la _adaptabilidad_, _instalabilidad_, _coexistencia_, _reemplazabilidad_ y cumplimiento de portabilidad.
* **Confiabilidad**: Se refiere a la capacidad del software para actuar bajo ciertas condiciones en un periodo de tiempo definido.
Las subcaracterísticas presentes son _madurez_, _tolerancia a fallos_, _recuperabilidad_ y cumplimiento de confiabilidad.
* **Usabilidad**: Define la cantidad de esfuerzo necesario para usar el software.
Posee 5 subcaracterísticas: _comprensibilidad_, _facilidad de aprendizaje_, _operabilidad_, _atractivo_ y cumplimiento de usabilidad.

### Patrón MVC

La literatura categoriza de distintas formas a este patrón, como un paradigma [@Burbeck1992] y como un patrón arquitectónico como tal[@Gos2004]; en este trabbajo será tratado como un _patrón_, debido a que aborda un problema de diseño arquitectónico.

El patrón _MVC_ es un patrón arquitectónico que divide una aplicación interactiva en 3 componentes [@Buschmann1996]:

* **Modelo**: Contiene la funcionalidad principal y los datos.
Es independiente de las representaciones de salida o comportamientos de entrada.
* **Vistas**: Muestran información al usuario.
Una vista obtiene datos desde el modelo y pueden existir múltiples vistas para el mismo modelo.
* **Controladores**: Manejan la entrada del usuario, interactuando con el modelo y vistas para cumplir su función.

El _contexto_ de uso de este patrón es en aplicaciones interactivas con interfaces flexibles humano-computador.
El _problema_ que este patrón soluciona se origina en las interfaces de usuarios, estas son especialmente propensas a cambiar en base a peticiones del cliente.
Se requiere un alto nivel de flexibilidad para cumplir con estos requerimientos, esta es difícilmente alcanzada si la interfaz de usuario está altamente ligada con la funcionalidad base.

Debido a la naturaleza cambiante del modelo, nace la necesidad de refrescar el contenido de las vistas, por lo que es esencial contar con un _mecanismo de prograpación de cambios_, que mantenga un registro de los componentes dependientes al modelo [@Buschmann1996].

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

Un _Web Service_ es un sistema identificado por un _URI_ cuyas interfaces públicas y enlaces son descritos utilizando _XML_ (La descripción es realizada en un _Web Service Description Language_(_WSDL_) [@Austin2004].
Su definición puede ser descubierta por otros sistemas, estos pueden interactuar con el _Web Service_ de acuerdo al comportamiento descrito en su definición, usando mensajes codificados en _XML_ transmitidos por protocolos de internet.

El grupo Stencil define _Web Service_ como componentes de software de bajo acoplamiento y reusables, que encapsulan funcionalidad discreta y son distribuidos y accedidos mediante lenguajes de programación a través de protocolos de internet estándares [@Sleeper2001].
Esta tecnología es compuesta por capas, donde las de bajo nivel son:

* **Protocolos de transporte comunes en internet**: Aunque los _web services_ no se asocian en particular a algún protocolo de transporte, se intenta que esta elección garantice el alcance y soporte universal.
Generalmente, los _web services_ utilizan el protocolo _HTTP_, utilizado principalmente por servidores web y navegadores.
* **Extensible Markup Language (XML)**: Es un formato ampliamente aceptado para el intercambio de datos y su semántica de correspondencia.
* **Simple Object Access Protocol (SOAP)**: Es un protocolo de mensajería y de comunicación tipo _RPC_ (Remote Procedure Call o llamada de procedimiento remoto) entre aplicaciones.
Se basa en _XML_ y usa protocolos de transporte de internet como el _HTTP_ para mover datos.

También cuenta con capas de alto nivel:

* **Web Services Description Language (WSDL)**: Es un descriptor basado en _XML_ sobre como conectarse a un _web service_ en particular.
* **Universal Description, Discovery, and Integration (UDDI)**: Representa un conjunto de protocolos y un directorio público para la búsqueda y registro en tiempo real de _web services_ y otros procesos de negocios.
* **Web Services Flow Language**: Describe la lógica de negocios necesaria para integrar múltiples servicios en un proceso de negocios desde principio a fin.
* **Otras reglas de negocio**: Son aquellas reglas de negocio que deben implementarse para confiar en la automatización de procesos de negocios críticos, entre estas reglas encontramos mecanismos de seguridad y autenticación y calidad de servicio.

## Representational State Transfer (_REST_)

_REST_ es un estilo arquitectónico para sistemas de hipermedios distribuidos [@Fielding2000].
La arquitectura _REST_ es un tipo de _Web Service_, sin embargo la diferencia yace en que _REST_ fue diseñado para la web y sus protocolos, limitándose exclusivamente a esas áreas [@Skulason2008].

Las diferencias entre ambas tecnologías se encuentran en la codificación y forma de enviar los mensajes: En _SOAP_ se busca canalizar toda la información necesaria en una envoltura _SOAP_, por ejemplo, al enviar mensajes _SOAP_ mediante _HTTP_, se envia el mensaje en el body del request _POST_.
Mientras que en _REST_, el único método de transporte válido es _HTTP_, por lo que se aprovechan las características de este protocolo.
De esta forma, la arquitectura _REST_ utiliza _URIs_ para acceder a _entidades_ y _recursos_.
Teniendo definido el "dónde" se accede a los datos, es necesario definir el "cómo", aquí nuevamente se aprovecha el estándar HTTP, utilizando sus verbos: _GET_, _HEAD_, _PUT_, _DELETE_ y _POST_.
El uso de cada verbo puede verse en la siguiente lista:

* **GET**: Muestra el estado actual del recurso.
* **DELETE**: Elimina el recurso.
* **PUT**: Reemplaza el contenido de un recurso.
* **POST**: Crea un nuevo recurso.

_REST_ no restringe el formato de codificación de los mensajes, por lo que la única limitación es que estos puedan ser contenidos en el body de un request _HTTP_.
Las estructuras que se utilizan comúnmente son _XML_, _Atom_, _RSS_, _XHTML_, _Schema XML_ y _JSON_ (JavaScript Object Notation, una _serialización_ de objetos Javascript en forma de texto).
La última estructura es usada intensivamente en aplicaciones web que utilizan _AJAX_ (Asynchronous Javascript and XML), donde los clientes javascript presentes en navegadores son usados para extraer y actualizar contenido sin refrescar la página [@Skulason2008].

## Base de datos

Antes de poder definir una base de datos como tal, es necesario definir _dato_, esta palabra es un sustantivo que se refiere a cosas sabidas o asumidas; hechos o figuras desde las cuales se pueden construir conclusiones, generando así _información_ [@Ceruti1999].
Esta definición es complementada por el Departamento de defensa de los Estados Unidos [@???], diciendo que un dato es una representación de hechos, conceptos o instrucciones de una forma normalizada que es adecuada para la comunicación, interpretación o procesado, ya sea por humanos o de forma automática.

<!--A partir de la definición de dato, es posible construir un conjunto de datos, a lo que Ceruti caracteriza como una pila de datos que están relacionados de alguna forma.

TODO: Terminar esto, suena pajoso -->

## Programación orientada a objetos

<!-- Filler -->

## Java Persistence API

La función de la _Java Persistence API_ o _JPA_, es especificar un modelo de persistencia estándar y sencillo de usar en plataformas Java SE y Java EE [@Boeck2011].
Su principal característica es la especificación del _object relational mapping_ (Mapeo objeto-relacional) directamente en los objetos de persistencia, conocidos en este contexto como entidades.
Un _mapeo objeto-relacional_ (_ORM_), provee un mecanismo para que sistemas orientados a objetos mantengan sus datos de forma segura en una base de datos, con manejo transaccional y controlados mediante objetos cuando sea necesario [@ONeil2008].
De esta forma, el _ORM_ se encarga de manejar en tiempo de ejecución las relaciones entre las entidades, entregando grafos de objetos que representan relaciones complejas entre objetos; también se encarga de seguir el ciclo de vida de los objetos, llevando la cuenta de las acciones aplicadas sobre ellos y ejecutando las queries SQL necesarias para persistir estos hechos en la base de datos.


## Bean Validation

La validación de datos es una tarea que ocurre en la aplicación, desde la capa de presentación a la capa de persistencia [@Bernard2009].
Muchas veces la lógica desarrollada es implementada en cada capa, lo que es susceptible a fallos y una pérdida de tiempo.
Para solucionar el problema de duplicación de código de validación, los desarrolladores suelen implementar esta lógica en el modelo del dominio, sin embargo esto provoca que las clases del dominio estén abarrotadas con código que a fin de cuentas es información de la propia clase.

_Bean Validation_ es presentado en la _JSR_ (_Java Specification Request_) 303 [@Bernard2009], definiendo un modelo de metados y un _API_ para validación, el que puede ser implementado en forma de _anotaciones_ o descripciones utilizando _XML_.


## Lenguaje de Programación Java

El lenguaje de programación Java fue desarrollado por _Sun Microsystems_ a principios de los 90, para proveer un lenguaje orientado a objetos, portable e interpretado, su gran propuesta de valor es el manejo de memoria, esta es manejada de forma automática [@Gosling1995].

<!-- Agregar info sobre la JVM, J2SE y J2EE -->

## Framework Spring

Spring es el framework de desarrollo más popular de la plataforma Java [@DashrathMane2013]. Este framework provee un modelo exhaustivo de programación y configuración para aplicaciones de negocio modernas basadas en Java, para cualquier tipo de infraestructura; su objetivo es hacer más sencillo el desarrollo de aplicaciones _J2EE_ para usar y promover buenas prácticas de programación utilizando un modelo de programación basado en _POJO_ (Clases Java simples, independientes de algún framework).
_Spring_ posee un diseño modular, que permite la adición de componentes tales como el _contenedor_ principal o el soporte _JDBC_.

Esta imagen muestra las capas de componentes del framework:

![Spring Framework Architecture](source/figures/001_spring_framework_architecture.png)

### Core Container

Aquí se encuentran las funciones principales del framework y se compone de los siguientes módulos:

* _Core_: Provee las partes fundamentales del framework, incluyendo las funcionalides de _Inversión de control_ (IoC) e _Inyección de Dependencias_ (Dependency Injection).
* _Bean_: Provee la _BeanFactory_, una implementación del patrón _Factory_.
* _Context_: Utiliza los módulos _Core_ y _Bean_ para proveer acceso a cualquier objeto definido y configurado.
* _Expression Language_: Permite un lenguaje de expresiones para acceder y manipular grafos de objetos en tiempo de ejecución.

### Data Access/Integration

Esta capa incluye los siguientes módulos:

* _JDBC_: Provee una capa de abstracción sobre _JDBC_, eliminando la necesidad de la tediosa programación relacionada a _JDBC_.
* _ORM_: Provee capas de integración para APIs de _ORM_ populares, incluyendo _JPA_, _JDO_, _Hibernate_ y _iBatis_.
* _OXM_: Provee una capa de abstracción que soporta implementaciones de mapeos _Objeto/XML_ para _JAXB_, _Castor_, _XMLBeans_, _JiBX_ y _Xstream_.
* _JMS_: Este módulo contiene características para producir y consumir mensajes.
* _Transactions_: Soporta manejo transaccional programático y declarativo para aquellas clases que implementan interfaces especiales y _POJOS_ definidos por el usuario.

### Web

La capa web de _Spring_ es compuesta por los siguientes módulos:

* _Web_: Este módulo provee funcionalidades básicas orientadas a web, tales como el manejo de subida de ficheros multipart y la inicialización de contextos y servlets para la web.
* _Web-Servlet_: Este módulo contiene la implementación del patrón MVC de Spring.
* _Web-Struts_: Este módulo contiene las clases utilizadas para integrar una aplicación Struts con Spring.

### Miscelaneos

Esta capa incluye soporte para orientación a aspectos y pruebas:

* _AOP_ (Aspect Oriented Programming): Este módulo provee una implementación para orientación a aspectos, en la cual se definen intercepciones en llamadas a métodos y puntos de corte, los que permiten desacoplar código que implemente funcionalidad que debe ser separada.
* _Aspects_: Provee integración con el framework _AspectJ_.
* _Instrumentation_: Provee clases de instrumentación para ser usados sobre ciertos servidores de aplicaciones.
* _Test_: Este módulo permite realizar pruebas sobre componentes _Spring_ con los frameworks _Junit_ o _TestNG_.
