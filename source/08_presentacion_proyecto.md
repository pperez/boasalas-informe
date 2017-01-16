# Presentación del proyecto

## Descripción del proyecto

Este proyecto aborda el diseño e implementación de una plataforma en línea que permita la asignación de salas y laboratorios en un campus universitario, puntualmente en la Universidad Tecnológica Metropolitana.

La plataforma tiene contemplados los procesos internos de esta institución, entre ellos la preinscripción de cursos (Procedimiento previo a la inscripción formal de cursos que vela por evitar inconsistencias al asignar salas y laboratorios) y asignación final de salas a cursos.

El acceso visible a esta plataforma permite visualización de las asignaciones en cada campus, salas y laboratorios en un horario seleccionado.

## Objetivos

### General

Diseñar e implementar un sistema de administración de horarios de salas y laboratorios para la Universidad Tecnológica Metropolitana.

### Específicos

* Formalizar y sistematizar los procesos de asignación de salas y laboratorios.
* Construir una plataforma extensible y de carácter abierto que permita la integración de aplicaciones móviles u otros sistemas de gestión.
* Construir la plataforma utilizando tecnologías enterprise de carácter abierto.

## Metodología

El abordaje de este proyecto consiste inicialmente en recopilar los requerimientos de más alto nivel con los sujetos que manipularán y consumirán datos de la plataforma, esta recopilación se realiza de forma presencial y se enfoca en la formalización de los procesos que actualmente se llevan en la institución.
La fase de toma de requerimientos da paso a la confección de un modelo, validado en conjunto con los interesados por la plataforma.
Con un modelo formado es posible formalizar los requerimientos, de esta forma se pueden planificar las iteraciones semanales, las que al concluir entregarán funcionalidades a los usuarios
Al concluir la codificación de los requerimientos se revisa la plataforma con los interesados en el proyecto, agregando los errores como tareas para la próxima iteración; esto se repite hasta que los interesados del proyecto estén conformes con el funcionamiento de la plataforma.


## Alcances

* La plataforma operará en línea, requiriendo un dispositivo con acceso a internet y un navegador web.
* La plataforma se alimentará de los datos estadísticos existentes en _SEPA_, estos son una réplica de los datos manejados por _Dirección de Docencia_.
* La plataforma se aboca a los procesos de asignación y uso de salas, por lo que los procesos académicos fuera de este contexto no son manejados (e.g petición de cursos a departamentos).


## Limitaciones

* Esta plataforma utiliza la planificación académica, en algunos casos se pueden encontrar datos existentes en otras plataformas institucionales, sin embargo el enfoque no es replicar funcionalidades existentes en estas, si no que convivir con ellas de una forma consistente.
* La plataforma es accesible desde dispositivos móviles, sin embargo no se entregarán aplicaciones nativas para estos, por lo que la experiencia de usuario puede no ser igual que la entregada en equipos de escritorio.


## Recursos

Se prefieren tecnologías y herramientas de carácter libre, entre ellas destacamos:

* Base de datos PostgreSQL.
* Lenguaje de programación Java, utilizando el framework _Spring_.
* Servidor físico con _Ubuntu_ 16.04 server de 64 bits.
* Servidor de contenedor web _Tomcat_.


## Resultados esperados

Se espera que la sistematización de la asignación de salas permita que este recurso de explote a plenitud al evitar errores de asignaciones y notificando a tiempo cambios en su uso.
Adicionalmente se espera que la entrega de una integración abierta abra la puerta a desarrollos de nuevas plataformas para la institución, plataformas que puedan interactuar entre si.
