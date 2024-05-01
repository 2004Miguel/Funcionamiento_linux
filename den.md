---
id: th13t6zh9qgxuou3hsx7p80
title: La línea de comandos en Linux
desc: ''
updated: 1714519153156
created: 1712061762517
---
## Que es el shell?

Shell es la forma de referirce a un progrma generico que interpreta comandos. 


## Que es Bash?
bash es un programa de shell que interpreta comandos.

## Que es un comando ?
![alt text](image-20.png)

## Redireccionamiento I/O
* Normalmente la salida de un programa en la consola es de 2 tipos: Los resultados del programa (que se mandan a un archivo especial llamado standard output/stdout) y los errores y estados que se produscan (que se van a un archivo especial llamado standard error/stderr). Por defecto tanto la salida estándar como el error estándar no se guardan en el disco duro sino que están enlazados en la pantalla. La entrada de una aplicación se llama standard input/stdin que por defecto está **asociada al teclado**
* Para redireccionar la salida estándar de un comando a un archivo, se utiliza el operador **>**. Así: **ls -l /usr/bin > ls-output.txt**. Los resultados del comando ls se han mandado al archivo de texto. 
* Si la salida estándar de un comando da error y este se está redireccionando a un archivo y está bien desarrollado el comando, el archivo quedará vacío porque los errores no están configurados para la salida estándar sino para el **error estándar**. 
* Un truco para crear un archivo truncado o vacío a partir del redireccionamiento se puede usar: **> archivo.txt**
* El operador **>>** añade la salida de un comando a un archivo (sino existe lo crea) y no lo sobreescribe desde el principio como hace **>**. **ls -l /usr/bin >> ls-output.txt** sino que siempre va a añadir más contenido en ves de sobreescribir algo

## Redirigiendo el error estándar
* El shell no entiende entrada, salida y error estándar sino que utiliza **descriptor de archivos (file descriptor)**, el shell se refiere a esas cadenas con los descriptores 0, 1 y 2. Ejemplo: **ls -l /bin/usr 2> ls-error.txt** esa instrucción va a dar un error porque ese directorio no existe, entonces el error se va a guardar en el archivo ls-error.txt. 

## Eliminar salidas innecesarias
Cuando no se quiera ver la salida ni el error de un comando, se puede hacer: ls -l /bin/usr 2> /dev/null. El archivo null es un archivo especial que acepta entradas y no hace nada con ellas


## Redirigir la salida estándar y el error estándar al mismo tiempo
Existen 2 formas para hacer eso, una antigua y otra más moderna y eficiente: 
1. ls -l /bin/usr > ls-output.txt 2>&1. Primero redirigimos la salida estándar al archivo ls-output.txt y después redirigimos el descriptor de archivo 2 (error estándar) al descriptor de archivo 1 (salida estándar) usando la notación 2>&1. La redirección del error siempre debe ir después de la redirección de la salida o sino no funciona. 
2. El método más moderno: ls -l /bin/usr &> ls-output.txt. También se puede utilizar ls -l /bin/usr &>> ls-output.txt para **agregar** en vez de sobreescribir.  

## Redireccionando la entrada estándar
Un comando para hacer esto, es cat. Por defecto la entrada estándar es el teclado, haci que si se usa cat sin argumentos la consola se va a quedar esperando a que escribas algo. Para cambiar la entrada estándar de el teclado a un archivo se usa: cat < lazy_dog.txt y se va a mostrar el contenido del archivo

## Pipeline (tuberías)
Usando un pipe(tubo |) se puede usar la salida estándar de un comando para que sea la entrada estándar de otro. Por ejemplo: **ls -lhF /usr/bin | less** Lo que hace este comando es que el listado del directorio se va a poder ver página por página porque está combinado con less. Hay que entender la diferencia entre el operador > y |.
El operador de > se usa para: comando > archivo y el operador de | se usa para: comando | comando ya que el operador > va a tratar de "guardar/sobreescribir/añadir" la salida de un comando en el archivo siguiente, mientras que el operador | se usa para enlazar salidas y entradas de comandos (**ejemplo en la página 46 del usuario que daño el programa less**)

## Filtros
A menudo los pipe son usados como filtros: 
queremos hacer una lista combinada de todos los
programas ejecutables en **/bin** y en **/usr/bin**, que los ponga en orden y los veamos: **ls /bin /usr/bin | sort | less**



## Sintáxis de la salida de la ayuda de un comando
![alt text](image-21.png)

## Organización de la mana page
![alt text](image-22.png)

## Argumentos más comunes de ls
![alt text](image.png)
* -i. Sirve para ver el inodo de los archivos. Útil para saber si un enlace y un archivo sí son el mismo
* Una manera de mostrar solo los directorios con ls es: **ls -lhF | grep /**. l: long, h: human, F: classify

## Argumentos más utilizados para cp
![alt text](image-11.png)
![alt text](image-12.png)

## Ejemplos de cp
![alt text](image-13.png)


## Argumentos más usados de mv
![alt text](image-14.png)

## Ejemplos de mv
![alt text](image-15.png)

## Argumentos más usados de rm
![alt text](image-17.png)

## Ejemplos de rm
![alt text](image-18.png)
![alt text](image-19.png)


## Atajos más útiles de less
![alt text](image-2.png)

## Rutas importantes
![alt text](image-3.png)
![alt text](image-4.png)
![alt text](image-5.png)
![alt text](image-6.png)
![alt text](image-7.png)

## Enlaces simbólicos
Es un archivo referenciado por multiples nombres. Por ejemplo, hay programas x que necesitan recursos compartidos de foo pero este último cambia constamente de versión, el problema es que al cambiar de versión (de nombre) habría que ir a cambiar el nombre también en los programas x que usen recursos de foo. Para solucionar esto se hacen enlaces simbólicos, entonces los programas x pueden seguir usando foo pero foo va a apuntar a una versión específica y así solo habría que hacer un cambio cada vez que se actualice la versión. Son más modernos que los enlaces duros(**PÁGINA 19 y 27**)

## Enlaces duros
Hay 2 limitaciones con este tipo de enlaces: 
1. Un enlace no puede enlazar archivos que no estén en la misma particón de disco que el.
2. Un enlace duro no puede enlazar a un directorio 



## Comodines para nombres de archivos
![alt text](image-8.png)

## Clases de caracteres más usados
![alt text](image-9.png)

## Ejemplo de comodines
![alt text](image-10.png)

## Caracteres de escape
![alt text](image-24.png)

## Movimientos del cursor con el teclado
![alt text](image-25.png)

## Movimientos con el teclado en la terminal
* Con alt + num se mueve al pestaña que pertenezca al número
* Con alt + shift + w cierra una pestaña
* Con ctrl + shift + q cierra la terminal

## Edición de texto
![alt text](image-26.png)

## Cortar y pegar
![alt text](image-27.png)

## Comandos de completado
![alt text](image-28.png) **pag 61**

## Pendiente de consulta
* Jerarquía estándar del Sistema de Archivos Linux (FSSTND Y ficheros)
![alt text](image-164.png)
https://blog.alcancelibre.org/staticpages/index.php/estandar-jerarquia-sistema-archivos
* Formato de texto ASCII
* Todos los comodines para nombres de archivos
* Enlaces duros y simbólicos
* Expansión en el bash y entrecomillado (**pag 51**)
* Teletipos
* Libreria del bash **Readline**
* Completado programable (Ubuntu)
* Con script se puede grabar una sesión
* Como funcionaban las terminales (pc's no personales)
* Permisos especiales (setuid root, setgid bit, sticky bit)
* BSD
* PATH
* POSIX
* Código ANSI
* SHA256
* IEEE 1003 (API's)
* XML
* ROT13(ofuscación de texto)
* Documento-aqui
* Comer ver los repositorios desde donde se van a descargar los paquetes
* Como agregar nuevos repositorios para la descarga de paquetes
* Sistema X Window
* Que es APT
* que es dpkg
* que es una checksum


## Comandos básicos

* Casi todos los siguientes comandos vienen del paquete **coreutils**. 
* Es posible escribir varios comandos en una línea de la terminal, cada comando debe ir separado por un punto y coma (;): comando1; comando2; comando3...
* Para ver las viriables del sistema, se puede usar **printenv | less**

|COMANDO|USO|EJEMPLO
|:---|:---|:---:|
|date|Muestra la fecha actual|date
|cal|Muestra el calendario|cal
|df|Muestra la cantidad de espacio disponible en las unidades de disco|df
|ctrl + f4 (**cerrar sesión**)|Cierra la sesión actual y solo deja disponible una ventana de terminal. Para volver al entorno gráfico se hace con **alt + f7**
|COMANDOS DE NAVEGACIÓN|
|PWD|Muestra el directorio actual|pwd
|ls|Lista los contenidos de un directorio. También puede recibir varios argumentos, por ejemplo **ls ~ /usr**, lo que hace es que lista todo lo del directorio home (~) y lo que haya en usr.|ls
|file|Da una pequeña descripción del contenido que tiene un archivo|file image.png y su resultado: ![alt text](image-1.png)
|less| Permite examinar archivos de texto. Al ejecutarse se puede desplazar por el contenido y para salir se pulsa q| less nombre_archivo
|evince| Puede abrir documentos PDF. Tiene muchas opciones útiles (ver la man).|evince archivo.pdf
|mkdir| Crea directorios (carpetas). Se pueden crear varios directorios a la vez así: **mkdir dir1 dir2 dir3**|mkdir nombre_carpeta
|cp| Sirve para copiar archivos y directorios|**cp item1 item2** copia el archivo o direcotrio item1 al archivo o directorio item2. **cp item ... directorio** copia multiples archivos o directorios a un directorio
|mv| Mueve o renombra archivos o directorios|**mv item1 item2** para renombrar el item1 (directorio o archivo). **mv item1... directorio** Para mover multiples elementos de un directorio a otro
|rm| Borra archivos o directorios| **rm elemeno...**. Se pueden borrar multiples elementos al tiempo
|ln | Crea enlaces duros y simbólicos.|**ln archivo link** para crear un enlace duro. **ln -s elemento link** para crear un enlace simbólico donde "elemento" es un archivo o directorio. **ln fun fun-hard** crea un enlace duro del archivo fun. Para crear enlaces simbólicos solo hay que añadir el argumento de -s|
|type| Muestra de que tipo es un comando. Ya que un comando puede ser un ejecutable, una función del shell, un comando contenido en el propio shell o un alias| type comando
|which|Dice la ubicación de un ejecutable. **No funciona con builtins ni con alias**|which name_ejecutable. **which steam**
|help|Muestra una pequeña ayuda acerca de un **shell builtin**. Hay **programas ejecutables** que soportan el comando --help que da información de su uso |help name_builtin. help cd. Para ejecutables: mkdir --help
|man| Se usa para ver el manual de ciertos ejecutables pensados para ser usados en la terminal. ![alt text](image-22.png) **pag 36**|man ejecutable. Se puede especificar de que sección se requiere información **man num_sección ejecutable** 
|whatis|Muestra una breve descripción de lo que hace un comando| whatis comando. whatis evince
|info|Cuando se utiliza info, se utiliza un programa llamado info hecho para leer archivos de tipo info que están interconectados como nodos, para movernos por esos nodos tenemos los siguientes comandos: ![alt text](image-23.png)|info comando
|zless| Es una versión especial de less para mostrar el contenido de un archivo de texto que está en un archivo comprimo .gz (se hizo con el programa gzip)|
|alias| Se utiliza para cre alias de manera temporal ya que cuando se cierre la sesión, el alias va a desaparecer| alias nombre_alias='instrucciones'
|unalias| Se usa para borrar un alias| unalias nombre_alias
|cat| Se utilza leer uno o más archivos y copiarlos a la salida estándar. Se utiliza a menudo para unir archivos y ver el contenido de archivos cortos| Si se tuvieran los archivos movie.mpeg.001 ... movie.mpeg.099, se podria usar el comando cat para unirlos así: **cat movie.mpeg.0* > movie.mpeg**. Se puede crear un archivo con contenido sencillo: **cat > lazy_dog.txt** y lo que se copie después de ejecutar la instrucción se va a guardar en el archivo.**cat < lazy_dog.txt y se va a mostrar el contenido del archivo**
|sort| Muestra la concatenación de todos los ficheros en la salida estándar| ls /bin /usr/bin pip sort pip less
|uniq| se usa para no repetir datos tomados de una lista ordenada|ls /bin /usr/bin pip sort pip uniq pip less
|wc| Sirve para contar cuantas líneas, palabras y bytes hay en la entrada|ls /bin /usr/bin pip sort pip uniq pip wc -l. En este caso se uso con el argumento -l para solo mostrar el número de líneas que hay en la lista
|grep| Es un programa que permite encontrar patrones en un archivo de texto. Con -i **grep ignora las mayúsculas** y con -v **muestra las líneas que no coinciden con el patrón**| ls /bin /usr/bin pip sort pip uniq pip grep zip. En este ejemplo grep se usa para mostrar todos los archivos que tengan zip en el nombre. 
|head/tail| Muestran las 10 primeras líneas y las 10 últimas líneas. Con el argumento -n se puede especificar el número de líneas que se quieren ver de un archivo. Con el argumento -f en el tail **se puede ver el archivo en tiempo real**| head -n 5 ls-output.txt. tail -n 5 ls-output.txt. También puede ser usado en pipelines
|tee|Sirve para capturar el resultado de un pipeline en una fase intermedia|ls /usr/bin pip tee ls.txt pip grep zip. En este caso se guarda la lista generada y después se muestra solo los que tengan zip en el nombre
|history| Se usa para ver el historial de comandos que se han utilizado. Por defecto solo guarda los primeros 500 usados| Si se pulsa crtl + r y podremos buscar coincidencias con algún comando. Se puede usar **!num** para ejecutar un comando que se haya encontrado en el historial (num es la pocisión del comando)
|script|Permite grabar una sesión del shell| Buscar ejemplos

## Tipos de archivos más comunes
![alt text](image-29.png)

## Modo de archivo
Son los permisos que cada usuario, grupo y mundo tienen asignados
![alt text](image-30.png)
r: read; w: write; x: execute
![alt text](image-31.png)

## Ejemplos de configuración de permisos
![alt text](image-33.png)

## Patrones para establer los permisos en binario y octacl
![alt text](image-34.png)

## Establecer permisos de manera simbólica
![alt text](image-35.png)
![alt text](image-36.png)
![alt text](image-37.png)

## Ubuntu y sudo
En ubuntu el usuario tiene los mismos permisos que el root usando sudo **(página 74)**

## Ejemplos de los argumentos de chown
![alt text](image-38.png)
![alt text](image-39.png)
**otro caso en la página 75**

## Comandos para administrar los permisos de los usuarios
* Las cuentas de usuario están definidos en el directorio **/etc/passwd**
* Los grupos están definidos en el directorio **/etc/group**
* El archivo **/etc/shadow** guarda información de las contraseñas de cada usuario

|COMANDO|USO|EJEMPLO
|:---|:---|:---:|
|id|Muestra info del usuario| id
|chmod| sirve para establecer permisos| chmod 600 archivo.txt. En este caso se le estableción **lesctura y escritura para el usuario(6), para el mundo y el gurpo no tienen ningún permiso(0)**
|umask|Controla los permisos dados por defecto cuando un archivo es creado|**NO ENTIENDO BIEN COMO FUNCIONA**
|su| Se usa para arranchar un shell como otro usuario| su -l user, lo que hace es que se carga un shell de login para el usuario especificado cambiando el home al del usuario que se quire. Si no se especifica el usuario, se asume que es el superusuario **su -**. 
|sudo| Funciona casi igual que el comando su solo que tiene algunas funcionalidades adicionales. El administrador puede configurar sudo para que usuario regulares ejecuten comandos como otro usuario (normalmente el superusuario) de manera muy controlada. **para autenticarse usando sudo el usuario utiliza su propia contraseña**|sudo backup_script, así se utilizaría el comando. **Para ver que privilegios se tienen por parte de sudo se puede hacer: sudo -l**
|chown|Se utiliza para cambiar el propietario de los archivos. Es necesario tener privilegios de superusuario| Se usa: chown [propietario][:[grupo]] archivo...
|passwd| se usa para cambiar la contraseña de otros usuarios y la propia| **mirar que más se puede hacer con este comando**
|adduser| **consultar el comando**|consultar
|useradd| **consultar el comando**|consultar
|groupadd|**consultar el comando**|consultar

## Arranque del sistema
* Los archivos de arranque del sistema están en /etc. Estos archivos se denominan **init scripts** y se encargan de iniciar los servicios
* Los procesos que se ejecutan en el fondo sin necesidad de un usuario en la interface se denominan **daemon programs(demonios)**

## Estado de los procesos
![alt text](image-40.png)



## Comandos para administrar procesos
* Para iniciar procesos en el fondo(que se inicie el procesos y se pueda seguir usando el bash) se añade & al final del comando

|COMANDO|USO|EJEMPLO
|:---|:---|:---|
|ps|Muestra procesos del sistem. Las columnas de este campo son: TTY-Teletype se refire al terminal que controla el proceso, |ps. Con ps x muestra más información. ps aux simula el comportamiento de BSD y muestra estas opciones: ![alt text](image-41.png)
|top|Muestra la actividad de los procesos en tiempo real, que se actualiza cada 3s|top. Significado de las columnas ![alt text](image-42.png)![alt text](image-43.png)
|jobs|Muestra los trabajos que hemos arrancado desde la terminal|jobs
|kill| Se usa para mandarle señales a un programa. Por defecto kill manda la señal de **TERM (Terminar)** pero también se pueden mandar las siguientes señales: ![alt text](image-44.png)![alt text](image-45.png). Debes ser el propietario de un proceso o ser root para poder enviarle señales con kill. Otras señales usadas por el sistema: ![alt text](image-46.png). Con **kill -l** se pueden ver las señales que se pueden enviar con kill| kill pid
|killall|Se mandan señales a un programa específico o a un usuario **(profundizar)**|killall name_proceso

## Más comandos relacionados con procesos
![alt text](image-47.png)


## El entorno
En el entorno se almacenan datos de la sesión actual. Se guardan 2 tipos de datos: variables de shell que son bits puestos por el bash y las variables de entorno son el resto de datos. 
* Para definir variables de entorno o añadir direcciones al entorno hay que modificar le archivo **.bash_profile** o .profile. Para todo lo demas se colocan los cambios en **.bashrc**

## Algunas variables
![alt text](image-48.png)
![alt text](image-49.png)

## Archivos de arranque para sesiones de shell con login
![alt text](image-50.png)

## Archivos de arranque para sesiones de shell sin login
![alt text](image-51.png)

* En la sección INVOCATION de la man page de bash se cubren los archivos de arranque



## Comandos para ver el entorno
|COMANDO|USO|EJEMPLO
|:---|:---|:---:|
|printenv| Muestra las variables del entorno| printenv. Se puede ver el valor de una variable **printenv variable**
|set| Muestra las variables de entorno, shell y funciones definidas del shell| set. Se puede ver el valor de una variable **echo $variable**
|alias| Muestra los alias del sistema| alias

## Editores de texto
**Para actualizar el archivo de .bashrc se puede usar el comando: source .bashrc**
* VI
* VIM, que es una versión mejorada de vi
* nano
* gedit, que es el editor de texto que viene por defecto en distros con GNOME
* kedit
* kwrite
* kate

## vi
![alt text](image-52.png)
vi en realidad es vim
![alt text](image-53.png)

* Cuando vim arranca lo hace en modo comando, significa que casi cualquier tecla es un comando, si se empieza a escribir entonces vim se vuelve loco
* En la documentación de vim el modo comando se llama modo normal y los comandos ex (:) se llaman modo comando
## Atajos para mover el cursor
![alt text](image-55.png)

|COMANDO|USO|EJEMPLO
|:---|:---|:---:|
:q| sirve para salir de vim|:q. Si vim no se cierra es porque tal vez no se han guardado cambios, entonces se ejecuta **:q!** para indicar que igual se quiere salir del programa. **prueba pulsando 2 veces la tecla esc si te pierdes**
|i| Entra en modo *insert**. De esta forma ya se puede editar el texto| i
|esc| Se vuelve al **modo comando**| esc
|:w| Se guardan los cambios hechos en el archivo. Si se quiere guardar una copia del archivo entonces **:w name_new_file** y se creará una copia| Hay que estar en **modo comando** para poder ejecutar el comando
|u| Deshace acciones| Hay que estar en modo comando y pulsar la u
|a| Entra en modo inserción y el cuersor se posiciona la final de la línea| a
|A| Posiciona el cursor al final de la línea| Hay que estar en el modo comando
|o| Inserta una línea bajo la que está situada el cursor| o
|O| Inserta una línea sobre la que está situada el cursor| O
|comandos de borrado| Deben ser usados en modo comando|![alt text](image-56.png)
|Comandos de copiado|Se usa en modo comando|![alt text](image-57.png)
|p| Pega texto del portapapeles debajo de la línea sobre la que está el cursor| d además de borrar sirve como cortado porque si borra algo con d, se puede pegar con p
|P| Pega el texto sobre la línea en la que está el cursor
|J| subre líneas a la línea  actual que estén por debajo de la posición del cursor| J
|f| Se usa para buscar coincidencia en **1 línea**, para repetir la busqueda se presiona **;**| fa posiciona el cursor en la primera a que encuentre
|/| busca patrones en todo el texto| Primero se posiciona al inicio del archivo y luego se utiliza el comando
|n| Se repite la busqueda hecha con **/**| Después de hacer la primera busqueda y de haber presionado enter, se presiona n para volver a buscar en otra posición
|Busqueda y reemplazo global|![alt text](image-58.png)|![alt text](image-59.png) si se le agrega **c**, vim parará cada vez que encuentre una coincidencia y pregunta si queremos hacer el reemplazo ![alt text](image-60.png) De esta forma aparece la pregunta: ![alt text](image-61.png) Cada una de las opciones significa: ![alt text](image-62.png)
|Editando varios archivos| vim file1 file 2| vim file1 file2
|:n| cambia al siguiente archivo que esté abierto| :n
|:N| Cambia al anterior archivo| :N
|:buffers|Muestra los archivos que están siendo editados| :buff + tab para ver varias coincidencias con el patrón. Se puede usar **:buffer num** para cambiar al tercer archivo por ejemplo
|:e file_name| permite abrir más archivos para editarlos| cuando se abren archivos de esta forma, no funcionan los comandos :n y :N, para cambiar entre archivos hay que usar el comando :buffer
|:r| se usa para insertar un archivo dentro de otro| :r file_name
|ZZ| Guarda el archivo actual y cierra vim|En modo comando
|:syntax on| se usa para cambiar el modo de vim a modo de resaltado de sintáxis para escribir scripts| :syntax on. Si no funciona, hay otra alternativa :set syntax=sh
|:set hlsearch| para resaltar el resultado de una busqueda|activa la opción de destacar los resultados de búsqueda.Digamos que buscamos la palabra echo, Con esta opción activada, cada instancia de la palabra será destacada.
|:set tabstop=4|establece el número de columnas ocupadas por un carácter tabulador. Por defecto son 8 columnas. Estableciendo el valor a 4 (que es una práctica común) permite a las líneas largas ajustarse más fácilmente a la pantalla.| usar en modo comando
|:set autoindent|activa la función auto indentado. Esto hace que vim indente una nueva línea la misma cantidad que la línea recién escrita. Esto acelera la escritura en muchos tipos de construcción de programas. Para detener la indentación, pulsa Ctrl-d.

Estos cambios pueden hacerse permanentes añadiendo estos comandos (sin los dos puntos delante)
a tu archivo ~/ .vimrc.



## Personalizando la cadena del PROMPT
* La forma del prompt es definida por la variable **PS1(Prompt String One)**
![alt text](image-63.png)
![alt text](image-64.png)
* ![alt text](image-65.png)
En este caso, la cadena del prompt va a aparecer vacía, osea que el prompt no se ve pero está ahí
* ![alt text](image-66.png)
En el prompt solo aparece un signo de dolar
* ![alt text](image-67.png)
Cada vez que aparece el prompt hace un beep. Por ejemplo cuando termina de ejecutar un comando
* ![alt text](image-68.png)
Se muestra información del usuario y la hora. **hora nombre_host signo_dolar**
![alt text](image-76.png)Así modifiqué mi prompt:**PS1=/\[\033[1;35m/\]\A \\# \j \\[\033[0;36m\\]\u@\h:\\$\\[\033[0;31m\\]\w\[\033[0m\\] **
    

* La cadena original del prompt era (está guardada en la variable **ps1_old**): 
![alt text](image-70.png)
## Secuencias de escape para establecer colores
![alt text](image-71.png)
![alt text](image-72.png)
![alt text](image-73.png)
![alt text](image-74.png)
![alt text](image-77.png)
* **Para guardar permanentemente el prompt hay que agregar export PS1 al final del archivo**
* Así se ven los colores de fondo:
![alt text](image-75.png)

## Gestión de paquetes (página 118)
* Un paquete normalmente está destinado a una distribución concreta y solo funcionará en esa distribución 
* La mayoria de las distribuicones se clasifican dentro de 2 tecnologías de familias de paquetes más grandes: **Debian (.deb) y Red Hat(.rpm)**
![alt text](image-78.png)
* **Herramientas de bajo y alto nivel**: Las primeras se encargan de instalar, eliminar y crear paquetes y las segundas realizan busquedas por medatadatos y resolocuión de dependencias (Las dependencias son scripts que necesitan ciertos paquetes para que puedan funcionar correctamente) al igual que la descarga e instalación de paquetes
![alt text](image-79.png)
![alt text](image-80.png)
![alt text](image-81.png)
![alt text](image-82.png)
![alt text](image-83.png)
![alt text](image-84.png)
![alt text](image-85.png)
![alt text](image-86.png)
![alt text](image-87.png)
![alt text](image-88.png)
![alt text](image-89.png)

## Medios de almacenamiento(No me interesa en este momento) página 133
* El archivo /etc/fstab  lista los dispositivos del equipo
* Un punto de montaje es un directorio en algún lugar del árbol del sistema de archivos
* El buffer es un dispositivo que se implementó en las impresoras para no detener el trabajo del pc, este se instalaba en medio del pc y la impresora. En linux, se van a tener los datos que son leídos y necesitan ser escritos en otro dispositivo en memoria por el mayor tiempo posible para impedir el contacto con dispositivos lentos. No significa que linux esté "utilizando" la memoria significa que linux está sacando el mayor provecho de buffering que pueda

|COMANDO|USO
|:---|:---:|
|mount| Sirve para montar sistemas de archivos. Si se utiliza sin argumentos lista los sistemas de archivos montados
|free|muestra info sobre el uso de memoria

## Redes
|COMANDO|USO|EJEMPLO
|:---|:---|:---:|
|ping| Se usa para escanear una red. Este comand manda paquetes **IMCP ECHO_REQUES** a un host especificado. Es posible configurar la mayoria de los dispositivos de red para que ignoren estos paquetes haciendo más seguro el host o indetectable, también es común configurar el corta fuegos para bloquear el tráfico de ICMP| ping linuxcommand.org
|traceroute o tracepath| Muestra una lista de todos los hops o saltos que el tráfico hace para llegar desde el sistema local al host especificado| traceroute google.com
|netstat| Se usa para examinar diferentes configuraciones de la red| netstat. Con los argumentos -ie muestra más info
|ftp| Es un cliente ftp que permite conexiones remotas usando este protocolo (no es recomendabla ya que los datos viajan de forma plana)| ftp serverftp
|lftp| Es un cliente mejorado del protocolo ftp|
|wget| Es útil para descargar archivos de páginas web e incluso sitios enteros| wget link_página
|ssh (pag 149)| Es igual que ftp solo que la conexión es encriptada y host remoto se verifica para que en realidad sea quien dice ser| ssh remote_server
|Tunelización ssh| Es usado para ejecutar una aplicación con GUI en un sistema remoto y que la pantalla aparezca en local| ![alt text](image-90.png)

## Comandos para encontrar archivos
El operador de tubería (|) se reemplaza por la palabra pip para no interferir con el formato de las tablas
* Nombres simpáticos: ![alt text](image-102.png) pag 164

|COMANDO|USO|EJEMPLO
|:---|:---|:---:|
|locate|Busca en la base de datos de nombre de archivos todo aquel que coincida con la cadena dada| locate /bin/zip, muestra todos los archivos que terminen en el directorio **bin y empiecen con zip**. locate zip pip grep bin, en este caso se buscan todos los archivos que tengan zip en su nombre y con grep solo se muestran los archivos que tengan zip y bin en su nombre
|find| Busca archivos en directorios y subdirectorios por una gran variedad de atributos. La forma como find funciona es atravez de **opciones, tests y acciones**| find ~ muestra todos los archivos que haya en todas las carpetas del home
|test| es una aplicación de find| find ~ -type d pip wc -l, esta instrucción solo va a mostrar los directorios que hay en el home. find ~ -type f pip wc -l se muestran los archivos normales en el home
|![alt text](image-91.png)| Estos son los test más comunes que soporta find| se usa igual que en los ejemplos anteriores. ![alt text](image-92.png)
|unidades de almacenamiento en find| ![alt text](image-93.png)
|test más comunes| ![alt text](image-94.png)![alt text](image-95.png)![alt text](image-96.png)![alt text](image-97.png)
|operadores| Se usan junto con los test para combinarlos y hacer busquedas más complejas|
|algunos operadores|![alt text](image-98.png)| find ~ \(-type f -not -perm 0600 \) -or \(-type -d -not -perm 0700 \). Este comando busca todos los archivos que no tengan permiso 0600 o si es un directorio que no tenga permiso 0700
|Acciones predefinidas de find| Se utilizan para hacer algo con el resultado de find| ![alt text](image-99.png)
|accciones definidas por el usuario| ![alt text](image-100.png)|Para mejorar la eficiencia, se puede cambiar el ; por un +, esto hace que el comando deseado solo se ejecute una vez 
|wargs| También se utiliza para mejorar la eficacia de find, con la caracteristica de que este comando puede utilizar la entrada estándar y la convierte en argumentos para el comando que se quiere ejecutar|![alt text](image-101.png)
|opciones| ![alt text](image-103.png)

## Comprimiendo archivos sin perdida
* zcat
* zless
* bzip2 

|COMANDO|USO|EJEMPLO
|:---|:---|:---:|
|gzip y gunzip| se usan para comprimir y descomprimir sin perdida| **gzip foo.txt** comprime el archivo que resulta en otro archivo con la extención gz y gunzip foo.txt **descomprime el archivo**
|Alguanas opciones de gzip|![alt text](image-104.png)![alt text](image-105.png)


## Empaquetar archivos(página 171)

|COMANDO|USO|EJEMPLO
|:---|:---|:---:|
|tar| Es la herramienta clásica en unix para empaquetado| tar modo[opciones] ruta...
|modos de tar| ![alt text](image-106.png)|![alt text](image-107.png)

## zip
Es tanto una herramienta de empaquetado como de compresión.

## Sincronización de archivos y directorios
rsync es la herramienta preferida para este tipo de trabajo. Leer más sobre esta herramienta ya que puede ser útil al momento de hacer copias de seguiridad en otro dispositivo que esté en la red local

# Expresiones regulares
son notaciones simbólicas usadas para identificar patrones en el texto.
![alt text](image-108.png)
* Los literales son las coincidencias exactas, por ejemplo cuando se busca que la palabra "hola" esté en el nombre de un archivo
* Los metacaracteres son signos que se usan para hacer más complejo el patrón de busqueda. Son estos: ![alt text](image-109.png) ![alt text](image-110.png)
* ^: Hace que la coincidencia solo ocurra si el patrón se encuentra al principio de la línea: ![alt text](image-111.png)
* $: Hace que la coincidencia solo ocurra si el patrón se encuentra al final de la línea: ![alt text](image-112.png)
* ![alt text](image-113.png)
* **Linux tiene un diccionario en /usr/share/dict**
* []: Se usan para encontrar un caracter específico de una colección: ![alt text](image-114.png) 
Dentro de los corchetes los metacaracteres pierden su significado excepto **^(símbolo de intercalación)** que se usa para indicar negación solo si es el primer carácter sino pierde su significado y **-** que se usa para indicar un rango de caracteres. **grep -h '\[^bg]zip' dirlist*.txt** va a buscar todos los nombres de archivo que NO empiezan con b ni g. **grep -h '[A-Z]' dirlist*.txt** va a buscar todos los archivos que empiecen con cualquier letra mayúscula. Se pueden expresar varios rangos así: **grep -h '^[A-Za-z0-9]' dirlist*.txt**, para que el guión pierda su significado debe ir al inicio
![alt text](image-115.png)![alt text](image-116.png)
* Las expresiones regulares están dividas en 2 grupos, **expresiones regulares básicas (BRE)** y **expresiones regulares extendidas(ERE)**. La diferencia es que con BRE se reconocen los caracteres: ^, $, ., [], * y con ERE funcionan los metacaracteres: (), {}, ?, +, |
![alt text](image-117.png)

## Alternancia
Permite coincidencias dentro de una serie de cadenas y otras expresiones regulares, ejemplo:
![alt text](image-118.png)
Esto siginifica que la salida estándar del comando echo se entuba al grep si se tiene AAA o BBB coinciden.
Otro ejemplo: 
![alt text](image-119.png)

## Cuantificadores
Las expresiones regulares extendidas (ERE) soportan el número de veces que se encuentra un elemento
#### ? 
![alt text](image-120.png)
### *
![alt text](image-121.png)
### +
![alt text](image-122.png)
### {}
![alt text](image-124.png)

## Procesado de texto

|COMANDO|USO|EJEMPLO|
|:---|:---|:---:|
|cat| se usa para ver y crear texto| el argumento -A muestra los caracteres no imprimibles como **espacio, tabulación, salto de línea, etc**. El argumento -n numera las líneas y el -s suprime las líneas en blanco
|uniq| Elimina las líneas duplicadas| Para que uniq haga su trabajo debe ser usado con sort: sort foo.txt pip uniq
|patch| se usa para actualizar archivos de texto| ![alt text](image-125.png)
|tr| permite hacer una busqueda y reemplazo| ![alt text](image-126.png)![alt text](image-127.png)

# Aspell
Es un corrector ortográfico pero de inglés. ![alt text](image-128.png)

# Herramientas de formateo simple (pag 229)
# Compilando programas
Compilar es traducir el código fuente de un programa (código escrito con un lenguaje de programación) al lenguaje máquina (código binario).
Los primeros programas fueron escritos en código binario, debido a su complejidad se vio la necesidad de desarrollar una manera más amigable de desarrollo y de ahí nace el lenguaje ensamblador y después los lenguajes de alto nivel. 
Algunos compiladores pasan el código fuente a lenguaje ensamblador y de ahí se usa un ensamblador para terminar de pasar el código a lenguaje máquina.

Los lenguajes **de script o interpretados** se traduce línea por línea al lenguaje máquina cada vez que se van a ejecutar lo que hace que sean más lentos que un lenguaje compilado.

El motivo por el que los lenguajes interpretados se popularizaron es porque a medida que un programa crece el tiempo de compilación se vuelve más lento y esté tiempo se reduce con los interpretes.

El **enlazador** son rutinas (librerias) del sistema que hacen tareas comunes como por ejemplo abrir un     archivo. La idea es que no se despilfarren recursos por cada programa que puede hacer eso sino establecer una porción de código que todos los programas usen para realizar la tarea.

## Compilando un programa en C
Para compilar se necesita el compilador, enlazador y make. 
El compilador C usado universalmente en el entorno Linux se llama gcc (Gnu C Compiler)

* Se consigue primero el código fuente de la aplicación. En este caso se va a compilar un programa llamado **diction** comprueba la calidad de escritura y edición de archivos de texto. Se hace: ![alt text](image-129.png)![alt text](image-130.png)
* Para descomprimir el archivo: ![alt text](image-131.png)
* Los archivos que tienen la extensión c son los archivos que contienen el programa. Es buena idea revisar los archivos **README, NEWS, INSTALL, COPYNG**
* Los archivos .h son cabeceras, quiere decir que contienen la descripción de las rutinas incluidas en un código fuente o librerías
* Para empezar a compilar primero se utilza el comando **configure**![alt text](image-132.png)![alt text](image-133.png)
* Se ejecuta **make** para terminar de compilar el programa 
* Para instalar el programa, solo resta ejecutar **sudo make install**

# Scripts de shell
Es un archivo que contiene una serie de comandos que el shell va a leer y ejecutar tal como están. 
Para escribir scripts de forma correcta y exitosa se encesitan tener en cuneta varias aspectos como permitir al archivo ejecutarse, osea, darle permisos y poner el script donde el shell pueda encontrarlo. Ejemplo: 
![alt text](image-134.png)

La primera línea que empieza con un **shebang (#!)** se usa para decirle al sistema que interprete debería usar para el script; la segunda línea es un **comentario** y la última es una instrucción de imprimer el mensaje "Hello world". 

Hay que cambiar los permisos del archivo para que pueda ejecutarse: ![alt text](image-135.png)

Para ejecutar el script: ![alt text](image-136.png)

La variable de entorno $PATH es donde el sistema almacena los directorios separados por 2 puntos (:) donde se guardan los ejecutables para iniciarlos. Para poder ejecutar nuestro programa como si fuera un comando más, debe estar guardado en una de estas direcciones, así: ![alt text](image-137.png)
![alt text](image-138.png)
![alt text](image-139.png)

En el siguiente script se crea una especie de reporte: 
![alt text](image-140.png)
* Profundizar en el "documento-aqui" (es la nomenclatura de **cat <<- _EOF_** [End Of File - Final Del Archivo])

Para crear funciones en el archivo **.bashrc** se hace igual que en un script normal: 
![alt text](image-141.png).

Las variables para definirlas localmente (que su alcance solo sea en una función) hay que preceder el nombre de la variable con **local**. Así: 
![alt text](image-142.png)

# Control de flujo: Ramificando con if
![alt text](image-143.png)
La estructura del if tiene la siguiente forma: 
![alt text](image-144.png)
Para  indicar que una función o un script se ejecutaron de forma correcta, se usa **0** en la salida estándar y si hubo algún problema se usa cualquier otro número
![alt text](image-145.png)
## Expresiones test para archivos
![alt text](image-146.png)
![alt text](image-147.png)
![alt text](image-148.png)
![alt text](image-149.png)

# Test mejorado 
El operador [[]] admite todas las expresiones que test y también regex (Expresiones regulares)![alt text](image-150.png). 

El operador (()) sirve para evaluar operaciones con enteros. Es verdadera si su resultado es diferente de 0 ![alt text](image-151.png)

# Operaciones lógicas 
![alt text](image-152.png)

# Leyendo datos
![alt text](image-153.png)

read puede leer varias variables al mismo tiempo
**read var1 var2 var3...**
Si cuando al momento de leer muchas variables se ingresan menos de las que el sistema espera, las otras quedan vacias y si se ingresan más de las que el sistema espera los valores restantes se asignan a la última variable

# Opciones de read 
![alt text](image-154.png)
![alt text](image-155.png)

# IFS
Read entiende que palabras separadas por un espacio es un valor diferente, eso es porque la variable de shell **IFS** está configurada así pero se puede modificar para que el separador sea otro símbolo.
En el siguiente script se modificó la variable para diferenciar valores con los 2 puntos (:)![alt text](image-156.png)

# While
![alt text](image-157.png)

Para salir de un bucle se puede usar **break** que termina el bucle y sigue con la siguiente sentencia después del bucle. **Continue** se salta lo que sigue del bucle y continúa con la siguiente iteración. 

# Tracing o traza 
Para ver verficar que se está ejecutando en el script se puede agregar el argumento x a la primera línea del script para que quede así: **#!/bin/bash -x** esto va a mostrar el resultado y la ejecución del script: 
Script ![alt text](image-158.png)
Ejecución: ![alt text](image-159.png)

# Control de flujo: Ramificando con case
![alt text](image-160.png)
Ejemplo de uso de case: ![alt text](image-161.png)
![alt text](image-162.png)
Para poner varias patrones hay que separarlos con la barra verical **(|)**. Añadir ";;&" al final de una acción, no se termina el bucle sino que se evalua la siguiente condición para ver si coincide o no. Así ![alt text](image-163.png)

# Parámetros posicionales 
![alt text](image-165.png)
![alt text](image-166.png)
![alt text](image-167.png)
Se pueden acceder a más de 9 parámetros usando la nomenclatura de ${10}, ${11}, ${12}...
la variable $# muestra el número de argumentos

# Página 334 se retoma el proyecto de sys_info_page con algunad mejoras

# Bucle for
![alt text](image-168.png)
![alt text](image-169.png)
![alt text](image-170.png)

# bc 
Es u n programa que permite hacer cálculos matemáticos un poco más complejos que los que permite le shell. Se pueden hacer cálculos desde un archivo escrito en c o interactivamente desde la terminal: 
![alt text](image-171.png)
Desde la terminal: 
![alt text](image-172.png)

# Script para ver cuantos archivos son modificados en una sesión (pag 362)
El tema de los arrays empieza en la **página 360**
![alt text](image-173.png)

# Script para ver los archivos, propietarios y grupos dae un directorio
![alt text](image-175.png)

# Subshell y grupos de comando
Estas técnicas son usadas para ejecutar más de un comando en una sola instrucción, por ejemplo: 
![alt text](image-174.png)
La diferencia de las 2 técnicas es que un grupo de comandos los ejecuta en la sesión actual mientras que un subshell los ejecuta en un subshell, hace una copia de la sesión actual y esa copia se pierde cuando la ejecución finaliza

# Extras 






