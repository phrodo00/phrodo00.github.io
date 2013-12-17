---
layout: post
title: Instalando paquetes de node-js en la home
categories:
- Herramientas
tags:
- Coffescrpit
- Instalación
- Node.js
status: publish
type: post
published: true
meta:
  _edit_last: '3'
---
[npm](http://npmjs.org/), el gestor de paquetes de node-js es capaz de instalar
paquetes de forma "local" o "global". Los paquetes instalados de forma local se
instalan en el directorio actual y están pensados para incluirse en otros
programas, como bibliotecas. Si se instalan de forma global, los deja en el
sistema para que se puedan usar como programas. El problema es que normalmente
la instalación global requiere permisos de administrador, además que nunca se
aprecia un gestor de paquetes metiéndose en la raíz aparte de la distro. Para
evitar estos problemas se puede configurar a npm para que instale los paquetes
globales en la home del usuario. Para hacer esto, es necesario crear un archivo
~/.npmrc con los contenidos:

```
prefix = ~/.local
```

y claro, en alguna parte de nuestro ~/.bashrc (si usan bash, para zsh claramente
el archivo es ~/.zshrc) hay que agregar a ~/.local/bin a la path:

```
export PATH=$HOME/.local/bin:$PATH
```

Con esto ya podemos instalar programas de node-js directamente en la home, por
lo que el [tutorial para instalar coffeescript](http://localhost:4000/blog/2011/07/06/instalando-coffeescript-en-la-home/)
pasa a ser:

```
$npm install -g coffee-script
```

y lo mismo para less o uglify-js.
