# Alertas en Telegram

## **Paso 1: Debemos crear un bot en Telegram**


Buscamos en la barra de busqueda de Telegram , el bot **@Botfather** e iniciamos el chat con él con el comando **/start**

![image](/img/capturas/Botfather.png)

## **Paso 2: Creación de un nuevo bot**

Una vez llamado el BotFather , utilizamos el comando **/newbot** para crear un nuevo bot y ponerle nombre segun nos indique instagram

![image](/img/capturas/newbot.png)

## **Paso 3: Ponerle nombre a un usuario en el nuevo bot**

A continuación siguiente con las indicaciones de telegram , crearemos un usuario dentro del nuevo bot para poder acceder a la API Token que necesitamos para configurar la alerta.

![image](/img/capturas/UsuarioApi.png)

## **Paso 4: Obtener el ID Chat**

Una vez creado nuestro bot , obtendremos nuestro ID Chat para poder configurar nuestro script para nuestras alertas de checkmk
Lo obtendremos creando un grupo con el bot **@RawData**

![image](/img/capturas/IdChat.png)

## **Paso 5: Configuración del Script**

Una vez ejecutado nuestro bot con el comando **/start**

El siguiente paso será configurar nuestro Script que os dejo [pinchando aqui](/contenido/telegram.sh) para que podais modificarlo con vuestros IDChat y Token

Para poder configurar correctamente el script , la siguiente parte debera quedar de la siguiente manera con vuestro Token configurado:

![image](/img/capturas/Token.png)

La parte siguiente es como deberiamos configurar nuestro IDChat correctamente:

![image](/img/capturas/ScriptID.png)

A continuación configuramos la parte donde debemos poner la Ip de nuestro servidor Checkmk

![image](/img/capturas/ip.png)

Y por último la parte para poder recibir correctamente las alertas deberá quedar de la siguiente manera con vuestros IDChat y Token

![image](/img/capturas/msg.png)

## **Paso 6: Ejecutar el Script en el servidor Checkmk**

El script debe estar dentro de las siguientes rutas, una dentro del sistema y otro dentro del sitio creado para checkmk (las dos rutas son la misma pero en diferente ubicaciones):

![image](/img/capturas/Ruta1.png)

![image](/img/capturas/ruta2.png)

Una vez dentro el script de la rutas , debemos darle permisos de ejecución con el siguiente comando:

``
chmod +x nombredelscript
``

Una vez dado los permisos de ejecución procederemos a ejecutar el script y nos saldrá el siguiente resultado y recibiremos una notificación en nuestro bot.

![image](/img/capturas/ejecucion.png)

![image](/img/capturas/noti.png)

## **Paso 7: Creación de Regla dentro de Checkmk**
Una vez dentro del Checkmk procederemos a crear una regla para la alerta.

En la ruta **Configuración --> Eventos --> Configuración de las notificaciones**

Añadimos regla y la configuramos de la siguiente manera con tu Token y tu IdChat.
![image](/img/capturas/regla.png)

Una vez guardada la regla debera quedar de la siguiente manera.

![image](/img/capturas/finRegla.png)

## Comprobación
Ahora cada vez que tengais una alerta en vuestros dispositivos monitorizados os llegaran a vuestro bot de la siguiente manera

![image](/img/capturas/Alerta.png)