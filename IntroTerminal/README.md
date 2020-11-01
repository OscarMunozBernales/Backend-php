# Curso de introducción a la terminal y lineas de comando

# 1. Introducción.
En este curso vamos aprender lo siguiente:
- Qué es la terminal.
- Por qué usar la terminal.
- Cómo usar la terminal.
- Cómo aprovechar la terminal al maximo.

## 1.1. ¿Que es y como funciona la terminal?
Para empezar vamos a explicar que es una computadora (a grandes rasgos), en una computadora tenemos memoria, en esa memoria se almacenan instrucciones yu algunos datos, lo que hace la computadora es revisar periodicamente esa memoria, levantar una instrucción, ejecutarla y guardar los resultados (eso se repite constantemente).
La computadora tiene un lenguaje unico que no es complatible con nuestro lenguajes, es por esto que tenemos una terminal, algo asi como un intermediario entre la computadora y nosotros. Lo mismo que se puede realizar en una interfaz grafica se puede ejecutar en una terminal.

### Los comandos.
Un comando consiste en:
- Nombre del programa.
- Parámetros.
- Modificadores.

La diferencia entre los parametros y los modificadores, es que los modificadores alteran una instrucción y los parametros son simplemente información adicional para la ejecución de un programa.

```
comando -flag1 -flag2 -arg1 -arg2 
```

Vamos a ver unos comandos:
- date: muestra la fecha de hoy.
- echo "mensaje": muestra un mensaje en la pantalla
- man: es un manual que muestra información de un comando, por ejemplo **man date**
- history: muestra el historial de todos los comandos escritos.
- !hash (sacado del history): ejecuta el comando del hash

Utilidades de CLI.
- autocompletar con la tecla tab.
- la flecha para arriba muestra los comandos ya escritos.

## 1.2. ¿Qué es y cómo funciona el sistema de archivos?  - Organización de archivos.
Cada archivo esta compuesto por su nombre y ubicación, esto es lo que llamamos el path
```
directorio/directorio/archivo.ext
```
Cabe recalcar que dentro de un directorio no puede existir dos archivos con los mismos nombre, ademas que los archivos no pueden tener caracteres especiales.
Ahora vamos a mostrar unos comandos que sirven para organizar los archivos:
- ls: muestra los archivos del direcctorio.
- ls -a: muestra todos los archivos del directorio incluso los ocultos.
- pwd: nos muestra la ubicación en la que nos encontramos.
- cd: sirve para cambiar de directorio.
- mkdir: crea un directorio.
- cp archivo ubicación archivo a copiar: copia un archivo
- rm: borra un archivo.
- mv: mueve un archivo.
- rmdir: borra un directorio.
