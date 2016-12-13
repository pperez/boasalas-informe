# Implementación del sistema a medida

Según las descripciones presentadas en el capítulo anterior, se presenta una posible implementación utilizando el patrón de microservicios y herramientas de código abierto.
El stack tecnológico utilizado se compone principalmente de lo siguiente:

* Java 8.
* Spring Framework.
* Spring Cloud.
* PostgreSQL 9.
* Vue.js.

## Modelos de datos de servicios

TODO: Hacer diagrama de datos.

## Metodología de Desarrollo

TODO: Mmm, llenar esto?

## Desarrollo de microservicios con Spring Cloud

_Spring Cloud_ es  una colección de herramientas construidas por [Pivotal](https://pivotal.io) diseñadas para solucionar patrones comúnmente encontrados en aplicaciones distribuidas. Entre las problemáticas solucionadas encontramos las siguientes.

### Manejo de configuraciones centralizado

Al crecer la cantidad de servicios (microservicios) desplegados, el manejo de configuraciones en cada uno de ellos se vuelve inmanejable si es realizado de forma manual. _Spring Cloud_ soluciona esto con su **Config server**, un servicio que concentra globalmente las configuraciones del sistema, y **Config client**, una libreria que configura el contexto de una aplicación desde el **config server**.

![Spring Cloud Config](source/figures/spring-cloud-jug-switzerland-11-638.jpg)

### Servicio de descubrimiento de servicios

Otra problemática presentada al tener una gran cantidad de microservicios en ejecución, es llevar registro de que en que hosts y puertos estos exponen sus servicios, hacer esto manualmente se vuelve inmanejable a medida que escala nuestra plataforma. Esto es abordado con **Spring Cloud Eureka**, consistente en un servicio donde los microservicios puedan autoregistrarse y una libreria cliente para descubrir instancias de microservicios desde el servidor. Esta funcionalidad tambien permite tener direccionamiento dinámico y balanceo de carga.

![Spring Cloud Eureka](source/figures/eureka.png)

### Corta-circuitos

Debido a la naturaleza distribuida de este patrón, las llamadas a un servicio pueden gatillar multiples llamadas a otros servicios, haciendo que el sistema sea susceptible a fallas en cascada. Esta problemática es paleada mediante la aplicacion del patrón _Circuit Breaker_, abordado con **Hystrix**.

![Netflix Hystrix](source/figures/circuit_breaker_state_diagram.gif)

### Monitoreo

Vigilar la salud de cada parte del sistema es posible debido al _Circuit Breaker_, a su vez se pueden recolectar estadísticas, estas pueden ser mostradas en paneles de control (Dashboards) y utilizadas para lanzar automáticamente alarmas cuando ciertos umbrales sean sobrepasados. Los datos son recolectados por **Turbine** y servidos por **Hystrix Dashboard**

![Hystrix Dahsboard](source/figures/hystrix-dashboard-fig6-100586598-large.idge.png)

### API Gateway

En un esquema de microservicios, una vista puede requerir información de multiples servicios, por lo que desde nuestros clientes (e.g Navegadores visualizando una _SPA_ (Single Page Application), teléfonos inteligentes con Android o iOS, etc) debemos tener un punto de entrada a todo nuestro ecosistema. Esta problemática se aborda con un _API Gateway_, siendo esta la puerta de entrada a los servicios de nuestro sistema, en conjunción con el descrubrimiento de servicios lograremos que los clientes accedan a distintos servicios mediante rutas específicas.
Otro punto a favor de esta herramienta es la adición de filtros, así podemos añadir lógica a las distintas etapas de una petición. _Spring Cloud_ incluye el _API Gateway_ de _Netflix_ llamado **Zuul**, este soporta los siguientes tipos de filtros:

* **Pre**: Ejecutados antes de que la petición sea dirigida.
* **Routing**: Manipular el direccionamiento de la petición.
* **Post**: Ejecutados despues de que la petición sea dirigida.
* **Error**: Ejecutados si se producen errores al procesar la petición.

![Spring Cloud Zuul](source/figures/zuul-api-gateway.jpg)

### Autenticación y autorización con OAUTH 2.0

La aplicación de _OAUTH 2.0_ a un entorno de microservicios influye de esta forma:

* Se agrega un nuevo servicio _Oauth Authorization Server_, este emite tokens que pueden ser usados para autorización en otros servicios.
* Cada servicio actuará como un _Oauth Resource Server_.
* Los consumidores externos de servicios actuarán como _Oauth Clients_.
* El gateway actuará como un _Oauth Token Relay_, funcionando primeramente como un _Oauth Resource Server_ para luego pasar el token de acceso hacia los servicios internos.

_Spring Cloud_ provee soporte de _Oauth 2.0_ en su módulo _Spring Cloud Security_.

![Spring Cloud Security](source/figures/68747470733a2f2f71696974612d696d6167652d73746f72652e73332e616d617a6f6e6177732e636f6d2f302f313835322f31393936393035372d633864312d653264372d666435362d3832666537383465376133362e706e67.png)
