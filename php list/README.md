# Listas de distribución
## Introducción
En esta actividad instalaremos y activaremos un servicio de gestión de Listas de Distribución basado en el software **phpList**, creando campañas de envío masivo y págians de suscripción para posibles usuarios.

---

# phpList
## 1. Instalación
Comenzamos descargando el código fuente de `phpList` y movemos el contenido de la carpeta */lists* al directorio de nuestro servidor web */var/www/html/*
<p align="center"><img src="img/Captura02.PNG"></p>

Cambiamos el usuario propietario a `www-data` y los permisos sobre dicha carpeta
<p align="center"><img src="img/Captura03.PNG"></p>

Lo siguiente sería acceder a **MySQL** para crear una base de datos, un usuario con acceso a la misma y sus respectivos privilegios
<p align="center"><img src="img/Captura04.PNG"></p>

Vemos el contenido final del directorio y modificamos el fichero de configuración *config/config.php*
<p align="center"><img src="img/Captura05.PNG"></p>

Una vez dentro del mismo, cambiamos los parámetros preestablecidos por los nuestros correspondientes a nuestra configuración de MySQL
<p align="center"><img src="img/Captura06.PNG"></p>

Teniendo esto ya hecho, ya podremos acceder desde un navegador a la interfaz gráfica de phpList en *localhost/list/admin*
<p align="center"><img src="img/Captura07.PNG"></p>

Rellenamos los campos que nos son solicitados, como por ejemplo, el nombre de nuestra organización, un correo electrónico y una contraseña
<p align="center"><img src="img/Captura08.PNG"></p>

Avanzamos en la instalación
<p align="center"><img src="img/Captura09.PNG"></p>

Vemos como se crean las tablas en nuestro servidor de base de datos
<p align="center"><img src="img/Captura10.PNG"></p>

Una vez realizado este proceso, podremos continuar con la con configuración
<p align="center"><img src="img/Captura11.PNG"></p>

## 2. Configuración
Vemos los parámetros de configuración que faltan
<p align="center"><img src="img/Captura12.PNG"></p>

Para ello, accedemos al panel de administración de phpList con la cuenta de administrador
<p align="center"><img src="img/Captura13.PNG"></p>

Añadimos el primer usuario
<p align="center"><img src="img/Captura15.PNG"></p>

Editamos los datos de `raul`
<p align="center"><img src="img/Captura16.PNG"></p>

Hacemos lo mismo con `dario`
<p align="center"><img src="img/Captura14.PNG"></p>

Y con `carlos`
<p align="center"><img src="img/Captura17.PNG"></p>

Por otro lado, crearemos la primera lista de usuarios
<p align="center"><img src="img/Captura19.PNG"></p>

Para más tarde, añadir los usuarios que acabamos de crear
<p align="center"><img src="img/Captura20.PNG"></p>

Vamos a añadir los usuarios suscriptores a esta lista
<p align="center"><img src="img/Captura21.PNG"></p>

Vemos los usuarios agregados
<p align="center"><img src="img/Captura22.PNG"></p>

Y verificamos las lista de suscriptores totales
<p align="center"><img src="img/Captura23.PNG"></p>

## 3. Campaña
A continuación, crearemos la primera campaña para enviar de forma masiva. Le asignamos un título, destinatario y contenido
<p align="center"><img src="img/Captura24.PNG"></p>

Configuramos otro parámetros como un primer destinatario de prueba
<p align="center"><img src="img/Captura25.PNG"></p>

Establecemos el tipo de formato del fichero de la campaña
<p align="center"><img src="img/Captura26.PNG"></p>

Tenemos también la posibilidad de programar el envío de dicha campaña
<p align="center"><img src="img/Captura27.PNG"></p>

Seleccionamos la lista de suscriptores a los que queremos enviarla
<p align="center"><img src="img/Captura28.PNG"></p>

Finalizamos confirmando el envío
<p align="center"><img src="img/Captura29.PNG"></p>

Visualizamos como se ha enviado la campaña que acabamos de crear
<p align="center"><img src="img/Captura31.PNG"></p>

Ampliamos los detalles de dicha campaña
<p align="center"><img src="img/Captura32.PNG"></p>

## 4. Campaña
Por último, crearemos una página de suscripción
<p align="center"><img src="img/Captura40.PNG"></p>

Vamos a añadir una nueva
<p align="center"><img src="img/Captura41.PNG"></p>

Editamos dicha página de suscripción a nuestro parecer, editando el código de la página *html*
<p align="center"><img src="img/Captura42.PNG"></p>

Confirmamos que se ha creado la página de suscripción
<p align="center"><img src="img/Captura43.PNG"></p>
