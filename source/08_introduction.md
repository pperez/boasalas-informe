# Presentación del proyecto

## Descripción del proyecto

Este proyecto presenta el diseño y construcción de un nuevo servicio para los integrantes de nuestra casa de estudios, que permita de forma sencilla la asignación y consulta del uso de salas de clases y  laboratorios en los distintos campus de la universidad.
Se pueden distinguir 3 módulos principales en la construcción de este servicio:

* Backoffice: Módulo que permite a los encargados de los espacios (Salas, laboratorios y otros) realizar asignaciones en función a los periodos y cursos establecidos por la institución.

* Presentación: Módulo que permite consultar las asignaciones de recursos, especificando parámetros de consulta, tales como horarios en un bloque determinado en cada campus, horario de clases de un docente en especial y horarios particulares para el estudiante que realize la consulta.
Este módulo estará construido de tal forma de ser integrable con la mayor cantidad posible de dispositivos, tomando en cuenta los avances actuales sobre televisores y teléfonos inteligentes (Smart TVs y SmartPhones respectivamente), y básicamente cualquier dispositivo que cuente con acceso a Internet y posea un kit de desarrollo de software.

* Actualizador de datos: Este módulo es el encargado de actualizar la información curricular de la institución (Volcandola en los registros locales del sistema propuesto), permitiendo así a los encargados tener información actualizada desde una fuente de datos oficial de la universidad;  este módulo elimina la necesidad de que las escuelas o departamentos asociados tengan que enviar tal información a los encargados de los recursos.

El diseño arquitectónico de este servicio permitirá la integración con las plataformas desarrolladas por estudiantes y funcionarios de la institución, dando un puntapie inicial a una posible consolidación e interacción de los sistemas de TI que posee actualmente la institución e incluso con aquellos que serán desarrollados a futuro.


## Objetivos

### General

Poner a disposición de la institución un sistema de manejo de salas y laboratorios de campus con visión a posibles integraciones futuras a otros sistemas o herramientas de TI.

### Específicos

* Formalizar y sistematizar el proceso de administración de salas y laboratorios.
* Construir un sistema que posea puntos de integración con otros sistemas o herramientas.
* Utilizar las herramientas que demanda el mercado en la construcción de sistemas para una institución que se vincula directamente con este.

## Metodología

El diseño arquitectónico de este proyecto contempla una toma de requerimientos, realizada en forma presencial con los principales involucrados por los procesos actuales de asignación de salas y laboratorios.
La toma de requerimientos da paso a la confección del diseño arquitectónico del sistema y el plan de actividades de desarrollo, el que será distribuido en hitos semanales y desarrollado por un equipo de trabajo compuesto de una persona.
El plan de actividades se compone de muchas tareas, las que cuentan con una estimación inicial, permitiendo saber a priori el costo del proyecto y en cuanto tiempo será completado. A su vez el plan de actividades posee revisiones por los Stakeholders (Principales interesados y afectados por el desarrollo de este proyecto).


## Alcances

* El proyecto opera de forma online, por lo que se requiere de un dispositivo con acceso a internet y un navegador web.
* El proyecto utiliza como fuente de datos la planificación académica provista por la Dirección de Docencia de la institución, permitiendo eliminar duplicidad de la información.


## Limitaciones

* El sistema recopila información académica, sin embargo no es una réplica de las funcionalidades existentes en otras plataformas institucionales (Dígase Dirdoc, Reko, Mi UTEM y otros), en vez de duplicar información (Como es el caso de Dirdoc y Mi UTEM) se busca que el sistema sea integrable con otras fuentes de datos.
* Si bien el sistema es accesible desde dispositivos móviles como smartphones o tablets, no se asegura una experiencia de usuario rica como en plataformas desktop.


## Recursos

A groso modo, se contempla el uso de los siguientes componentes:

* Motor de base de datos PostgreSQL
* Framework Java Spring y librerías 3rd party asociadas.
* Servidor con Ubuntu 14.04 server de 64 bits, capaz de ejecutar el motor de base de datos referenciado anteriormente y un contenedor a aplicaciones Java web (De preferencia Tomcat).

El licenciamiento de los recursos de software utilizados es de carácter libre.


## Resultados esperados

Se espera que la construcción de un proyecto con puntos de integración abiertos permita la interacción entre plataformas utilizadas en la institución, reduciendo de forma drástica los tiempos requeridos por procesos realizados de forma manual. A su vez el diseño pensado en la integración de otros sistemas permite a los integrantes de la institución el desarrollo de plataformas que exploten los datos recabados por el sistema, pudiendo generar innovación y proyecciones que ayuden en la toma de decisiones institucionales.
