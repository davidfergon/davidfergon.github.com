---
layout: post
tagline: 
title: 'De la nada al "Todo Continuo" y del Scrum más canónico al Kanban con #NoEstimates'
tags : [Integración Continua, Continuous Integration, Despliegue Continuo, Continuous Deployment, Entrega Continua, Continuous Delivery, Scrum, Kanban]
comments : true
language : es
date: "2015-06-16"
english_url: "2015-06-16-from-nothing-to-continuous-everything-from-scrum-to-kanban-with-noestimates.html"
---
{% include JB/setup %}

`Integración Continua`, `Entrega Continua`, `Despliegue Continuo`... ¡Todo Continuo!

**Un sumun de la agilidad podría ser el siguiente: minimizar lo máximo posible el tiempo entre el nacimiento de una tarea, por ejemplo desarrollar una nueva funcionalidad X, y la disponibilidad de la funcionalidad X en un entorno productivo.**

Pero para llegar a ese punto es importante haber recorrido un camino que nos lleve de una forma no forzada a esa situación. **Como analogía podemos pensar en [la importancia que tiene gatear](http://www.bebesymas.com/salud-infantil/gatear-es-muy-importante-8-razones-de-peso) antes de caminar**. El gateo no es imprescindible, pero sí muy recomendable porque sirve para afianzar muchas cosas en el desarrollo del bebé. Del mismo modo, **si queremos disponer de un equipo ágil para nuestro desarrollo de producto, conviene empezar por metas menos ambiciosas**. Cambiar la forma de trabajar implica un tiempo de adaptación ya que todos somos [reticentes a los cambios](http://www.cronista.com/management/-El-cerebro-es-reticente-al-cambio-20131226-0013.html).

Creo que lo mejor es que me apoye en un ejemplo para desarrollar mi explicación de como se puede evolucionar, de la forma más natural y fluida posible, desde el `Scrum` más canónico a un modo de desarrollo lo más agil posible usando Kanban, dándole cabida al movimiento `#NoEstimates` y obtener así lo que podemos denominar `Todo Continuo`:

### 1. Origen

Estamos desarrollando nuestro producto software pero queremos hacerlo de un modo ágil, ir creando el mínimo producto viable y nos decidimos por usar `Scrum`.

No olvidemos que estamos incorporando en nuestra empresa una metodología ágil, es un cambio de mentalidad que todos los activos de la empresa deben interiorizar por lo que lo más conveniente es ceñirse al corsé del `Scrum` lo máximo posible: Realizar todas las reuniones, estimar, ser estrictos con los tiempos de los `sprints`, etc. 

Hay mucha literatura acerca de `Scrum`, por eso no voy a entrar en detalle, así que sólo apunto alguna pincelada:

* El dueño del producto (`product owner`) mantiene el `product backlog`, un listado con las historias de usuario ordenadas por prioridad.
* Marcamos un periodo de tiempo, denominado `sprint`, para el desarrollo de nuevas funcionalidades (para empezar con una cifra habitual decimos que los sprints serán de 4 semanas).
* Al inicio de ese periodo se identifican las tareas que se pueden llevar a cabo en ese tiempo (`sprint backlog`) y el equipo de desarrollo estima el tiempo necesario para llevarlas a cabo.
* Tras cada iteración tendremos un incremento del producto, un producto usable aunque sea parcialmente.
* Las pocas o muchas funcionalidades desarrolladas han de estar plenamente operativas dándole valor al producto.
* Las funcionalidades que no se completen no se tendrán en consideración.

Este esquema puede ayudar a hacernos una mejor idea de la metodología `Scrum`:

<p align="center">
<img src="../images/scrum_diagram.gif" title="Diagrama de la metodología Scrum">
</p>

[Fuente de la imagen](http://braintrustgroup.com/product/scrum-process-poster-24-x-36/)

Bueno, el caso es que pasan algunos `sprints` (peridos de desarrollo) y ya nos sentimos "ágiles", entre un sprint y otro el `Product Owner` puede corregir el rumbo que lleva el producto si el resultado obtenido no le convence.

Además el equipo de desarrollo dispone de alguna herramientas para el desarrollo como un sistema de control de versiones (p.e. `git`).

Pero el número de líneas de código crece y técnicamente queremos ir más allá...

### Integración Continua (Continuous Integration)

> (wikipedia) "consiste en hacer integraciones automáticas de un proyecto lo más a menudo posible para así poder detectar fallos cuanto antes. Entendemos por integración la compilación y ejecución de pruebas de todo un proyecto."

Decidimos ahora incorporar una aplicación del estilo a: `Bamboo`, `Cruise Control`, `Jenkins`...con el fin de disponer de una `Integración Continua`.

Gracias a estas herramientas cualquier subida de código a nuestro control de versiones dispara automáticamente la compilación del código afectado, además nos ayuda a la ejecución y validación de tests.

<p align="center">
<img src="../images/integracion_continua.gif" title="Integración Continua">
</p>

Perfecto, somos más ágiles para detectar problemas en las compilaciones, en las dependencias entre componentes, encontrar bugs, etc.

Pero aprovechando que disponemos de `Jenkins` (por especificar una aplicación concreta) seguimos queriendo ir más allá...

### Entrega Continua (Continuous Delivery)

> (wikipedia) "es un enfoque de ingeniería de software en el que los equipos mantienen la producción de software en ciclos cortos y se asegura de que el software puede liberarse de forma fiable en cualquier momento."

No nos conformamos con que los tests unitarios se ejecuten de manera automática. Ahora queremos probar que nuestro producto:

* Se despliega correctamente.
* Los tests funcionales y de integración que certifican la calidad de la plataforma se pasan correctamente.
* Si los dos puntos anteriores se verifican, entonces disponemos de una versión de nuestro producto susceptible de ser desplegada en producción.

<p align="center">
<img src="../images/entrega_continua.gif" title="Engrega Continua">
</p>

Pero seguimos queriendo más y pensamos en ir aún más allá...

### Despliegue Continuo (Continuous Deployment)

Podemos considerar que el `Despliegue Continuo` es una extensión de la `Entrega Continua`.

El `Despliegue Continuo` nos lleva a un paso más allá de la `Entrega Continua`: Cada cambio que supera de manera exitosa las pruebas automáticas podemos desplegarlo de forma automática en producción.

<p align="center">
<img src="../images/despliegue_continuo.gif" title="Despliegue Continuo">
</p>

Parece que técnicamente lo tenemos todo automatizado, pero ahora podemos ir un poco más allá en la gestión...

### Todo Continuo (Continous Everything)

Pues bien, ahora tras la finalización de cada sprint (4 semanas) realizamos de forma automatizada todo el proceso...pero ¿por qué esperar cuando ya tenemos todos los pasos automatizados?

Llegados a este punto, podemos plantearnos dejar atrás `Scrum`, nos ha ayudado a ser disciplinados y a que toda la empresa esté concienciada de una filosofía ágil. Podemos reducir el tiempo del `Sprint` en un primer paso hasta que decidamos prescindir del uso de `Scrum` porque ahora, tal vez **ha llegado la hora de caminar ¡e incluso de correr! (`Kanban` + `#NoEstimates`) y podemos dejar atrás el gateo (`Scrum`).**

Tecnológicamente estamos tan avanzados que un cambio en el código puede verse, siempre que haya pasado satisfactoriamente por todas las etapas, en producción con mucha celeridad.

Los clientes tendrán rápidamente las correcciones de bugs, las nuevas funcionalidades, las mejoras... disponibles en el entorno de producción. 

Pero para esto hay que ser conscientes que el producto ha de estar muy maduro, el equipo debe de estar perfectamente coordinado y entrenado, y ha de pasar bastante tiempo para llegar a este punto de funcionamiento donde se puede gestionar todo utilizando un tablero `Kanban`, y [teniendo en cuenta 4 cosas](http://www.scrummanager.net/blog/2013/09/kanban-las-4-cosas/), en el que las tareas se encolan por prioridad y cada miembro del equipo va tomando la tarea más prioritaria cuando haya terminado su tarea anterior.

Llegados a este punto tiene cabida el movimiento `#NoEstimates` (En otra entrada tal vez le dedique más tiempo al [movimiento `#NoEstimates`](http://www.javiergarzas.com/2014/11/tiene-realmente-sentido-estimar-y-si-deberiamos-estimar-el-software-el-movimiento-noestimates.html), pero esa será otra guerra ya que hay muchos matices, algunos que comparto y otros que no). Porque llegados a este punto ¿para qué estimar? las tareas se irán realizando lo antes posible según su prioridad y según se terminen se tendrán ya disponibles en producción de forma automática. Incluso se puede realizar varios despliegues en producción al día.

Quiero incidir en que este proceso llevará varios meses, años...no es algo que sea inmediato, hay que ir paso a paso, automatizando lo máximo posible las tareas y adaptando el tipo de gestión a la situación en la que te encuentras en cada momento.

¿Y tú qué opinas? ¿Consideras que el Todo Continuo es interesante? ¿Qué grado de automatización tiene tu organización?

