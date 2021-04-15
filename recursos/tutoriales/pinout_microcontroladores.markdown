---
layout: page
title: Pinout Microcontroladores ESP8266
---

Existen distintas marcas y modelos de microcontroladores con el chip ESP8266,que es el que usaremos en este curso. Como existen distintos fabricantes, cada uno modifica el diseño de las placas según sus preferencias y eso nos genera distintos tipos de formatos, medidas y asignación de pines en cada una.  

Armamos una tabla con la asignación de pines de distintas placas para que puedan corroborar que están haciendo correctamente las conexiones en el circuito en base al código que usemos.

#### Tabla de correspondencias de pines

| Arduino | NodeMCU V3 y V1 | Wemos D1 Mini | Wemos D1 Mini Pro | Wemos D1 R1 |
| 0  | D3 | D3 | D3 | D8 |
| 1  | TX | TX | TX | TX |
| 2  | D4 | D4 | D4 | D9 |
| 3  | RX | RX | RX | RX |
| 4  | D2 | D2 | D2 | D4 |
| 5  | D1 | D1 | D1 | D3 |
| 6  | -  | -  | -  | - |
| 7  | -  | -  | -  | - |
| 8  | -  | -  | -  | - |
| 9  | S2 | -  | -  | - |
| 10 | S3 | -  | -  | -|
| 11 | -  | -  | -  | - |
| 12 | D6 | D6 | D6 | D6 |
| 13 | D7 | D7 | D7 | D7 |
| 14 | D5 | D5 | D5 | D5 |
| 15 | D8 | D8 | D8 | D10 |
| 16 | D0 | D0 | D0 | D2 |
| A0 | A0 | A0 | A0 | A0 |


### Cómo leer la tabla?
Por ejemplo para las placas NodeMCU V1, NodeMCU V3, Wemos D1 Mini y Wemos D1 Mini Pro,   

> *si en el código de Arduino usamos el pin 0, en nuestras placas estamos utilizando el pin D3,*   

a diferencia de la placa Wemos D1 R1 que el pin 0 de nuestro código corresponde con el pin RX.  

Esto se visualiza en el siguiente ejemplo Blink que viene incluido en Arduino. Para el LED utilizamos en el código el pin 0 que corresponde en la placa al pin D3.
<br>

[![Pinout NodeMCU V3](/assets/images/pines_ejemplo.png "Pinout Ejemplo")](/assets/images/pines_ejemplo.png){:height:200px}

<br>  
