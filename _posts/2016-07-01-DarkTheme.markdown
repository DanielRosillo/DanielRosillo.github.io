---
layout:     post
title:      "Android Studio para retrasados: Implementar tema oscuro en 2 pasos"
date:       2019-09-01 00:17:40
author:     "Daniel Rosillo"
header-img: "img/2752814.jpg"
categories: Quick
---
<div style="text-align: justify;">
<div class='post-body entry-content'>
<br>
<p>Con este artículo se inaugura la zona Android, implementaciones rápidas, sin problemas y entendibles para nosotros los retrasados que no leemos la documentación.
Son muchas las formas de implementar el tema oscuro o de noche en una aplicación, una de estas formas nos la brinda la librería Appcompat del paquete de librerías AndroidX, que a partir de la Api 28 introduce una serie de mejoras enfocadas a estandarizar su uso y relacionarlo a los ámbitos diarios.
<br>
<br />
<p>NOTA<br>
<p>Algunas funciones como la asignación de tema automático o según el consumo de batería están disponibles solo para la Api 28(Android 9).
<br>

<a href="https://2.bp.blogspot.com/-_cCRPk4QL1k/W8sCpKnairI/AAAAAAAAAkI/S1l_if5p4RACmKqfYi7xqevCeMhuHWV9QCLcBGAs/s1600/DELYSIDANN02.jpg" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" data-original-height="324" data-original-width="324" height="200" src="https://2.bp.blogspot.com/-_cCRPk4QL1k/W8sCpKnairI/AAAAAAAAAkI/S1l_if5p4RACmKqfYi7xqevCeMhuHWV9QCLcBGAs/s200/DELYSIDANN02.jpg" width="200" /></a>

<br>
<h1>Ingredientes</h1>
<br>
<p>En el build.gradle de la aplicación, agregamos la dependencia o si la tenemos la actualizamos por:
<br><br>
<blockquote>
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">implementation 'androidx.appcompat:appcompat:1.1.0-rc01'</span><br />
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
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">name="AppTheme" parent="Theme.AppCompat.DayNight.DarkActionBar"</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">name="colorAccent">@color/colorAccent</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">name="android:windowTranslucentNavigation">true</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">name="android:navigationBarColor">@android:color/transparent</span><br />
</blockquote>


<br>
<p>En caso de tener un NavigationDrawer, editar herencia de este tema:
<br>

<blockquote>
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">name="AppTheme.PopupOverlay" parent="Theme.AppCompat.DayNight.DarkActionBar"</span><br />
</blockquote>

<br>
<p>Creamos las mecánicas del manejador apoyándonos del uso de una preferencia.
<br>

<blockquote>
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">
SharedPreferences mDefaultPreferences = PreferenceManager.getDefaultSharedPreferences (this);</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">if (isChecked)</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">{</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">    
mDefaultPreferences.edit ().putBoolean ("dark_mode", true).apply ();</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">    AppCompatDelegate.setDefaultNightMode (AppCompatDelegate.MODE_NIGHT_YES);</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">}</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">else</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">{</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">    
mDefaultPreferences.edit ().putBoolean ("dark_mode", false).apply ();</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">    AppCompatDelegate.setDefaultNightMode (AppCompatDelegate.MODE_NIGHT_NO);</span><br />
<span style="font-family: &quot;courier new&quot; , &quot;courier&quot; , monospace;">}</span><br />
</blockquote>

<p>Ejemplo de implementacion en un NavigationDrawer:<br>
<a href="https://ibb.co/kS0HKSH"><img src="https://i.ibb.co/kS0HKSH/photo5141193604591626279.jpg" alt="photo5141193604591626279" border="0"></a>

<a href="https://ibb.co/ySYY45J"><img src="https://i.ibb.co/ySYY45J/photo5141193604591626278.jpg" alt="photo5141193604591626278" border="0"></a>

<a href="https://ibb.co/sVg3QQR"><img src="https://i.ibb.co/sVg3QQR/photo5141193604591626280.jpg" alt="photo5141193604591626280" border="0"></a>

<br>
<br>

<h1>Repositorio del Ejemplo<h1>
<br>
 <div class="badges">
                    <a class="badge-link" href="https://github.com/DanielRosillo/NightDrawerMenu"><img src="/img/git.png" alt=""></a>
                     </div>
            
<div style='clear: both;'></div>
<br>
<br>

<p>Fuentes
<p>https://www.freepik.com/free-vector/sunset-mountains-landscape-with-purple-gradient-colors_5315515.htm#page=1&query=mountains&position=8

<p>Fraternalmente Daniel Rosillo;