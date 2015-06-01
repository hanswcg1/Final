
#Diplomado Software Libre GNU/LINUX - EGPP
## Modulo II
##Docente: David Mendoza Paco

```
INDICE
1.	COMANDOS GENERALES
2.	INSTALACION DE DEBIAN
3.	CONFIGURACION DE RED
4.	REPOSITORIOS
5.	GITHUB
6. 	TECNOLOGIA DE VIRTUALIZACION KVM
7. 	INSTACION DE DEBIAN EN DISCO VIRTUAL
8. 	CREACION DE GRUPO
9. 	CREACION DE VOLUMENES LOGICOS
10.	CONFIGURACION DINAMICA DE DHCP
11.	REDIMESION DEL DISCO VIRTUAL
12.	UTILITARIO EN MODO GRAFICO
13.	CONFIGURACION DEL DNS
14.	MANEJO DEL SSH
```

###COMANDOS GENERALES

##COMANDOS BASICOS DE LINUX
*** Listar Archivos***
```
ls
```
***Listar Archivos por Fecha de Modificación***
```
ls -lahtr
```
***Cear Directorios***
```
mkdir nombre_carpeta
```
***Crear Sub-Carpetas***
```
mkdir -p /nombre_carpeta/nombre_subcarpeta
```
***Crear varias carpetas***
```
mkdir /pmp/{c1,c2,c3,c4,c5,c6}
```
***Crear Varias carpetas en subcarpetas***
```
mkdir -p /tmp/aaa/bbb/ccc/{c1,c2,c3,c4,c5,c6}
```
***Ingresar al directorio actual***
```
mkdir ./hola/
```
***Identificacion del Directorio Actual***
```
.  (Punto)
```
***Crear un archivo vacio de texto plano***
```
Touch ***nombre_archivo***
```
***Edicion de archivos***
```
	*nano*
	*vi*
	*vim*
	*etc*
```
***Concatenacion de archivos***
```
ls -l >> nombre de archivo
```
***Busqueda de archivos***
```
grep nombre_archivo_buscar
find ~name /* |a \ * 
```
***Borrar CARPETA***
```
rm -r ***nombre de archivo***
```
***Crear carpeta en Directorios sin permiso***
```
sudo mkdir /opt/aaa
```
***Ingreso a carpetas***
```
cd Documentos
```
***salir***
```
cd ..
cd ~  //salir de home//
```
***Instalar paquetes***
```
apt-get install  ***nombre paquete***
aptitude install ***nombre paquete***
```

#INSTALACION DEBIAN JHESSY 8.0
## Ingresar al SETUP del Equipo
###Ir al menú de Boot
### Establecer el CD ROM como primario
```
También se puede iniciar desde USB cuyo caso se asignaría como PRIMARIO8
```
*Colocar el CD ROM instalador de Debian e iniciar la instalación
*Presionar ENTER en la opción resaltada INSTALL

*	Seleccionar  el lenguaje a ser usado (ESPAÑOL)

*	Seguidamente seleccionamos el país (BOLIVIA)

*	Posterior seleccionamos el Teclado a usar, recomendando que si es teclado para español elegir la opción LATINOAMERICANO

*	Posteriormente emergerá un mensaje para configurar la red, se debe saltar este paso

*	Luego nos solicitara la contraseña del usuario ROOT

*	Ingresamos y confirmamos el PASSWORD
```
Para asignar la contraseña recordamos que el mismo sea de acuerdo a las buenas practicas establecidas en COBIT 
``` 
*	Asignar el nombre completo del usuario

*	A continuación nos sugiere el primer nombre del usuario descrito en el paso anterior, podemos ratificarlo o escribir uno nuevo.

*	Ingresamos y confirmamos el PASSWORD

###PARTICION DE DISCO
Existen diferentes opciones para la partición del disco, el mismo esta sujeto al uso que se le va a dar al equipo y/o a los sistemas pre instalados en el mismo, sin embargo se recomienda realizar el procedimiento eligiendo la forma MANUAL,  establecidas en COBIT

``` 
Para este ejemplo haremos uso de una particion de 100 establecidas en COBIT 
``` 
####Partición para el BOOT
a) Elegimos nueva partición de tipo PRIMARIO y elegir la opcion al PRINCIPIO	
b) Asignamos el tamaño de la particion 2GB
c) Utilizar como: Ext 4
d) Punto de montaje: /boot
e) Se ha terminado de definir la particion

####Partición para el SWAP
a) Elegimos nueva partición de tipo PRIMARIO y elegir la opcion al PRINCIPIO
b) Asignamos el tamaño de la particion 2GB
c) Utilizar como: Area de intercambio
d) Se ha terminado de definir la particion

####Partición para el RAIZ
a) Elegimos nueva partición de tipo PRIMARIO y elegir la opcion al PRINCIPIO
b) Asignamos el tamaño de la particion 20GB
c) Utilizar como: Ext 4
d) Punto de montaje: /raiz
e) Se ha terminado de definir la particion

####Partición para el HOME
a) Elegimos nueva partición de tipo PRIMARIO y elegir la opcion al PRINCIPIO
b) Asignamos el tamaño de la particion 40GB
c) Utilizar como: Ext 4
d) Punto de montaje: /home
e) Se ha terminado de definir la particion

####Partición para Datos
a) Elegimos nueva partición de tipo PRIMARIO y elegir la opcion al PRINCIPIO
b) Asignamos el tamaño de la particion 3GB
c) Utilizar como: Ext 4
d) Punto de montaje: Introducir manualmente
e) introducir  /datos
e) Se ha terminado de definir la particion

Seguidamente emergera el AVISO: Finalizar el Particionamiento

Y el Mensaje DESEA FINALIZAR seleccionar <SI>


###CONFIGURACION DE LA RED

***Informacion de la tarjeta de red***
```
 lspci 
 lspci |grep -i network 
 lspci |grep -i ethernet
```
***Informacion de la red wifi***
```
 lspci |grep -i wireles
```
***Configuracion de red modo gráfico IPV4 ó IPV6***
```
gnome-control-center network
```
###REPOSITORIOS

***Ingreso como super usuario***
```
sudo su
su
```
***Ingreso a repositorio***
```
nano /etc/apt/sources.list
```
***Instalacion de sudo***
```
apt-get install sudo
add user **usuario** sudo
```
***Instalacion de drives de red***
```
aptitude search ~dBCM4313
apt-get install firmware-brcm80211
non-free
```
*** Instalacion de drives por puertos DVD***
```
sudo mkdri /mnt/dvd2
sudo mkdir /mnt/dvd3
sudo mount /mnt/hd/iso/wheezy/debian-7.4.0 - amd 64 - DVD -1.ISO  /mnt/dvd!
```

###GITHUB

##Indice

* Creacion de nuevo proyecto
* Crear Repositorio y clonacion con **git clone**
* Creacion de Archivo .md y configuracion de la cuenta con **git config**
* Preparar archivo para subir y colocar mensaje con **git commit**
* Subir el archivo al repositorio con **git push**

***Instalacion de git***
```
apt-get install git
```
##Creacion de nuevo proyecto
```
git init
```
* Crear un archivo de tipo .md para este ejemplo con el siguiente comando.

```
:~$ nano README.md
```

Editamos el archivo creado con la estructura **Mark Down**.
```
* :(Lista)
# :(Titulo)
##:(subtitulo)
...
```

Una vez editadon nuestro documento de tipo .md guardamos y configuramos nuestra cuenta para subir y hacer un commit de la siguiente forma.
```
:~$ git config --global user.name "nombre_de_usuario".
:~$ git config --global user.email tu_correo@tipo.com
```
La configuracion de la cuenta solo se la debe hacer una sola vez.

##Crear Repositorio y clonacion con **git clone**

Para crear un repositorio dentro de la pagina de GitHub seguimos los siguientes pasos:
* click en el icono o simbolo mas (+)
* Click en **New repository**

* Colocar un nombre para el reposistorio
* Seleccionar el check de tipo Public
* Click en el boton **Create Repository**

* Ubicarnos en la carpeta o directorio donde deseamos clonar el Repositorio
* Copiar la url Generada despues de haber creado el Proyecto

* Ubicados ya en la carpeta colocamos el siguiente codigo en la terminal.

```
git clone [Url:http//github.com/nombreusuario/Nombre_Proyecto.git]
```
* Revisamos si realmente clono de manera correcta el proyecto con la siguiente linea de comandos en la terminal.

```
:~$ ls
```
* Ingresa a la carpeta clonada y colocar el siguiente codigo para ver archivos ocultos.

```
:~$ ls -la
```

## Preparar archivo para subir con 'git commit'
Luego de haber configurado nuestra cuenta preparamos el archivo para subir al repositorio con el comando **"commit"**.
```
:~$ git commit -m "Mensaje_del_archivo"
```
Luego de haber echo el commit vera que en la pagina de nuestra cuenta no existe aun el archivo, esto se debe que con el comando commit solo se prepara el archivo para subir a nuestro repositorio, para subir realmente el archivo deberemos hacer con el comando push.

## Subir el archivo al repositorio con 'git push'
Luego de haber preparado el archivo con el commit, solo nos queda hacer un push para subir al repositorio.
Para poder hacer push al archivo se hace con la siguiente linea de codigo.
```
:~$ git push origin master
```
Luego de haber echo el push nos pedira datos de nuestra cuenta, el nombre usuario y password de la cuenta.
Una vez colocado nuestros datos de cuenta nos vamos a la pagina de git y actualizamos y veremos que ya ha sido subido nustros archivos.
Para saber el estado actual de nuestro archivo podemos ver con la siguiente linea de codigo.
```
:~$ git status
```
La linea de codigo nos muestra el estado actual que tiene nuestro reporsitorio.
Para subir un nuevo archivo al repositorio deberemos usar el comando:
```
:~$ git add nombre_del_archivo.add (o)
:~$ git add . (sube todos los archivos que hayamos creado).
```

#VIRTUALIZACION CON KVM

***Verificamos si el equipo soporta la virtualizacion***
```
grep vmx /proc/cpuinfo      PARA EQUIPOS Intel
grep svm /proc/cpuinfo      PARA EQUIPOS AMD
```
***INSTALACION DE KVM***
```
apt-get install qemu-kvm libvirt-bin virtinst virt-viewer
```
***Para Administrar KVM***
```
apt-get install virt-manager
```
***Una ves instalado KVM Adicionamos los usuarios al grupo KVM***
```
adduser usuario kvm
adduser usuario libvirt
```
##INSTALACION DE SO LINUX EN MAQUINA VIRTUAL

* * *
Para particionar una maquina virtual con particion LVM seguimos los siguientes pasos.
1. /boot
2. swap
3. / (Sistema de fichero Raiz)
3. LVM
4. home
5. tmp

# 1.- /boot
* Seleccionamos el tipo de particion **Manual**.
* Seleccionamos el **disco duro Virtual**.
* Seleccionamos **Crear tabla de particion**.
* Seleccionamos el Espacio Libre del disco virtual.
* Elegimos **Nueva Particion** y le damos un tamano (256 MB) para el booteo.
* Marcamos como tipo **Primario**.
* Posicion **Principio**.
* Seleccionar la Opcion utilizar como..(Elegimos **Sistema de ficheros  ext2**).
* Punto de montaje **/boot**
* Elegir **Finalizar Particion.**
* * *
# 2.- Swap
* Seleccionamos **Espacio Libre**
* Elegimos **Nueva Particion**
* Le damos un espacio de 512MB
* Seleccionamos el tipo de particion como **Logica**
* Y lugar de la Particion **Principio**
* Seleccionamos la Opcion utiliza como... (Elegimos **Area de Intercambio**)
* Elegir **Finalizar Particion**
* * *
# 3.- / (SISTEMA DE FICHERO RAIZ)
* Seleccionamos **Espacio Libre**
* Elegimos **Nueva Particion**
* Le damos un espacio de 1GB o mas
* Tipo de particion **Logica**
* Lugar de la Pariticion **al Principio**
* Seleccionamos la Opcion utiliza como... (Elegimos **Sistema de ficheros ext4**)
* Punto de Montaje **/ Sistema de fichero Raiz**
* Elegir **Finalizar Particion**
* * *
# 4.- LVM
* Seleccionamos la Opcion Configurar el Gestor de Volumenes Logico LVM
* Guardar los cambios de la Particion anterior.
* Seleccionar la Opcion **Crear Grupo de Volumen**
* Colocamos un Nombre significativo y le damos aceptar
* Seleccionamos el espacio libre y le damos Aceptar
* Finalizamos la Particion
* * *
# 5.- home
* Seleccionamos la Opcion **Crear Volumen Logico**
* Seleccionamos el grupo de volumen que se creo anteriormente 
* Le damos un nombre al Volumen Logico 'home'
* Le damos un tamano de 500MB
* * *
# 6.- tmp
* Seleccionamos nuevamente **Crear Volumen Logico**
* Seleccionamos el grupo de volumen que se creo anteriormente.
* Le damos un nombre al Volumen Logico 'tmp'
* Le damos un tamano de 200MB
* Y finalmente seleccionamos la Opcion Terminar.
* * *

Ahora configuramos las opciones de Arranque de la particion Creada.
* Seleccionamos el home de LVM que se creo le damos enter.
* Le damos Utilizar como.. (ext4)
* Seleccionamos Punto de Montaje home
* Y seleccionamos se ha terminado de definir la particion

Ahora configuramos el tmp.
* Seleccionamos el tmp del LVM creado
* Seleccionamos Utilizar como.. (ext4)
* Seleccionamos Punto de Montaje (/tmp)
* Y seleccionamos se ha terminado de definir la Particion

***Y por ultimo seleccionamos Finalizar Particion para que comience con la instalacion del nuevo Sistema Operativo***

##PARTICIONES DE DISCO DURO

1. Sacamos una copia de la imagen (ubicamos el lugar de instalacion)
1. ls -l (para ver el archivo)
2. sudo cp debian.img debian.img.bak => COPIA

##INCREMENTO DE TAMAÑO DE PARTICION

Ver particiones df -h
aumentamos memoria para tmp 100 megas mas
vgdisplay (para ver espacio libre)
vgs para ver del grupo
lvs Muestra la datos de los discos
lvextend -L+100M /dev/mapper/gpsistemas-tmp
ahora redimencionamos sistemas de archivos
umount /tmp (desmontamos la particion para que actualice los datos) si no funciona forzamos a que se desmonte umoun -l /tmp
e2fsck -f  /dev/mapper/gpsistemas-tmp (para ver si todo esta correcto)
resize2fs dev/mapper/gpsistemas-tmp (para redimencionar)
mount /tmp (montamos la particion) y df -h para ver estado de la particion

##DECREMENTO DE TAMAÑO DE PARTICION

## REDUCIR EL TAMAÑO DE LA PARTICION

### Desmonstamos la particion de / tmp

```
umount /dev/mapper/sistemas-tmp
df -h
```

### Reducimos el tamaño de la particion

```
e2fsck -f /dev/mapper/sistemas-tmp 100M
resize2fs /dev/mapper/sistemas-tmp 100M 
```

### ahora montamos la particion de /tmp

```
mount /tmp
```

### Reducimos la informacion

```
lvreduce -L 100M /dev/sistemas-tmp
lvs
```

## Agregar nuevo hardware de almacenamiento a nuestra virtual.

### adicionamos el disco HD nuevo.
### Verificamos el tamaño de las extenciones.
```
df -h
fdisk -l
```

### Vemos el tamaño de las particiones para poder crear un nuevo volumen.

```
cfdisk /dev/vdb
``` 

### Verificamos con:

```
vgdisplay

pvdisplay   //verifica los grupos a los que pertenece
```

### Ahora cramos la nueva particion.

```
cfdisk /dev/vdb
```

### nos mostrara en consola algunas opciones en donde le daremos:
### New - Primario - tamaño: 1024M - Beging - Write - y Quit

### Teniendo ya la particion, creamos la particion física del HD

```
fdisk -l /dev/vdb1

pvcreate /dev/vdb1     //Nos mostrara un mensaje de Sercifull
```

### Creamos el nuevo nuevo grupo del Volumen lógico

```
vgcreate grupoA /dev/vdb1
```

### Verificamos si se a unido al grupo

```
pvdisplay
lvs
```

### Ahora crearemos el Volumen Logico dentro del grupoA

```
lvcreate -L 500M -n volumen01 greupoA
lvs
```

### Le damos el formato a la nueva particion

```
mkfs.ext3 -m 0 /dev/mapper/greupoA-Volumen01
```

### Ahora montamos la particion

```
mkdir /mnt/volumen01
mounnt /dev/mapper/grupoA-volumen01 /mnt/volumen-01
```

### Para poder montar automaticamente en cada reinicio modificamos, y adicionamos la direccion del montaje del nuevo volumen

```
nano /etc/fstab
```

## Ampliar tamaño del HD

### Ingresamos hasta la hubicacion de las unidades virtuales, una ves dentro la carpata donde se encuentran nuestras virtuales le damos el siguiente comando:

```
qemu-img resize nombre_maquina_virtual +10G
```

### Verificamos el Espacio adicionado con:

```
cfdisk /dev/vda
```

### Ahora cambiamos el Tamaño de la particion reiniciando con el "Git-parted", cambiando de tamaño del Extend y del LVM.

## Configuracion de redes en Linux.

### Ver las conexiones de las redes-

```
nm-connection-editor
```

### El Archivo para ver la configuracion de la Red es en la direccion.

```
/etc/network/interfaces
```

### Donde la interfas de red es: eth0
### donde el loop bak : lo

## Configuracion Dinamica

### al ingresar a la configuracion de la red, se encontrara en "dhcp"

## Configuracion Estatica

### Ingresamos a la configuracion de la red.

```
/etc/networking/interfaces
```

### Cambiar la configuracion estatica de la red.

```
iface eth0 inet static
address numero_ip
netmask mascara_red
gateway ip_gateway
```

### Reiniciamos los servicios de red, de dos formas.

```
service networking restart
/etc/init.d/networking restart
```

### Verificamos la ip

```
ip addr show eth0
```

### Adicionamos las DNS al equipo.

```
nano /etc/resolv.conf
```

## Servicio SSH

### Instalamos el Servicio ssh

```
apt-get install ssh
```

### Configuramos el Servicio SSH

```
nano -c /etc/ssh/sshd_config
```

### En la linea 31 colocamos "no" en PubKeyAutentication no

### Reiniciamos el Servicio SSH

```
service ssh restart
```

### Ingresamos desde otra maquina.

```
ssh usuario@ip_server_ssh
```

### Crear documento y lo subimos por ssh a la carpeta /tmp

```
echo "hola mundo" > hola.txt

scp hola.txt usuario@ip_server_ssh:/tmp
```

### Para poder copiar varias carpeta por SSH se usa lo siguiente:

```
scp -r /tmp/datos_carpeta/ usuario@ip_server_ssh:/srv
```

### Desabilitar el usuario root de SSH, en la linea 27 de la configuracion de SSH

```
en : PermitRootLogin  no
```

### Para poder ver los usuarios conectados por ssh

```
who
```

## Crear llaves para SSH

### Creamos la llave del usuario con el siguiente comando

```
ssh-keygen -t rsa -b 2048
```

### Copiamos la llave al Servidor SSH

```
ssh-copy-id -i /usuario/.ssh/id_rsa.pub usuario@ip_server_ssh
```

### Verificamos la copia de las llaves publicas

```
head ~/.ssh/id_rsa.pub
```
### Otorgar permisos a carpetas

```
chmod o+w prueba/
```

### Quitar permisos

```
chmod o-w prueba/
```

### Permisos solo de lectura

```
chmod 437 prueba/
```

### Cambiar usuarios de carpetas

```
chown root:usuario prueba/
```

### Adicionar usuarios en Linux

```
sudo useradd usuario1
```

### Adicionar Password de usuario

```
sudo passwd usuario1
```

### Listar usuarios del equipos

```
getent passwd
```

### Ingresar como otro usuario

```
sudo su - usuario1
```

### Crear usuario

```
sudo adduser usuario2
```
