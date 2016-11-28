# Diseño de un sistema a medida

Esta alternativa consiste en el desarrollo a medida del sistema para la universidad, utilizando herramientas empresariales y tecnologías de punta.

Para el desarrollo de los servicios que forman el sistema se utilizará el patrón arquitectónico de microservicios, facilitando así la escalabilidad del sistema bajo la demanda.

## Metodología de Desarrollo

TODO: Mmm, llenar esto?

## Descripción de servicios

Este apartado detalla las funciones de cada servicio y ciertos requerimientos técnicos fundamentales para la implementación.

### Servicio  de autenticación

Este servicio es el encargado de proveer _autenticación_ y _autorización_ en las diversas capas del sistema principal.
Pertenece al _Sistema Estadístico de Profesores y Alumnos (SEPA)_ de la universidad y será desarrollado para permitir integraciones con otras aplicaciones que requieran el uso de datos estadísticos.

La utilización del protocolo _OAUTH2_ es fundamental para cumplir con esta tarea.

### Servicio de preinscripción

Este servicio es el encargado de procesar las pre-inscripciones de cursos en secretarías de estudio o unidades afines, para así definir la programación horaria final a entregar a la _Dirección de Evaluación Académica_.
Su funcionamiento consiste en manipular la disponibilidad de salas en los campus necesarios, pre-asignando las salas, de forma de poder realizar ajustes en los horarios de los cursos a ser ofertados en el siguiente semestre lectivo.

### Servicio de asignación

Este servicio permite realizar asignaciones de salas o laboratorios a cursos, teniendo cada asignación una fecha y periodo específicos.
En este servicio también se encuentra la lógica que integra el trabajo previo de asignación realizado en el servicio de pre-inscripción.
Una característica fundamental de este servicio es el acceso a los cursos inscritos en el semestre lectivo, evitando errores de tipeo y enforzando la correctitud de los datos manipulados.
También se incluye aquí la lógica de entrega de llaves, indicador necesario para saber el uso real de salas y laboratorios.

### Servicio de notificaciones

Este servicio es el encargado de enviar notificaciones a los usuarios al producirse cambios en eventos que los involucran (e.g cambio de sala de clases, nueva asignación horaria para un cursos, asignación de alguna evaluación, etc), así como también de manipular las prefrencias de los usuarios respecto a las notificaciones recibidas (e.g si las notificaciones son recibidas mediante correo, sms u otro medio, si desea recibir notificaciones o no, para que cursos recibir notificaciones, etc)


### Servicio de información

Este servicio posee información correspondiente a la universidad como tal, manejando las relaciones entre campus, facultades, departamentos y datos como salas (Incluyendo su capacidad y otras características), grupos de trabajo (Encargados de asignar horarios para salas, o realizar peticiones de salas).

### Servicio de informes

Este servicio contiene la lógica de generación de informes de gestión y análisis de datos necesarios para la institución.

<!--

### Módulo modelo

Este módulo es el encargado de manejar la capa de datos del sistema, exponiendo servicios reutilizables por otros módulos del sistema. Aquí se observa la lógica de negocios aplicada sobre la base de datos, con las restricciones respectivas aplicadas.

Los componentes tecnológicos a utilizar son los siguientes:

* **JPA**: _API_ de persistencia de datos, utilizada para _mapear_ las relaciones entre objetos de la base de datos al modelo orientado a objetos del sistema.
* **Spring Data JPA**: Componente utilizado para construir repositorios _JPA_, con los que se generan automáticamente queries a la base de datos, pudiendo reutilizar estos repositorios en distintas partes de los servicios expuestos por el módulo.

### Módulo integrador

Este módulo es el encargado de actualizar datos en el sistema local, su estrategia es utilizar tareas programadas para consumir datos desde el web-service de _SEPA_, trayendo así automáticamente los siguientes datos:

* Facultades
* Departamentos
* Docentes
* Asignaturas
* Escuelas
* Carreras
* Cursos
* Periodos
* Horarios
* Estudiantes
* Cohortes
* Asignaturas cursadas/en curso

De esta forma, no es necesario hacer una carga manual de estos datos, agilizando las tareas importantes de los usuarios finales de este sistema: _La asignación y reserva de salas_.

Los componentes tecnológicos a utilizar en este módulo son los siguientes:

* **Quartz**: La libreria de _scheduling_ (programación) de tareas, con ella se pueden definir tareas a ser ejecutadas periódicamente, manteniendo actualizada la información listada más arriba.
* **Jackson**: Librería encargada de _parsear_ (interpretar) la información obtenida desde el servicio _REST_ de _SEPA_.

### Módulo API

Este módulo es el encargado de exponer el servicio _REST_ al mundo. La principal característica de este servicio es disponibilizar a desarrolladores el manejo de los datos existentes en el sistema, aplicando la lógica de negocios de la institución basada en control de acceso por perfiles  de usuario.

El _API_ expuesto es de tipo _REST_ y puede ser consultado por cualquier sistema o dispositivo que soporte peticiones _HTTP_ y maneje objetos _JSON_.

Los componentes tecnológicos a utilizar en este módulo son los siguientes:

* **JAXRS**: Este componente se encarga de proveer soporte de servidores y clientes _REST_; en este módulo se utilizan ambas modalidades, debido a que se debe consumir el servicio _REST_ de _SEPA_ para realizar la autenticación, además de proveer acceso a los distintos recursos via _REST_.
* **Spring Security**: Este componente es utilizado para manejar el acceso (o denegación de este) a los distintos recursos, implementando complejas lógicas de _ACL_ basadas en los perfiles existentes.

### Módulo web

Este módulo es el encargado de servir la aplicación web, construida utilizando el patrón _MVC_.

Los componentes tecnológicos a utilizar en este módulo son los siguientes:

* **JSF**: Framework web, orientado a componentes. <!-- TODO: mejorar esto, suena paupérrimo
* **Spring Security**: Este componente es utilizado para manejar el acceso (o denegación de este) a los distintos recursos, implementando complejas lógicas de _ACL_ basadas en los perfiles existentes.


## Modelo de datos (Lógico-Relacional)

Para cumplir con los requerimientos, el modelado de datos fue el siguiente:

![Modelo Lógico-Relacional](source/figures/002_diagram_salas.png)

-->
