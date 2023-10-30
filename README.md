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

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/a57ccde4-4f63-4091-b91e-1a3148e39cf7)

Imagen mysql.sh

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/63ea6ce1-914b-4056-b9b4-3b5e98ce5640)

Imagen Creación de Máquinas

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/bec0deb7-53b7-4c1c-833c-b35e557cd2b2)

Después de haber configurado las máquinas lo que haremos será comprobar que estas estan activas

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/65a2a59c-7e23-4aa5-848a-17b8c3b244d9)

## 3.- Configuración Apache

Una vez asegurado que todo está correctamente deberemos crear una carpeta en */var/www* para clonar el repositorio del ejercicio en su interior

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/3d3ed47b-d0fc-40fd-8d07-4253fcfc39ff)

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/aff5e5a6-2bb8-4a05-a763-2666e009d0c0)

Después deberemos entrarnos en la carpeta *src* dentro de la carpeta que hemos clonado y moverlo a nuestra carpeta creada con anterioridad

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/bcabf0a1-6dad-4511-83b5-f785c9fc7e7e)

Lo siguiente seria irse a */ect/apache2/sites.available* y copiar el archivo de configuracion para modificarlo nosotros a nuestro gusto

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/8b897580-bee1-424f-977a-e2cb5299c8c4)

Y depués de crearlo lo que haremos será editarlo agregando la direccion de la carpeta que hemos creado anteriormente

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/4814f9f4-accf-452f-bb6c-3237f81dd9cc)

Utilizando el siguiente comando lo que haremos será habilitar el archivo que acabamos de modificar y despues nos iremos hasta */ect/apache2/sites.enabled* para desactivar el archivo que copiamos antes y utilizaremos el comando **systemctl reload** para actualizar lo que hemos hecho

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/00c6c9b6-23ae-4e88-8617-b91df3f3cf26)

Por último lo que tendremos que hacer será acceder al fichero *config.php* y cambiar los valores del interior acorde a los de nuestra máquina

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/be2da028-dcb6-4fd9-a618-9f0928f05a96)

(Deberemos de tener instalado el servidor de mysql en modo cliente con *sudo apt install -y default-mysql-client* 

## 4.- Configuración Mysql

Lo primero que deberemos de hacer en nuestro servidor Mysql será editar el fichero *50-server.cnf* dentro de */etc/mysql/mariadb.conf.d* y cambiar la bind-address por la de tu máquina server

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/6578c6ca-ae92-42ae-bcbf-7894063e6957)

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/ac10fefd-e4c2-4b04-a3e1-fb137517f3f4)

Depués entraremos en la base de datos desde el root y crearemos un usuario que contenga todos los permisos con la ip de la máquina apache

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/0df9fa06-e001-44fa-8c14-ff75b90c3b2e)

Posteriormente tenemos que clonar el repositorio de github que contiene la base de datos que deseamos

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/924e0266-d0e2-4eb5-8dea-9e3fdde8de5d)

Por último accedemos a la carpeta clonada, a su subdirectorio db y en el archivo *Database.sql* borramos las tres ultimas líneas

![image](https://github.com/Pelayo23/LampDosNivelesPelayo/assets/146436033/b71a1139-7390-4eb1-8730-ee033f5116ec)

Aquí se muestra la comprobacion de que la base de datos existe
