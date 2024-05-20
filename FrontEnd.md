---
id: 8i1fj9vd8gbkw2pmatu3sv8
title: FrontEnd
desc: ''
updated: 1716246687313
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