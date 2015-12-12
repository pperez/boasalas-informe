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

* _EMS Campus_ (De _Deans Evans & Associates_).
* _25Live_ (De _CollegeNET_)


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

#### 25Live

25Live es el producto de _CollegeNET_ que permite la asignación de salas y laboratorios. Su modelo de negocio es un _SAAS_, lo que elimina la necesidad de instalar o mantener el software.

Las características que este software ofrece son:

* Seguimiento de disponibilidad de lugares y recursos.
* Asignación o petición de espacios para una o múltiples fechas.
* Especificación de equipo de audio/video, catering y otros recursos necesarios para cada fecha.
* Manejo granular de permisos de visualización, edición y asignación para grupos específicos.
* Publicación de eventos a calendarios online de campus mediante _25Live Publisher_.
* Impresión de reportes de confirmación.
* Registro de participantes por fecha.
* Realizar búsquedas personalizadas para eventos, ubicaciones y recursos.
* Suscripción mediante _feeds RSS_ para alimentar calendarios o correos electrónicos.
* Manejo de registro en eventos, incluyendo tickets y procesado de pagos.

Hay dos puntos que marcan una diferencia sobre soluciones similares, la primera es la naturaleza _SAAS_, esta característica puede verse como una ventaja o una desventaja, ya que el staff de la institución pierde el control de los datos existentes en el sistema. La segunda característica es la adaptación entre el _SIS_ de la institución y _25Live_; para esto, _CollegeNET_ pone a disposición de sus clientes el _API_ de Web Services de _Series25_, sin embargo esto pertenece a otro producto, lo que influye en el precio total de la solución.

![25Live Screenshot](source/figures/003_screenshot_25live.jpg)

### Diseño e implementación de un sistema "in-house"

El diseño desde cero de un sistema permite evitar las complicaciones encontradas al adoptar una solución envasada, sobre todo si esta no tiene la flexibilidad suficiente para adaptarse a los variados requerimientos presentados en distintas instituciones.

Un sistema construido desde cero debe proveer funcionalidades acordes al estado de adopción tecnológica de la sociedad, sociedad en que el uso de _smartphones_ asciende cada vez más [@Heggestuen2013]. Las características que incluya este sistema no solo deben ceñirse al tipo de tecnología de moda, más bien debe aprovecharse de estas tecnologías para facilitar la calidad de vida de los usuarios, aterrizando este punto al presente trabajo, es entregar una gran experiencia en _UX_ (User Experience).

Con estas premisas en mente, las características ofrecidas por el sistema deberian ser:

* Integración unidireccional con el _SIS_ de la institución (Dirdoc, para el caso actual).
* Exposición de un _API REST_, permitiendo el desarrollo de aplicaciones para distintas marcas y modelos de smartphones u otros dispositivos inteligentes.
* Plataforma web para administración de reservas de salas.
* Manejo de información granular con perfiles de usuarios y reglas de control de acceso (_ACL_).
* Plataforma web para visualización de reservas y horarios, para académicos, estudiantes y administrativos.
* Confección de informes de gestión y automatización del envio de estos a los distintos administrativos interesados.

En el siguiente capitulo se presenta una propuesta que cumpla las características mencionadas.
