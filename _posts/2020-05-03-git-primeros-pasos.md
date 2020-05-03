---
layout: post
title: Primeros pasos en Git
subtitle : conceptos que necesitamos aprender para comprender cómo se organizan las cosas y cómo se rastrean nuestros archivos con Git.
tags: [Git/Github]
author: Tania R. Zúñiga
comments : true
---

En un [post anterior](https://tanx.dev/2020/04/30/before-cv.html) hable de como podemos comparar dos archivos y resaltar sus diferencias desde nuestro Terminal.

Sin embargo, hacer una copia cada que hacemos un cambio no suena como una solución eficiente, pues luego de un tiempo tendremos muchos archivos con nombres tipo: &nbsp;*final.py*,  &nbsp;*final-final.py*, &nbsp;*final-real-cambios.py*, &nbsp;etc. 

<br>

Sacar copias no parece una solución viable. Por suerte tenemos una herramienta muy poderosa que nos puede ayudar a llevar un registro de los cambios que hacemos en nuestro proyecto! Y lo mejor de todo es open source (lo que significa que es gratis 100% real no fake).

<br>

Ahora quiero aclarar que Git es una herramienta que nos ayuda llevar el registro de los cambios de todo tipo de proyectos, no solo de código y lo te cuento en el post de [aca](https://tanx.dev/2020/04/30/git-es-para-todos.html).

<br>

<h3>Conceptos básicos</h3>

Obviamente no vas a memorizarlos, esto no es primaria, solo es para nos entendamos.

<br>

Hay dos formas de trabajar un repositorio con git,una es creando el nuestro `git init` y otra es clonarlo `git clone url` (hablare de eso en otra ocasión).

>El `git init` lo debemos correr dentro de la carpeta donde vayamos a trabajar. Ejem: *C:/user/Desktop/miPrimerGit*

Primero quiero contarte que es el **git directory**, este contiene todos los cambios que has hecho, sería algo así como tu **historial de navegación**.

Mientras que el **working tree** contiene la versión actual de los archivos, que dentro de nuestra analogía seria las **pestañas abiertas** ahora mismo.

<br>

El **staging area**, también llamado **index**, es un archivo de Git que contiene toda la información sobre los archivos y cambios que se incluirán en el próximo comando. 

En otras palabras, contiene los **archivos cambiados** que fueron marcados para ser incluidos en el **proximo commit**.

Usamos `git   add   nombre_del_archivo` para ponerlo en el staging area.

![git_environment](\assets\img\gitPrimerosPasos\git_environment.png)

Un **commit** es hacer un registro del estado en el que se encuentra un proyecto. Cada uno de los commit que hacemos se almacena en el git directory.

Para realizar un commit usamos el commando `git commit -m 'Un mensaje'` en el mensaje podemos explicar que modificaciones hicimos. Créeme tu yo del futuro u otros desarrolladores estarán agradecidos.

Los commits que hagamos los podemos ver usando `git log`.

Cabe destacar que podemos o no llevar registro de nuestros archivos. Los archivos de los que NO llevamos registro son **untracked  files** y de los que sí son **tracked files**.


<h4>States (estados)</h4>
Git detecta los cambios que le haces a los tracked files, usando `git status` puedes verlos. Algunos *states* son los siguientes
1. **Modified:** Significa que le hemos hecho cambios como:
   - **Adding** / agregar
   - **Modifying** / modificar
   - **Deleting** / eliminar
2. **Staged:** El archivo será guardado (en el Git directory) en el proximo commit.
3. **Committed**: Cuando ya se guardaron los cambios (en el Git directory).

<br>

Esa es un poco de la *jerga* al usar git. No te preocupes mucho por aprender los comandos, por ahora. 

Muchos IDEs o Editores como [Atom](https://atom.io/) o [Visual Studio Code](https://code.visualstudio.com/) te permiten trabajar con git sin necesidad de usar comandos.

Ademas de que existen varias herramientas con interfaz de usuario para manejar git como [GitKraken](https://www.gitkraken.com/) o [GithubDesktop](https://desktop.github.com/).

Siéntete libre de explorar cual se adapta a tus necesidades. Si los comandos se te hacen muy complicados, no sufras.

Espero está mini guiá te ayude a entender cositas de Git.

<br>

Iconos diseñados por <a href="https://www.flaticon.es/autores/freepik" title="Freepik">Freepik</a>,  <a href="https://www.flaticon.es/autores/ultimatearm" title="ultimatearm">ultimatearm</a> from <a href="https://www.flaticon.es/" title="Flaticon"> www.flaticon.es</a>