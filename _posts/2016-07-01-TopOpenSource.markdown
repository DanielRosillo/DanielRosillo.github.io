---
layout:     post
title:      "Top 5: Aplicaciones Open-Source en Android"
date:       2020-02-02 00:17:40
author:     "Daniel Rosillo"
header-img: "img/73.jpg"
description: Hoy conoceremos algunas aplicaciones basadas en este modelo que están disponibles para Android, y que en muchos casos fácilmente pueden sustituir a sus contrapartes más famosas como las apps de Google.
categories: Quick
image: /img/73.jpg

---
<div style="text-align: justify;">
<br>
<p>El código abierto es un modelo de desarrollo de software basado en la colaboración abierta. Se enfoca más en los beneficios prácticos (acceso al código fuente) que en cuestiones éticas o de libertad que tanto se destacan en el software libre.  Hoy conoceremos algunas aplicaciones basadas en este modelo que están disponibles para Android, y que en muchos casos fácilmente pueden sustituir a sus contrapartes más famosas como las apps de Google, a diferencia de estas últimas y otras las siguientes apps no contienen trackers ni tampoco anuncios.
<br>
<br />
<h1>VLC</h1><br>
<p>Un viejo y conocido veterano de guerra VLC, este reproductor sustituye a Google Play Music sin problemas, ofreciendo opciones de reproducción avanzadas que simplemente una vez que las uses serán imposibles de olvidar, algunas de ellas son: 
<br>
&#8226;&nbsp;&nbsp;&nbsp;Reproducción Pop-Up Player en videos. <br>
&#8226;&nbsp;&nbsp;&nbsp;Reproducción de solo audio en videos. <br>
&#8226;&nbsp;&nbsp;&nbsp;<br>SleepTimer.<br>
&#8226;&nbsp;&nbsp;&nbsp;<br>Jump to time.<br>

<a href="https://images.videolan.org/vlc/screenshots/1.0.0/fitted_vlc_101_w7_2.jpg" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img src="https://images.videolan.org/vlc/screenshots/1.0.0/fitted_vlc_101_w7_2.jpg" class="img-responsive" /></a>
<br>
<p>VLC está disponible mediante FDROID
<br>


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
<p>Fraternalmente Daniel Rosillo;