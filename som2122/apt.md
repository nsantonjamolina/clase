
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


Cuando realizamos las operaciones de instalación de paquetes


## Ejercicios

1. First item

2. Second item

3. Third item

My favorite search engine is [cosas_1](som2122/cosa.md).
My favorite search engine is [cosas_2](https://github.com/nsantonjamolina/clase/blob/70425cc9a6ddf254d5c959a41b37f63b15c7a4d3/som2122/cosa.md).


