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

_Spring Cloud_ es  una colección de herramientas construidas por [Pivotal](https://pivotal.io) diseñadas para solucionar patrones encontrados comúnmente en aplicaciones distribuidas. Entre las problemáticas solucionadas encontramos las siguientes:

## **Manejo de configuraciones centralizado**: Al crecer la cantidad de servicios (microservicios) desplegados, el manejo de configuraciones en cada uno de ellos se vuelve inmanejable si es realizado de forma manual. _Spring Cloud_ soluciona esto con su **Config server**, un servicio que concentra globalmente las configuraciones del sistema, y **Config client**, una libreria que configura el contexto de una aplicación desde el **config server**.

![Spring Cloud Config](source/figures/spring-cloud-jug-switzerland-11-638.jpg)

## **Servicio de descubrimiento de servicios**:
