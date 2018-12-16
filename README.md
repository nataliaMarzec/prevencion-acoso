[![Waffle.io - Columns and their card count](https://badge.waffle.io/nataliaMarzec/prevencion-acoso.svg?columns=backlog)](https://waffle.io/nataliaMarzec/prevencion-acoso)
[![Build Status](https://travis-ci.org/nataliaMarzec/prevencion-acoso.svg?branch=master)](https://travis-ci.org/nataliaMarzec/prevencion-acoso)

# Prevención acoso

## Software necesario

### OpenJDK :

 - Ir a la página oficial https://openjdk.java.net/install/
 - Desde consola escribir: ̣̣`sudo apt-get install openjdk-8-jre_`  O sudo apt-get install openjdk-6-jdk 

 
### Maven:

 - Ir a la página oficial de Maven https://maven.apache.org/download.cgi para decargar el paquete binario.
 
 - Ir a la terminal al directorio:
        `cd /opt`
        
 - Extraiga el archivo apache-maven en el directorio opt:
        `sudo tar -xvzf ~/Downloads/apache-maven-3.6.0-bin.tar.gz`
        
 - Edite el archivo / etc / environment y agregue la siguiente variable de entorno:
        `M2_HOME="/opt/apache-maven-3.6.0"`
        
 - También, agregue el directorio bin a la variable PATH:
        `/opt/apache-maven-3.6.0/bin`
        
 - Edite el contenido (por ejemplo puede usarse el editor nano https://www.neoguias.com/como-instalar-y-utilizar-nano/):
        `sudo nano /etc/environment`  
         
 - ADVERTENCIA: no reemplace el archivo de entorno con el siguiente contenido porque es posible que ya tenga diferentes variables de entorno que se requieren para que otras aplicaciones funcionen correctamente. Observe el final de la variable PATH y la variable M2_HOME:
 
         `PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/ 
                         games:/usr/lib/jvm/jdk-10.0.2/bin:/opt/apache-maven-3.6.0/bin"
          JAVA_HOME="/usr/lib/jvm/jdk-10.0.2"
          M2_HOME="/opt/apache-maven-3.6.0`  
           
 - Actualice el comando mvn:
 
          `sudo update-alternatives --install "/usr/bin/mvn" "mvn" "/opt/apache-maven-3.6.0/bin/mvn" 0
           sudo update-alternatives --set mvn /opt/apache-maven-3.6.0/bin/mvn`
     
 - Agregue la finalización de Bash a mvn para que pueda completar los comandos de Maven presionando Tab varias veces:
 
         `sudo wget https://raw.github.com/dimaj/maven-bash-completion/master/bash_completion.bash --output-document /etc/  bash_completion.d/mvn`
   
 - Para verificar la versión de mvn:
 
         `mvn --version`
   
### MySQL:
 
  - Instalar Mysql Server en https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04
  - Actualizar el índice de su paquete, instale el _mysql-server_ paquete y luego ejecute el script de seguridad incluido.

        `sudo apt-get update
         sudo apt-get install mysql-server
         mysql_secure_installation`
  
### Eclipse:

 - Ir a  http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers
 
 - Descargar el paquete Eclipse y descomprimirlo en el directorio /opt
 
 - Crear un archivo _eclipse.desktop:
   
       `nano eclipse.desktop`
       
 - luego copiar el siguiente código:
 
        `[Desktop Entry]
         Name=Eclipse 
         Type=Application
         Exec=env UBUNTU_MENUPROXY=0 eclipse44
         Terminal=false
         Icon=eclipse
         Comment=Integrated Development Environment
         NoDisplay=false
         Categories=Development;IDE;
         Name[en]=Eclipse`
         
 - Empezamos a instalar:
 
        `sudo desktop-file-install eclipse.desktop`
        
 - Para crear un acceso directo o lanzador ver http://www.mundo9eek.com/2016/08/instalar-ide-eclipse-en-linux-Ubuntu-16.04.html (puntos 8 al 11)
        

## Configuración del entorno

### Crear la base de datos.
  - Para inicializar la base de datos desde la consola de Mysql Server escribir los siguientes comandos:     
         `mysql -u root -proot`

 - Crear una base de datos desde la consola y usarla(mas comandos en https://desarrolloweb.com/articulos/2408.php):

 - create database prevencion_acoso;
         `use prevencionAcoso;`

 - si es necesario borrar la base de datos, usar:
         `drop database prevencionAcoso;`

### Cargar los datos iniciales

##### Para levantar el proyecto con jetty desde eclipse:

- Elegir _Run_ del menu de eclipse, luego  elegir la opción _Run Configurations_
- Buscar _Maven Build_
- Hacer clic con botón derecho sobre _Maven Build_ y elegir _new_
- En la ventana que se despliega:
	- si queremos podemos en _Name_ escribir un nombre
	- en el botón _Workspace_ elegimos nuestro proyecto
	- en donde dice Goals: escribimos _jetty:run_
	- luego hacemos clic en el boton _Run_

##### Para levantar el proyecto desde consola:

- Desde donde se encuentra nuestro proyecto abrimos una terminal, luego ejecutamos el comando `mvn jetty:run`.

- Por último, independientemente de la opción elegida, abrimos un navegador y escribimos `localhost:8080`.

##### Para debuguear:

- Levantar el proyecto por consola como se indica en el paso anterior, pero utilizando el comando `mvnDebug` en vez de `mvn`. Quedaría `mvnDebug jetty:run`.

- En el Eclipse, ir a `Run -> Debug configurations...` y agregar una nueva del tipo `Remote Java Application`. Configurarlo como se ve en la imagen, usando `localhost` para el _Host_ y `8000` para el _Port_:

  ![debug](https://user-images.githubusercontent.com/43456410/50048332-d8e5fb80-00a7-11e9-96c0-c4ea34624436.png)
      
### Importar el proyecto en Eclipse.

 - Clonar el proyecto Maven desde la terminal:
       `git clone https://github.com/nataliaMarzec/prevencion-acoso`

  - Integrar el proyecto Maven clonado a Eclipse con `mvn eclipse:eclipse`; luego se podrá importar en Eclipse, desde el menú -> _import_ -> _Existing Maven Projects_ 

  - Probar el Maven desde consola con `mvn test` ;otra opción con Eclipse, sobre la clase _Test.java_ clicklear sobre _Run As_ -> _JUnit_
 





 
 


