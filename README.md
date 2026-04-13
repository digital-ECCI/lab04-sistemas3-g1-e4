
[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/0V8i2zWk)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23531322&assignment_repo_type=AssignmentRepo)
# Lab04: Visualización de Datos en Raspberry Pi con Node-RED 

## Integrantes
Juan David Santoyo Tejada - 118849
Cristian Andres Quintero Rodriguez - 112281
Monica Sofia Aljure - 

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



## Conclusiones
