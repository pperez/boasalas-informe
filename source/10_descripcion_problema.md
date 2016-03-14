# Descripción del problema

## Problemática actual

La institución carece de un procedimiento de petición/asignación de salas y laboratorios.
Este procedimiento debiese ser de caracter transversal a los campus existentes, de forma que facilite la gestión, control y seguimiento de los problemas o victorias que emergen del uso de las salas en el transcurso del periodo académico.

El procedimiento actual es similar en los campus, diferenciandose en las unidades encargadas de la asignación de las salas bajo su responsabilidad.

### Procedimiento actual

#### Petición de cursos a departamentos

En este paso se busca asignar docentes a los cursos demandados por la institución, las unidades encargadas de realizar esta petición son las escuelas (O unidades similares, como Plan Común de Ingeniería en el Campus Macul).
La petición consiste en un documento que especifique las asignaturas y cantidad de cursos requeridos para cada una, el destinatario de la petición es el departamento calificado para dictar tales asignaturas.

#### Asignación de docentes y horarios a cursos

La petición recepcionada en el paso anterior, es analizada por el departamento, tomando en cuenta variables como la cantidad de docentes disponibles, horas destinadas a docencia por docente (Caso de los funcionarios docentes que cuentan con contrato). Este análisis produce la asignación de horarios y docentes a los cursos pedidos por las escuelas.

#### Feedback entre escuelas y departamentos

Las escuelas son las encargadas de minimizar la cantidad de topes de horarios producidos en el paso anterior, teniendo que demandar a los departamentos cambios en los horarios dispuestos.
La metodología utilizada para esta tarea escapa de los alcances del presente trabajo.

#### Petición de salas y laboratorios

La escuela, al contar con los horarios para cada curso, esta lista para realizar la petición de salas para cada uno.
Se realizan peticiones a cada unidad encargada de las salas que sean necesarias, en función a los requerimientos propios de cada asignatura (e.g es necesario un proyector, laboratorio de computación, sala con mesas de dibujo, etc).

#### Asignación de salas y laboratorios

En este paso, las unidades receptoras de las peticiones de salas realizan el procesado de estas, teniendo en cuenta las particularidades presentes en los Campus, es así como actualmente en el Campus Macul, las primeras peticiones en ser procesadas son las presentadas por el Plan Común de Ingeniería, seguidas del resto de las unidades de especialidad.
<!-- con la particularidad de poseer un orden para procesar las peticiones, justificado por la naturaleza de las unidades, es el caso del Campus Macul, donde la unidad primordial es Plan Común de Ingeniería, siendo esta la primera unidad para la que se procesan las peticiones de salas. -->

Este paso tambien puede generar conflictos en los horarios de cursos, teniendo horarios en que no se encuentran salas con las características requeridas por los cursos, produciendose así un feedback con las escuelas, para que hagan los cambios pertinentes en tales horarios.

#### Formalización de cursos

Luego de haber pasado por este flujo de trabajo, los cursos deberían estar libres o poseer muy pocos conflictos de horarios, siendo estos enviados a la _Dirección de Evaluación Académica_ para ser ofertados al estudiantado en el siguiente periodo académico.

### Problemas en el modelo actual

El proceso explicado en el punto anterior no expone las problemáticas generadas en el transcurso del periodo académico, donde la rigidez de la asignación horaria nubla la realidad vivida por estudiantes, docentes y funcionarios.

Nuestra institución requiere que algunos de sus integrantes desempeñen diversas tareas administrativas que afectan la programación académica, generandose así cambios de horarios de caracter informal, cambios que no son registrados en la programación oficial. Al manejarse de esta forma los cambios horarios, se pierde una oportunidad de mejora tanto para las escuelas, docentes y administrativos.

La principal oportunidad de mejora, tanto para el proceso en si, como para la visualización de este, es la implementación de un sistema que modele la realidad, exponiendola a los actores críticos. Este sistema debe permitir que tanto los estudiantes, docentes y diversos funcionarios puedan visualizar la programación académica de la institución, tanto como manejarla.


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
