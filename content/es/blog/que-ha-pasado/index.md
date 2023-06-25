---
title: "¿Qué ha pasado con OpenFormula?"
description: "Entrada sobre lo sucedido tras 3 años del anuncio de OpenFormula"
lead: "Han pasado 3 años desde el anuncio de OpenFormula, sin embargo no ha habido actividad ¿qué ha pasado?"
date: 2023-06-25T02:32:00+06:00
lastmod: 2023-06-25T00:22:00+06:00
draft: false
weight: 50
images: []
contributors: ["Uri Mtz"]
---
OpenFormula nació cómo un proyecto personal sobre el cual quería poner cientos de fórmulas y mostrarlo en una página web, al anunciarlo no tenía idea de lo grande que podría ser esa simple tarea. El hacerlo con simple HTML y CSS no me permitía llegar muy lejos sin tener que hacer mucho trabajo manual (simplemente la página de conversiones requería de 1033 líneas de código HTML).

## Intentos posteriores

Tras ver las limitaciones de técnicas y de tiempo que HTML y CSS imponían abandoné el proyecto y tras un año lo reanudé esta vez el intento parecía tener mejores resultado e incluso se publicó una versión más o menos funcional, esta usaba una biblioteca de Javascript y un archivo de texto (JSON) para poder tomar las fórmulas y poblar las tablas necesarias.

Ese fue un gran progreso hacia la mejora de la página, sin embargo perdí el objetivo principal y me distraje haciendo "mejoras" innecesarias a la página. Así mismo el carecer conocimientos en Javascript hacía que el proceso tomara mucho más tiempo del necesario, por lo que perdí la pasión de nuevo.

Otros intentos se hicieron personalmente, jugando con la misma biblioteca y el estilo llegué a la conclusión de que probablemente no era el momento para hacer la aplicación y decidí centrarme en aprender las tecnologías necesarias para poder lograrlo.

Aprendí un sin fin de cosas al intentarlo y eso me ayudó a aprender otras cosas más rápido pero debido a problemas personales perdí la pasión totalmente hacia este proyecto y en general el aprender lo necesario para poder continuarlo.

## Actualidad

Después de casi 2 años de abandono decidí ponerme manos a la obra y comencé a escribir una nueva versión de OpenFormula, esta ocasión con muchas mejoras respecto a las primeras versiones.

La presencia de la IA, ChatGPT principalmente, me ayudó demasiado a aprender nuevas cosas las cuales apliqué a la versión actual. Junto con el uso de una biblioteca más avanzada para poblar las tablas logré  finalmente un resultado muy similar al que quería desde un inicio pero a pesar de haber logrado ese gran avance me di cuenta de la gran cantidad de factores que seguía sin considerar lo cual hizo que detuviera el desarrollo, para poder tomar un tiempo tomando las decisiones correctas

## Limitantes y decisiones no tomadas

La última versión de OpenFormula, cómo ya lo mencioné, me hizo darme cuenta de la gran cantidad de decisiones que hacían falta tomar para poder dar un producto de calidad.

### Interfaz de usuario y experiencia de usuario

El usar una biblioteca de CSS tiene sus bendiciones, me permitió generar una página visualmente buena y concentrarme en hacer el código que controla el resto de la aplicación. Y aunque la página en si misma no es fea, no tiene identidad propia y no habla de la aplicación en si misma, es simplemente el camino para dar mostrar fórmulas por lo que vi, es importante generar una identidad, sí, existe el logo y sus dos colores, pero no hay documentación de ello ni convenciones de estilo o siquiera una idea del cómo debería lucir una aplicación de este tipo (existen pocas apps similares y son poco llamativas). Debido a las razones anteriores habré de dedicar un tiempo en hacer diseño y buscar el mejor, darle una identidad finalmente a OpenFormula para poder luego plasmarla.

La experiencia de usuario es otro tema complejo que surgió en el momento de hacer las tablas, puedo listar algunas de las preguntas que se me ocurrieron y que a día de hoy siguen en el aire:

- ¿Cómo organizo las fórmulas?
- ¿Cómo deberían los usuarios buscarlas?
- ¿Cuál es el nombre más adecuado para una fórmula?
- ¿Debería permitir que sean copiadas?

Son sólo 4 preguntas de las muchas que surgieron durante el desarrollo de la última versión y aunque algunas fueron respondidas, sólo fue a medias y muchas quedan sin respuesta.

Luego de pensarlo, vi que es necesario un estudio de experiencia de usuario, al final del día yo ya no seré el principal usuario de la app, por lo que es importante que la aplicación sea intuitiva pero que de igual forma se quede dentro de las limitaciones técnicas.

### Limitaciones técnicas

Dejando a un lado mi desconocimiento en ciertas tecnologías, el uso de bibliotecas de terceros limita de cierta forma el cómo debería progresar la aplicación, la versión hecha en 2021 usaba una biblioteca muy sencilla y se limitaba a permitirme mostrar fórmulas, por otro lado, la versión más reciente me permite hacer uso de funciones más avanzadas pero agrega demasiado peso innecesario a la página y la hace sumamente ineficiente, dando 64 puntos en un "estudio" de eficiencia, un puntaje muy bajo para la sencillez de la página. Existen muchas otras limitaciones de las que hablaré en otro post (para tener registro), pero espero se entienda el punto.

El hacer uso de bibliotecas de tercero tiene la ventaja de disminuir el trabajo pero disminuye la rapidez de carga, aumenta el peso de la página y es más probable que aparezcan bugs que no pueda solucionar sin modificar toda una biblioteca que no sé cómo está programada, esto nos lleva al siguiente punto.

## Futuro

Si llegaste hasta aquí, espero hayas leído lo anterior, en resumen, el hacer OpenFormula está lleno de limitantes que se pueden solucionar pero que tomarían demasiado tiempo, tiempo que podría usar para desarrollar nuevas funciones o agregar nuevas fórmulas.

El futuro del proyecto a corto plazo es un tanto incierto, hace falta tomar muchas decisiones y planeación para poder seguir un camino fijo y hacer las cosas para evitar lo que pasó en un inicio, distracciones por errores no previstos, etc. Lo que dure el "futuro a corto plazo", será y está siendo usado para tomar las decisiones correctas y organizar el proyecto para hacerlo funcional lo más rápido posible.

No quiero dar fechas porque no estoy seguro del tiempo que tomará aprender las nuevas tecnologías y desarrollar mi propia implementación de una biblioteca de tablas o si quiera del diseño de la página, pero habré de decir que se están tomando las decisiones adecuadas ahora para poder lograr una aplicación de exelencia.

A largo plazo hay muchísimos planes para la aplicación, algunas ideas más sencillas que otras, pero que al final aportarán al ecosistema de OpenFormula, pero hay que recordar que antes de correr hay que caminar, por lo que las primeras nuevas versiones de la app que vean la luz sólo mostrarán fórmulas sin más.

## Ayuda

Ciertas decisiones no se pueden tomar solas, se requieren de datos y opiniones, inicialmente requiero de la ayuda de la comunidad para poder tomar decisiones en cuanto a la experiencia de usuario, preferencias de interfaz, etc.

Diseñaré alguna encuestas que luego me ayudarán a tomar lo que pienso, serán las mejores decisiones para una buena aplicación y en base a esto se podrá comenzar el diseño y la programación detrás de ello.

Otra forma de ayudar es llenando las bases de datos, pues ese es el proceso más laborioso. Estoy haciendo una aplicación en Java que debería permitir escribir las fórmulas a las bases de datos, sin embargo la publicación tampoco es un proceso automático ni sencillo para gente con nula experiencia usando GitHub, a pesar de ello podrás descargarla y usarla, escribiré una guía del cómo debe usarse y cómo puedes compartirme tus fórmulas.

## Reflexión

Tras años de haber anunciado el proyecto y no haber una versión "final", pareciera que la aplicación ya no se hará jamás, pero esto es falso. Hace falta aprender muchas tecnologías, programar y tomar muchas decisiones, lo cual toma tiempo por lo que no se espera una versión estable o final hasta dentro de mucho tiempo, lo que si puedo prometer son versiones de desarrollo y prueba en cuanto las tenga.

Estos años me han dado el tiempo para pensar mejor el cómo debería organizarse un proyecto tan grande y he aprendido mucho de OpenFormula, por lo que no abandonaré el proyecto pero avanzaré a mi ritmo. Tal vez la herramienta ya no me sirva a mi o a ninguna de las personas que esperaba ayudar, pero ayudará a las generaciones futuras a tener un software de calidad donde puedan consultar fórmulas y hacer uso de otras herramientas, todo en un solo lugar, ese fue, es y será la misión de OpenFormula.
