---
layout: post
tagline: 
title: Product Owner, el Spiderman del Scrum.
tags : [Product owner, Propietario del producto, Product Backlog, Historia de usuario, User History, Scrum, Agile]
comments : true
language : es
date: "2015-04-27"
english_url: "2015-04-27-product-owner-scrums-spiderman.html"
---
{% include JB/setup %}

Existen dos tendencias principales en los tipos de `Product Owner`: 

1. El caso más canónico, existe un cliente que adquiere el rol de `Product Owner`. Y teniendo en cuenta que ese cliente puede ser de tu empresa o de otra.
2. Y en los que una persona (la mayoría de casos que conozco suele ser un Jefe de proyecto) con trato directo con el cliente, recopila las necesidades y toma el rol de product owner de cara al `Equipo` de desarrollo.

Si estuviéramos en el `Mundo Utopía` y tuviéramos que escribir una carta a Papá Noel o a los Reyes Magos de Oriente para pedir el `Product Owner` de manual (el mencionado en el primer caso), podríamos tener algo así:

    Queridos Reyes Magos:

    Quiero un Product Owner para el producto sofware que mi empresa está desarrollando, pero no uno del montón.

    Quiero que mi product owner sea una persona que tenga una visión muy clara del producto que se desea desarrollar. Además ha de disponer del tiempo suficiente para dedicarse a una serie de menesteres tales como: 

    - Definir la visión del producto.
    - Transmitir de forma clara esa visión al equipo de negocio.
    - Transmitir de forma clara esa visión al equipo de desarrollo.
    - Marcar el Roadmap del producto.
    - Definir el Product Backlog, redactando y priorizando: Epics, Historias de usuario...
    - Facilitar las historias de usuario para el Sprint actual y para al menos el siguiente periodo.
    - Mantener el Product Backlog, modificando, re-priorizando, re-redactando, etc.
    - Tiene que definir los criterios de aceptación.
    - Ha de participar en la reunión de Sprint Planning.
    - Mantener relación con los Stakeholders.
    - Colaborar codo con codo con el Scrum Master.
    - bla, bla, bla

Y claro, tras esta enumeración vemos que ser `Product Owner` es disponer de mucho poder, y ya se sabe que:

> Un gran poder conlleva una gran responsabilidad. (Ben Parker, el tío Ben, vamos el tío de Spiderman)

<p align="center">
<img src="../images/spiderman.jpg" title="Portada de The Amazing Spider-Man vol. 2 #50">
</p>
[Fuente de la imagen de Spiderman](http://en.wikipedia.org/wiki/Spider-Man)

Soy consciente de que no es sencillo disponer de un `Product Owner` con todas las características de las que estamos hablando, incluso hay momentos en los que es imposible. Pero lo que sí podemos esperar de nuestro `Product Owner`, que no es ningún superhéroe, es que disponga de unas mínimas características (aptitudes y actitudes) para tratar de llevar a buen puerto el producto en un `Mundo Real` no en el `Mundo Utopía`:

* Debe de tener los conocimientos necesarios, estar cualificado para el puesto y disponer del tiempo necesario para atender a las labores del mismo.
* Mantener el `Product Backlog` con, al menos, las historias necesarias para el próximo `Sprint`.
* Definir claramente las `historias de usuario` (más adelante éscribiré una entrada especial para este tema), para ello algunos puntos importantes son:
    + Recuerda: _"Como \_\_ quiero \_\_ para \_\_"_
    + Ponerle cariño a la redacción, esmerarse en no dejar ambigüedades y dejar finalmente textos concisos.
    + Describir **qué se desea, no cómo se desea**. El qué es territorio y responsabilidad del `Product Owner`, pero el cómo debe ser el `Equipo` el encargado de llevarlo a cabo (Es cierto que no todo es blanco y negro y existe el gris. Hay veces en las que es inevitable marcar parte del cómo. Por ejemplo la obligación del uso de software sin coste de licencia o al revés, la obligación de uso de un producto concreto por imposición contractual de la compañía).
    + Definir los criterios de aceptación para que dicha historia se dé por válida. Este punto es importante a la hora de desarrollar tests y donde estaría un punto de entrada de tareas para el posible equipo de `QA`.
* Delegar y confiar en el `Equipo`, no agobiar en exceso y saber esperar al final del `Sprint` para ver los resultados.
* Evitar o al menos minimizar la incorporación de nuevas historias dentro del `Sprint` actual. Como no estamos en el `Mundo Utopía` sabemos que existen urgencias, apariciones de bugs, etc. pero debería de identificarse tanto la urgencia como la importancia y obrar en consecuencia, para ello siempre es útil recordar esta matriz:

<p align="center">
<img src="../images/urgente_importante_matriz.svg" title="Matriz urgente importante" width="600" height="450">
</p>

* Y sobretodo no dejarse corromper por la posición de poder y verse invadido por el [complejo de dios](http://es.wikipedia.org/wiki/Complejo_de_dios). Es imposible tener todas las respuestas y todos los conocimientos, hay que saber compartir dudas, pedir consejo y escuchar a los demás.

Siempre se habla del `Scrum Master` como un líder servicial, pero también el `Product Owner` debe de tener ese espíritu. El `Equipo` está ahí para darle lo que desea, para complacer sus necesidades, por lo que debe de colaborar abiertamente con ellos dándoles todas las facilidades posibles. **Entre el `Equipo` y el `Product Owner` debe haber ante todo confianza mutua**, sin esto es muy complicado logarar el éxito.

Los `Product Owners` que conoces ¿tienen al día el `Product Backlog`? ¿La redacción de `Historias de Usuario` es su fuerte? ¿Existe confianza mutua entre el `Equipo` y el `Product Owner`?




