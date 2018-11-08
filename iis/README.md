# IIS - Servidor Web básico

##  Informe de instalación y configuración de las diferentes prácticas realizadas sobre IIS en Windows 2016.

**INFORME I**

Instalar IIS en windows 2016 server, para ello agregamos un nuevo rol o características.

![](iis1/1.PNG)

Incluimos Autenticación Básica y de Windows.

![](iis1/2.PNG)

![](iis1/3.PNG)

Comprobamos el acceso a nuestro servidor web (localhost) desde un navegador web (aparece una página en construcción).

![](iis1/4.PNG)

Entramos en el cliente y accedemos, desde el navegador web, a la página principal del
servidor a través de la IP del servidor.

![](iis1/5.PNG)

Accedemos ahora desde el cliente a la misma página mediante el nombre principal del dominio y desde cualquier otro alias que hayamos definido en la configuración DNS.

![](iis1/6.PNG)

Creamos los alias y comprobamos la conexión.

![](iis1/7.PNG)

![](iis1/8.PNG)

Tratamos de acceder desde el cliente al sitio www del dominio principal.
* ¿Qué ocurre? **Da error**

![](iis1/9.PNG)

Añadimos un alias en el servicio DNS que relacione el sitio www con el dominio principal.

![](iis1/10.PNG)

Intentamos ahora acceder desde el cliente.

![](iis1/11.PNG)

Creamos una página web HTML(index.htm) como página principal del dominio y la colócamos en C:\Inetpub\wwwroot.

![](iis1/12.PNG)

Comprobamos el acceso a esta página desde el propio servidor y desde el cliente, utilizando los diferentes alias y direcciones configurados en el servicio DNS.

* Desde el dominio en el servidor.

![](iis1/13.PNG)

* Desde el alias en el servidor.

![](iis1/14.PNG)

* Desde el cliente al dominio.

![](iis1/15.PNG)

* Desde el cliente al alias.

![](iis1/16.PNG)

Creamos un pequeño sitio web con varias páginas e imágenes organizadas en subcarpetas de wwwroot.

![](iis1/17.PNG)

![](iis1/18.PNG)

Abrimos el Administrador de Internet Information Services y comprobar la estructura del sitio creado en Sitio Web Predeterminado.

![](iis1/24.PNG)

![](iis1/19.PNG)

Accedemos y navegamos por el sitio web tanto desde el servidor como desde el cliente.

* Desde el servidor a pagina1.

![](iis1/20.PNG)

* Desde el servidor a pagina2.

![](iis1/21.PNG)

* Desde el cliente.

![](iis1/22.PNG)

* Desde el cliente a pagina1.

![](iis1/23s.PNG)

**INFORME II**

Creamos dos nuevos sitios web, uno asociado al dominio principal;

![](iis2/1.PNG)

Y otro a un subdominio.

![](iis2/2.PNG)

Comprobamos.

![](iis2/3.PNG)

Incluimos una nueva zona de búsqueda directa en el servicio DNS para ambas zonas con las opciones de configuración necesarias (registros A, CNAME, …).

* DNS de la zona principal.

![](iis2/4.0.PNG)

![](iis2/4.PNG)

* Le añadimos un CNAME al dominio principal.

![](iis2/5.PNG)

![](iis2/8.PNG)

* Le añadimos un host al dominio principal.

![](iis2/9.PNG)

* DNS del subdominio.

![](iis2/6.PNG)

![](iis2/7.PNG)

* Le añadimos un host al subdominio.

![](iis2/10.PNG)

* Le añadimos un CNAME al subdominio.

![](iis2/11.PNG)

**Incorporamos algunos archivos HTML, imágenes y subcarpetas al nuevo sitio web y comprobamos el acceso desde navegadores web tanto del servidor como del cliente.**

* Comprobación de zona 1 desde servidor.

![](iis2/13.PNG)

* Comprobación de zona 1 desde cliente.

![](iis2/14.PNG)

* Comprobación de zona 2 desde servidor.

![](iis2/12.PNG)

* Comprobación de zona 2 desde cliente.

![](iis2/15.PNG)


**INFORME III**

Creamos una carpeta que se corresponda
con una sección del sitio web creado en la práctica anterior.

![](iis3/0.PNG)

Creamos un nuevo directorio virtual en IIS dentro del sitio web y lo  relaciónamos con la carpeta que hemos creado, dentro del mismo hacemos 3 subcarpetas con páginas html para comprobar el funcionamiento de los  sitios.

![](iis3/1.PNG)

![](iis3/2.PNG)

Realizamos las configuraciones DNS necesarias para que los diferentes nombres que hemos creado referentes a nuestro sitio web sean resueltos correctamente.

* Para ello añadimos un hostname llamado departamentos en la zona principal apuntando al servidor.

![](iis3/3.PNG)

* Creamos un alias servicios y lo enlazamos con departamentos.

![](iis3/4.PNG)

![](iis3/5.PNG)

* Comprobamos desde el servidor al directorio departamentos.

![](iis3/6.PNG)

* Comprobamos desde el servidor a la subcarpeta informatica.

![](iis3/7.PNG)

* Comprobamos desde el servidor a la subcarpeta administración.

![](iis3/8.PNG)

* Comprobamos desde el servidor a la subcarpeta contabilidad.

![](iis3/9.PNG)

* Comprobamos desde el cliente a la subcarpeta administración.

![](iis3/10.PNG)

* Comprobamos desde el cliente a la subcarpeta informatica.

![](iis3/11.PNG)
