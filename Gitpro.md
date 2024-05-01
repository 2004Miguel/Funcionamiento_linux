---
id: evdy848c0cpufp05spptn6v
title: Gitpro
desc: 'Libro escrito por Scott Chacon (uno de los fundadores de GitHub)'
updated: 1714522359494
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