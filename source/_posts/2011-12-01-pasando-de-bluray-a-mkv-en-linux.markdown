---
layout: post
title: Pasando de bluray a mkv en linux
categories:
- Herramientas
tags:
- Bluray
- HD
- Linux
- Muxing
- Video
status: publish
type: post
published: true
meta:
  _edit_last: '3'
---
Para pasar del formato TS de discos bluray (y en mi caso, de las cámaras con
disco duro de panasonic), se debe primero demuxear los archivos de video
(ubicados en la carpeta STREAM. No sé como será en los discos bluray, pero en la
cámara está en *AVCHD/BDMV*) utilizando
[TSMuxer](http://www.videohelp.com/tools/tsMuxeR). Para utilizarlo, simplemente
se descomprime el archivo y se ejecuta tsMuxerGUI. Para que quede un solo video,
se debe agregar el primer video de la serie con el botón “add”, y el resto con
“join”. Solo falta selexionar el “Demux” en la parte de output y hechar a correr
el demuxeo. Es útil usar el directorio /tmp/, ya que estos datos no los vamos a
utilizar mucho.

[{% img center http://i.imgur.com/cOh6d.png 400 %}](http://imgur.com/a/G6Hc4#0)

Una vez listo eso, se debe instalar mkvtoolnix-gui (debería estar en el gestor
de paquetes de la distro), y agregar los archivos demuxeados. En el caso de la
cámara que estaban usando (Panasonic HDC-HS80), mkvtoolnix no pudo detectar el
framerate del video, por lo que hay que ingresarlo manualmente, y en esta cámara
es 60000/1001.

El framerate me causó problemas porque en TSMuxeR dice que el video tiene 29.97
fps (o sea, 30000/1001), pero el video se veía demasiado lento. Me imágino que
la variación se provoca debido al interlazado, pero no estoy seguro.

[{% img center http://i.imgur.com/4M2yU.png 400 %}](http://imgur.com/a/G6Hc4#1)

Y listo el archivo mkv para poder agregarlo a algun editor de video o
simplemente verlo.
