---
layout: page
title: Solución a error en Mac SO Big Sur
---

Quienes tengan instalado el sistema operativo Big Sur van a encontrar errores a la hora de cargar los archivos de Arduino en el microcontrolador. Como suele pasar con las últimas versiones que MAC va lanzando, se encuentran incompatibilidades con muchas aplicaciones o hardware, por eso recomendamos no instalar siempre la última versión a menos que sea necesario.

Lo que tenemos que hacer es encontrar el archivo list_ports_osx.py para cambiar dos líneas de código que el sistema operativo utiliza para conectar con nuestro microcontrolador.  

La solución la explicamos debajo:

1. Localizar el archivo
   1. Abrir Finder
   1. En el menú superior hacer click en "Go/Go to folder" 
   1. Para acceder directamente a la carpeta escribir en la ventana ~/Library/Arduino15/packages/esp8266/hardware/esp8266/2.7.4/tools/pyserial/serial/tools/list_ports_osx.py o probar solo con ~/Library
   1. Sobre el archivo **list_ports_osx.py** hacer click derecho para abrir el archivo con Text Edit


1. Cambiar las líneas de código
   1. Comentar las líneas 29 y 30 agregando # delante de cada línea
   1. Apretar Enter
   1. Agregar estas líneas debajo:  

```
iokit = ctypes.cdll.LoadLibrary('/System/Library/Frameworks/IOKit.framework/IOKit')  
cf = ctypes.cdll.LoadLibrary('/System/Library/Frameworks/CoreFoundation.framework/CoreFoundation')
```
<br>
<!-- blank line -->
<figure class="video_container">
  <iframe src="https://res.cloudinary.com/reynagaassets/video/upload/v1616728718/DISOC/fix_big_sur.mov" width="100%" height= "400" frameborder="0" allowfullscreen="true"> </iframe>
</figure>
<!-- blank line -->
