# Marco teórico

## Realidad UTEM

### Campus

La _Real Academia Española_ define campus como el "Conjunto de terrenos y edificios pertenecientes a una universidad" [@Espanol2015].

### Asignación de salas y laboratorios

TODO: Definir esto en la realidad UTEM.

### Curso y sección

TODO: Definir esto en la realidad UTEM.

## Sistema

Un sistema es un conjunto de elementos interdependientes e interactuantes; un grupo de unidades combinadas que forman un todo organizado, cuyo resultado es mayor que el resultado que las unidades podrían tener si funcionaran independientemente [@Chiavenato1995].

Al llevar este término a la informática, se limitan los elementos/componentes a _hardware_, _software_ y _humanos_ (humanware) [@JaramilloBarea2012].

## Conceptos utilizados en la confección de sistemas

TODO: Agregar una descripción sobre esto, y como se relacionan entre si para construir sistemas.

### Framework

Un framework es una aplicación reusable y "semi-completa" que puede ser especializada para producir aplicaciones personalizadas [@Fayad1997].
Un framework permite disminuir los costos y esfuerzos producidos por el continuo redescubrimiento y reinvención de conceptos  y componentes transversales en la industria del software.
Los beneficios principales del uso de frameworks son la modularidad, reusabilidad, extensibilidad e inversión de control que proveen a los desarrolladores.

Por otra parte, un framework es una técnica de reuso orientada a objetos, la cual difiere de la visión  basada en componentes del reuso del software [@Johnson1997].
Se puede pensar en un framework como un componente en el contexto en que una aplicación puede utilizar varios frameworks, sin embargo la diferencia principal radica en el mayor niel de personalización en comparación a la mayoría de los componentes, además de que los frameworks poseen interfaces de mayor complejidad.

Existen 3 tipos de frameworks [@Fayad1997]:

* **Frameworks de infraestructura de sistemas**: Su tarea es simplificar el desarrollo de infraestructuras portables y eficientes, tales como sistemas operativos, frameworks de comunicación, herramientas de procesado de lenguaje y frameworks de interfaces de usuarios.
* **Frameworks de integración middleware**: Su tarea es la integración de componentes entre aplicaciones distribuidas.
Su concepción responde a la necesidad de incrementar la capacidad de los desarrolladores de modularizar, reusar, y extender sus infraestructuras para trabajar sin problemas de forma distribuida.
* **Frameworks de aplicaciones empresariales**: Este tipo de framework tiene un amplio rango de aplicaciones y cuenta con alto retorno de inversión (ROI) debido a que con ellos es posible desarrollar aplicaciones de alta calidad rápidamente; sin embargo, el costo de desarrollar este tipo de frameworks es alto, por lo que generalmente se opta por adquirir sistemas envasados y realizar integraciones con frameworks de middleware.

#### Clases  de frameworks

Hay dos clases de frameworks, estas se diferencian por la forma en que sus componentes son reutilizados y extendidos (Para añadir funcionalidad no ofrecida) [@Fayad1997].

##### Frameworks White-box

Su reuso y extensión es realizado mediante herencia y sobrecarga de métodos _hooks_ predefinidos (Utilizando patrones como _Template Method_ [@Gamma1994] o similares).

Debido a su forma de reuso y extensión (Herencia) es necesario que el desarrollador tenga un íntimo conocimiento de cada pieza interna de estos, produciendo que el software desarrollado tenga un gran acoplamiento a la estructura jerárquica de herencia del framework.

##### Frameworks Black-box

La extensión en esta clase de frameworks es realizada definiendo interfaces compatibles con el framework e inyectándolas a este mediante composición.

Por otra parte, el reuso de funcionalidades es realizado mediante la definición de componentes que cumplan con ciertas interfaces e inyectando estos componentes al framework con patrones como _Strategy_ y _Functor_ [@Gamma1994].

Su estructura basada en composición y delegación permite que sea más sencillo su uso y extensión (En comparación a los frameworks White-box).
Este beneficio incurre en un elevado costo de desarrollo, debido en que las etapas de diseño deben definirse interfaces y hooks que anticipen un amplio espectro de casos de uso [@Hermann1995].

### Patrones de diseño

Una de las grandes problemáticas que enfrentan los desarrolladores en la etapa de diseño de un sistema, son las limitaciones generadas por las decisiones de diseño tomadas en componentes que se desean reutilizar, entre estas decisiones encontramos algoritmos e interfaces propias de componentes u objetos.

Esta problemática es compartida por desarrolladores, generalmente en distintos contextos y componentes, la busqueda de soluciones generales a problemas de diseño avanzó hasta la creación de los _patrones de diseño_ [@Sommerville2005].

Un _patrón de diseño_ es la descripción de un problema y la esencia de su solución, de forma que esta pueda ser reutilizada en distintos contextos [@Sommerville2005].
Se destaca la naturaleza abstracta del patrón, al no entrar en los detalles de su especificación;, sin embargo un patrón es una expresión de conocimiento y experiencia acumulada.

Hay 3 aspectos principales que todo patrón de diseño debe incluir [@Gamma1994]:

* Una _descripción abstracta_ de las relaciones existentes entre objetos o clases, la abstracción es requerida debido a que describe un diseño general y no uno particular.
* El _problema de diseño_ que será abordado por la estructura abstracta, de esta forma se determina en que escenarios es aplicable el patrón.
* Las _consecuencias_ (positivas y negativas) introducidas al aplicar la estructura abstracta a la arquitectura del sistema. Este punto ayuda a determinar si el patrón debe aplicarse o no.

#### Patrón Factory

Este patrón se encarga de escoger y retornar una clase desde un conjunto de clases en función a un dato provisto. Comúnmente, el conjunto de clases comparte un _ancestro_ en común (Por lo que la interfaz de uso es igual para todas), pero cada una de ellas realiza distinta lógica [@Cooper1998].

Es recomendable utilizar el patrón _Factory_ en las siguientes situaciones:

* Una clase no puede anticipar que clase de objetos debe crear.
* Una clase utiliza sus subclases para especificar que objetos crea.
* Es necesario definir el _dónde_ almacenar la lógica en que se escoge la clase a crear.

#### Patrón Proxy

Este patrón es utilizado cuando se necesita representar un objeto complejo como uno más simple [@Cooper1998]. Otro uso de este patrón es la optimización del uso de recursos, ya que un _Proxy_ puede retrasar la carga de un objeto que incurra en altos tiempos de carga (ej: cargar una imagen, inicializar un array) hasta que este sea realmente necesario. Finalmente, un uso muy común de este patrón es para enforzar los permisos de acceso a objetos, permitiendo un acceso granular a los objetos de negocio [@Cooper1998].

<!-- TODO: Añadir una imagen explicativa del patrón proxy, me tinca algo con seguridad como los filtros de laravel -->

#### Patrón Singleton

El uso del patrón _Singleton_ es recomendado cuando la lógica de la aplicación requiere que exista solo una instancia de una clase [@Cooper1998]. Esta técnica es muy utilizada en _Spring Framework_ al definir componentes, ya que por defecto son _Singletons_.

#### Patrón Inyección de dependencias

TODO: Añadir definición de esto.

#### Patrón Repository

El patrón _Repository_ nace de los problemas generados al acceder a los datos presentes en una aplicación, estos datos pueden existir en diversos almacenamientos, ya sean bases de datos, web services, ficheros de texto u otros; el acceso directo a datos puede generar los siguientes problemas:

* Código duplicado.
* Aumentar la probabilidad de errores de programación.
* Bajo control de los datos de negocio.
* Dificultad al centralizar políticas relacionadas a datos tales como _cache_.
* Imposibilitar la realización de pruebas a la lógica de negocio en forma aislada (Pruebas unitarias).

Estas problemáticas son agrupadas bajo la necesidad de unificar el punto de acceso a datos en la aplicación. Es así que este patrón ofrece una interfaz centralizada para el acceso a datos, reutilizable en alguna capa de la aplicación [@Evans2004].

### Patrones Arquitectónicos

Un _patrón arquitectónico_ es la expresión de una estructura fundamental para sistemas de software [@Buschmann1996].

"Un patrón arquitectónico no es una arquitectura; un software concreto tiene una arquitectura que es una _instancia_ de un patrón arquitectónico" [@Malinen2013]. Este concepto tiene una íntima relación a la función de los _patrones de diseño_, debido al nivel de abstracción que ambos tipos de patrones deben presentar.
Una de las características más importantes de los patrones arquitectónicos es proveer atributos de calidad [@Malinen2013].

El patrón provee un conjunto definido de subsistemas, especificando sus responsabilidades e incluye las reglas y guías para organizar las relaciones entre ellos.

Un patrón arquitectónico es una forma de comunicar experiencias de diseño de arquitecturas de software, produciendo así software de mejor calidad; en otras palabras un patrón arquitectónico promueve la reutilización de diseños [@Bass2012].

#### Atributos de calidad

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

#### Patrón MVC

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

#### Patrón de Microservicios

La "arquitectura de microservicios" describe una forma de diseñar un sistema separando sus servicios en artefactos independientemente desplegables.

## Componente

Un componente es un trozo de software, cuyo propósito es ser utilizado, sin cambio alguno, por una aplicación que esta fuera del control de los escritores del componente [@Fowler2004].

Un término similar es el de _Servicio_, cuya principal diferencia es la localidad de uso del componente, en un servicio se espera que el uso sea remoto, mediante alguna interfaz remota; aunque en términos prácticos pueden utilizarse como sinónimos [@Fowler2004].

## API (_Application Programming Interface_)

## HTTP (_Hyper Text Protocol_)

Es un protocolo situado en la capa de aplicación del modelo _OSI_, diseñado para sistemas de información de hipermedios distribuidos y colaborativos [@Fielding1999].
Este protocolo es genérico y las peticiones son _stateless_ (cada petición es independiente a las anteriores); puede ser utilizado para propósitos distintos al manejo de hipermedios mediante la extensión de los métodos de petición, códigos de error y _headers_ [@Masinter1998].

La _RFC2616_ especifica que estos son términos escenciales para la descripción del protocolo [@Fielding1999]:

### Cliente

Un programa que establece _conexiones_ con la finalidad de realizar peticiones.

### Conexión

Una capa de transporte virtual establecida entre dos programas cuyo propósito es la comunicación.

### Mensaje

Es la unidad básica de la comunicación _HTTP_, consiste en una secuencia estructurada de octetos correspondiente a una sintaxis específica y transmitida mediante una conexión.

### URI (_Universal Resource Identifier_)

Un _URI_ corresponde a un _string_ formateado que identifica un recurso mediante nombre, ubicación o cualquier otra característica.

### Recurso

Un objeto de datos de red o servicio que puede ser identificado mediante un _URI_.
Un recurso puede presentar multiples representaciones (distintos lenguajes, formatos de datos, tamaños y resoluciones) o variar en otras formas.

### Petición (_Request_)

Un mensaje _HTTP_ de petición, es enviada por el cliente y tiene como objetivo un recurso.
Una petición se compone del método a ser aplicado sobre el recurso, el identificador del recurso, la versión del protocolo en uso, un conjunto de cabeceras (en las cuales el cliente puede enviar información adicional respecto a la petición), finalmente se encuentra el cuerpo del mensaje.

### Respuesta (_Response_)

Corresponde a un mensaje _HTTP_ de respuesta.
El servidor envia una respuesta luego de procesar la petición del cliente, esta respuesta se compone de la versión del protocolo usada, el código de estado (y su razón), un conjunto de cabeceras agregando información que no puede ser expresada a través del código de estado, finalmente se encuentra el cuerpo del mensaje.

### Entidad (_Entity_)

Corresponde a la información transferida como "carga útil" de una petición o una respuesta.
Una entidad consiste en meta-información, la que se separa en campos de cabecera (_headers_) y contenido (o cuerpo). <!-- si deseo extenderlo, sección 7 -->

### Representación (_Representation_)

Corresponde a una entidad incluida en una respuesta que esta sujeta a la negociación de contenido.
Pueden existir multiples representaciones asociadas a un código de respuesta particular.

### Agente de usuario (_User Agent_)

Corresponde al cliente que inicia la petición. Muchas veces corresponden a navegadores, editores, arañas (_spiders_) y otras herramientas de usuario.

### Servidor

Corresponde a un programa que acepta conexiones para servir peticiones mediante el envio de respuestas.

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

## Paradigmas de programación

Un paradigma de programación es un estilo o "forma" de programación [@Floyd1979].

### Programación orientada a objetos

Este paradigma de programación insta a la construcción de sistemas mediante la descomposición del problema en objetos para luego escribir las interacciones entre estos objetos. Un objeto permite abstraer comportamiento y datos en una sola entidad conceptual (y física) [@Elrad2001].

<!--
### Programación orientada a aspectos

La programación orientada a aspectos sigue el linaje dejado por la programación procedural, estructurada, funcional, lógica y con tipos de datos abstractos, en la tarea de lograr una separación clara de los asuntos/preocupaciones en el nivel del código fuente [@Elrad2001].

Actualmente, el paradigma de programación predominante es el _Orientado a objetos_ [@Elrad2001], este ha permitido el desarrollo de grandes aplicaciones, sin embargo posee sus limitaciones. Estas limitaciones se presentan al observar requerimientos que no pueden ser satisfechos enfocándose en uno o dos objetos, sino que deben ser satisfechos enfocándose en la interacción entre ellos y restricciones globales.
-->

### Inversión de Control (_IOC_)

<!-- TODO: Calzar a jefe para que me explique con peras y manzanitas esto y el patrón DI -->

## Java Persistence API

La función de la _Java Persistence API_ o _JPA_, es especificar un modelo de persistencia estándar y sencillo de usar en plataformas Java SE y Java EE [@Boeck2011].
Su principal característica es la especificación del _object relational mapping_ (Mapeo objeto-relacional) directamente en los objetos de persistencia, conocidos en este contexto como entidades.

Un _mapeo objeto-relacional_ (_ORM_), provee un mecanismo para que sistemas orientados a objetos mantengan sus datos de forma segura en una base de datos, con manejo transaccional y controlados mediante objetos cuando sea necesario [@ONeil2008].

El _ORM_ se encarga de manejar en tiempo de ejecución las relaciones entre las entidades, entregando grafos de objetos que representan relaciones complejas entre objetos; también se encarga de seguir el ciclo de vida de los objetos, llevando la cuenta de las acciones aplicadas sobre ellos y ejecutando las queries SQL necesarias para persistir estos eventos en la base de datos.


## Bean Validation

La validación de datos es una tarea que ocurre en la aplicación, desde la capa de presentación a la capa de persistencia [@Bernard2009].
Muchas veces la lógica desarrollada es implementada en cada capa, lo que es susceptible a fallos y una pérdida de tiempo.
Para solucionar el problema de duplicación de código de validación, los desarrolladores suelen implementar esta lógica en el modelo del dominio, sin embargo esto provoca que las clases del dominio estén abarrotadas con código que a fin de cuentas es información de la propia clase.

_Bean Validation_ es presentado en la _JSR_ (_Java Specification Request_) 303 [@Bernard2009], definiendo un modelo de metadatos y un _API_ para validación, el que puede ser implementado en forma de _anotaciones_ o descripciones utilizando _XML_.


## Lenguaje de Programación Java

El lenguaje de programación Java fue desarrollado por _Sun Microsystems_ a principios de los 90, para proveer un lenguaje orientado a objetos, portable e interpretado, su gran propuesta de valor es el manejo de memoria, esta es manejada de forma automática [@Gosling1995].

<!-- TODO: Agregar info sobre la JVM, J2SE y J2EE -->
<!-- TODO: Agregar info sobre servidores de aplicaciones -->

## Framework Spring

Spring es el framework de desarrollo más popular de la plataforma Java [@DashrathMane2013]. Este framework provee un modelo exhaustivo de programación y configuración para aplicaciones de negocio modernas basadas en Java, para cualquier tipo de infraestructura; su objetivo es hacer más sencillo el desarrollo de aplicaciones _J2EE_ para usar y promover buenas prácticas de programación utilizando un modelo de programación basado en _POJO_ (Clases Java simples, independientes de algún framework).
_Spring_ posee un diseño modular, que permite la adición de componentes tales como el _contenedor_ principal o el soporte _JDBC_.

Esta imagen muestra las capas de componentes del framework:

![Spring Framework Architecture](source/figures/001_spring_framework_architecture.png)\newline

<!-- TODO: Eliminar el hack feo de la imagen -->

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


## Digital Signage (_Cartelería Digital_)

La cartelería digital es una forma de tecnología de publicidad electrónica que soporta la presentación de contenidos multimedia de forma dinámica [@Harrison2004].

En su forma más básica, un letrero digital se compone de un dispositivo de visualización y un controlador de visualización, donde un  dispositivo de visualización puede ser un monitor _LCD_, _LED_ o incluso un proyector. El dispostivo controlador de visualización puede ir desde un reproductor de DVD a un computador de propósitos generales [@Harrison2004].

## Role Based Access Control (_RBAC_)

La idea central de esta técnica de control de acceso, es que los usuarios no tienen acceso a los objetos de negocio; si no que los permisos son asociados a roles, y los usuarios pasan a ser miembros de los roles apropiados o reasignados de roles de ser necesario. De esta forma se simplifica el manejo de la _autorización_ y se provee una forma flexible de especificar y enforzar las políticas de protección de negocio [@Ferraiolo1995]. Otro punto a favor de esta técnica, es el manejo de _permisos_, debido a que es posible asignar nuevos permisos a medida que se implementan nuevas aplicaciones o funcionalidades, o revocar permisos a un rol de ser necesario.

## SIS (_Student Information System_)

## SEPA (_Sistema Estadístico Profesores y Alumnos_)

<!-- Buscar en la biblioteca el tt de sepa -->

## Scheduler de tareas basado en tiempo

El propósito de un _Scheduler_ de tareas basado en tiempo es ejecutar comandos, series de comandos o scripts en un horario determinado. Un scheduler es generalmente ejecutado en sistemas que están corriendo las 24 horas del día, 7 días a la semana [@Peters2009].

## Historias de Usuario

Una historia de usuario describe funcionalidad valiosa para un usuario o comprador de un sistema o software [@Cohn2004]. En su libro, Cohn muestra que una historia de usuario es compuesta por 3 aspectos:

* Una descripción escrita de la historia, utilizada para planificación y como recordatorio.
* Conversaciones acerca de la historia que sirvan para profundizar los detalles de la historia.
* Pruebas que comuniquen y documenten los detalles, estas pueden ser utilizadas para determinar cuando una historia este completa.

Debido a que las historias de usuario son generalmente escritas en papel [@Cohn2004], es que podemos nombrar a estos aspectos como _Tarjeta_ (_Card_), _Conversación_ (_Conversation_) y _Confirmación_ (_Confirmation_) [@Jeffries2001].

Hay que tener en consideración que las historias de usuario deben _representar_ el interés del cliente en el sistema/software, mas no _documentarlo_, esto quiere decir que al confeccionar historias de usuario se deben dejar de lado comentarios que hagan referencia a la implementación (A menos que el interés principal del cliente sea este, debido al mercado en que el software se insertará) [@Cohn2004].

<!-- TODO: Añadir una imagen que muestre los 3 aspectos de una historia de usuario -->


## ETL (_Extraction Transformation Load_)

Es un proceso encargado de extraer datos de sistemas posiblemente heterogéneos, realizar transformaciones (ej: conversión y limpieza de datos) para finalmente cargar los datos transformados en el almacen de datos objetivo [@Thomsen2009].

## SAAS (_Software As A Service_)

_SAAS_ es un tipo de computación en la nube, en el que la aplicación es hospedada en un proveedor de servicio y luego es accesada mediante Internet por un cliente [@Velte2009].

Los servicios ofrecidos mediante _SAAS_ pueden ser agrupados en dos categorias:

* **Línea de servicios de negocios**: Corresponden a las soluciones de negocios ofrecidas a compañias y negocios. Son vendidos mediante suscripción y se enfocan al área de procesos de negocio, tales como aplicaciones de manejo de cadena de distribución, manejo de relaciones con clientes (_CRM_), entre otras.

* **Servicios orientados al cliente**: Corresponden a las soluciones ofrecidas al público general en forma de suscripción. Lo más frecuente es que su uso sea gratuito y su financiamiento se logre mediante publicidad. Los ejemplos de esta categoria son los servicios de correo web, juegos en línea, entre otras.

Las ventajas ofrecidas a la organización se generan principalmente por la desligación de esta sobre la mantención del sofware, entre las ventajas encontramos las siguientes:

* Reducción de costos de licencias de software.
* Eliminación de costos de instalación y mantención de hardware y software.
* Los proveedores _SAAS_ generalmente son sometidos a auditorias muy meticulosas.
* Los ciclos de actualización permiten al cliente estar con la versión más actualizada en el menor tiempo posible, permitiendo a la organización invertir en innovación en su industria, en vez de estar manteniendo versiones deprecadas de aplicaciones.


## Proceso de desarrollo de Software

Un proceso es un conjunto de actividades, acciones y tareas que se ejecutan cuando va a crearse
algún producto del trabajo.
Una actividad busca lograr un objetivo amplio (por ejemplo, comunicación con los participantes) y se desarrolla sin importar el dominio de la aplicación, tamaño del proyecto, complejidad del esfuerzo o grado de rigor con el que se usará la ingeniería de software. Una acción (diseño de la arquitectura) es un conjunto de tareas que producen un producto importante del trabajo (por ejemplo, un modelo del diseño de la arquitectura). Una tarea se centra en un objetivo pequeño pero bien definido (por ejemplo, realizar una prueba unitaria) que produce un resultado tangible [@Pressman2002].
El proceso de software no es una receta rígida que asegure el éxito de un trabajo, más bien es un enfoque adaptable que permite a los usuarios confeccionar su propio conjunto de acciones y tareas y organización de estás para el trabajo. El objetivo de este proceso es la entrega oportuna y con la calidad requerida para satisfacer a los interesados en el proyecto y los usuarios finales.
Finalmente, existen 5 etapas transversales a todo proyecto de software, es decir, son aplicables en todo proyecto, independiente de su tamaño o complejidad.

### Actividades estructurales de un proceso de desarrollo de Software

#### Comunicación

La comunicación con el cliente es una parte crítica en el desarrollo y debe preceder a cualquier trabajo técnico. Aquí se busca entender los objetivos de cada participante respecto al proyecto y reunir los requerimientos que definan las características y funciones del software.

#### Planeación

Esta etapa genera el plan de desarrollo de software, el cual contiene las tareas técnicas a realizar, los riesgos probables, recursos requeridos, productos de trabajo obtenidos y una programación de actividades.

#### Modelado

El modelado es una actividad utilizada en distintas disciplinas que permite tener un panorama general de la situación que se quiere representar. Esto no es distinto en el desarrollo de software y ayuda a entender mejor los requerimientos y el diseño que los satisfagan.

#### Construcción

Esta etapa combina la generación de código y las pruebas requeridas para descubrir errores en este.

#### Despliegue

Se hace la entrega del software al consumidor, quien debe evaluar y generar feedback.


### Flujos del proceso de software

La organización de las actividades estructurales vistas en el punto anterior forman distintos tipos de flujos de software, entre los que encontramos el flujo lineal, iterativo, evolutivo y en paralelo.

#### Flujo lineal

Un flujo de proceso lineal ejecuta cada una de las cinco actividades estructurales en secuencia, comenzando por la comunicación y terminando con el despliegue.

![Flujo Lineal](source/figures/flujo_lineal.png)

#### Flujo iterativo

Un flujo de proceso iterativo repite una o más de las actividades antes de pasar a la siguiente.

![Flujo Iterativo](source/figures/flujo_iterativo.png)

#### Flujo evolutivo

Un flujo de proceso evolutivo realiza las actividades en forma "circular". A través de las cinco actividades, cada circuito lleva a una versión más completa del software.

![Flujo Evolutivo](source/figures/flujo_evolutivo.png)

#### Flujo paralelo

Un flujo de proceso paralelo ejecuta una o más actividades en paralelo con otras (por ejemplo, el modelado de un aspecto del software tal vez se ejecute en paralelo con la construcción de otro aspecto del software).

![Flujo Paralelo](source/figures/flujo_paralelo.png)
