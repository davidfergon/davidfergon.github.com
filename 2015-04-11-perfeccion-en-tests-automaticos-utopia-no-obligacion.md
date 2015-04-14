---
layout: post
tagline: 
title: Perfección en tests ¿utopía?. No, obligación.
tags : [Continuous Delivery, QA, Quality Assurance, Aseguramiento de la calidad, test, prueba, cucumber, jenkins]
comments : true
language : es
date: "2015-04-11"
english_url: "2015-04-11-perfect-tests-utopia-no-obligation.html"
---
{% include JB/setup %}

Toda compañia que genera un producto software, debería de dedicar sus esfuerzos a tener un sistema de [Continuous Delivery](http://en.wikipedia.org/wiki/Continuous_delivery) los más depurado posible. Para ello es clave una palabra: `automatización`...pero dejaremos el tema de la automatización para otro momento, hoy voy a centrarme en la responsabilidad que tiene el departamento de QA y su deber de ser exigentes con los resultados de sus tests automáticos. Partamos de un par de premisas para un ejemplo más concreto:

* El uso de [Cucumber](https://cukes.info/) para la definición/ejecución de pruebas automáticas.
* La utilización de [Jenkins](https://jenkins-ci.org/) y del plugin [Publish pretty cucumber-jvm reports on Jenkins](https://github.com/masterthought/jenkins-cucumber-jvm-reports-plugin-java).

Comenzamos...

### Nacimiento del equipo de QA

En el origen de un equipo de QA, el número de tests automatizados es cero, por lo tanto las pruebas que realiza dicho equipo se llevan a cabo de forma manual lo que implica un gasto de tiempo (y por tanto de dinero) considerable.

### Primeros tests automatizados

Después de un cierto tiempo (si se está utilizando Scrum, lo más probable es que dicho tiempo sea un sprint) se dispondrán de los primeros tests automatizados. Dichos tests se lanzarán automáticamente tras la generación de la versión X.Y.Z del producto software.

En este caso y por claridad con las cuentas vamos a suponer que se lanzan 10 tests automáticos y el resultado obtenido es que no falla ninguno. ¡Perfecto!

Ejemplo de informe sin errores: 

<p align="center">
<img src="../images/cucumber_no_error.jpg" title="Report without errors" width="600" height="450">
</p>

### Automatizando que es gerundio
 
El tiempo pasa y el equipo de QA ya ofrece 100 tests automáticos. Se genera ahora la versión X.Y.(Z+n) y al correr la batería de pruebas el resutlado es que un 10% de los tests fallan (10 tests de 90).

Ante esta situación se analizan los tests y pueden ocurrir diferentes cosas:

1. El test está mal diseñado o implementado, hay un `bug` en el test. **ACCIÓN** --> crear un bug (Jira, Bugzilla, Mantis, etc.) y corregirlo lo antes posible. 
2. El test está correcto, el software tiene un `bug`. **ACCIÓN** --> crear un bug (Jira, Bugzilla, Mantis, etc.) y corregirlo lo antes posible. 
3. El test carece de sentido porque la funcionalidad que cubría ha desaparecido. **ACCIÓN** --> Eliminar el test 
4. El test está correcto, pero en el entorno donde se están llevando a cabo las pruebas tiene problemas de rendimiento, de comunicaciones...o los valores de timeouts son los correctos para producción pero son demasiado exigentes para el entorno del laboratorio, o de desarrollo.

Ejemplo de un informe con errores:

<p align="center">
<img src="../images/cucumber_errores.jpg" title="Report without errors" width="600" height="550">
</p>


Este cuarto punto es ante el que hay que tener cuidado porque, si no se actúa de ninguna manera, podría llevarnos a una situación indeseable que es obtener el sello de certificación de QA sin un 100% de los tests pasados. Esto es peligroso porque si reiteradas veces se dan por buenas las ejecuciones de los tests con un 10% de errores, podría llevarnos a la falsa sensación que con un 90% de tests aceptados el software a probar es correcto, y esta tendencia prolongada en el tiempo es inadmisible, porque unos cuantos meses después...

La automatización de tests crece a pasos agigantados dentro del equipo de QA y disponemos ahora de 10.000 tests automatizados. Pero como hemos ido relajando las exigencias de los tests se siguen asumiendo que un 10% de erores es válido...¡¡y esto supone que hay 1000 tests que fallan!!.

Por eso, ante la situación del punto 4, creo necesario que exista alguna acción al respecto. Apunto algunas opciones a continuación:

* El test desaparece, porque no puede asegurarse que su resultado sea concluyente.
* El test desaparece para el entorno X. Se decide que en ese entorno el test no puede ser ejecuado con el nivel mínimo de garantías.
* El test se modifica para adecuarse al entorno X. Habría que adecuar la configuración de parámetros a cada entorno. Para deducir dichos valores podrían hacerse uso de benchmarks en los diferentes entornos que nos indiquen relaciones del tipo: "La base de datos del entorno A responde 3 veces más rápido que la del entorno B".
* Se modifica el entorno (más CPU's, más memoria, mejoras en las comunicaciones, cambios en la base de datos, etc.) de tal modo que el test cumpla su objetivo.

De este modo QA sólo certificaría cuando sus tests se cumplan al 100%, no habría dudas ni consideraciones excepcionales que pueden ser peligrosas y llevarnos a una falsa sensación de estabilidad ante la presencia de fallos.

Por eso considero que **la búsqueda de la perfección en pruebas (obtener un 100% de resultados correctos) no debe de ser algo utópico, sino una obligación**, no sólo por parte del equipo de QA en sus tests, sino también por parte de cualquier programador en sus tests unitarios, de integración, etc.

En este aspecto en [amplía)))](http://www.amplia.es) (donde trabajo actualmente) tenemos la suerte de contar con una [persona meticulosa al frente del QA](https://www.linkedin.com/pub/jorge-rodriguez/8/a81/2ba/es).

¿Tus tests están al 100%? ¿Se te ocurre alguna acción más válida para el punto 4? ¿Alguna situación más que provoque un test erróneo?