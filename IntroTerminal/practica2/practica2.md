# Practica 2.

## Desafio
El desafío de esta clase consiste en crear un archivo con al menos 30 líneas de texto del lenguaje de programación que más te guste.
​
Luego de esto, crea dos nuevos archivos con el contenido de este archivo, uno con la primera mitad y el otro con la segunda mitad. Pero no puedes usar un editor de texto ni copiar el texto a mano, debes usar los comandos que estudiamos en clases anteriores para obtener el resultado que necesitas y enviarlo al archivo indicado.
​
Finalmente, usa el comando date para obtener la fecha y hora de hoy. Y añade ese resultado al final del primer archivo que creaste (el que debía tener al menos 30 líneas). No puedes copiar y pegar, debes hacerlo directamente desde la terminal y sin editores de texto. Pero ten mucho cuidado de no borrar el resto de contenido de tu archivo.

## Desarrollo.

- El archivo que vamos a ocupar se llama operatorias.php

```
# Contamos las lineas 
> cat operatorias.php | wc -l
36
# Creamos los documentos
> head -18 operatorias.php > texto1.php
> tail -18 operatorias.php > texto2.php

# agregamos la fecha de hoy al archivo operatorias.php
> date >> operatorias.php
```