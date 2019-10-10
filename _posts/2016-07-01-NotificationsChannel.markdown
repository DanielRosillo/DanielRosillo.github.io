---
layout:     post
title:      "Android Studio para retrasados: Implementar canales de notificaciones + Ejemplo"
date:       2019-10-09 00:17:40
author:     "Daniel Rosillo"
header-img: "img/8400.jpg"
description: Las notificaciones nos permiten mantener una linea de comunicacion entre el usuario y nuestra aplicacion, desde Android 8 se ha simplificado este comportamiento hasta hacerlo bastante sencillo de implementar.
categories: Quick
image: /img/8400.jpg

---
<div style="text-align: justify;">
<br>
<p>Es muy común tratar de implementar esta funcionalidad y tener diferente tipo de errores, a partir de Android 8 esto ha cambiado, desde ahora todas las notificaciones usan canales y configuraciones bien definidas.
<br>
<br>
<h1>ENTORNO</h1>
<br>
<a href="https://2.bp.blogspot.com/-_cCRPk4QL1k/W8sCpKnairI/AAAAAAAAAkI/S1l_if5p4RACmKqfYi7xqevCeMhuHWV9QCLcBGAs/s1600/DELYSIDANN02.jpg" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img src="https://2.bp.blogspot.com/-_cCRPk4QL1k/W8sCpKnairI/AAAAAAAAAkI/S1l_if5p4RACmKqfYi7xqevCeMhuHWV9QCLcBGAs/s200/DELYSIDANN02.jpg" class="img-responsive" /></a>
<br><br>
&#8226;&nbsp;&nbsp;&nbsp;	Android Studio 3.5  <br>
&#8226;&nbsp;&nbsp;&nbsp;	minSdkVersion 26 <br>
&#8226;&nbsp;&nbsp;&nbsp;	targetSdkVersion 29 
<br>
<br>
<h1>INGREDIENTES</h1>
<br>
&#8226;&nbsp;&nbsp;&nbsp;  Nombre del canal de notificación. (Identifica el tipo de notificación y es obligatorio) <br>
&#8226;&nbsp;&nbsp;&nbsp;	ID de la aplicación. (Lo encuentras en buildGradle nivel App.)
<br>
<br>
<h1>PREPARACIÓN</h1>
<br>
<p>Creamos un objeto de nombre cualquiera el cual debe heredar de ContextWrapper y definimos 3 métodos de acción: 
&#8226;&nbsp;&nbsp;&nbsp; createChannels -> Crea todos los canales que asociemos a la aplicación, así como sus ajustes por defecto (vibración, sonido...)<br>
&#8226;&nbsp;&nbsp;&nbsp; push -> Para enviar las notificaciones.<br> 
&#8226;&nbsp;&nbsp;&nbsp; getManager -> Para retornar un manejador de notificaciones (Lo ofrece el sistema por defecto). <br>
<p>De igual forma sobrescribimos el constructor ya que este requiere de un contexto que será dado por la actividad en cuestión y que recuperaremos en una variable local. 
<br>
<a href="https://ibb.co/7VdP4jZ"><img src="https://2.bp.blogspot.com/-_cCRPk4QL1k/W8sCpKnairI/AAAAAAAAAkI/S1l_if5p4RACmKqfYi7xqevCeMhuHWV9QCLcBGAs/s200/DELYSIDANN02.jpg" class="img-responsive" /></a>
<br>


<p>Ejemplo de implementación:<br>
<a href="https://ibb.co/kS0HKSH"><img src="https://i.ibb.co/kS0HKSH/photo5141193604591626279.jpg" alt="photo5141193604591626279" img class="img-responsive" ></a>

<a href="https://ibb.co/ySYY45J"><img src="https://i.ibb.co/ySYY45J/photo5141193604591626278.jpg" alt="photo5141193604591626278" img class="img-responsive"></a>


<br>
<br>

<h1>Repositorio del Ejemplo<h1>
<br>
 <div class="badges">
                    <a class="badge-link" href="https://github.com/DanielRosillo/NightDrawerMenu"><img src="/img/git.png" alt="" img class="img-responsive"></a>
                     </div>
            
<div style='clear: both;'></div>
<br>
<br>

<p>Fuente del background
<br>
<div class="badges">
                    <a class="badge-link" href="https://www.freepik.com/free-vector/illustration-notification-icon-blue-background_2632303.htm#page=1&query=notification&position=16" ><img src="/img/images.jpeg" alt="" img class="img-responsive"></a>
                     </div>
<br>
<p>Fraternalmente Daniel Rosillo;