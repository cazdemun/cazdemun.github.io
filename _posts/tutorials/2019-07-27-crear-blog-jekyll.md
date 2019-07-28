---
layout: post
title:  "Crear un blog con Jekyll en Ubuntu 16.04 WSL y publicarlo en Github Pages"
date:   2019-07-27 19:00:00 -0500
categories: blog
---

Esta es la forma más simple y rápida que he encontrado para hostear un blog de Jekyll en Github Pages. Las partes con (opcional) pueden saltarse.

## Crear un blog con Jekyll

Revisar que Jekyll ya este [instalado](https://cazdemun.github.io/blog/2019/07/26/instalar-jekyll.html). Para crear un blog se usan los siguientes comandos (el nombre usado para crear el blog no importa).

    jekyll new justice_blog
    cd justice_blog

## Levantar un servidor local (opcional)

Solamente para la primera vez que se despliegue el servidor de desarrollo se agrega los comandos `bundle exec` al inicio.

    bundle exec jekyll serve

    jekyll serve

Levantar un servidor de desarrollo es simplemente para verificar que la proyecto funciona, para publicar la página en Github Pages este paso no es necesario.

## Pequeño paréntesis sobre Github Pages y Github Projects (opcional)

Se puede hostear un sitio web en Github a través de Github Pages y Github Project. La diferencia es que a Github Pages se accede directamente con la dirección `username.github.io`, mientras que a Github project se accede a través de `username.github.io/repository`. 

Podemos derivar de esto que solo puedes tener un repositorio "principal", y múltiples projectos secundarios, lo cual me levanta la duda: _¿qué pasa si una página del sitio principal tiene un permalink con la misma extensión que la de un Github Project?_

Supongo que la idea es que el repositorio principal sea el "hub" que una todos los otros proyectos.

## Crear un repositorio en Github

>A diferencia de otros tutoriales, asumiré que ya existe una cuenta en Github, y se tiene Git y Git Bash instalado.

[Source 1](https://pages.github.com/)

[Source 2](http://jmcglone.com/guides/github-pages/)

Se crea un repositorio desde Github, pero el nombre de este repositorio debe tener el formato `username.github.io`. El repositorio debe crearse vacío, i.e. sin un archivo README.md como ofrece la interfaz de Github.

## Crear un repositorio local

En la carpeta donde se encuentra el blog de Jekyll (en nuestro caso `justice_blog`) se abre el Git Bash (en realidad cualquier consola con git instalado debería funcionar), y se tipea los siguiente comandos.

    git init
    git remote add origin https://github.com/username/username.github.io.git
    git add .
    git commit -m "First commit"
    git push -u origin master

Ya sé que es un poco obvio, pero cada `username` tiene que reemplazarse con tu usuario de github. Evita que tu nombre de usuario tenga caracteres raros, que ahí si no sé qué hacer.

Una pequeña ~~cagada~~ anécdota es que puse mal el nombre `username.github.io` al momento de crear el repositorio y tuve que modificar el remote, pero aprender a usar github será otra guía.

## Desplegar la pagina en Github Pages

Incluso con todos esos pasos, al intentar acceder a `username.github.io`, no pasa naa. Esto es porque hace falta una pequeña modificación. En el archivo `_config.yml` es necesario modificar una línea.

    url: "" # the base hostname & protocol for your site, e.g. http://example.com

Poner la dirección `https://username.github.io`

    url: "https://username.github.io"

Y, tadá, debería funcionar.

## Actualizar el blog

Actualizar cualquier cambio es tan simple como hacer un commit-push (name a more iconic duo).

    git add .
    git commit -m "New change"
    git push

Ahora, aprender a usar Jekyll es otra cosa, recomiendo este maravilloso [tutorial de YouTube](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB), el cual ya recomendé en un tutorial anterior. O la [documentación oficial de Jekyll](https://jekyllrb.com/docs/), que todavía no leo.
