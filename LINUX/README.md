# Servidor Web Apache - Linux

Se pretende obtener un conjunto de sitios web similares a los realizados en IIS, es decir, algo semejante a lo siguiente:

    Dominio principal: miempresa.com (o similar)
    Alias página principal: www.miempresa.com
    Sitio seguro (https): pagos.miempresa.com (o miempresa.com/pagos)
    Carpetas privadas protegidas: empleados.miempresa.com (o miempresa.com/empleados)
    Instalación PHP, MySQL, phpMyAdmin
    Gestión bases de datos: phpmyadmin.miempresa.com (o miempresa.com/phpmyadmin)
    Instalación FTP o SSH (opcional)
    Instalación y configuración plataforma Drupal, Joomla, Moodle, Gallery, osCommerce, etc. en página principal


## Para ello tienes que seguir los siguientes pasos.


## Apache:
        * Instalar Apache: sudo apt-get install apache2

![](imagen/1.PNG)
![](imagen/2.PNG)

        * Comprobar acceso a localhost

![](imagen/3.PNG)

        * Añadir línea www.miempresa.com asociada a IP servidor en /etc/hosts.

![](imagen/4.PNG)

         Comprobar acceso.

![](imagen/5.PNG)

        * Reiniciar apache: sudo /etc/init.d/apache2 restart.

![](imagen/6.PNG)



## PHP:
        * Instalar php: sudo apt-get install php5

![](imagen/7.PNG)

![](imagen/8.PNG)

        * Comprobar acceso a index.php -<?php phpinfo(); ?>-.
        Para ello copiamos el fichero index y lo renombramos como **index.php** y añadimos el codigo **<?php phpinfo(); ?>**

![](imagen/9.PNG)

![](imagen/10.PNG)

          * Comprobamos la pagína.

![](imagen/11.PNG)

        * sudo apt-get install libapache2-mod-php5.

![](imagen/12.PNG)

![](imagen/13.PNG)



## Crear Hosts Virtuales en Apache, es decir, asociar carpetas con sitios web.

        * Creamos empleados.miempresa.com --> /var/www/empleados.

![](imagen/14.1.PNG)


        * Configuramos los Hosts Virtuales.

![](imagen/14.PNG)

        * Activamos las pagínas.

![](imagen/15.1.PNG)

        * Comprobamos la pagína.

![](imagen/15.PNG)


## Configurar sitio web seguro pagos:

    Al instalar Apache, se instala también SSL
    Generar certificado autofirmado:
      *  § openssl genrsa -des3 -out server.key 1024

![](imagen/16.PNG)

      *  § openssl rsa -in server.key -out server.pem

![](imagen/17.PNG)

      *  § openssl req -new -key server.key -out server.csr

![](imagen/18.PNG)

      *  § openssl x509 -req -days 360 -in server.csr -signkey server.key -out server.crt

![](imagen/19.PNG)


## Modificar /etc/apache2/sites-available/000-default.conf según indicaciones PDF para crear host virtual seguro.


![](imagen/24.PNG)

      * Creamos el host.

![](imagen/26.PNG)

      * Reiniciar el sitio.

![](imagen/27.PNG)

      * Comprobar el sitio.

![](imagen/28.PNG)


## Acceso a carpetas privadas


    **Autenticación mediante .htaccess:**
    * Estructura: empleados.miemepresa.com (acceso a todos los empleados pero no anónimos).
    * Creamos el directorio **claves** y el fichero **htpaswwd** con la configuración.

![](imagen/20.0.PNG)

![](imagen/20.PNG)


    * Creamos los usuarios **Pepe y Arminda**.

![](imagen/21.PNG)

![](imagen/22.PNG)

    * Creamos el archivo de VirtualHost para el sitio Pagos.

![](imagen/24.PNG)


    * Añadimos pagos.miempresa.com a /etc/hosts.

![](imagen/26.PNG)

    * Reiniciamos el servicio Apache2.

![](imagen/27.PNG)


    * Comprobamos que la pagína funciona.

![](imagen/28.PNG)



## MySQL
    * Instalar MySQL: sudo apt-get install mysql-server.

![](imagen/30.PNG)


![](imagen/31.PNG)


![](imagen/32.PNG)


## phpMyAdmin
    * Descargar última versión (tar.gz) desde phpmyadmin.net.

![](imagen/40.PNG)

    * Cremos la carpeta phpmyadmin en /var/www.

![](imagen/41.PNG)

    * Descomprimir en subcarpeta de /var/www.

![](imagen/42.PNG)

    * Añadimos a /etc/hosts phpmyadmin.

![](imagen/43.PNG)

    * Creamos el VirtualHost de phpmyadmin.

![](imagen/44.PNG)

    * Activamos el fichero y reiniciamos el servicio apache2.

![](imagen/45.PNG)

    * Comprobar acceso.

![](imagen/46.PNG)
