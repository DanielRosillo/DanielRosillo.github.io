---
layout:     post
title:      "Android Studio para retrasados: Implementar tema oscuro en 2 pasos + Ejemplo"
date:       2019-09-01 00:17:40
author:     "Daniel Rosillo"
header-img: "img/2752814.jpg"
description: Son muchas las formas de implementar el tema oscuro o de noche en una aplicación, una de estas formas nos la brinda la librería Appcompat del paquete de librerías AndroidX.
categories: Quick
image: /img/2752814.jpg

---
<div style="text-align: justify;">
<br>
<p>Con este artículo se inaugura la zona Android, implementaciones rápidas, sin problemas y entendibles para nosotros los retrasados que no leemos la documentación.
Son muchas las formas de implementar el tema oscuro o de noche en una aplicación, una de estas formas nos la brinda la librería Appcompat del paquete de librerías AndroidX, que a partir de la Api 28 introduce una serie de mejoras enfocadas a estandarizar su uso y relacionarlo a los ámbitos diarios.
<br>
<br />
<p>NOTA<br>
<p>Algunas funciones como la asignación de tema automático o según el consumo de batería están disponibles solo para la Api 28(Android 9).
<br>

<a href="https://2.bp.blogspot.com/-_cCRPk4QL1k/W8sCpKnairI/AAAAAAAAAkI/S1l_if5p4RACmKqfYi7xqevCeMhuHWV9QCLcBGAs/s1600/DELYSIDANN02.jpg" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img src="https://2.bp.blogspot.com/-_cCRPk4QL1k/W8sCpKnairI/AAAAAAAAAkI/S1l_if5p4RACmKqfYi7xqevCeMhuHWV9QCLcBGAs/s200/DELYSIDANN02.jpg" class="img-responsive" /></a>

<br>
<h1>Ingredientes</h1>
<br>
<p>En el build.gradle de la aplicación, agregamos la dependencia o si la tenemos la actualizamos por:
<br><br>

<blockquote>
implementation 'androidx.appcompat:appcompat:1.1.0-rc01'<br />
</blockquote>
<br>
<h1>Preparación</h1>
<p>Dentro de la carpeta values/styles/, encontramos los archivos de nuestro tema.
<br>
<br>
&#8226;&nbsp;&nbsp;&nbsp;	Styles.xml <br>
&#8226;&nbsp;&nbsp;&nbsp;	Styles.xml (21)
<br>

<p>Editamos el primero, y cambiamos la herencia de nuestro tema por defecto, que es Theme.AppCompat.Light.DarkActionBar, debe quedar algo como lo siguiente:
<br>

<blockquote>
name="AppTheme" parent="Theme.AppCompat.DayNight.DarkActionBar"<br />
name="colorAccent">@color/colorAccent<br />
name="android:windowTranslucentNavigation">true<br />
name="android:navigationBarColor">@android:color/transparent<br />
</blockquote>


<br>
<p>En caso de tener un NavigationDrawer, editar herencia de este tema:
<br>

<blockquote>
name="AppTheme.PopupOverlay" parent="Theme.AppCompat.DayNight.DarkActionBar"<br />
</blockquote>

<br>
<p>Creamos las mecánicas del manejador apoyándonos del uso de una preferencia.
<br>

<blockquote class="img-responsive">

SharedPreferences mDefaultPreferences;
mDefaultPreferences = PreferenceManager.getDefaultSharedPreferences (this);<br />
if (isChecked)<br />
{<br />
   
mDefaultPreferences.edit ().putBoolean ("dark_mode", true).apply ();<br />
   AppCompatDelegate.setDefaultNightMode (AppCompatDelegate.MODE_NIGHT_YES);<br />
}<br />
else<br />
{<br />
   
mDefaultPreferences.edit ().putBoolean ("dark_mode", false).apply ();<br />
   AppCompatDelegate.setDefaultNightMode (AppCompatDelegate.MODE_NIGHT_NO);<br />
}<br />
</blockquote>

<p>Ejemplo de implementación en un NavigationDrawer:<br>
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
                    <a class="badge-link" href="https://www.freepik.com/free-vector/sunset-mountains-landscape-with-purple-gradient-colors_5315515.htm#page=1&query=mountains&position=8" ><img src="/img/images.jpeg" alt="" img class="img-responsive"></a>
                     </div>
<br>
<p>Fraternalmente Daniel Rosillo;</p>
-Manager at Rosillo Labs;