---
id: 8i1fj9vd8gbkw2pmatu3sv8
title: FrontEnd
desc: ''
updated: 1718234120665
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

## Linked List (Listas enlazadas)
Conjunto de **nodos** ordenados que contienen los valores que necesitamos, cada uno tiene un valor y una referencia al siguiente nodo. Hay 2 tipos de linked list, las simples **singly linked list** y las dobles **doubly linked list**. 
Hay que tener claro los conceptos: 
* value: es el valor que guardamos
* head: referencia la primer nodo de la lista
* tail: referencia al último nodo de la lista
* next: referencia de un nodo al siguiente nodo
* prev: referencia al nodo anterior

### syngly linked list
Cada nodo guarda, **un valor** y **referencia la siguiente nodo**. Ejemplo: 
Las sygly se observan como un edificio, donde cada piso es un nodo y si quiero ir al piso 5 tengo que pasar por el 1, 2, 3 y 4 para llegar al destino. Esta es una representación: 
![alt text](image-431.png)

### doubly linked list
Cada nodo tiene, **referencia al nodo siguiente(next), referencia al nodo anterior (prev), valor del nodo, referencia al primer nodo (head), referencia la último nodo**

![alt text](image-432.png)

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

## <html\>
Es la etiqueta raíz dentro de la cual se deberan escribir las demás etiquetas. Se puede especificar el idioma principal con el atributo **lang**. Dentro de esta etiqueta también se debe declarar la **head** y **body**

## <head\>
Es la primera etiqueta que va después de la raíz (html). En esta etiqueta se van a definir elementos que no tienen efecto visual pero que son descriptivos para el navegador que tienen una relevancia, sin embargo, acá va la etiqueta **tittle** que si tienen un efecto visual

## <body\>
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
Se usa para relacionar términos y sus definiciones. Para abrir una lista de este tipo se usa **\<dl\>**, para indicar un término en la lista se usa **\<dt\>** y para especificar la definición se usa **\<dd\>**
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
 Cascading Style Sheets - Hojas de estilo en cascada 

 # Selectores
 Es la parte del código css que indica a que elemento html se le va a aplicar el estilo
 ![alt text](image-375.png)

## Selector de elemento \<tag>
Es el elemento html explícito al que se le va a aplicar el estilo 
![alt text](image-376.png)

## Selector de clase (.)
Cualquier elemento html que en el atributo **class** tenga el nombre de la clase que se le va a aplicar el estilo, será modificado
![alt text](image-377.png)

## Selector id (#)
El estilo se aplicará a cualquier elemento html que en el atributo **id** coincida con el estilo. Solo se ve utilizar esta propiedad si en el documento hay algún estilo muy particular que se debe aplicar a un elemento
![alt text](image-378.png)

## pseudoclase (:)
Las pseudoclases dependen del elemento porque **todos no tienen los mismos**. Afectan al estado de un elemento según lo que se haga. Por ejemplo cambiar el color de un botón cuando el mouse esté sobre él 
![alt text](image-379.png)

## pseudoelementos (::)
Modifican el aspecto interno de la etiqueta. 
![alt text](image-380.png)

## Selector agrupados
El estilo se le aplica a la clase h1 y special   
![alt text](image-447.png)

## Selector de atributo 
El estilo se aplica si un atributo está presente en el elemento o si el atributo tiene un valor específico   
![alt text](image-448.png)
![alt text](image-449.png)

## Combinadores
El estilo se le aplica a los parrafos hijos directos de article
![alt text](image-450.png)

El siguiente estilo solo se le aplica al parrafo que hay después de un h1
![alt text](image-451.png)

Acá se seleccionan todos los elementos p que están después de un h1, sin importar que halla otros elementos entre un h1 y p
![alt text](image-452.png)

**Hay muchos selectores** 
https://www.w3schools.com/cssref/css_selectors.php

# Implementación de css
## inline
Son los estilos que se pueden aplicar a una etiqueta con el atributo **style**. **Es recomendable no usar este método para aplicar estilos ya que ensucia la estructura html**
![alt text](image-381.png)

## internal css
Son estilos dentro del documento html pero dentro de las etiquetas **\<style>\</style>**. Tampoco es recomendable usar este método para aplicar estilos
![alt text](image-382.png)

## external css
Es la manera más recomendada para aplicar estilos, se basa en un documentos .css que se encarga de gestionar todos los estilos del documento de html. Se enlazan con la etiqueta en el head \<link rel="stylesheet" href="">

# Especificidad
Marca la importancia que tiene un estilo a la hora de aplciarse a un elemento dependiendo del lugar donde fue definido y el selector usado. La jerarquía de los selectores es la siguiente: 
![alt text](image-383.png)

Para calcular la especificidad hay que tener en cuenta
![alt text](image-384.png)
![alt text](image-385.png)

Calculadora de especificidad https://www.codecaptain.io/tools/css-specificity-calculator

# Modelo de caja o box model
Es la forma en la que estan delimitados los elementos html. Hay 2 tipos de elementos: 
## Elementos en línea 
Son todos aquellos que conviven uno junto al otro sin generar saltos de línea como img, strong, span

## Elementos de bloque 
Representan elementos que implican un bloque lógico aislado, debe llevar un espacio antes y después de su aparición como las etiquetas div, p, article y section. 

## Display
Con la propiedad **display** de css es posible modificar el comportamiento de estos elementos
![alt text](image-386.png). 
* inline
* block
* flex, permite maquetar de una manera más fácil las páginas. Hay un contenedor llamado **flexbox** que contiene la propiedad **display: flex**, desde ese contenedor se podrá: 
![alt text](image-404.png)
Esto permite diseños flexibles, alineación de elementos y reordenar contenido sin tocar el código HTML

## Elementos básicos de flexbox
![alt text](image-405.png)
* item: son los cuadros verdes, lo que está dentro del contenedor
* eje principal (barra morada) es la orientación de lso items

Para manipular la dirección y comportamiento de los items del flexbox se usan las propiedades **flex-direction y flex-wrap**, flex wrap permite que los items no se salgan o sí dependiendo del valor. 
![alt text](image-406.png)
![alt text](image-407.png)
Así se ve un contenedor con **flex-wrap: wrap**, el contenedor crece para permitir que los items quepan, en cambio con **flex-wrap: nowrap** los elementos se ponen más pequeños: 
![alt text](image-427.png)
![alt text](image-428.png)
La propiedad de **justify-content** permite acomodar los items dentro del contenedor con respecto al eje principal
![alt text](image-408.png)
![alt text](image-409.png)
![alt text](image-410.png)
![alt text](image-411.png)
![alt text](image-412.png)
![alt text](image-413.png)
**align-items** permite acomodar los items con respecto al eje secundario
![alt text](image-414.png)
![alt text](image-415.png)
![alt text](image-416.png)
![alt text](image-417.png)
![alt text](image-418.png)
![alt text](image-419.png)

Las propiedades anteriores son propiedades que se aplican al **contenedor** excepto **align-self** que se aplica a los items, las siguientes propiedades se aplican a los items. Así se vería align-self: 
![alt text](image-429.png)
El contenedor tiene definido **align-items: flex-end** (osea que los elementos están ordenados en posición horizontal así que el eje secudnario es el vertical) pero los elementos 1 y 4 tienen la propiedad **align-self: flex-start** acomoda los elementos respecto al eje secundario lo que provoca ese cambio 
![alt text](image-420.png)
Profundizar como funciona esta propiedad
![alt text](image-421.png)
![alt text](image-422.png)
![alt text](image-423.png)
![alt text](image-424.png)
![alt text](image-425.png)
![alt text](image-426.png)

# Tipografía 
![alt text](image-387.png)
Google tiene un repertorio de fuentes en su producto gratuito **Google fonts**. Para asegurarse de que la tipografía se cargue exitosamente, se tienen 2 opciones: 
## Descargar localmente la fuente
![alt text](image-388.png)
 
## CDN
![alt text](image-389.png)
Este ejemplo es de Google font

## Tamaño 
Los tamaños de la tipografía se puede especificar con: 
![alt text](image-390.png)

## Medidas absolutas
Representan un tamaño específico
![alt text](image-391.png)

## Medida relativa
![alt text](image-392.png)

## Medida específica
![alt text](image-393.png)

Solamente con la propiedad **font-size** se puede específicar de diferentes formas el tamaño

## Estilo de la tipografía
![alt text](image-394.png)

# Peso de la tipografía 
Se refiere al grosor de la letra
## Valores abosolutos
![alt text](image-395.png)

## Valores relativos
![alt text](image-396.png)

## Númericos
![alt text](image-397.png)

El grosor se define en el atributo **font-weight**


# Backgroun image
object fit le dice a la imágen como redimensionarse en su contenedor para caber. Puede ser containe, cover, fill, none, scale-down
* Fill, este es el valor por defecto de la propiedad **object fit**. La imágen cambia de tamaño para llenar la dimensión dada, de ser necesario la imágen se aplasta o se estira para que quepa en el contenedor
* contain, la imágen mantiene su relación de aspecto pero se cambia de tamaño para ajustarse a la dimensión dada
* cover, la imágen mantiene su relación de aspecto y llena la dimensión dada. La imágen se cortara para ajustarse
* none, la imágen no cambia de tamaño
* scale down, la imágen se reduce a la versión más pequeña de none o containe

Para especificar las dimensiones de una imágen se usan los atributos width y height que es ancho y alto

# Inherit
Es un valor permitido en todas las propiedades de css. Hce que el elemento al cual se le aplica tome el valor calculado de la propiedad de su elemento padre

# Decorar una lista
![alt text](image-399.png)
![alt text](image-400.png)
![alt text](image-401.png)
![alt text](image-402.png)
![alt text](image-403.png)

# Maquetación 
Es la etapa en la que se estrucutra, se ordena y distribuyen los elementos del sitio web como menús, imágenes, botones, videos, enlaces, titulos, etc. 

# Grid  
css grid layout permite hacer las páginas más flexibles dependiendo del tamaño de la pantalla. Se puede organizar el contenido en filas y columnas. Para usar un diseño grid, hay que definir el display del contenedor como **grid**. 
**grid-template-rows:** define cuantas filas va a tener la tabla, **grid-template-columns:** define cuantas columnas tendrá la tabla, **grid-template-areas** define el nombre de cada cuadriculo. Por ejemplo: 
![alt text](image-433.png)
Este es el result
![alt text](image-434.png)
O también puede ser: 
![alt text](image-435.png)
![alt text](image-436.png)

# Responsive

Técnica de diseño web. NO importa desde que dispositivo se acceda a la página, siempre se va a mostrar el contenido de manera correcta

# Media queries
Con esta técnica se pueden definir estilos completamente diferentes dependiendo del tamaño del dispositivo
![alt text](image-437.png)
![alt text](image-438.png)
![alt text](image-439.png)
![alt text](image-440.png)
![alt text](image-441.png)
![alt text](image-442.png)
 Por ejemplo: 
 Si la pantalla tiene un ancho mínimo de 900px:
 ![alt text](image-443.png)
así se ve:
![alt text](image-444.png)
Y si la pantalla tiene un ancho máximo de 700px: 
![alt text](image-445.png)
![alt text](image-446.png)

# Librerias CSS
![alt text](image-453.png)
![alt text](image-454.png)

# Angular






















































































































































































