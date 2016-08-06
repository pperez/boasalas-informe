# Presentación del proyecto

## Descripción del proyecto

Este proyecto presenta el diseño y construcción de un sistema para la comunidad de nuestra casa de estudios, que permita la administración y consulta del uso de salas de clases y laboratorios en los distintos campus y espacios de la universidad.
El sistema cuenta con 3 módulos separados por funcionalidad:

### Módulo de Preinscripción de cursos

Este módulo aborda el proceso de ajuste de horarios de cursos entre las escuelas y secretarías de estudio (u otras entidades que manejan los horarios de salas y laboratorios).
Este proceso se realiza previamente a la inscripción oficial de cursos en la _DEA_ (Dirección de Evaluación Académica) y consiste en la asignación de salas y laboratorios a los cursos entregados por las escuelas, aquí cabe la posibilidad de que ciertos cursos sufran modificaciones de horarios debido a la disponibilidad de espacios.
Finalmente, el sistema permite realizar el enlace entre las preinscripciones ingresadas y los cursos oficialmente inscritos, en el caso de que hayan diferencias, son areglables en el módulo de asignación.


### Módulo de Asignación

Este módulo aborda el proceso de asignación de salas o laboratorios a los cursos inscritos oficialmente.
Posee integraciones con notificaciones mediante correo electrónico para eventos importantes, como cambios de salas u horarios.



<!--
* Backoffice: Módulo que permite a los encargados de los espacios (Salas, laboratorios y otros) realizar asignaciones en función a los periodos y cursos establecidos por la institución.

* Presentación: Módulo que permite consultar las asignaciones de recursos, especificando parámetros de consulta, tales como horarios en un bloque determinado en cada campus, horario de clases de un docente en especial y horarios particulares para el estudiante que realice la consulta.
Este módulo estará construido de tal forma de ser integrable con la mayor cantidad posible de dispositivos, tomando en cuenta los avances actuales sobre televisores y teléfonos inteligentes (Smart TVs y SmartPhones respectivamente), y básicamente cualquier dispositivo que cuente con acceso a Internet y posea un kit de desarrollo de software.

* Actualizador de datos: Este módulo es el encargado de actualizar la información curricular de la institución (Volcándola en los registros locales del sistema propuesto), permitiendo así a los encargados tener información actualizada desde una fuente de datos oficial de la universidad;  este módulo elimina la necesidad de que las escuelas o departamentos asociados tengan que enviar tal información a los encargados de los recursos.

El diseño arquitectónico de este sistema permitirá la integración con las plataformas desarrolladas por estudiantes y funcionarios de la institución, dando un puntapié inicial a una posible consolidación e interacción de los sistemas de TI que posee actualmente la institución e incluso con aquellos que serán desarrollados a futuro.

-->

## Objetivos

### General

Diseñar e implementar un sistema de manejo de salas y laboratorios para un campus universitario que permita integraciones a otros sistemas y herramientas de TI.

### Específicos

* Formalizar y sistematizar el proceso de administración de salas y laboratorios.
* Construir un sistema que posea puntos de integración con otros sistemas o herramientas.
* Utilizar las herramientas que demanda el mercado en la construcción de sistemas para una institución que se vincula directamente con él.

## Metodología

El diseño arquitectónico de este proyecto contempla una toma de requerimientos, realizada en forma presencial con los principales involucrados en los procesos actuales de asignación de salas y laboratorios.
La toma de requerimientos da paso a la confección del diseño arquitectónico del sistema y el plan de actividades de desarrollo, el que será distribuido en hitos semanales y desarrollado por un equipo de trabajo compuesto de una persona.
El plan de actividades contempla diversas tareas, las que cuentan con una estimación de tiempo inicial, permitiendo saber a priori el costo del proyecto y en cuanto tiempo será completado.
A su vez el plan de actividades posee revisiones por los Stakeholders (Principales interesados y afectados por el desarrollo de este proyecto).


## Alcances

* El proyecto operará de forma online, por lo que se requiere de un dispositivo con acceso a internet y un navegador web.
* El proyecto utiliza como fuente de datos la planificación académica provista por la Dirección de Docencia de la institución, permitiendo eliminar duplicidad de la información.


## Limitaciones

* El sistema recopila información académica, sin embargo no replica las funcionalidades existentes en otras plataformas institucionales (Dígase Dirdoc, Reko, Mi UTEM y otros).
* Si bien el sistema es accesible desde dispositivos móviles como smartphones o tablets, no se asegura una experiencia de usuario rica como en plataformas desktop.


## Recursos

En general, se contempla el uso de los siguientes componentes:

* Motor de base de datos PostgreSQL.
* Lenguaje de programación Java, utilizando el framework _Spring_ y librerías 3rd party relacionadas.
* Servidor con Ubuntu 14.04 server de 64 bits, capaz de ejecutar el motor de base de datos referenciado anteriormente y un contenedor a aplicaciones Java web.

El licenciamiento de los recursos de software utilizados es de carácter libre.


## Resultados esperados

Se espera que la construcción de un proyecto con puntos de integración abiertos permita la interacción entre plataformas utilizadas en la institución, reduciendo drásticamente los tiempos requeridos por procesos realizados de forma manual.
A su vez el diseño pensado en la integración de otros sistemas permite a los integrantes de la institución el desarrollo de sistemas que exploten los datos existentes en el sistema, pudiendo generar innovación y proyecciones que apoyen la toma de decisiones institucionales.
