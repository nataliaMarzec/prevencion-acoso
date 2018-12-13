[![Waffle.io - Columns and their card count](https://badge.waffle.io/nataliaMarzec/prevencion-acoso.svg?columns=backlog)](https://waffle.io/nataliaMarzec/prevencion-acoso)
[![Build Status](https://travis-ci.org/nataliaMarzec/prevencion-acoso.svg?branch=master)](https://travis-ci.org/nataliaMarzec/prevencion-acoso)

# Prevención acoso

## Software necesario

##### JDK 1.8:

- Para verificar si cumple con los requisitos de Java 1.8 ir a https://www.java.com/es/download/help/sysreq.xml y luego escribir en la terminal `cat /etc/issue` 

- Ir a http://java y descargar paquete

- Escriba  `cd nombre_ruta_acceso_directorio` en la terminal.

- Mueva el archivo binario de almacenamiento .tar.gz al directorio actual.

- Desempaquete el tarball e instale Java

   `tar zxvf jre-8u73-linux-x64.tar.gz`
 
##### Maven:

 - Ir a la página oficial de Maven http://maven.apache.org/
 
##### MySQL:
 
  - Instalar Mysql Server en https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04
  
##### Eclipse:

 - Instalar IDE Eclipse en http://www.eclipse.org/downloads/packages/release/neon/3/eclipse-ide-java-ee-developers

## Configuración del entorno

** Crear la base de datos.
  - Para inicializar la base de datos desde la consola de Mysql Server escribir los siguientes comandos:
     
`mysql -u root -proot`

  - Crear una base de datos desde la consola y usarla(mas comandos en https://desarrolloweb.com/articulos/2408.php):

 - create database prevencion_acoso;
`use prevencionAcoso;`

 - Luego desde la clase GenerateDataMain correr _Run_-> _JavaApplication_ para crear la base de datos.
Si es necesario borrar la base de datos, usar:
`drop database prevencionAcoso;`

##### Cargar los datos iniciales

* Para levantar el proyecto con jetty desde eclipse:
- elegir _Run_ del menu de eclipse, luego  elegir la opción _Run Configurations_
- buscar _Maven Build_
- hacer clic con botón derecho sobre _Maven Build_ y elegir _new_
- en la ventana que se despliega:
	- si queremos podemos en _Name_ escribir un nombre
	- en el botón _Workspace_ elegimos nuestro proyecto
	- en donde dice Goals: escribimos _jetty:run_
	- luego hacemos clic en el boton _Run_

* Para levantar el proyecto desde consola:
- desde donde se encuentra nuestro proyecto abrimos una terminal, luego ejecutamos el comando `mvn jetty:run`.

- Por último, independientemente de la opción elegida, abrimos un navegador y escribimos `localhost:8080`.

* Para debuguear:

- Levantar el proyecto por consola como se indica en el paso anterior, pero utilizando el comando `mvnDebug` en vez de `mvn`. Quedaría `mvnDebug jetty:run`.

- En el Eclipse, ir a `Run -> Debug configurations...` y agregar una nueva del tipo `Remote Java Application`. Configurarlo como se ve en la imagen, usando `localhost` para el _Host_ y `8000` para el _Port_
      
#### Importar el proyecto en Eclipse.

 - Clonar el proyecto Maven desde la terminal:
       `git clone https://github.com/nataliaMarzec/prevencion-acoso`

  - Integrar el proyecto Maven clonado a Eclipse con `mvn eclipse:eclipse`; luego se podrá importar en Eclipse, desde el menú -> _import_ -> _Existing Maven Projects_ 

  - Probar el Maven desde consola con `mvn test` ;otra opción con Eclipse, sobre la clase _Test.java_ clicklear sobre _Run As_ -> _JUnit_
 





 
 


