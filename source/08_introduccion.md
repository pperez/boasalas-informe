# Presentación del proyecto

## Descripción del proyecto

Uno de los recursos críticos en una institución de educación son las salas de clases y laboratorios;
actualmente la asignación de estos es un proceso manual y propicio a fallos. Este proyecto apunta a proveer un sistema la administración y consulta del uso de salas y laboratorios, en todos los campus y espacios controlados por la universidad.

El sistema cuenta con 3 módulos separados por funcionalidad:

### Módulo de Preinscripción de cursos

Este módulo aborda un proceso realizado previamente a la inscripción de cursos en la _DEA_ (Dirección de Evaluación Académica), consistente en la coordinación de cursos y horarios entre escuelas y secretarías de estudio (u otras entidades que manejan salas y laboratorios). Para diferenciarlo del proceso realizado en _DEA_, se le llama proceso de _Preinscripción_.
Además el sistema permite establecer una relación entre las preinscripciones y los cursos oficialmente inscritos, en el caso de que hayan diferencias, son reparables en el módulo de asignación.

### Módulo de Asignación

Este módulo aborda el proceso de asignación de salas o laboratorios a los cursos inscritos oficialmente.
Los eventos importantes son enviados como notificaciones mediante correo electrónico, estos eventos pueden ser cambios de salas, horarios u otros.

### Módulo de Consulta

Este módulo permite a los usuarios consultar las asignaciones realizadas, permitiendo filtrar por sus intereses, como los cursos que tiene en el periodo académico actual, asignaciones en una sede o en un día en particular.

## Objetivos

### General

Diseñar e implementar un sistema de administración de horarios de salas y laboratorios para la Universidad Tecnológica Metropolitana.

### Específicos

* Formalizar y sistematizar el proceso de administración de salas y laboratorios.
* Construir un sistema que provea integración con otros sistemas o herramientas.
* Utilizar las herramientas demandadas por el mercado en la construcción de sistemas para una institución que se vincula directamente con él.


## Metodología

El diseño arquitectónico de este proyecto contempla una toma de requerimientos, realizada en forma presencial con los principales involucrados en los procesos actuales de asignación de salas y laboratorios.
La toma de requerimientos da paso a la confección del diseño arquitectónico del sistema y el plan de actividades de desarrollo, el que será distribuido en hitos semanales.
El desarrollo y codificación del proyecto se realizará bajo la metodología _PSP_ (Personal Software Process).
El plan de actividades contempla diversas tareas, las que cuentan con una estimación de tiempo inicial, permitiendo saber a priori el costo del proyecto y en cuanto tiempo será completado.
A su vez el plan de actividades posee revisiones por los _Stakeholders_ (Principales interesados y afectados por el desarrollo de este proyecto).


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
* Servidor con Ubuntu 16.04 server de 64 bits, capaz de ejecutar el motor de base de datos referenciado anteriormente y un contenedor a aplicaciones Java web.

El licenciamiento de los recursos de software utilizados es de carácter libre.


## Resultados esperados

Se espera que este proyecto permita tener una visión más completa sobre el uso real de salas y laboratorios, mejorando así la asignación de este recurso y ayudando en la toma de decisiones de la institución.
Adicionalmente se espera que la entrega de un _API_ abra la puerta a desarrollos de nuevas plataformas para la institución, y que estas puedan interactuar entre si.
