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

# 2. APrneder a manipular archivos a través de la terminal.

## 2.1. ¿Qué es y cómo funciona el sistema de archivos?  - Organización de archivos.
Cada archivo esta compuesto por su nombre y ubicación, esto es lo que llamamos el path
```
directorio/directorio/archivo.ext
```
Cabe recalcar que dentro de un directorio no puede existir dos archivos con los mismos nombre, ademas que los archivos no pueden tener caracteres especiales.
Ahora vamos a mostrar unos comandos que sirven para organizar los archivos:
> ls: muestra los archivos del direcctorio.

> ls -a: muestra todos los archivos del directorio incluso los ocultos.

> pwd: nos muestra la ubicación en la que nos encontramos.

> cd: sirve para cambiar de directorio.

> mkdir: crea un directorio.

> cp archivo ubicación archivo a copiar: copia un archivo

> rm: borra un archivo.

> mv: mueve un archivo.

> rmdir: borra un directorio.


## 2.2. Comandos para trabajar desde nuestra ubicación

Lista los archivos que se encuentran en el directorio sobre el que estamos trabajando:

> ls

Lista todos los archivos incluyendo aquellos que se han definido como ocultos:

> ls -a

Todos los directorios contienen los archivos . y .., estos son punteros a directorios.

> .. --> directorio padre
> . --> directorio actual

Otros parámetros que puedes usar con el comando ls:

Ordena los archivos por fecha de modificación:

> ls -t

Ordena elementos primero por nombre y después por extensión:

> ls -x

Ordena los elementos primero por extensión y luego por nombre:

> ls -X

Muestra toda la información: usuario, grupo, permisos, tamaño, fecha y hora de creación.

> ls -l

Muestra la misma información que ls -l pero con las unidades de tamaño en KB, MB:

> ls -lh

Muestra el contenido de todos los subdirectorios de forma recursiva:

> ls -R

Ordena los resultados por tamaño de archivo:

> ls -S

### Comandos para cambiar de ubicación

Print Working Directory: se usa para mostrar el directorio actual en el que nos encontramos trabajando.

> pwd

cd: se utiliza para cambiar de directorio. Luego del comando se debe especificar la ruta del directorio al que nos queremos mover. Por ejemplo:

> cd /home/mi_usuario

Comandos para mover, copiar o borrar

cp: copiar un archivo hacia un directorio.

> cp [archivo que se va a copiar] [directorio hacia el que se va a mover]

rm: eliminar un archivo.

> rm archivo.txt

`mv``: mover un archivo, cambiar su ubicación. La sintaxis es así:

>mv [ruta del archivo] [directorio hacia el que se va a mover]

rmdir: eliminar un directorio. En este caso es importante resaltar que, para que el directorio pueda ser eliminado, no puede contener archivos u otros directorios en su interior.

> rmdir [ruta / nombre del directorio a eliminar]

## 2.3. Manejo de archivos binario y utilidades interectivas.
De todos los archivos que hay en nuestra computadora hay una distinción muy importante, los archivos binarios y de texto.

Los archivos binarios, son programas ejecutables, documentos fotos, videos, etc.

Los archivos de texto, tambien son archivos binarios pero que son legibles para los humanos.

Utilidades interactivas, programas que procesan texnto en tiempo real

Alguna de ellos son VIM  y nano.

## 2.4. Utilidades batch y batch avandados.
Utilidades batch o procesamiento por lotes, son programas que procesan texto y emiten el resultado.

Utilidades Batch
cat: Nos muestra el contenido completo de un archivo

> cat tables.txt

head: Nos muestra las primeras lineas (También podemos escoger cuantas lineas queremos utilizando el modificador [-n #]).
Ejemplos:

> head tables.txt

> head -n 5 tables.txt

tail: Muestras las ultimas lineas del final (Inverso a head, tambien le funciona modificadores)
Ejemplos:

> tailtables.txt

> tail -n 5 tables.txt
    
### Utilidades Batch Avanzadas:
    
grep: Permite trabajar con expresiones regulares, funciona como un buscador dentro del archivo.

> grep hanks dump1.sql = [comando][expresión regular][archivo]

> Para buscar sin importar si esta en mayuscula o miniscula:

> grep -i hanks dump1.sql

> Tambien podemos buscar una expresión de una frase que termine con la misma palabra que estemos buscando:

> grep -i “hanks’),$” .

sed: Screem Editor, tratamiento de flujos de caracteres. Este comando nos permite reemplazar una expresión por otra.
ejemplos:

> sed ‘s/hanks/selleck/g’ dump1.sql = [comando][subcomando- sustitución][expresión original][nueva expresión][modificador-(/g de global, indica que tiene que hacerse a lo largo de todo el flujo)][Indicar cual es el flujo a utilizar (Archivo de texto)]

SED no modifica el archivo, lo que hace es crear un nuevo flujo con la modificación

Para eliminar la ultima linea podemos utilizar:

> sed ‘$d’ nuevasPelis.csv = [Comando][’$sub-comando’][archivo]

awk: Trataminento de texto delimitado, este comando sirve para trabajar con archivos de textos delimitados por comas.
Ejemplos:

> awk -F ‘;’ ‘{ print $1}’ nuevasPelis.csv

# 3. Comprender los mecanismos de comunicación y Administración entre procesos.

## 3.1. Comunicación entre procesos: Qué són y cómo se utilizan los flujos estándar