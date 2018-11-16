# Instalación y Configuración de un servidor Web Avanzado

### Informe I
## Carpetas seguras

Creamos una nueva zona de búsqueda directa en los servicios DNS asociada al dominio miEmpresa.

![](info1/1.PNG)

![](info1/2.PNG)

Creamos también una carpeta miEmpresa en C:\ y una subcarpeta **principal**.

![](info1/0.PNG)

Creamos un nuevo sitio web denominado miEmpresa en IIS asociado a la subcarpeta anterior y con acceso a través de la dirección www.miEmpresa.com.

![](info1/3.PNG)

Creamos un  nuevo  sitio web (denominado ‘pagos’) como subdominio de **miEmpresa(pagos.miEmpresa.com)** y configura este último para ser accedido de forma segura, vía ‘https’.

![](info1/4.PNG)

![](info1/5.PNG)


Creamos el sitio web, con la configuración adecuada en IIS y en los servicios DNS.

![](info1/6.PNG)

Comprobamos el acceso (aún vía ‘http’) con un navegador desde el propio servidor y desde un cliente W7.

![](info1/7.PNG)

![](info1/7.1 .PNG)

**Configuración A:** Seguimos los pasos del tutorial y configuramos el nuevo sitio  para que se pueda acceder (sólo) como sitio web seguro (https) con un Certificado Autofirmado.

* Creamos el certificado.

![](info1/8.PNG)

![](info1/9.PNG)

* Agregamos pagos como sitio seguro (https) y lo comprobamos.

![](info1/10.PNG)

![](info1/11.PNG)

![](info1/11.1.PNG)


**Configuración B:** Creamos un nuevo sitio seguro **(tienda.miempresa.com)** con la generación de un Certificado Digital a través de la aplicación  **OpenSSL.**

![](info1/14.PNG)

Realizaremos la solicitud de un nuevo certificado de servidor para nuestro sitio seguro y creamos el  fichero **certreq.txt** para alojar la solicitud.

![](info1/17.PNG)


Descargamos e instalamos OpenSSL para Windows.

![](info1/20.PNG)

A través de OpenSSl generamos un nuevo certificado de servidor.

![](info1/21.1.PNG)

Generamos una clave privada de la entidad certificadora.

![](info1/21.PNG)

Creamos un certificado digital de la entidad certificadora y finalmente, crear un certificado digital de nuestra web.


![](info1/22.PNG)

![](info1/23.PNG)

* Comprobamos.

![](info1/24.PNG)

Importamos el nuevo certificado de servidor creado para completar la petición pendiente en nuestro sitio seguro ‘pagos’.
![](info1/24.1.PNG)


* Configuramos el DNS.
![](info1/16.2.PNG)

Requerimos que a nuestros sitios seguros sólo se pueda acceder mediante una conexión segura y reiniciamos los sitios web.
* Tienda

![](info1/15.PNG)

* Pagos

![](info1/16.PNG)

* Comprobamos que se ha creado el SSL correctamente.

![](info1/25.PNG)

![](info1/26.PNG)


Finalmente, accedemos mediante http y mediante https a los sitios seguros desde el propio servidor y desde un cliente W7, aceptando los posibles problemas con la entidad certificadora.

* Comprobamos *pagos*.

![](info1/29.PNG)

![](info1/30.PNG)

* Comprobamos *tienda*.

![](info1/31.PNG)

![](info1/32.PNG)

* Comprobamos *pagos* desde el *cliente*.

![](info1/33.PNG)

* Comprobamos *tienda* desde el *cliente*.

![](info1/34.PNG)

### Informe II

## Carpetas Privadas

Necesitamos crear una carpeta empleados (dentro de miEmpresa).

![](info2/0.PNG)

Dentro de esta, tres o cuatro subcarpetas personales con nombres de empleados y una, denominada común, a la que tendrán acceso todos los empleados, pero no otros usuarios sin identificar.

Colocamos un fichero index.html diferente en cada una de las carpetas creadas, con el objetivo de poder comprobar el acceso desde un navegador.

![](info2/2.PNG)

Crearemos el nuevo sitio web, como subdominio de nuestro dominio principal, asociado a la carpeta genérica empleados.

![](info2/1.PNG)

![](info2/3.5.PNG)


* Le añadimos la Ip (antes no la habia puesto).

![](info2/1.1.PNG)

Añadimos al DNS principal el subdominio.

![](info2/3.6.PNG)

Para el sitio web creado y para cada una de sus carpetas, deshabilitamos el acceso anónimo *(al deshabilitarlo en el sitio web, por defecto lo hace en las carpetas).*

![](info2/4.PNG)

Agregamos la función de Autenticación Básica a nuestro Servicio de IIS a través de la Administración del Servidor.

![](info2/5.PNG)


En Active Directory, crearemos un usuario para cada empleado (tantos como carpetas personales) y un grupo Empleados que los incluya a todos.

**Grupo empleados**

![](info2/6.PNG)

**Usuario Goku**

![](info2/7.PNG)


**Usuario Zohan**

![](info2/8.PNG)

**Usuario Takumi**

![](info2/9.PNG)

Añadimos y comprobamos los usuarios en el grupo.

![](info2/10.PNG)

![](info2/11.PNG)

Desactivamos, para la carpeta **empleados**, los permisos heredables a través de las opciones avanzadas en la ficha de seguridad.

![](info2/12.1.PNG)

Añadimos grupo de Administradores con Control Total.

![](info2/13.PNG)

Grupo Empleados con Lectura y Ejecución+ Mostrar Carpeta+Leer.

![](info2/12.PNG)


Realizamos el mismo procedimiento para cada una de las carpetas personales de los empleados, colocando como usuarios autorizados el  **Grupo de Administradores (Control Total)**

* Takumi.

![](info2/18.PNG)

* Goku.

![](info2/19.PNG)

* Zohan.

![](info2/22.PNG)

Y **el empleado propietario de cada carpeta** (con los permisos que creas convenientes).

 * Takumi.

 ![](info2/16.PNG)

 * Goku.

 ![](info2/20.PNG)

 * Zohan.

 ![](info2/21.PNG)


Realizamos el mismo procedimiento para la carpeta ‘comun’, colocando como usuarios autorizados el **Grupo de Administradores (Control Total)**

* Común Administradores.

![](info2/14.PNG)

Y el **grupo  Empleados** (con los permisos que creas convenientes).

* Común Empleados.

 ![](info2/15.PNG)


Comprobamos el acceso, tanto **desde el servidor**.

* Comprobación de Goku.

![](info2/30.PNG)

![](info2/31.PNG)

* Comprobación de Zohan.

![](info2/32.PNG)

![](info2/33.PNG)

* Comprobación de Takumi.

![](info2/34.PNG)

![](info2/35.PNG)

* **Acceso a comun con Zohan**

![](info2/36.PNG)

![](info2/37.PNG)

Como **desde el cliente**, a las diferentes carpetas con distintos usuarios.

* Comprobación de Goku.

![](info2/40.PNG)

![](info2/41.PNG)

* Comprobación de Zohan.

![](info2/42.PNG)

![](info2/43.PNG)

* **Acceso a comun con Goku**

![](info2/44.PNG)

![](info2/45.PNG)
