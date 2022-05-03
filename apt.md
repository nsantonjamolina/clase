
# Comando APT
 
**APT**, **Advanced Packaging Tool**, es un comando que permite a los usuarios administrar los paquetes de su distribución Linux. Mediante este comando podemos instalar, actualizar, eliminar paquetes de Ubuntu, Debian y otras distribuciones. Estos paquetes contienen aplicaciones, actualizaciones, etc. 

 
### Principales comandos con APT

  

*Hay que tener en cuenta que el comando apt se debe lanzar en modo administrador. Por tanto hay que lanzarlo con sudo*



### Actualizar los repositorios



APT funciona como una base de datos de los paquetes disponibles. Por lo tanto, siempre debemos tener la base de datos actualizada.  



`sudo apt update`  



### Actualizar los paquetes y los programas

  

`sudo apt upgrade`



### Diferencias entre apt update y apt upgrade


Mediante apt update conseguimos que el sistema conozca si existen nuevas versiones de un paquete pero no lo actualiza. 
Es necesario ejecutar apt upgrade para poder obtener los nuevos paquetes. 



`sudo apt update && sudo apt upgrade -y`



### Instalar

  

`sudo apt install <programa>`
`sudo apt install <programa_1> <programa_2> <programa_3>`



Si tratamos de instalar un paquete que ya tenemos instalado simplemente instalará la versión más actual.

  

### Listar los paquetes para instalar o actualizar

  

`sudo apt list`

  

### Listar los paquetes instalados

  

`sudo apt list --installed`

  

### Listar los paquetes disponibles para actualizar

  

`sudo apt list --upgradeable`

  

### Buscar paquetes

  

`sudo apt search <cadena_de_texto>`

  

### Reinstalar un paquete

  

`sudo apt reinstall paquete`

  

### Eliminar un paquete

  

`sudo apt remove paquete`

  

### Eliminar todo rastro de un paquete

  

`sudo apt purge paquete`

  

### Limpiar el sistema con APT

  

`sudo apt autoremove`  
Elimina las dependencias de paquetes que han sido eliminados


## Sobre repositorios
# Añadir repositorios de forma manual


Cuando realizamos las operaciones de instalación de paquetes, estos son descargados de unos pocos repositorios. 
Un repositorio, básicamente, es un servidor que contiene la información de los paquetes disponibles. 

Los repositorios que son utilizados están en el fichero

`/etc/apt/sources.list`

Además, dentro del siguiente directorio también podemos encontrar algunos repositorios

`/etc/apt/sources.list.d/`

# Instalación por medio de add-apt-repository

El comando `add-apt-repository [options] repository` permite añadir un repositorio al conjunto de repositorios.

1. Añadir la clave pública `sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4`
2. Añadir el repositorio `sudo add-apt-repository 'deb [arch=amd64] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse'`

De este modo ya tenemos el repositorio asociado a la aplicación MongoDB

Podemos proceder a instalarlo mediante `sudo apt install mongodb-org`


### Sintaxis del fichero sources.list

`deb http://lliurex.net/bionic bionic main restricted universe multiverse`

Es habitual querer instalar paquetes que no están en nuestro repositorio.
Es necesario añadir estos repositorios al listado de repositorios disponibles

La forma manual es la siguiente:

`curl -L https://couchdb.apache.org/repo/bintray-pubkey.asc | sudo apt-key add -`
Es habitual que los repositorios requieran una certificado (GPG) para poder interactuar. Con el comando anterior lo descargamos y lo añadimos al repositorio de llaves públicas. 

`echo "deb https://apache.bintray.com/couchdb-deb bionic main" | sudo tee -a /etc/apt/sources.list`
Añadimos la URL a nuestro listado de repositorios

`sudo apt update`
`sudo apt install couchdb`

## Ejercicios

Los siguientes ejercicios deben realizarse sobre una máquina virtual [Ubuntu](https://ubuntu.com/download/desktop/thank-you?version=22.04&architecture=amd64)

1. Consulta los paquetes que hay instalados en tu equipo
2. Lanza el comando `sudo apt install`. Muestra el resultado.
3. Lanza el comando `sudo apt upgrade`. Muestra el resultado y explica qué ha sucedido. 
4. Busca si existe el paquete gimp
5. Instala gimp
6. Elimina gimp (comando remove)
7. Añade el repositorio personal `ppa:gerardpuig/ppa` e instala el programa ubuntu-cleaner
8. Instala vlc elimina (comando purge)





2. 

3. Explica qué es un repositorio.

4. Instalando mariadb

6. Ejecuta y explica los siguientes comandos

sudo apt update; sudo apt install software-properties-common apt-transport-https
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
sudo apt install code

7. ¿Cómo podemos eliminar una clave PGP pública que ya no utilicemos?
8. 

5. Instalando **Spotify**

    -   Instala curl (Herramientas para la transferencia de archivos)
        - sudo apt install curl
    -   Importa la clave pública
        - curl -sS https://download.spotify.com/debian/pubkey_5E3C45D7B312C643.gpg | sudo apt-key add - 
        - echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
    -   Acualización e instalación
        - sudo apt-get update && sudo apt-get install spotify-client    

My favorite search engine is [cosas_2](https://github.com/nsantonjamolina/clase/blob/70425cc9a6ddf254d5c959a41b37f63b15c7a4d3/som2122/cosa.md).

