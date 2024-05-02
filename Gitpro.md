---
id: evdy848c0cpufp05spptn6v
title: Gitpro
desc: 'Libro escrito por Scott Chacon (uno de los fundadores de GitHub)'
updated: 1714653942635
created: 1714517141476
---

# Inicio sobre el control de versiones 
Un controlador de versiones se desarrolló con el fin de hacer que perdure de manera eficiente y sencilla las versiones e histórico de un archivo/proyecto. Guardando el quien, cuando, como, que y donde en una base de datos para posteriormente permitir verificar errores o reucperar cosas. 
![alt text](image-176.png)

## VCS Centralizados
![alt text](image-177.png)
La ventaja de este sistema de control de versiones frente a uno local es que permite la colaboración de varias personas. Uno de los incovenientes es que si se cae el servidor, nadie va a poder seguir trabajando en con el VCS

## VCS Distribuidos
![alt text](image-179.png)
La ventaja de este sistema es que cada cliente va a tener una copia exacta y completa del repositorio. 

## Forma en que Git maneja los cambios
![alt text](image-180.png)
Al momento de guardar un cambio, Git literalmente toma una instantánea y crea una referencia para acceder a ese cambio. Si el archivo no se modificó, se guarda la versión más reciente

## Git tiene integridad
Significa que todo en Git es verificado por una suma de comprobación (checksum) antes de ser almacenado eso significa que todo lo que se haga en Git va a ser conocido por el sistema. Esta checksum es generada por el método **hash SHA-1**. En Git es muy difícil que la información se pierda 

## Los 3 estados
### Confimado
Significa que los cambios están guardados de manera segura en la base de datos local
### Modificado
Significa que has modificado el archivo pero todavía no lo has confirmado a la db
### Preparado
Significa que un archivo modificado se marcó en su versión actual para que vaya en la próxima versión
![alt text](image-181.png)

### Directorio de Git
El directorio de Git es donde se almacenan los metadatos y la base de datos de objetos para tu proyecto. Es la parte más importante de Git, y es lo que se copia cuando clonas un repositorio desde otra computadora.

### Directorio de trabajo
El directorio de trabajo es una copia de una versión del proyecto. Estos archivos se sacan de la base de datos comprimida en el directorio de Git, y se colocan en disco para que los puedas usar o modificar.

### Área de preparación 
El área de preparación es un archivo, generalmente contenido en tu directorio de Git, que almacena información acerca de lo que va a ir en tu próxima confirmación. A veces se le denomina índice (“index”), pero se está convirtiendo en estándar el referirse a ella como el área de preparación.

![alt text](image-182.png)

## Configurando Git por primera vez 
![alt text](image-183.png)
![alt text](image-184.png)
![alt text](image-185.png)
Para comprobar las configuraciones que Git hizo se puede usar **git config --list**
![alt text](image-186.png)
## Servidor de IRC
Para obtener ayuda se puede usar los canales #git o #github del servidor IRC Freenode **irc.freenode.net**

# Fundamentos de Git
## Inicializando un repositorio en un directorio existente
Para iniciar un repositorio se usa el comando: **git init**. Esto crea un subdirectorio llamado **.git**

## Clonando un repositorio existente
**git clone url** de esta manera se clona todo la historia del proyecto remoto de manera local. Si se quiere clonar un repo con un nombre diferente puede hacerse **git clone url newname**
![alt text](image-187.png)

## Ciclo de vida del estado de los archivos
![alt text](image-188.png)

## Revisando el estado de los archivos
Con el comando **git status** se ve el estado del archivo

## Rastrear archivos nuevos 
**git add filename**. Rastrear un archivo (tracked) significa que se le van a sacar instantáneas (se van a guardar en la db). 

## Preparar archivos modificados
Git prepara archivos (staged) de acuerdo al estado en el que estaba cuando se ejecuta **git add**. Entonces un archivo puede estar en el stage y fuera del stage
![alt text](image-189.png)

## Salida abreviada
![alt text](image-190.png)

## Ignorar archivos
![alt text](image-191.png)
### Reglas de patrones que se pueden incluir en el .gitignore

![alt text](image-192.png)

## Ver los cambios preparados y no preparados
**git diff** muestra que cambió pero aún no está preparado, si los cambios están preparados git diff no va a mostrar nada. Si se quiere ver lo que se a preparado y será incluido en la próxima confirmación se puede usar **git diff --staged** este comando compara los cambios preparados con la última instantánea confirmada
![alt text](image-193.png)

## Confirmar cambios
**git commit -v** De está forma aparace en el editor lo que has modificado y va a ser confirmado. Para escribir el mensaje de confirmación directamente en el comando sin abrir el editor de texto se puede usar **git commit -m**. Para saltarse la parte del añadido se puede usar el argumento -a en el comando commit **git commit -a -m** y se van a añadir automáticamente los archivos que están rastreados. 

## Eliminar archivos
**git rm**. Este comando borra los archivos del stage y del directorio de trabajo, si solo se borrará el archivo del área de trabajo aparecería "cambios sin preparación para confirmar" en la salida de git status
![alt text](image-194.png)
Si preparo un archivo y lo quiere eliminar se puede usar **git rm --cached fileName** (también se puede especificar patrones glob)

## Cambiar el nombre de archivos
**git mv namefila newname**

## Ver el historial de confirmaciones 
**git log**. Con el argumento **-p** se muestran las diferencias en cada confirmación. **git log --stat** tras cada confirmación muestra cuantos archivos han sido modificados y cuantas líneas se han agregado y eliminado, al final de todos los commits muestra un resumen de esa información. 
Con pretty se puede especificar el formato de salida de los logs, se le pueden pasar las opciones **oneline, short, full, fuller** . Además también se puede especificar el formato propio
![alt text](image-195.png)
### Opciones útiles para pretty
![alt text](image-196.png)
graph
![alt text](image-197.png)
### Opciones más comunes de git log
![alt text](image-199.png)
### Limitar la salida del historial
Se puede usar **git -log -n**, donde n es un número cualquiera para mostrar los n últimos commits. **git log --since=2.weeks** de esta manera se pueden ver los commits hechos durante las 2 últimas semanas, Este comando acepta muchos formatos. Puedes indicar una fecha concreta ("2008-01-15"),o relativa, como "2 years 1 day 3 minutes ago" ("hace 2 años, 1 día y 3 minutos").

![alt text](image-200.png)
![alt text](image-201.png)
![alt text](image-202.png)

## Deshacer cosas
### Deshacer commits
![alt text](image-203.png)
### Deshacer un archivo preparado 
Para sacar un archivo del staging se usa **git reset HEAD nameFile**
### Deshacer un archivo modificado 
Con **git checkout <"file">** de esta forma vuelve al estado en le que estaba el archivo en la última confirmación 

## Repositorio remotos
Para añadir repositorios remotos se debe hacer **git remote add \[nombre] \[url]**. Si se quiere traer toda la información de un repo al repositorio personal se utiliza **git fetch \[nombre_repo]**
![alt text](image-204.png)
Este comando no combina automáticamente con mi trabajo ni modifica el trabajo que ya se tenía, la combianción se hace manualmente. Con **git pull** trae la información del remoto y los combina automáticamente con lo que ya se tenía en la rama 

### Enviar a los repositorios remotos 
**git push \[nombre-remoto] \[nombre-rama]**
![alt text](image-205.png)

### Eliminar y renombrar remotos
**git remote rename newName**
![alt text](image-206.png)
Para eliminar un remoto se usa **git remote rm name**
![alt text](image-207.png)

## Etiquetado
Son puntos especificos en el historial marcados como importantes. Para listar las etiquetas se usa **git tag** Hay 2 tipos de etiquetas, las ligeras y las anotadas

![alt text](image-208.png)

### Etiquetas ligeras
es muy parecido a una rama que no cambia - simplemente es un puntero a un commit específico.

### Etiquetas anotadas
Sin embargo, las etiquetas anotadas se guardan en la base de datos de Git como objetos enteros. Tienen un checksum; contienen el nombre del etiquetador, correo
electrónico y fecha; tienen un mensaje asociado; y pueden ser firmadas y verificadas con GNU Privacy Guard (GPG). Normalmente se recomienda que crees etiquetas anotadas, de manera que tengas toda esta información; pero si quieres una etiqueta temporal o por alguna razón no estás interesado en esa información, entonces puedes usar las etiquetas ligeras.

![alt text](image-209.png)

### Etiqueta ligera
![alt text](image-210.png)


### Etiquetado tardío
Para crear una etiqueta de un commit que sucedio hace tiempo o no fue reciente, también se puede etiquetar especificando su checksum
![alt text](image-211.png)
![alt text](image-212.png)

### Compartir etiquetas
Por defecto cuando se realiza un git push al servidor, no se envian las etiquetas, para enviarlas hay que ejecutar **git push origin \[etiqueta]** o si se quieren enviar todas entonces **git push origin --tags**

### Sacar una etiqueta
![alt text](image-213.png)

## Alias de Git 
![alt text](image-214.png)
Si se queire ejecutar un comando externo de git, el comando debe iniciar con !, así: 
![alt text](image-215.png)

# Ramificaciones en Git

Para crear una rama nueva se usa **git branch nameBranch**. El apuntador HEAD es especial ya que apunta a la rama local en la que estes en ese momento
![alt text](image-216.png)
Con ese comando se puede ver a donde apunta cada rama

## Cambiar de ramas
**git checkout branchName** de esta manera el apuntador HEAD cambia a la rama donde hayas cambiado 
![alt text](image-217.png)
Cuando se realiza un cambio en la rama nueva, sucede esto:
![alt text](image-218.png)

Al volver a la rama master, se ve así: 
![alt text](image-219.png)
![alt text](image-220.png)
![alt text](image-221.png)

El flujo de trabajo realizado en diferentes ramas se puede ver de una forma gráfica así: 
![alt text](image-222.png)
 Para saltar entre ramas hay que tener un directorio de trabajo limpio, no tener nada en el staging ni y todos los commits hechos.
 Para hacer una fusión se usa **git merge branch**. Para borrar una rama que no se necesita más se hace **git branch -d branch**
 ![alt text](image-223.png)
![alt text](image-226.png)
## Fusion Fast forward
![alt text](image-224.png)

## Fusion Recursive
![alt text](image-225.png)
![alt text](image-227.png)

## Tipos de merge para consultar
* Fast-forward
* Recursive

## Principales problemas al hacer fusiones




