# Diagramas de flujo de códigos

## ¿Qué plataforma utilizamos?
Los diagramas de flujo de nuestro equipo se realizaron en la plataforma [**Whismical**](https://whimsical.com/) , desde
la cual mediante cuadros de texto pudimos representar la lógica de nuestra programación, utilizamos 3 simbolos principales

1. **Pill**: Es la que define los inicios y finales de los algoritmos, la utilizamos de color celeste para dar incio
y rojo para finalizar, siendo facilmente distinguible
2. **Rectangle**: Es utilizado para representar mediante lenguaje natural el equivalente a funciones de alto nivel, en
este caso utilizamos un color verde
3. **Diamond**: Representa un condicional, es lo que le da la capacidad al robot de tomar sus propias decisiones en base
al estado en el cual se encuente al momento de evaluarlo

## ¿Por qué escogimos esta plataforma?

Esto se debe a que cuenta con diversas plantillas y cuadros de texto listos para usarse al estilo *drag and drop* lo cual
nos permite ahorrar tiempo mejorando la eficiencia y no nos limita a un *pseudocodigo* con reglas estrictas como **Pseint**
ademas al ser 100% online y no requierir de instalaciones nos permite trabajar desde cualquier ordenador con acceso a internet

## ¿Como lo implementaremos?

Para implementar estos diagramas en nuestro sistema robotico programaremos las placas esp32 en **C++** en Arduino ide debido a que
nos ofrece un punto medio de abstracción, no es tanta como micropython permitiendo optimizar el codigo pero no tan bajo nivel como
assembly o similares lo cual nos permite ahorrar tiempo de desarrollo. Las Nvidia Jetson AGX Orin y Orin nano se desarrollaran con
un backend en **Python** para poder ejecutar los modelos de IA en la plataforma donde son estandar mientras que el frontend lo
haremos en **HTML, CSS y Javascript** para poder personalizar al maximo el *localhost*.

> La comunicación entre unidades se realizará por *ESPNOW* esto nos permite tener una telemetria estable al ser el sistema de
comunicacion desarrollado por espressif

## Imagen de guia
![Imagen](https://raw.githubusercontent.com/anuwarobotics/Anuwa-robotics-/refs/heads/main/Diagramas%20de%20flujo%20codigos/Diagrama%20flujo%20joroi.png)
