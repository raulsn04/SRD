# Instalación y configuración de un servidor de correo

## Instalar servicio SMTP en Linux, utilizando el servidor Postfix.

  * Descargar e instalar postfix: apt-get install postfix.

  ![imagen](imagen/0.PNG)

  * Configuración de postfix:
    * Escoger instalación como Sitio de Internet

      ![imagen](imagen/1.PNG)

    * Crear dominio miempresa.com o similar

      ![imagen](imagen/2.PNG)

    * finalización de la instalación de postfix.

      ![imagen](imagen/3.PNG)

  * Comprobar servicio (y puerto) SMTP activo y a la escucha con netstat–utap.

  ![imagen](imagen/4.PNG)

  * Realizar  una  prueba  de  envío  de  mensaje  entre  dos  usuarios  del  sistema  mediante telnet,  tal  y  como  se  indica  en  el  ejemplo  del  apartado Prueba  de  Funcionamientodel documento pdf.

  ![imagen](imagen/5.PNG)

  * comprobamos que recibió el mensaje.

  ![imagen](imagen/6.PNG)

  * Instalar  un  cliente  de  correo  electrónico  en  un  cliente  (por  ejemplo Evolution,  para Ubuntu).

  ![imagen](imagen/7.PNG)

  * Crear  dos  nuevas  entradas  en  /etc/hosts:  smtp.miempresa.com  y  pop.miempresa.com asociadas a la IP del servidor.

  ![imagen](imagen/8.1.PNG)

  * Crear al menos dos cuentas asociadas a usuarios existentes en el servidor y asociadas al dominio creado en Postfix.

  ![imagen](imagen/8.1.PNG)

  * Configurar datos de las cuentas (dirección correo, servidores entrante y saliente).

  ![imagen](imagen/9.PNG)

  ![imagen](imagen/10.PNG)

  ![imagen](imagen/11.PNG)

  ![imagen](imagen/12.PNG)

  ![imagen](imagen/13.PNG)

  ![imagen](imagen/14.PNG)

  ![imagen](imagen/15.PNG)

  ![imagen](imagen/16.PNG)

  * Ahora añadimos el segundo usuario en evolution.

  ![imagen](imagen/17.PNG)

  ![imagen](imagen/18.PNG)

  ![imagen](imagen/19.PNG)

  ![imagen](imagen/20.PNG)

  ![imagen](imagen/21.PNG)

  * Realizar  envío  de  dos  correos,  uno  con  cada  una  de  las  cuentas  creadas.  Comprobar  la recepción de estos correos en el servidor examinando la carpeta /var/mail.

  ![imagen](imagen/23.PNG)

  ![imagen](imagen/24.PNG)

  ![imagen](imagen/25.PNG)

## Instalar servicio IMAP y servidor Correo Web SquirrelMail:

* Instalar servicio IMAP con apt-get install dovecot-imapd.

  ![imagen](imagen/30.PNG)

* Comprobar servicio (y puerto) IMAP activo y a la escucha con netstat –utap.

  ![imagen](imagen/31.PNG)

* Instalar aplicación correo web SquirrelMailcon apt-get install squirrelmail.

  ![imagen](imagen/32.PNG)

* Carpeta de configuración en /etc/squirrelmail.

  ![imagen](imagen/33.PNG)

* Carpeta de aplicación en /usr/share/squirrelmail.

  ![imagen](imagen/34.PNG)

* Copiar lineas no comentadas /etc/squirrelmail/apache.conf en un nuevo fichero .conf de /etc/apache2/sites-available, habilitar sitioy reiniciar apache.

  ![imagen](imagen/35.PNG)

* Creamos enlace simbólico del fichero.

  ![imagen](imagen/36.PNG)

* Reiniciamos apache.

  ![imagen](imagen/37.PNG)

* Acceder vía HTTP en /localhost/squirrelmail.

  ![imagen](imagen/38.PNG)

**En este último apartado nos ha dado fallo con el fichero de configuración y nos da el error anteriormente visto en la captura**

* Acceder desde una máquina cliente, vía HTTP, al gestor de correo SquirrelMail instalado.
* Enviar  y  recibir  correos  entre  las  dos  cuentas  creadas  desde  el  cliente  y  utilizando  el gestor de correo web SquirrelMail.
* Comprobar que los mensajes enviados desde ambas cuentas se siguen encontrando en los respectivos buzones de los usuarios en /var/mail.

## Instalar servicio POP3:

* Instalar servicio POP3 con apt-get install dovecot-pop3d.

  ![imagen](imagen/40.PNG)

* Comprobar servicio (y puerto) POP3 activo y a la escucha con netstat –utap.

  ![imagen](imagen/41.PNG)

* Configurar  MUA  (gestor  de  correo  cliente  Evolution  o  similar)  en  máquina  cliente  para que  acceda  a  la  recepción  de  correo  a  través  del  protocolo  POP3  instalado  en  el servidor.

  ![imagen](imagen/42.PNG)

  ![imagen](imagen/43.PNG)

  ![imagen](imagen/44.PNG)

* Enviar  y  recibir  correos  entre  las  dos  cuentas  creadas  desde  el  cliente  y  utilizando  el gestor de correo del cliente.

  ![imagen](imagen/45.PNG)

  ![imagen](imagen/46.PNG)

* Verificamos que los correos llegaron.

  ![imagen](imagen/47.PNG)

  ![imagen](imagen/48.PNG)
