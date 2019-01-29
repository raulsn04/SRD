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

# //////////////////////////////////////////////////////////////////////////////


# Configuración de hMailServer en Windows Server
