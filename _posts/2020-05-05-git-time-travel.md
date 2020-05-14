---
layout: post
title: ¿Cómo viajar en el tiempo con Git?
subtitle : Deshacer cambios en Git
tags: [Git/Github]
author: Tania R. Zúñiga
comments : true
---

Hay diversas formas de (des)hacer cambios en Git. Pero, dependiendo que deseas deshacer es el comando que usaras. Aquí te dejo los más comunes:

<br>

<h3>Deshacer cambios antes de hacer commit</h3>

Hiciste cambios, no has puesto tus archivos en el *staged area* *, y quieres **regresar** a como tenias las cosas en el **último commit**. Solo debes usar el comando:


``` shell
git checkout nombre_del_archivo
```

Así restauras un archivo que modificamos, a la version del último commit.

<br>

Por otro lado, si queremos **sacar un archivo** del *staged area* * usamos el commando:


``` shell
git reset nombre_del_archivo
```

Podría decirse que `git reset` es lo contrario a `git add`.

<br>

> *
> Si no sabes que es el staged area en el post de [aquí]( {% post_url 2020-05-03-git-primeros-pasos %} ) te lo cuento.

<br>

<h3>Modificar un commit</h3>

En este caso, **acabas de hacer un commit** pero **faltaron archivos** o pusiste un **mensaje incorrecto**. No te preocupes se puede hacer algo.
Si te faltaron archivos por incluir, asegurate de agregar los al staged area con `git add nombre_del_archivo`. Y después usa el comando:
<br>
``` shell
git commit --amend
```
<br>

Al ejecutar el comando, **sobrescribirá** el último commit con lo que tenemos en el staged area. También nos abrirá el editor de texto que tengamos por defecto**, esto nos va a permitir modificar el mensaje de nuestro commit.

<br>
<br>

**Puedes cambiar el editor de texto por defecto usando el comando: `git config --global core.editor "code"`, para usar Visual Studio Code  o `git config --global core.editor "atom"` para usar Atom.

<br>

> ⚠️
> De preferencia usa git commit --amend solo en repositorios locales.

<br>

<h3>Deshacer commit</h3>

Hiciste un commit y lo quieres **deshacer**, se puede, simplemente tienes que usar:

<br>
``` shell
git revert ID_commit
```
<br>

El comando git revert funciona como un *undo*. Después de usarlo nos va a abrir el editor de texto para que escribamos un mensaje explicando porque deshicimos cierto commit. Finalmente, creara un nuevo commit con los cambios reflejados.

![revert_command_pic]({{ site.baseurl }}/assets/img/gitPrimerosPasos/revert.png)
En esta imagen vemos como el cambio "verde" de la v3 se deshizo luego de hacer revert de dicha versión.

<br>

El ID_commit es un identificador único ( o *hash*) que tiene tiene cada commit. El ID lo puedes obtener usando `git log` y es esa larga cadena de números y letras, de hecho tiene 40 caracteres. Después de usar git log, aprieta la tecla `Q` para salir/continuar.

<br>

<h3>Regresar a un commit especifico</h3>

Supongamos que hiciste muchos cambios (v1, v2, v3, "version actual") y quieres regresar a la v2. Puedes regresar a un **commit especifico** usando:

``` shell
git checkout ID_commit
```
<br>

Eso sí que será viajar en el tiempo, pues los commit posteriores a v2 no existirán más. En la siguiente imagen lo ilustro mejor.

<br>

![time_travel_pic]({{ site.baseurl }}/assets/img/gitPrimerosPasos/time_travel.png)
En esta imagen vemos como los commits v3 y "versión actual" desaparecen, pues regresamos totalmente a v2.

<br>

> ⚠️
> Regresará todo a como estaba en el commit que decidas. Eliminando archivos, lineas, commits posteriores, etc.

<br>
<br>

 Esos son algunos comandos (los que más uso) para deshacer cambios. Espero esta pequeña compilación te sea útil para "viajar en el tiempo" y te evite sufrir por cambios indeseables. Más adelante hablare de como las branches/ramas pueden ser muy útiles para hacer pruebas (y evitarnos viajes en el tiempo).

¿Qué otros comandos conoces para deshacer cambios? Dejalos en los comentarios 😃.

<br>
Iconos diseñados por <a href="https://www.flaticon.es/autores/smashicons" title="Smashicons">Smashicons</a> from <a href="https://www.flaticon.es/" title="Flaticon"> www.flaticon.es</a>