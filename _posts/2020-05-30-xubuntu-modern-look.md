---
layout: post
title: Moderniza Xubuntu 🐁
subtitle : Dale un aspecto moderno a Xubuntu 20.04
tags: [Linux]
author: Tania R. Zúñiga
comments : true
---

Está semana empece a usar Xubuntu como mi sistema operativo principal. Una de las primeras cosas que hice fue modificar su aspecto para que fuera más moderno y comodo para mi. Linux (en particular Xubuntu) me permite tener lo mejor de dos mundos, de manera muy fácil. Hablo del *dock* al estilo macOS y el menú desplegable como Windows XP.  😀 

![resultado]({{ site.baseurl }}/assets/img/modernXubuntu/default_to_cool.png)

¿Te gustaría tener una configuración así? 

¡En este post te cuento paso a paso como conseguirla!

<br>

<h3>Cambiar iconos y ventanas en Xubuntu</h3>

Estoy usando los iconos *Papirus*. Los puedes obtener de su [repo oficial](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme)
o usando los comandos:

```
sudo add-apt-repository ppa:papirus/papirus
sudo apt-get update
sudo apt-get install papirus-icon-theme
```

<br>

El tema que estoy usando se llama **Dark Olympic**, lo puedes descargar de [aquí](https://www.pling.com/s/XFCE/p/1302313/). Descarga *"Dark-Olympic.zip"* en la sección de *"Files"*.

![Descargar_tema]({{ site.baseurl }}/assets/img/modernXubuntu/download_theme.png)

Selecciona "Save File".

![Save_theme]({{ site.baseurl }}/assets/img/modernXubuntu/save_file.png)

Después ve a la carpeta de Descargas y con click derecho sobre *"Dark-Olympic.zip"* escoge "Extraer aquí". Esta acción generara un folder llamado Dark-Olympic. 

![descomprimir]({{ site.baseurl }}/assets/img/modernXubuntu/extraer_aqui.png)

Ahora da click derecho dentro de la carpeta Descargas y selecciona "Abrir un terminal aquí

![abrir_terminal_descargas]({{ site.baseurl }}/assets/img/modernXubuntu/abrir_terminal}.png)

o usa el comando
```
cd Descargas/
```

<br>

Para instalar el tema Dark-Olympic, en el terminal que abrimos, escribirlos el siguiente comando
```
sudo mv Dark-Olympic/ /usr/share/themes/
```

<br>

Ahora para elegirlo, abre el menú Desplegable busca "Configuración" o "Administración de la configuración" y dirígete a "Apariencia"

![Apariencia]({{ site.baseurl }}/assets/img/modernXubuntu/abrir_configuracion.png)


<br>

Cambia el tema por "Dark-Olympic"

![select_dark-olympic]({{ site.baseurl }}/assets/img/modernXubuntu/selecciona_dark-olympic.png)

<br>

Luego ve al apartado de "Iconos" y escoge "Papirus-Dark"

![select_papirus-dark]({{ site.baseurl }}/assets/img/modernXubuntu/selecciona_iconos_papirus.png)

<br>

¡Ya casí! Solo que los marcos de la ventana se ven raros ¿no?

Clickea "Toda la configuración" para regresar a la Configuración. Ahora dirígete al "Gestor de ventanas"

![cambia_ventanas]({{ site.baseurl }}/assets/img/modernXubuntu/gestor_de_ventanas.png)

<br>

y selecciona "Dark-Olympic".

![select_papirus-dark]({{ site.baseurl }}/assets/img/modernXubuntu/ventanas_dark_olympic.png)

<br>

¡Ya tenemos nuestras ventanas moderas! Ahora vamos por nuestro Dock.

<br>

<h3>Agregar un Dock a Xubuntu</h3>

Para instalar el Dock, abrimos un terminal y tecleamos el comando 

`sudo apt-get install plank`

<br>

Una vez que termine la instalación abrimos el "menú Desplegable" buscamos "Plank".

![buscar_plak]({{ site.baseurl }}/assets/img/modernXubuntu/abrir_plank.png)

<br>

Al abrirlo, aparecerá nuestro Dock en la parte de abajo. Para editarlo a nuestro gusto, vamos a escribir en la terminal

`plank  --preferences`

<br>

Ese comando nos abrirá un menú. Estás son las configuraciones que estoy usando.

![preferences_plank]({{ site.baseurl }}/assets/img/modernXubuntu/plank_settings.png)

<br>

Para agregar una aplicacion solo tenemos que arrastarla hacia el dock o si esta abierta dar click derecho y seleccionar "Mantener en el dock". Para eliminara una aplicacion del dock solo tenemos que arrastarlas fuera del dock o deseleccionar "Mantener en dock".

<br>

Es recomendable que el Dock se inicie cada que prendas tu computadora. Pra ello dirigete a "Sesión e inicio" > "Autoarranque de aplicaciones" > " + Añadir". Agrega Plank de la siguiente forma

![open_plank_always]({{ site.baseurl }}/assets/img/modernXubuntu/plank_config.png)

<br>

<h3>Personalizar barra superior Xubuntu</h3>

Lo siguiente que haremos es editar la barra superior, damos click derecho en ella y nos dirigimos a "Panel" > "Preferencias del panel" 

<br>

En el menú que nos abra vamos a añadir un nuevo panel haciendo click en "+".

![add_panel]({{ site.baseurl }}/assets/img/modernXubuntu/aniadir_nuevo_panel.png)

<br>

Nos creara un "Panel 1" vamos a ir a "Elementos" y apretamos "+". Nos abrirá una ventana, donde buscaremos "Menú Whisker", como en la imagen. Le damos "+ Añadir". 

![add_menú_whisker]({{ site.baseurl }}/assets/img/modernXubuntu/menú_whisker.png)

<br>

Al dar doble clic sobre "Menú whisker" podemos cambiar el icono de Xubuntu por el que queramos en "Botón el panel" dando doble click sobre el Logo de Xubuntu.

![change_menu_whisker_logo]({{ site.baseurl }}/assets/img/modernXubuntu/editar_icono_menu_w.png)

<br>

Para elegir alguna imagen que tengamos guardada en "Seleccionar el icono de:" elegimos "Archivos de imagen" y podemos buscarla. Yo usare un cohete que tengo en la carpeta "Descargas". 

![change_menu_whisker_logo]({{ site.baseurl }}/assets/img/modernXubuntu/elegir_icono_de_imagen.png)

<br>

Ahora en "Preferencias del panel" > "Apariencia" podemos elegir el color de fondo de las barras/paneles. A mí me gusta transparente pero tú puedes escoger el que quieras. Pondré ambos paneles, el "Panel 0" y el "Panel 1", transparentes.
![fondo_transparente]({{ site.baseurl }}/assets/img/modernXubuntu/panel_aparencia.png)

<br>

Luego  "Preferencias del panel" > "Elementos" del "Panel 0" eliminare las ventanas y el MenÚ Whisker usando el " **-** ", dando como resultado

![elementos_panel_0]({{ site.baseurl }}/assets/img/modernXubuntu/wifi_hora_dia.png)

<br>

Despues en "Preferencias del panel" > "Presentación" del "Panel 0" modificare sus atributos para que queden así.

![presentacion_panel_0]({{ site.baseurl }}/assets/img/modernXubuntu/presentacion_panel_0.png)

<br>

Luego el "Panel 1" lo movemos a la ubicación de nuestra preferencia y seleccionamos "Bloquear panel" cuando estemos satisfechos. Yo lo puse en la esquina superior izquierda, usando las siguientes configuraciones.

![presentacion_panel_1]({{ site.baseurl }}/assets/img/modernXubuntu/panel1_preferencias.png)

<br>

<h3>Cambiar wallpaper en Xubuntu</h3>

Finalmente para cambiar el fondo de pantalla damos click derecho en nuestro escritorio y escogemos "Configuracion del escritorio".

Si queremos usar alguna imagen personalizada, en "Carpeta:" seleccionamos la ubicación donde tengamos fondo que deseamos. Yo tengo mi fondo la carpeta de "Descargas".
![presentacion_panel_1]({{ site.baseurl }}/assets/img/modernXubuntu/fondo_descargas.png)

> Tip ⭐
> 
>  Te recomiendo que guardes las imágenes que vas a usar de *wallpaper* en "Imágenes". ¡No las vayas a borrar por accidente!

<br>

Descarga el *wallpaper* que use <a target="_blank" id="raw-url" href="https://raw.githubusercontent.com/TanZng/tanzng.github.io/master/assets/img/modernXubuntu/wall_spaceX.jpg">aquí</a>.

Descarga el ícono que use <a target="_blank" id="raw-url" href="https://image.flaticon.com/icons/svg/214/214337.svg">aquí</a>.

<br>

<h3>Extras</h3>

<h5>Usar Neofetch en Xubuntu</h5>

Abre la terminal e instala **Neofetch** usando

`sudo apt update`

`sudo apt install neofetch`

Para ver el logo de Xubuntu en la terminal usa el comando

`neofetch --ascii_distro Xubuntu`

<br>

<h5>Abrir el Menú Desplegable de Xubuntu usando la tecla Windows</h5>

Si quieres abrir el Menú Desplegable (Menú Whisker) usando la tecla Windows abre el Menú Desplegable y busca "Teclado".

![buscar_teclado]({{ site.baseurl }}/assets/img/modernXubuntu/menu_d_teclado.png)

<br>

Dirígete a "Atajos de aplicación" y busca "xfce4-popup-whiskermenu" 

![popup_whisker_xfce4]({{ site.baseurl }}/assets/img/modernXubuntu/usar_teclaWindows.png)

<br>

dale doble click y cuando te salga una ventana como la siguiente, presiona la tecla Windows.

![presentacion_panel_1]({{ site.baseurl }}/assets/img/modernXubuntu/tecla_windows.png)

¡Ahora cuando presiones la tecla Windows desplegarás el Menú Whisker al estilo Windows XP!

<br>

¡Listo! 

¡Ya tenemos un Xubuntu más moderno y bonito! No olvides que puedes personalizarlo usando el tema, iconos, fondos y configuraciones que quieras. Comparte en los comentarios tus resultados.

![resultado]({{ site.baseurl }}/assets/img/modernXubuntu/resultado_final.png)
