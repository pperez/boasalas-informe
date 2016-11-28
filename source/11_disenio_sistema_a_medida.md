# Diseño de un sistema a medida

## Metodología de Desarrollo

TODO: Mmm, llenar esto?

## Descripción de servicios

Este apartado detalla las funciones de cada servicio y las tecnologías utilizadas en cada uno de ellos.

### Servicio  de autenticación

Este servicio es el encargado de proveer autenticación, tanto para la interfaz de usuario, como para otros servicios. Para proveer autenticación desde el _SIS_ de la universidad, se utiliza el servicio _REST_ de _SEPA_, además de autenticar con credenciales oficiales de la universidad es posible saber los roles del usuario en esta (Diferenciar si tiene acceso de docente, estudiante o administrativo).


#### Tecnologías usadas

### Módulo de preinscripción

Este módulo es el encargado de procesar las inscripciones de cursos en secretarías de estudio.

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