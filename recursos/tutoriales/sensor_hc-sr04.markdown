---
layout: page
title: Utilizar el sensor HC-SR04
---

[![Sensor ultrasónico HC-SR04](/assets/images/sensor_hcsr04.jpg "Sensor Ultrasónico HC-SR04")](/assets/images/sensor_hcsr04.jpg){:height:100px}

El HC-SR04 es un sensor de distancia de baja precisión basado en ultrasonidos. Con él es posible medir distancias de una forma sencilla y rápida, aunque en principio no se suele usar para eso. Lo más frecuente es que se utilice como un transductor para detectar obstáculos y poderlos evitar mediante otros mecanismos asociados a la respuesta del sensor.

### Simulador de funcionamiento

[![Simulador de sensor ultrasónico HC-SR04](/assets/images/sensor_hcsr04-tinkercad.jpg "Simulador Sensor    Ultrasónico HC-SR04")](/assets/images/sensor_hcsr04-tinkercad.jpg){:height:100px}

[Enlace a simulador de Tinkercad](https://www.tinkercad.com/things/2Db2m3GreDt-cool-fyyran-tumelo/editel?tenant=circuits){:target="_blank"}


#### Código de ejemplo  
En el siguiente ejemplo encendemos un led en función de la distancia en el último if.

    // ---------------------------------------------------------------- //
    // Arduino Ultrasoninc Sensor HC-SR04
    // Re-writed by Arbi Abdul Jabbaar
    // Edited Cristian Reynaga
    // Using Arduino IDE 1.8.7
    // Using HC-SR04 Module
    // Tested on 30 May 2021
    // ---------------------------------------------------------------- //
 
    #define echoPin 2 // attach pin D2 Arduino to pin Echo of HC-SR04
    #define trigPin 3 //attach pin D3 Arduino to pin Trig of HC-SR04
 
    #define led 13 // led que voy a encender
 
    // defines variables
    long duration; // variable for the duration of sound wave travel
    int distance; // variable for the distance measurement
 
    void setup() {
      pinMode(trigPin, OUTPUT); // Sets the trigPin as an OUTPUT
      pinMode(echoPin, INPUT); // Sets the echoPin as an INPUT
      pinMode(led, OUTPUT);
   
      Serial.begin(9600); // // Serial Communication is starting with 9600 of baudrate speed
      Serial.println("Ultrasonic Sensor HC-SR04 Test"); // print some text in Serial Monitor
      Serial.println("with Arduino UNO R3");
    }

    void loop() {
      // Clears the trigPin condition
      digitalWrite(trigPin, LOW);
      delayMicroseconds(2);
      // Sets the trigPin HIGH (ACTIVE) for 10 microseconds
      digitalWrite(trigPin, HIGH);
      delayMicroseconds(10);
      digitalWrite(trigPin, LOW);
      // Reads the echoPin, returns the sound wave travel time in microseconds
      duration = pulseIn(echoPin, HIGH);
      // Calculating the distance
      distance = duration * 0.034 / 2; // Speed of sound wave divided by 2 (go and back)
      // Displays the distance on the Serial Monitor
      Serial.print("Distance: ");
      Serial.print(distance);
      Serial.println(" cm");
 
      //Con el siguiente if consulto el valor de la variable distance y enciendo led si cumple la condición
      if(distance < 100){
         digitalWrite(led, HIGH);
      }else{
         digitalWrite(led, LOW);
      }
    }
 


[Enlace a documentación y tutorial](https://create.arduino.cc/projecthub/abdularbi17/ultrasonic-sensor-hc-sr04-with-arduino-tutorial-327ff6){:target="_blank"}