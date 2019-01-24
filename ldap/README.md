# INSTALACIÓN Y CONFIGURACIÓN SERVIDOR LDAP

## Instalar paquete LDAP apt-get install slapd

![](imagen/1.PNG)

![](imagen/2.PNG)

![](imagen/3.PNG)

## Instalar librerias apt-get install db4.8-util ldap-utils

![](imagen/4.PNG)

## Configurar LDAP dpkg-reconfigure slapd

![](imagen/6.PNG)

## Nombre de dominio DNS

![](imagen/7.PNG)

## Nombre de la organización

![](imagen/8.PNG)

## Contraseña de administrador

![](imagen/9.PNG)

![](imagen/10.PNG)

## Motor de la base de datos

![](imagen/11.PNG)

![](imagen/12.PNG)

![](imagen/13.PNG)

## Protocolo LDAPv2

![](imagen/14.PNG)

## DPKG configurado

![](imagen/15.PNG)

## Arranque y parada del Servidor LDAP

![](imagen/16.PNG)

# Administración LDAP, usar JXplorer

## Instalar JDK 7

![](imagen/18.PNG)

## Instalar JXplorer

![](imagen/17.PNG)

## Ejecutar JXplorer en Herramientas de Desarrollo

![](imagen/19.PNG)

## Conexión JXplorer

![](imagen/20.PNG)

![](imagen/21.PNG)

## Unidad organizativa Usuarios

![](imagen/22.PNG)

![](imagen/23.PNG)

## Unidad organizativa Profesores

![](imagen/24.PNG)

## Creación de Usuarios y configuración

![](imagen/25.PNG)

![](imagen/26.PNG)

## Cambiamos el id del grupo a los Usuarios

![](ldap2/1.PNG)

![](ldap2/2.PNG)

## Añadimos la contraseña a los Grupos

![](imagen/24.0.PNG)

## Añadimos la contraseña a los Usuarios

![](ldap2/0.PNG)

# Instalación y Configuración de Carpetas Privadas en Apache con autenticación LDAP:

## Habilitar módulos Apache2 LDAP, a2enmod ldap; a2enmod authnz_ldap

![](ldap2/3.PNG)

![](ldap2/4.PNG)

## Crear carpeta privada en /var/www con fichero index.html

![](ldap2/5.PNG)

![](ldap2/6.PNG)

## Crear nuevos sitios virtual es en /etc/apache2/sites-available/default con configuración de autenticación LDAP, añadir línea   AuthBasicProvider ldap en cada VirtualHost

**Usuario**

![](ldap2/7.PNG)

**Grupo**

![](ldap2/8.PNG)

## Sitio virtual privado de usuario y otro de acceso para grupo


![](ldap2/10.PNG)

## Accedemos a la página e iniciamos sesión con el Grupo
**Por errores que no podemos solucionar, no inicia la sesión**

![](ldap2/11.PNG)

## Accedemos a la página e iniciamos sesión con el usuario

![](ldap2/13.PNG)

![](ldap2/12.PNG)
