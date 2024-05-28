---
id: 8i1fj9vd8gbkw2pmatu3sv8
title: FrontEnd
desc: ''
updated: 1716854462400
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
## Listas desordenadas
Son las listas que tienen viñetas. Se usa la etiqueta **\<ul>** para definirlas y la etiqueta **\<li>** para agregar elementos
![alt text](image-341.png)

## Listas ordenadas
![alt text](image-342.png)
Las listas ordenadas tienen algunos atributos que pueden ser utiles: 
![alt text](image-344.png)

## Listas de definiciones
Se usa para relacionar términos y sus definiciones. Para abrir una lista de este tipo se usa **\<dl>**, para indicar un término en la lista se usa **\<dt>** y para especificar la definición se usa **\<dd>**
![alt text](image-343.png)

# Hipervínculos

Para usarlos se necesita la etiqueta anchor **\<a>**, para saber a donde apunta la etiqueta se usan los atributos **href** se le indica el link y **target** se usa para indicar DONDE se abren si en una nueva pestaña, ventana, etc. 

## Anclas
Son enlaces que redireccionan a algún elemento en la misma página. Para poder usar esto el elemento debe tener un id
![alt text](image-345.png)

# Forms
Los formularios son usados para recopilar información de los usuarios **\<form>\</form>**
Los elementos que comunmente van dentro de un form son:
 
## Input
**\<input>**, sirve para darle la posibilidad al user de ingresar información. Puede tener varios tipos: 
![alt text](image-346.png)

## Select
Se usa para generar una lista desplegable **\<select>\</select>**, para agregar elementos a la lista se usa **\<option>\</option>**. Es importante tener en cuenta el atributo de value para el option ya que ese es el valor que se va a almacenar cuando el usuario selecciona, que es diferente al valor mostrado. 
![alt text](image-347.png)

## textarea
Es una caja de texto con mayor capacidad que un input normal. Se aplica **\<textarea>\</textarea>**

## fildset
Agrupa varios campos que están relacionados a un mismo conjunto de datos
![alt text](image-348.png)
![alt text](image-350.png)

## legend
Se usa para darle un titulo al conjunto de datos que se agruparon con fildset. El "titulo" de "Datos personales" es gracias a la etiqueta legend
![alt text](image-349.png)

## optgroup
Permite agrupar varias opciones de una lista desplegable
![alt text](image-351.png)

## Enviar datos de un formulario
### Button
Para enviar datos de un form lo primero que hay que hacer es crear un botón y definir su atributo **type** según lo que se quiere que haga el botón 
![alt text](image-352.png)

### method
Es la manera en como los datos se van a enviar. **get** muestra los datos en la URL. El inicio del envío de los datos va a aparecer con un ? y serán formateados como un par clave-valor separados por un ampersand (&). Estos signos se conocen como **query params**. Post manda los datos de forma que no sean visibles en la URL

### action
Es el atributo de form donde se especifica la página que procesa los datos que el formulario envió

# Metaetiquetas
Sirven para describir con mucha presición el contenido del sitio web. Para declarar los metedatos se hace en la etiqueta **head**

## Etiqueta link
Se usa para enlazar nuestra página con contenido extra de otra página. Debe tener 2 atributos como mínimo: **rel** establece el contenido entre mi página y la página a enlazar y el atributo **href** para especificar la ubicación del contenido a enlazar
![alt text](image-353.png)
![alt text](image-354.png)
Esta etiqueta se usa normalmente para usar css: 
![alt text](image-355.png)

## Meta
Con esta etiqueta se definen varias caracteristicas como:
![alt text](image-356.png)
de esta manera se establece el conjunto de caracteres que el documento va a usar
![alt text](image-357.png)
Con esta etiqueta nos aseguramos de que el contenido de la página se ajuste a la pantalla del dispositivo

## SEO (Search Engine Optimitazion)
Esta técnica consiste en agregar distintas metaetiquetas con el fin de que los motores de búsqueda puedan mostrar nuestra página en los primeros resultados. 
![alt text](image-358.png)
![alt text](image-359.png)
![alt text](image-360.png)

## Modificadores de headers
![alt text](image-361.png)

## Especificar datos para robots
### Crawlers o indexador o rastreador
Es un programa informático que se encarga de hacer una copia de todos los enlaces que hay en las páginas web y crear una copia en su base de datos para interconectar millones de páginas web

### robots.txt
Estos archivos le dicen al crawler que contenido es innecesario de la página para tener en cuenta al momento de indexar
![alt text](image-362.png)
Con esta etiqueta también le decimos al robot que información indexar y cúal no. no archive le dice al motor de búsqueda que no guarde la página en el archivo y **nosnipped** le dice al motor de búsqueda que no liste la página en los motores de búsqueda

# Etiquetas de recursos
## etiqueta img
Se usa para mostrar imágenes en la página. Necesita de los atributos **src** que especifica la dirección donde está alojada la imágen, puede ser en el directorio de la página y **alt** que sirve para especificar un texto alternativo que va a describir el contenido de la imágen en caso de que el recurso no se pueda cargar o para usuario que necesiten ayuda visual. **\<img />**

## Etiqueta de audio
**\<audio controls>\</audio>** el atributo de controls debe ir para que aparezca el reproductor. 
![alt text](image-363.png)

Es posible especificar diversas fuentes de reproducción de audio para que el navegador tome la elección que más convenga
![alt text](image-364.png)

## MIME TYPE
Es una forma estandarizada de indicar la naturaleza de un archivo, documento o conjunto de datos
https://developer.mozilla.org/es/docs/Web/HTTP/Basics_of_HTTP/MIME_types

https://www.iana.org/assignments/media-types/media-types.xhtml#audio

## Etiqueta de video 

**\<vide>\</video>**
![alt text](image-365.png)

## Etiqueta de iframe
Sirve para incrustar contenidos a mi sitio web, como videos desde youtube con el fin de hacer más ligero mi sitio. Por ejemplo para insertar videos de youtube: 
![alt text](image-366.png)
![alt text](image-367.png)

# Semántica en HTML

Es la forma correcta de escribir los elementos con código. Una etiqueta es semántica cuando indica el contenido que tiene. Por ejemplo la etiqueta **\<section>** se usa para indicar que hay un capítulo o sección dentro de la página. Hacer buen uso de las etiquetas semánticas permiten una mejor indexación de los buscadores 
![alt text](image-368.png)
![alt text](image-369.png)
html5doctor.com

Todos los elementos de html5: https://html5doctor.com/element-index/

Hoja de trampa: https://learntheweb.courses/topics/html-semantics-cheat-sheet/

## span y div
 Estas etiquetas solo se deben usar cuando el contenido que se quiere representar no pueda ser incluido en las etiquetas semánticas existentes. **profundizar en su uso**

 ## header
 Se usa para marcar un grupo de elementos de introducción (titulo, logo, info de contacto y otros elementos introductorios que identifican el sitio web) o de navegación dentro de una sección o documento. Puede contener el índice de una sección, formulario de búsqueda y logos relevantes. Se puede usar 1 etiqueta header por cada sección del documento
 ![alt text](image-370.png)

 ## hgroup
 Agrupa un conjunto de uno o más encabezados, h1-h6. Su uso más común es ajuntar el título de la página con su eslogan. **Se eliminón en el estándar de HTML5 en 2018, se debe evitar su uso**

 ## nav
 Se usa para marcar una sección cuya función sea la navegación por la página web. 
 ![alt text](image-371.png)

 ## main
 Sirve como contenedor de la parte más importante de un documento. No debe haber más de una etiqueta main en un documento y esta debe ser descendiente de una de las siguientes etiquetas: html, body, div o form. 

 ## article
 Se usa para marcar un contenido independiente que tendría sentido en otro contexto diferente al tratado en el documento y que podría usar información que viene de otros sitios. Se usa para marcar información que viene de otro sitio
 ![alt text](image-372.png)

 ## section
 Se usa para marcar una sección genérica de una app o documento, es una agrupación temática del contenido
 ![alt text](image-373.png)

 ## aside
 Marca un trozo de contenido que está relacionado con el contendio de la página pero que no hace parte del mismo ![alt text](image-374.png)

 ## footer
 Se usa para marcar el pie de una sección o de un documento

 # CSS








































































































































































































