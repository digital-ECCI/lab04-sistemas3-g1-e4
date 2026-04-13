
[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/0V8i2zWk)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23531322&assignment_repo_type=AssignmentRepo)
# Lab04: Visualización de Datos en Raspberry Pi con Node-RED 

## Integrantes
Juan David Santoyo Tejada - 118849
Cristian Andres Quintero Rodriguez - 112281
Monica Sofia Aljure - 87815

## Documentación

Descripción

En este laboratorio se desarrolló un flujo en Node-RED que permite seleccionar un color mediante un selector gráfico (color picker), visualizar sus valores en formato RGB y almacenarlos en un archivo de texto dentro de la Raspberry Pi. Posteriormente, estos datos pueden ser utilizados por un script en Python para su procesamiento.

Objetivos

* Implementar un flujo en Node-RED utilizando nodos del dashboard.
* Capturar valores de color en formato hexadecimal.
* Convertir valores HEX a RGB mediante una función en JavaScript.
* Visualizar los datos en una interfaz web.
* Almacenar los resultados en un archivo de texto.

Procedimiento

1. Instalación de Node-RED

Se realizó la instalación de Node-RED en la Raspberry Pi utilizando el script oficial:

```bash
bash <(curl -sL https://raw.githubusercontent.com/node-red/linux-installers/master/deb/update-nodejs-and-nodered)
```

Posteriormente, se inició el servicio con:

```bash
node-red-start
```

2. Acceso a la interfaz

Se accedió a la interfaz web desde un navegador mediante:

```
http://<IP_RASPBERRY>:1880
```
3. Instalación del Dashboard

Se instaló el paquete de dashboard para habilitar elementos gráficos:

```bash
cd ~/.node-red
npm install node-red-dashboard
```

4. Creación del flujo

Se implementó un flujo con los siguientes nodos:

* `ui_colour_picker`: permite seleccionar un color.
* `function`: convierte el valor hexadecimal a RGB.
* `ui_text`: muestra los valores RGB en la interfaz.
* `file`: guarda los valores en un archivo de texto.
* `debug`: muestra los datos en la consola de depuración.

5. Conversión de datos

El color seleccionado se recibe en formato hexadecimal y se convierte a RGB mediante el siguiente código:

```javascript
let hex = msg.payload;

// Convertir HEX a RGB
let r = parseInt(hex.substring(1,3), 16);
let g = parseInt(hex.substring(3,5), 16);
let b = parseInt(hex.substring(5,7), 16);

msg.payload = `R:${r}, G:${g}, B:${b}`;
return msg;
```
6. Visualización

Se accedió al dashboard mediante:

```
http://<IP_RASPBERRY>:1880/ui
```

Donde se visualiza el selector de color y los valores RGB generados.

7. Almacenamiento de datos

Los valores RGB se almacenan en el archivo:

```
/home/pi/rgb.txt
```

Cada vez que se selecciona un color, se agrega una nueva línea con los valores correspondientes.

Resultados obtenidos

* Se logró implementar correctamente un flujo funcional en Node-RED.
* Se pudo seleccionar colores de manera interactiva desde una interfaz web.
* Los valores fueron convertidos exitosamente de formato hexadecimal a RGB.
* Se visualizaron los datos en tiempo real en el dashboard.
* Se almacenaron correctamente los valores en un archivo de texto.

Ejemplo de salida:

```
R:255, G:0, B:0
R:120, G:45, B:200

Dificultades encontradas

* Problemas de conectividad de red (cambio de IP de la Raspberry Pi).
* Errores en la instalación de Node-RED por falta de memoria.
* Fallos en la instalación del dashboard por problemas de red.
* Configuración incorrecta del nodo `colour picker` (formato HEX en lugar de RGB).
* Error de configuración de nodos por falta de asignación de `Group` y `Tab`.

## Conclusiones

Conclusiones

El uso de Node-RED facilita la creación de aplicaciones interactivas mediante programación visual. Se logró integrar correctamente la adquisición de datos, su procesamiento y almacenamiento. Este laboratorio demuestra cómo Node-RED puede ser utilizado para el desarrollo rápido de interfaces IoT y la integración con scripts en Python para análisis posterior.

Archivos del proyecto

* `lab04_flow.json`: flujo de Node-RED exportado.
* `rgb.txt`: archivo generado con los valores RGB.
* `README.md`: documentación del laboratorio.
