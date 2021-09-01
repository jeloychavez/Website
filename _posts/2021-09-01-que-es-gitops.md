---
layout: post
title: ¿Qué es GitOps?
subtitle : GitOps es la forma correcta de administrar tu Infraestructura como Código (IaC). Es muy importante que le des amor a la infraestructura como código, de la misma forma que cuidas al código de tu aplicación.
tags: [Git, DevOps]
author: Tania R. Zúñiga
comments : true
---

Hace no mucho, si queríamos poner nuestro código en producción, necesitábamos configurar manualmente un servidor, nuestra infraestructura, que albergará nuestra aplicación o base de datos. Este proceso manual no solo requiere mucho tiempo, sino que también es propenso a errores. Es por eso que en la actualidad, los desarrolladores optaron por crear *scripts* que se encargan de configurar la infraestructura. Estos *scripts* se conocen como Infraestructura como Código / *Infrastructure as Code* (IaC).

<br>

A medida que nuestras aplicaciones evolucionaron, nuestra Infraestructura como Código también lo hizo. Un simple *script* en Bash o Python ya no era suficiente; es por eso que herramientas como Terraform, Ansible, Chef o Puppet acudieron al rescate. Todas estas herramientas nos permiten indicar fácilmente las instrucciones que nuestra infraestructura necesita ejecutar para preparar el servidor donde alojaremos nuestro código.

<br>

Por eso, IaC es el estándar en la industria el día de hoy. Pues nos hace la vida más fácil, pero ¿qué pasa cuando ...?

<br>

- ¿Tenemos esta increíble infraestructura como código que automatiza tantas cosas pero aún las ejecutamos manualmente en nuestro proveedor de nube (GCP, AWS, Azure, etc.)?

- ¿Hicimos cambios en él y simplemente los lanzamos para que se ejecuten sin revisión o prueba de código?

<br>

Como puede imaginar, esto es lento y muchas cosas pueden salir mal en el proceso.

![Meme_GitOps]({{ site.baseurl }}/assets/img/que-es-gitops/memeGitOps.png)


Lo mejor que podemos hacer por nuestro IaC es revisarlo, *testearlo* y automatizar el proceso de *deploy*. En pocas palabras, usar GitOps para lograr una hermosa Infraestructura como Código 💙.

<br>

<h3>¿Qué es GitOps?</h3>

GitOps es una metodología moderna para entregar nuestro IaC. En esta metodología, usamos Git para rastrear la evolución del código, revisamos los cambios, los aprobamos y luego implementamos esos cambios, tal como lo haríamos con el código de la aplicación.

<br>

El flujo de GitOps no es complicado, así que no hay excusa para no usarlo.

<br>

El flujo de GitOps se ve así:

Podemos ver que la GUI de [GitKraken](https://gitkraken.link/tanx) para Git está en la fase de *Stage* y *Commit* pues nos permitirá preparar y confirmar nuestros cambios. Además GitKraken nos permitirá abrir una Pull Request en GitHub o GitLab.

![GitOps_flow]({{ site.baseurl }}/assets/img/que-es-gitops/GitOps-GitOps Flow.png)

<br>

Para los desarrolladores de código, este flujo es familiar, ¿cierto? Pero el flujo no termina ahí; necesitamos poner nuestro IaC en nuestro [clúster de servidores](https://es.wikipedia.org/wiki/Cl%C3%BAster_de_computadoras). Tenemos dos opciones para hacer esto:

1. Modelo de *Push*
2. Modelo de *Pull* ⭐️

<br>

<h3>Modelo Push</h3>

<br>

Usamos Modelo Push cuando nuestro servidor de CI/CD ejecuta un *push* (¿tiene sentido no?) en git para enviar el código con los cambios al entorno de producción. 🥳

![Push_Model]({{ site.baseurl }}/assets/img/que-es-gitops/GitOps-Push Model.png)

<br>

<h3>Modelo Pull</h3>

<br>

En este otro modelo, tenemos un "agente" (como Argo CD o Flux CD) instalado en nuestro cluster. Este agente será el encargado de hacer *push* para obtener los cambios del repositorio. 🥳🥳

![Pull_Model]({{ site.baseurl }}/assets/img/que-es-gitops/GitOps-PullModel.png)

<br>

<h3>Herramientas para GitOps</h3>

<br>

Probablemente estés pensando: ¿Qué herramientas me pueden ayudar a ejecutar el flujo de GitOps?

<br>

Bueno, ya mencioné (de forma superficial) algunas de ellas, pero enumeraré algunas que son estándar en la industria.

<br>

Por supuesto, Git es la piedra angular de este flujo. Recuerda, con GitOps buscamos entregar código de calidad. Git nos permitirá rastrear y observar la evolución de nuestro código.

<br>

Cuando termines los cambios en tu IaC, puedes revisarlos fácilmente con GitKraken antes de hacer *commit*.

Además, GitKraken te permite verificar fácilmente el historial de cambios en un archivo. Pues usa colores para denotar las líneas agregadas y eliminadas, de modo que puedas identificar rápidamente los cambios.

<br>

Con el poder de GitKraken en tus manos, ¡ningún cambio se te escapará al revisar el código! Puedes descargar gratis [GitKraken desde aquí](https://gitkraken.link/tanx).

<br>

![code_review]({{ site.baseurl }}/assets/img/que-es-gitops/History.png)

<br>

Luego de hacer commit, puedes abrir una [Merge Request desde GitKraken](https://www.gitkraken.com/learn/git/tutorials/what-is-a-pull-request-in-git), sin importar si usas [GitHub](https://www.gitkraken.com/learn/git/problems/github-pull-requests) o GitLab. También desde GitKraken, puede revisar las Merge Request creadas por miembros de tu equipo.

<br>

> 💡 **Sin usar el navegador**: desde la GUI de GitKraken puedes aprobar o hacer comentarios en las Merge Request de GitHub ¡Esto ahorra mucho tiempo!

<br>

Para el Modelo *Push* podemos usar: [Jenkins](https://www.jenkins.io/) es un servidor de automatización open source que permite a los desarrolladores de todo el mundo construir, probar e implementar su software de manera confiable.

<br>

Para el Modelo *Pull*  podemos usar: [ArgoCD](https://argo-cd.readthedocs.io/en/stable/) es una herramienta de despliegue continuo que implementa el seguimiento de los repositorios haciendo Pulling.

<br>

<h3>¿Listo para sumergirte en GitOps?</h3>

<br>

Recuerda, si tu IaC no es tan bueno como el código de tu aplicación, lo más probable es que tu infraestructura falle. Y sin Infraestructura, nadie puede utilizar tu aplicación. Por lo tanto, es mejor mantener seguro nuestro IaC testeando y revisándolo.

<br>

Implementar un flujo de GitOps en tus proyectos no es muy complicado y existen herramientas que lo hacen mucho más fácil, incluso si nunca antes has usado Git, como [GitKraken](https://gitkraken.link/tanx). Usar GitOps trae muchas otras ventajas como:

<br>

- Código de calidad
- Automatiza el proceso
- Transparencia ante todo el equipo
- Rápido despliegue y retroceso

<br>

Por otro lado, es posible que ya estés usando GitOps en tu proyecto, pero si aún no lo estás usando, definitivamente es hora de comenzar. 🚀

<br>

![es_hora_de_hacerlo]({{ site.baseurl }}/assets/img/que-es-gitops/time-to-do-it-its-time.gif)

Puedes leer este post en inglés en el [GitKraken Blog](https://www.gitkraken.com/blog/what-is-gitops)