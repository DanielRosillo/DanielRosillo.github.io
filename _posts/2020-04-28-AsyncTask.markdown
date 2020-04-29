---
layout:     post
title:      "AsyncTask fue desechada... ¿y ahora qué?"
date:       2020-04-28 00:17:40
author:     "Daniel Rosillo"
header-img: "img/girls.jpg"
description: AsyncTask paso a ser una API obsoleta dentro del universo Android 10(API 29), este cambio es inmediato y se ve reflejado al actualizar el targetSdkVersion al nivel 29 en cualquier aplicación.
categories: Quick
image: /img/girls.jpg

---
<div style="text-align: justify;">
<br>
<p>Con bastantes años en servicio y algunos millones de crashes AsyncTask paso a ser una API obsoleta dentro del universo Android 10(API 29), este cambio es inmediato y se ve reflejado al actualizar el targetSdkVersion al nivel 29 en cualquier aplicación. 

<p>Esto se debe a la estandarización de procesos que Google ha estado implementando a varios niveles del sistema Android, dichos cambios que empezaron en Android 8(API 26) hoy se van consolidando y a su paso se llevan viejas costumbres y sus maneras de operar. 

<p>Las siguientes son alternativas funcionales que sustituyen en su totalidad las AsyncTaks y siguen siendo soportadas en Android 10. 
<br>
<br>
<h1>OPCIONES NATIVAS</h1>
<br>
<h2>Futures</h2>


<p>Fraternalmente Daniel Rosillo;
-Manager on Rosillo Labs;