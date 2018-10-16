 # Instalación y Configuracón DNS Windows Server

Crear zona de búsqueda directa para el servidor, la llamamos zona1.rasirclases.com.

![imagen](imagen/2.PNG)

Crear zona de búsqueda inversa para subred, añadimos la id de la red para que identifique las subredes.
![](imagen/3.PNG)

![](imagen/3.2.PNG)

Configuramos los reenviadores con DNS público (195.235.113.3 / 80.58.61.250 / 8.8.8.8).

![](imagen/4.PNG)

![](imagen/5.PNG)

Configuramos el servidor para ser servidor DNS Caché.
![](imagen/6.PNG)
Comprobar el funcionamiento como caché DNS de la máquina al acceder a sitios de Internet.
![](imagen/7.PNG)

Configurar cliente para que su servidor DNS sea el servidor W2016.
![](imagen/8.PNG)

##### En la zona de búsqueda directa añadir los siguientes registros:

* Un alias para el servidor denominado server.
![](imagen/9.2.PNG)

* Una impresora con IP fija denominada printer (no hace falta alias).
![](imagen/10.PNG)

![](imagen/11.PNG)
* Un servidor de correo (ficticio) denominado correo, asociado a una dirección en tu servidor.

![](imagen/12.PNG)

Hacemos un registro de recursos nuedo **(MX)**
![](imagen/13.PNG)

* Crear una subzona denominada servicios (dominio nuevo).

![](imagen/15.PNG)


 * Agregar un servidor ftp (asociado a la misma IP del servidor) .

![](imagen/16.PNG)

 * Una impresora nueva (con una IP fija).

![](imagen/17.PNG)

* Equipo del administrador del sistema (también con IP fija).

![](imagen/18.PNG)

Comprobamos que se ha creado todo correctamente.

![](imagen/19.PNG)

###### Comprobamos que se resuelven los nombres desde la consola del servidor.

 ![](imagen/20.PNG)

 Validamos un cliente en el dominio.

![](imagen/21.PNG)

 Comprobamos que el nombre de su equipo aparece en la zona de búsqueda del servidor como un nuevo registro A.

 ![](imagen/22.PNG)


 Comprobar desde la consola del cliente que se resuelven correctamente los nombres dados de alta en el servidor (aunque en algunos casos, si se trata de direcciones ficticias, no se obtenga respuesta).

 ![](imagen/23.PNG)

 Realizar, también desde el cliente, algunas operaciones con nslookup tanto dentro como fuera de nuestra intranet.


 ![](imagen/24.PNG)
