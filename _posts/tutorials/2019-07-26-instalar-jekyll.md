---
layout: post
title:  "Instalar Jekyll en Ubuntu 16.04 WSL (Windows Subsystem for Linux)"
date:   2019-07-26 18:00:00 -0500
categories: blog
---

Estoy básicamente siguiendo los pasos de esta [maravillosa playlist](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB).

## Instalar Ruby (pasar a la siguiente opción)

[Source](https://www.ruby-lang.org/en/documentation/installation/#apt)

    sudo apt update
    sudo apt-get install ruby-full
    ruby -v
    >>> ruby 2.3.1p112 (2016-04-26) [x86_64-linux-gnu]

La versión era demasiado antigua. Intenté buscar cómo actualizarla de forma directa, pero todos los caminos me llevaban al Ruby Version Manager (RVM para los amigos).

## Instalar Ruby Package Manager (RVM)

[Source 1](https://rvm.io/rvm/install)

[Source 2](https://github.com/rvm/ubuntu_rvm)

Son varios comandos los que hay que copiar y pegar, pero la guía de la segunda fuente es bastante directa (además de oficial), y con solo instalar el RVM la versión de Ruby se actualiza. Al final de la instalación debería salir esto.

    .
    .
    .
    ruby -v
    >>> ruby 2.6.3p62 (2019-04-16 revision 67580) [x86_64-linux]
    gem -v
    >>> 3.0.3

## Instalar Jekyll

[Source](https://jekyllrb.com/)

    gem install jekyll bundler
    jekyll -v
    >>> jekyll 3.8.6