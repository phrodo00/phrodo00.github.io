---
layout: post
title: Instalando CoffeeScript en la home
categories:
- Herramientas
tags:
- Coffescript
- Instalación
- Node.js
status: publish
type: post
published: true
meta:
  _edit_last: '3'
---
[CoffeeScript](http://jashkenas.github.com/coffee-script) es un lindo lenguaje
que toma las mejores ideas de otros lenguajes dinámicos como python o ruby y se
compila a javascript. Para mí, la sintaxis es mucho más clara que la sintaxis
tipo algol de js.

Normalmente tengo mis herramientas de desarrollo web instaladas en mi home, así
puedo obtenerlas en cualquier distribución. Instalo
[Rails](http://rubyonrails.org/) sobre [rvm](https://rvm.beginrescueend.com/) y
uso pythonenvs para instalar [Django](https://www.djangoproject.com/) y
[Pyramid](http://pylonsproject.org/), así que ahora vamos a ver como instalar el
compilador de coffescript en la home.

Lo primero es instalar [Node.js](http://nodejs.org/), el runtime para programar
aplicaciones en javascript. Esto es tan simple como bajarse el fuente,
descomprimirlo, y, dentro de la carpeta, ejecutar:

```
./configure --prefix=$HOME/.local
make
make install
```

Una vez instalado, hay que asegurarse que ~/.local/bin sea parte del PATH, si no
lo es (o si no sabes lo que es el path) agrega esta línea a tu archivo
~/.bashrc:

```
export PATH=$HOME/.local/bin:PATH
```

Una vez hecho esto, es sólo cuestión de bajarse la última versión de
[coffescript](https://github.com/jashkenas/coffee-script/archives/master) (hacer
click en los enlaces con números de versión para no obtener la versión de
desarrollo), descomprimirla, y desde su carpeta hacer lo siguinte:

```
bin/cake --prefix $HOME/.local install
```

Ahora tenemos instalado coffee en la home y tan sólo nos basta ejecutar coffee
-c archivo.coffee para compilar nuestros archivos de coffeescript a javascript
:)
