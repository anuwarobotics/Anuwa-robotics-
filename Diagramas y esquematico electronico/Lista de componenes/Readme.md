# Lista de componentes

## ¿Que plataforma y tipo de archivo utilizamos?

Para la lista de componentes utilizamos archivos
1. **SVG** para realizar imagenes con escalado vectorial y no perder calidad al hacer zoom
2. **PNG** debido a ser uno de los estandares de imagenes mas común para uso en general
Los diagramas con todos los materiales se realizaron en la plataforma **Excalidraw** debido a ser *open source*
puede acceder a ella desde el link *https://excalidraw.com/*

## ¿Por que utilizamos esos componentes?

De entre los componentes mas destacados de nuestro proyecto destacamos el uso de
- **Nvidia Jetson AGX Orin**: Es la que ejecuta los modelos de IA localmente y realiza la mayor parte de calculos pesados,
en ella utilizamos aceleracion y optimizacion haciendo uso de la plataforma ***Cuda*** para aprovechar la GPU
- **Nvidia Jetson Orin nano**: Es necesaria para que mediante un cable displayport podamos dar video a nuestra pantalla HMI
de otra forma Ariyuu tendria que ser cableado para poder transmitir video, pero para darle la mayor autonomia en cuanto
a el movimiento se tefiere decidimos usar una segunda microcomputadora
- **Esp32**: Es el microcontrolador que utilizamos en cada una de nuestras unidades debido a que nos permite hacer uso de la
plataforma **IoT** de forma nativa, ademas su velocidad de reloj a 240mhz nos permite hacer calculos pesados

