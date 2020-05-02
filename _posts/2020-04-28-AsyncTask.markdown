---
layout:     post
title:      "AsyncTask fue desechada... ¿y ahora qué?"
date:       2020-04-28 00:17:40
author:     "Daniel Rosillo"
header-img: "img/girls.jpg"
description: AsyncTask paso a ser una API obsoleta dentro del universo Android 10(API 29), este cambio es inmediato y se ve reflejado al actualizar el targetSdkVersion al nivel 29.
categories: Quick
image: /img/girls.jpg

---
<div style="text-align: justify;">
<br>
<p>Con bastantes años en servicio y varios millones de crashes la API AsyncTask, para realizar llamadas asíncronas, paso a ser una API depreciada dentro del universo Android 11 (API R), este cambio se vuelve notorio incluso al actualizar el targetSdkVersion al nivel 29 (Android 10), en donde ya no marca dicha librería como sin soporte. 

<p>En las últimas versiones se ha visto un aumento de APIS desechadas, esto se debe a la estandarización de procesos que Google ha estado implementando a varios niveles del sistema Android, dichos cambios que empezaron en Android 8 (API 26) hoy se van consolidando y a su paso se llevan viejas costumbres y sus maneras de operar. 

<p>Las siguientes son alternativas funcionales que sustituyen en su totalidad las AsyncTaks y siguen siendo soportadas en Android 10. 
<br>
<br>
<h1>OPCIONES NATIVAS</h1>
<br>
<h2>Futures</h2>

<P>En primer lugar, Google recomienda usar los Futures para los que Java cuenta con soporte desde su versión 5, una a API bastante sutil y funcional que se encuentra nativamente en todas las versiones de Android.

<P>La única desventaja por decirlo así es que sigue un esquema de declaración clásico por lo que puede resultar poco intuitivo.
<br>
<p>Su sintaxis es la siguiente: 
<br>
<a href="https://ibb.co/TwV9H6Q"><img src="https://i.ibb.co/TwV9H6Q/Screenshot-from-2020-04-28-23-30-56.png" alt="Screenshot-from-2020-04-28-23-30-56" border="0"></a>
<br>
<a href="
https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/Future.html">Documentacón</a>
<br>
<br>

<h2>Completable Futures</h2> 

<p>Introducidos en Java 8 como una evolución natural de los Futures clásicos, para poder utilizarlos se deberá habilitar el soporte de Java 8 en Android, su sintaxis funcional la pone a la vanguardia respecto a tendencias similares en otros lenguajes. A diferencia de los Futures es posible complementar su funcionamiento concatenando operaciones mediante funciones anónimas.

<br>
<p>Su sintaxis es la siguiente: 
<br>
<a href="https://ibb.co/PjmCvQM"><img src="https://i.ibb.co/PjmCvQM/Screenshot-from-2020-04-28-23-41-26.png" alt="Screenshot-from-2020-04-28-23-41-26" border="0"></a>
<br>
<a href="https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CompletableFuture.html">Documentacón</a>
 <br>
<br>
<h1>OPCIONES NO NATIVAS<h1> 

<h2>RxJava<h2> 

<p>La librería por excelencia para tareas asíncronas, sin duda una gran opción, aunque nos obliga a mantener una compatibilidad extra al ser una librería agregada.
<br>
<a href="https://ibb.co/zGfKLMg"><img src="https://i.ibb.co/zGfKLMg/rxjava.png" alt="rxjava" border="0"></a>
<br>
<a href="https://github.com/ReactiveX/RxJava ">Link con la guía de implementación</a>
<br>
<br>
<p>Fraternalmente Daniel Rosillo;<br>
-Manager on Rosillo Labs;