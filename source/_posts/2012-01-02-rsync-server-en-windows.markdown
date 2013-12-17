---
layout: post
title: rsync server en windows
categories:
- Herramientas
tags:
- rsync
- Windows
status: publish
type: post
published: true
meta:
  _edit_last: '3'
---
Debido a que me gusta jugar starcraft resulta que me armé un computador de
gaming, y como la idea es poder jugar en cualquier momento, su OS principal es
windows, lo que es... extraño para mí. De cualquier forma, el primer paso en
recuperar la utilidad de mi computador de fue encontrar un servidor de rsync, y
resulta que [DeltaCopy](http://www.aboutmyip.com/AboutMyXApp/DeltaCopy.jsp) es
bastante bueno. [Acá hay un tutorial de como instalarlo](http://dailycupoftech.com/windows-backup-with-rsync-and-freenas/)
que encontré despues, mientras intentaba abrir el puerto, pero eso para otro
post.

**Edición:** Resulta que DeltaCopy por defecto no funciona con unicode, lo que
significa que si tienen el sistema linux desde el que están sincronizando en una
codificación distinta al server (que es lo típico), los nombres de los archivos
van a terminar todos mal. Para solucionar esto, se puede descomprimir
[utf8-cygwin](http://www.oki-osk.jp/esc/utf8-cygwin) encima del cygwin incluido
en DeltaCopy (la dll se encuentra en la misca carpeta donde instalaron el
programa), y reiniciando el servicio (click derecho en
Equipo→Administrar→Servicios→click derecho en DeltaCopy→Reiniciar).
