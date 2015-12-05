# Descripción del problema

## Problema detectado

<!-- Llename! -->

<!--
La asignación de recursos debe permitir saltearse los horarios definidos en el sistema académico oficial (Dirdoc), debido a los cambios extraprogramáticos acordados entre los estudiantes y el docente. # Se permiten malas prácticas académicas (En serio??), pero asi es la realidad...
-->

## Alternativas de solución

En este apartado se presentan soluciones al problema descrito.

### Adquirir una solución envasada

Las soluciones presentes en el mercado ofrecen las siguientes características:

* Eliminar el problema de reservar más de una vez una sala en un mismo tramo horario.
* Controlar los recursos disponibles, poniendo a disposición del staff los patrones de uso de cada recurso, es decir, quien, cuando y dónde estan siendo utilizados.
* Permitir integración con otros sistemas y _ERP_.

Las soluciones de este tipo evaluadas fueron:

* _U-Booking_ (De _U-Planner_)
* _EMS Campus_ (De _Deans Evans & Associates_).

#### U-Booking

_U-Booking_ es uno de los productos de _U-Planner_ en que se aplica ingeniería a la educación, su función principal es la reserva y publicación de salas.


#### Event Management System (EMS) Campus

Este software, es la respuesta de _Deans Evans & Associates_ para el manejo de salas/oficinas en la industria académica. El siguiente listado muestra las características importantes en el producto:

* Interfaz de uso principalmente web, permitiendo que el proceso de planificación sea online y sin rastros de papel.
* Planificación de cursos, exámenes y eventos extraprogramáticos, de forma recurrente o para un día/días en particular.
* Integración (bidireccional) con sistemas _SIS_ o _ERP_.
* Reportes que incluyen datos como el uso de asientos, disponibilidad por periodos horarios, tendencias de uso y otros.
* Integración del sistema al proceso utilizado en la institución, incluyendo granularidad en el manejo de permisos y perfiles.
* Baja necesidad de mantención por parte del departamento de _TI_.
* Realización de simulaciones para buscar un ajuste "óptimo".
* Registro auditable de transacciones (Reservas y demases eventos gatillados en el uso del software).

Este software ofrece integración con sistemas de _Digital Signage_, permitiendo a los integrantes de la institución visualizar mediante pantallas informativas la información sobre asignación de salas y laboratorios.

### Diseño e implementación de un sistema "in-house"

El diseño desde cero de un sistema permite evitar las complicaciones encontradas al adoptar una solución envasada, sobre todo si esta no tiene la flexibilidad suficiente para adaptarse a los variados requerimientos presentados en distintas instituciones.

Un sistema construido desde cero debe proveer funcionalidades acordes al estado de adopción tecnológica de la sociedad, sociedad en que el uso de _smartphones_ asciende cada vez más [@Heggestuen2013]. Las características que incluya este sistema no solo deben ceñirse al tipo de tecnología de moda, más bien debe aprovecharse de estas tecnologías para facilitar la calidad de vida de los usuarios, aterrizando este punto al presente trabajo, es entregar una gran experiencia en _UX_ (User Experience).
