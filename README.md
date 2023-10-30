# LampDosNivelesPelayo
# Índice
1. [Introducción: Trabajo a realizar](#Introducción)
2. [Creacion Máquinas y Scripts: Creacion Máquinas y Scripts](#Creacion-MaquinasyScripts)
3. [Configuración Apache: Configuración Apache](#Configuracion-Apache)
4. [Configuración Mysql: Configuración Mysql-Server](#Configuracion-Mysql)
   
## 1.- Introducción

### Se deberá:
1. Crear un repositorio público en github para el proyecto.
2. Configurar el entorno con vagrant, teniendo en cuenta que cada máquina deberá llamarse (hostname) con tu nombre, por ejemplo, PelayoGarridoApache y PelayoGarridoMysql.
3. Realizar el aprovisionamiento de cada máquina a través de un script bash.


## 2.- Creacion Máquinas y Scripts

Lo primero que deberiamos realizar es la crecion de apache.sh y mysql.sh que serian los scripts de las maquinas correspondientes a Apache y Mysql
Imagen apache.sh
![](apache_sh.PNG)
Imagen mysql.sh
![](mysql_sh.png)
Imagen Creación de Máquinas
![](Vagrantfile.png)
Después de haber configurado las máquinas lo que haremos será comprobar que estas estan activas
![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/65a2a59c-7e23-4aa5-848a-17b8c3b244d9)

## 3.- Configuración Apache

Una vez asegurado que todo está correctamente deberemos crear una carpeta en */var/www* para clonar el repositorio del ejercicio en su interior
![](2.png)
![](3.png)
Después deberemos entrarnos en la carpeta *src* dentro de la carpeta que hemos clonado y moverlo a nuestra carpeta creada con anterioridad
![](4.png)
Lo siguiente seria irse a */ect/apache2/sites.available* y copiar el archivo de configuracion para modificarlo nosotros a nuestro gusto
![](5.png)
Y depués de crearlo lo que haremos será editarlo agregando la direccion de la carpeta que hemos creado anteriormente
![](6.png)
Utilizando el siguiente comando lo que haremos será habilitar el archivo que acabamos de modificar y despues nos iremos hasta */ect/apache2/sites.enabled* para desactivar el archivo que copiamos antes y utilizaremos el comando **systemctl reload** para actualizar lo que hemos hecho
![](7.png)
Por último lo que tendremos que hacer será acceder al fichero *config.php* y cambiar los valores del interior acorde a los de nuestra máquina
![](8.png)
(Deberemos de tener instalado el servidor de mysql en modo cliente con *sudo apt install -y default-mysql-client* 
## 4.- Configuración Mysql

Lo primero que deberemos de hacer en nuestro servidor Mysql será editar el fichero *50-server.cnf* dentro de */etc/mysql/mariadb.conf.d* y cambiar la bind-address por la de tu máquina server
![](9.png)
![](10.png)
Depués entraremos en la base de datos desde el root y crearemos un usuario que contenga todos los permisos con la ip de la máquina apache
![](11.png)
Posteriormente tenemos que clonar el repositorio de github que contiene la base de datos que deseamos
![](12.png)
Por último accedemos a la carpeta clonada, a su subdirectorio db y en el archivo *Database.sql* borramos las tres ultimas líneas
![](13.png)
Aquí se muestra la comprobacion de que la base de datos existe
