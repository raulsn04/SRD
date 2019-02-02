# Informe Instalación y Configuración de Servicios de Correo Electrónico en Windows 2016 Server

## Instalar Servicio SMTP en Windows 2016 Server (manualmente o utilizando Asistente).

![](imagen/1.PNG)

![](imagen/2.PNG)

![](imagen/4.PNG)

![](imagen/5.PNG)

## Configuración de servicio SMTP a través del administrador de aplicaciones (IIS) 6.0. Realizar las siguientes acciones de configuración:

Establecer como IP todas las asignadas

Limitar el número de conexiones a 50

![](imagen/6.PNG)

Habilitar el registro en formato W3C, diario y en una carpeta determinada

![](imagen/6.0.PNG)

Configurar envío de mensajes dentro de nuestra red local: Aceptar la conexión al servidor y la retransmisión de mensajes a todos los equipos menos los que aparecen en la lista

**(incluir una IP cualquiera en la lista para impedir su acceso y retransmisión)**

conexión:

![](imagen/7.PNG)

![](imagen/8.PNG)

retransmisión:

![](imagen/10.PNG)

![](imagen/11.PNG)

Establecer autenticación anónima

![](imagen/12.1.PNG)


## Crear la exepción del firewall

exepción al puerto:

![](imagen/13.PNG)

puerto 25:

![](imagen/14.PNG)

permitir la conexion:

![](imagen/15.PNG)

![](imagen/16.PNG)

![](imagen/17.PNG)

![](imagen/18.PNG)

Comprobar la existencia del dominio AD predeterminado. Crea un dominio de tipo alias para disponer de cuentas en otro dominio.

![](imagen/19.PNG)

![](imagen/20.PNG)

![](imagen/21.PNG)

Comprueba carpetas de correo creados en C:\Inetpub\mailroot.

![](imagen/22.PNG)

# En el cliente Windows:

Configuración del cliente.

![](imagen/9.PNG)

Comprobar acceso al nuevo nombre DNS creado en el servidor.

![](imagen/23.PNG)

![](imagen/24.PNG)

![](imagen/29.PNG)


Enviar varios correos desde / hacia las diferentes cuentas y comprobar envío (real o ficticio) y carpetas mailroot. Las carpetas existentes en mailroot alojan mensajes en cola (Queue), mensajes para destinatarios desconocidos (Badmail) y mensajes entregados (Drop)

![](imagen/33.PNG)

## En el servidor:
Nueva configuración de servicio SMTP a través del administrador de aplicaciones (IIS) 6.0. Establecer autenticación básica de Windows. Probar diferentes configuraciones de dominio predeterminado, cifrado TLS, etc.

![](imagen/40.PNG)

![](imagen/41.PNG)


## En el cliente Windows:
Configurar las cuentas según los parámetros especificados en el servidor. Enviar varios correos desde / hacia las diferentes cuentas y comprobar envío y carpetas mailroot. En este caso sólo tendrán acceso al servidor SMTP cuentas del dominio y correspondientes a usuarios de AD.

![](imagen/31.1.PNG)

![](imagen/31.PNG)

![](imagen/32.PNG)

# ////////////////////////////////////////////////////////////////////


# Configuración de hMailServer en Windows Server


En primer lugar, hay que desinstalar el servicio SMTP de Windows 2016 Server.

![](imagen2/1.PNG)

![](imagen2/2.PNG)

Debes descargar e instalar en el servidor Windows 2016 server el servidor de correo hMailServer.

![](imagen2/3.PNG)

![](imagen2/4.PNG)

![](imagen2/5caro.PNG)

![](imagen2/6.PNG)

![](imagen2/7.PNG)

**Al instalar hMailServer, da un error con el net Framework 3.5.**

![](imagen2/8.PNG)

**Para instalarlo vamos a agrgar roles y caracteristicas en la admistración del servidor y lo instalamos desde ahí**

![](imagen2/9.PNG)

![](imagen2/10.PNG)

**Una vez instalado, volvemos a reinstalar hMailServer y ahora si finaliza correctamente**

![](imagen2/11.PNG)

**Establecemos la conexión**

![](imagen2/12.PNG)

Crea dos dominios denominados srd.edu y asir.edu.

![](imagen2/13.PNG)

Ejecuta los diagnósticos para ambos dominios y soluciona el error de backup asignando una carpeta para tal fin.
Establece copia de seguridad de los mensajes.

![](imagen2/14.PNG)

![](imagen2/15.PNG)

Ejecutamos otra vez el diagnóstico para comprobar que se ha corregio el error en los dos dominios.

![](imagen2/16.PNG)

![](imagen2/17.PNG)

Crea dos cuentas para dos usuarios ficticios en cada uno de los dos dominios. Investiga y configura las cuentas con diferentes opciones (cuota de disco, auto-reply, forwarding, signature, etc.)

**Creamos un usuario en el dominio asir.edu le configuramos la opcion de auto reply y forwarding**

![](imagen2/17.PNG)

![](imagen2/17.PNG)

![](imagen2/20.PNG)

**creamos otro usuario**

![](imagen2/21.PNG)

**Usuarios y dominios creados**

![](imagen2/22.PNG)

Configura el servicio DNS para crear las entradas mail.srd.edu y mail.asir.edu que apunten a la dirección ip del servidor windows 2012.

**Creamos los DNS**

![](imagen2/23.PNG)

![](imagen2/24.PNG)

![](imagen2/25.PNG)

**Creamos las entradas del host para MAIL.SRD.EDU**

![](imagen2/26.PNG)

**Creamos las entradas del host para MAIL.ASIR.EDU**

![](imagen2/27.PNG)


Configura en el cliente Windows un cliente de correo como thunderbird o Live Mail (en los ordenadores clientes) para acceder al servidor de correo instalado en Windows 2016.

**Descargamos el cliente de correos thunderbird**

![](imagen2/30.PNG)

![](imagen2/31.PNG)

**Añadimos las cuentas de los usuarios**

![](imagen2/32.PNG)

**Yo seleccione el servicio IMAP para los correos de este dominio**

![](imagen2/33.PNG)

![](imagen2/34.PNG)

![](imagen2/35.PNG)

**Añadimos el otro usuario**

![](imagen2/36.PNG)

![](imagen2/37.PNG)



#### Redactamos el correo

Realiza prueba de envío y recepción de correos entre los diferentes usuarios, comprobando, además de envío y recepción correctas, el efecto de las opciones configuradas en las cuentas.

**Enviamos el correo**

![](imagen2/38.PNG)

**Comprobamos que ha llegado**

![](imagen2/39.PNG)


Crea una lista de distribución empleados asociada al dominio.

![](imagen2/41.PNG)

Añade a los dos usuarios de miempresa.com a ella.

![](imagen2/42.PNG)

Realiza prueba de envío y recepción de correos por medio de la lista de distribución.

**enviamos desde lucas al mail de la lista y nos llega al correo de pepe**

![](imagen2/43.PNG)

![](imagen2/44.PNG)
