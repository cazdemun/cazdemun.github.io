---
layout: post
title:  "Crear un blog con Jekyll en Ubuntu 16.04 WSL (Windows Subsystem for Linux) y publicarlo en Github Pages"
date:   2019-07-26 19:00:00 -0500
categories: blog
---

Revisar que Jekyll ya este [instalado]().

    jekyll new justice_blog
    cd justice_blog

Solamente para la primera vez que se despliegue el servidor de desarrollo se agrega los comandos `bundle exec` al inicio.

    bundle exec jekyll serve

