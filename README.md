> Incluir aquí las medallas de Waffle y Travis.

# Prevención acoso

## Software necesario

Explicar aquí cómo instalar lo siguiente:

* JDK 1.8:


- Para verificar si cumple con los requisitos de Java 1.8 ir a https://www.java.com/es/download/help/sysreq.xml y luego escribir en la terminal $cat /etc/issue 

-Ir a http://java y descargar paquete

-Escriba: $ cd nombre_ruta_acceso_directorio

-Mueva el archivo binario de almacenamiento .tar.gz al directorio actual.

-Desempaquete el tarball e instale Java

         $tar zxvf jre-8u73-linux-x64.tar.gz

 
* Maven:

 - Ir a la página oficial de Maven http://maven.apache.org/
 
 - Descargar el siguiente archivo en el directorio opt/
 
 - Agregar al PATH el directorio bin:
 
     $ tar zxvf maven-3.0.3-bin.tar.gz
   
 - Agregar 
 
    $ export PATH=$PATH:/opt/maven/bin
    
   
 
 -Instalar desde el gestor de paquetes
 
         $sudo apt-get install maven

* MySQL:
 - Escribir las líneas de comando :
 
         $sudo apt-get install mysql-server
         
 - Iniciar o reiniciar el servidor mysql:
 
         $sudo /etc/init.d/mysql restart

 - Parar el servidor mysql:
 
         $sudo /etc/init.d/mysql stop
      

* Eclipse:

-Descargar desde la página oficial https://www.eclipse.org/neon/

## Configuración del entorno

Explicar aquí cómo hacer lo siguiente:

* Crear la base de datos.
 - Para crear la base de datos escribir los comandos:
     
         $create database prevencionAcoso;
         
         
* Cargar los datos iniciales.

 - Para crear la base de datos
     
         $create database prevencionAcoso
    
 - Para ejecutar la base de datos
   
         $use prevencionAcoso
  
 - Para borrar la base de datos
 
         $drop database prevencionAcoso;
        
* Importar el proyecto en Eclipse.

 - Crear un Workspace en IDE Eclipse
 
 - Clonar el proyecto desde consola 
 
        $git clone https://github.com/nataliaMarzec/prevencion-acoso
 
 - En el menú del IDE Eclipse ir al menú e ir a "Importar"


