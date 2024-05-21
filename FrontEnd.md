---
id: 8i1fj9vd8gbkw2pmatu3sv8
title: FrontEnd
desc: ''
updated: 1716298016682
created: 1716243280661
---

# Estructura de datos
https://javascript.info/array  
https://medium.com/techwomenc/estructuras-de-datos-a29062de5483
# Preguntas
* Estructuras contiguamente asignadas (arrays, matrices, heaps y hash tables)?
* Estructuras enlazadas(listas, árboles y gráfos)?
* Contenedores (stacks y queues)
* En que momento es conveniente usar cada estructura de datos? (array vs contenedores)

# Definición
Una estructura de datos es un conjunto de información agrupada. Existen estructuras de datos dinámicas y estáticas. La diferencia entre los 2 tipos es la capacidad que tienen para modificar su tamaño en medio de la ejecución del programa, las dinámicas pueden pero las estáticas no, además también hay estructuras **enlazadas y contiguas**

# Estructuras enlazadas
Este tipo de estructuras se caracteriza porque usa un mecanismo de "punteros" llamados nodos que apuntan al lugar donde está guardado el dato. Para trabajar con este tipo de estructuras hay que tener en cuenta que se debe guardar espacio para **el dato en sí a guardar y para la ubicación de la memoria del siguiente dato**. 

# Contenedores
Se caracterizan por la forma ordenada de recuperar los datos que depende de la forma en que se incertaron

## Stack(pila)
Este contenedor soporta la recuperación ordenada de datos LIFO(**Last Input - First Output** / Último en entrar - Primero en salir) lo que significa que el orden no importa 
![alt text](image-338.png)

## Queue (cola)
Soporta la recuperación ordenada de datos FIFO(**Firt Input - First Output** / Primero en entrar - Primero en salir) en este caso el orden si importa porque el dato que esté de primero es el que va a tener "toda la atención"
![alt text](image-339.png)

# HTML5
Es un lenguaje de etiquetas que permite definir la estructura de la página web, como los titulos, botones, párrafos, etc. HTML significa **Hypertext Markup Language - Lenguaje de Marcado de Hipertexto**. Para comentar se usa **\<!-- Comentario -->**

# Preguntas
* Como especificar la página de inicio sino se tiene un index?

## W3C 
World Wibe Consortium. Este estándar se crea con el fin de que todos los desarrolladores pueden entender el código que alguien más escribió. El sitio oficial es https://www.w3.org/ El estándar actual de HTML se encuentra en https://html.spec.whatwg.org/ 

## Nombrar archivos HTML
Se utiliza el método **kebab-case** que es todo en minúsculas y separar las palabras por guiones, es recomendable hacerlo en inglés 

# Etiquetas mínimas
## <!DOCTYPE>
Esta etiqueta le dice al nevegador que tipo de documento está por desplegar y le indica la versión de HTML que se uso para el desarrollo. Siempre debe ir en la parte superior

## \<html>
Es la etiqueta raíz dentro de la cual se deberan escribir las demás etiquetas. Se puede especificar el idioma principal con el atributo **lang**. Dentro de esta etiqueta también se debe declarar la **head** y **body**

## \<head>
Es la primera etiqueta que va después de la raíz (html). En esta etiqueta se van a definir elementos que no tienen efecto visual pero que son descriptivos para el navegador que tienen una relevancia, sin embargo, acá va la etiqueta **tittle** que si tienen un efecto visual

## \<body>
En esta etiqueta es donde van a estar ubicados la mayoria de elementos que el usuario va a poder ver

# Estructuración básica de textos
Además de tener en cuenta el uso de las etiquetas de párrafo (p) y de encabezados (h1-h6) hay que darle importancia a las etiquetas de negrita (b- bold), italica (i-cursiva) y underline (u-subrayado). Hay que mencionar que no se puede abusar de estas etiquetas ya que este formato es preferible darlo desde el **css**, en su lugar existen las etiquetas **strong** que se usa para señalar un texto importante en el documento y **em** que indica un fragmento de texto al cúal debe darse énfasis. 

# Estructuración básica de listas
