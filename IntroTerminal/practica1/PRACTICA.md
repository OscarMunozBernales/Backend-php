# Práctica: Tratamiento de texto.

Vamos a estudiar algunos comandos para procesar texto y emitir un resultado. Te recomiendo que no solo te quedes con la lectura, sino que experimentes todo lo que quieras con estos comandos, ya que más adelante los necesitarás para completar los desafíos.

## Trabajo findamental con archivos de texto.
En clases anteriores estudiamos cómo crear y organizar nuestras carpetas. Ahora vamos a trabajar con archivos que, por su puesto, debemos guardar en estos directorios que previamente creamos.

- **touch**: Nos permite crear un archivo
``` 
> touch archivo.txt 
``` 

- **cat**: Nos permite visualizar todo el contenido de nuestro archivos.
```
> cat archivo.txt
```

- **head**: Es muy parecido al comando cat. También nos permite visualizar el contenido de nuestros archivos, pero debemos indicarle cuántas líneas nos debe mostrar. Por defecto nos mostrará las primeras 10 líneas
```
# Primeras 10 líenas
> head archivo.txt

# primeras 20 líneas
> head -n 20 archivo.txt
```

- **tail**: Funciona igual que el comando head, pero al revés. Tambien debemos indicarle cuántas líneas nos debe mostrar, la diferencia es que nos las mostrará de abajo hacia arriba. Por defecto nos mostrará las últimas 10 líneas

```
# Últimas 10 líneas
> tail archivo.txt

# Últimas 5 líneas
> tail -n 5 archivo.txt
```

## Búsqueda y tratamiento de texto.

No solo podemos visualizar niestro archivos (o parte de ellos) tal cual como escribimos, también podemos filtrar y cambiar el contenido que podemos ver en los archivos.

Por ejemplo: imagina que tenemos un archivo gigante, con cientos o incluso miles de líneas. Si imprimieramos el contenido de todo el archivo sería muy dificil encontrar el nombre de uan persona o elemento especifico.

Y se vuelve aún mas complicado si necesitamos que las palabras que buscamos cumplan ciertas condiciones, como solo mayúsculas, que la siguiente o anterior palabra cumpla  ciertas condiciones, etc.

En estos casos podemos utilizar el comando **grep** para filtrar las líneas que queremos visualizar utilizando (o no) expresiones regulares:

```
> grep "palabra-clave" archivo_gigante.txt
```

Si nos da igual si la palabra clave incluye mayúsculas o minúsculas podemos utilizar el flag **-i**:
```
> grep -i "palabra-clave" archivo_gigante.txt
```

También podemos verificar si la línea incluye esta palabra clave al final:
```
> grep "palabra-clave$" archivo_gigante.txt
```

O Si la incluye al principio
```
> grep "$palabra-clave" archivo_gigante.txt
```

También hay situaciones donde necesitamos modificar un poco la información que obtenemos de un archivo de text.

Por ejemplo, imagina que nuestro archivo contiene un poema, frase o saludo para responderle a los usuarios de nuestra aplicación. El problema es que cada usuario tiene un nombre diferente.

> !Hola, NOMBRE_USUARIO! Felicidades por completar tu desafio con PUNTOS_USUARIO puntos.

No queremos editar este archivo. Solo necesitamos cambiar los caracteres **NOMBRE_USUARIO** por el verdadero nombre del usuario.

Para esto podemos utilizar el comando **sed**. Solo debemos indicarle que queremos realizar una sustitución (**s/**), la palabra que vamos a cambiar(**NOMBRE_USUARIO**), la nueva palabra que vamos a incluir (**Violeta**) y cerrar con el simbolo **/.**

```
> sed 's/NOMBRE_USUARIO/Violeta/' archivo_gigante.txt
```

Ahora imagina que, ademas del nombre, debemos cambiar tambine la puntuación de obtuvo el usuario:

```
> set 's/NOMBRE_USUARIO/Violeta/; s/PUNTOS_USUARIO/1000' archivo_gigante.txt
```

Puedes ver muchos más usos del comando **sed** en este [Tutorial](https://likegeeks.com/es/sed-de-linux/)