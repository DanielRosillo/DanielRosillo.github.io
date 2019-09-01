---
layout:     post
title:      "Android Studio para retrasados: Tema oscuro en 2 pasos"
date:       2019-09-01 00:17:40
author:     "Daniel Rosillo"
header-img: "img/high.jpg"
categories: Quick
---
<div style="text-align: justify;">
<div class='post-body entry-content'>
<br>
<p>Con este artículo se inaugura la zona Android, implementaciones rápidas, sin problemas y entendibles para nosotros los retrasados que no leemos la documentación.
Son muchas las formas de implementar el tema oscuro o de noche en una aplicación, una de estas formas nos la brinda la librería Appcompat del paquete de librerías AndroidX, que a partir de la Api28 introduce una serie de mejoras enfocadas a estandarizar su uso y relacionarlo a los ámbitos diarios.
<br>
<br />
<p>NOTA<br>
<p>Algunas funciones como la asignación de tema automático o según el consumo de batería están disponibles solo para la Api 28(Android 9).
<br>
<h1>Ingredientes</h1>
<br>
&#8226;&nbsp;&nbsp;&nbsp;	En el build.gradle de la aplicación, agregamos la dependencia a o si la tenemos la actualizamos por:
<br>

<blockquote>
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">implementation 'androidx.appcompat:appcompat:1.1.0-rc01'</span><br />
</blockquote>

<h1>Preparación</h1>
<p>Dentro de la carpeta values/styles/, encontramos los archivos de nuestro tema
<br>
&#8226;&nbsp;&nbsp;&nbsp;	Styles.xml 
&#8226;&nbsp;&nbsp;&nbsp;	Styles.xml (21)
<br>
<p>Editamos el primero, y cambiamos la herencia de nuestro tema por defecto, que es Theme.AppCompat.Light.DarkActionBar, debe quedar algo como lo siguiente:


<br>
<i>Fraternalmente Daniel Rosillo;</i>
<div style='clear: both;'></div>
