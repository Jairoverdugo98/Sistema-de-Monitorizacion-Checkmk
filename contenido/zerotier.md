# Creación De Una Red Privada en Zerotier

## Paso 1: Creación de una nueva red
En primer lugar para poder crear una nueva red privada para poder conectar internamente todos tus dispositivos , debemos acceder a [la zona central de zerotier](https://my.zerotier.com/), registrarte y crear una nueva red.

![image](/img/capturas/network.png)

## Paso 2: Configuración de la nueva red
Una vez creada , dentro de la red , podemos cambiar el nombre de la red , te dara el ID de la red , que necesitamos utilizar a la hora de la instalación e integración de nuestros dispositivos en nuestra red

![image](/img/capturas/ajustes.png)

Tambien podemos encontrar unos rangos de IP para que puedas elegir a tu gusto el que quieres para tu red.

![image](/img/capturas/rango.png)


## Paso 3: Integrar Dispositivos en nuestra red
En cada caso , explicare la forma de integrar e instalar el zerotier en cada agente para poder integrarlo sin problemas en checkmk independientemente de la red en la que nos encontremos.

Pero una vez instalado el zerotier en cada dispositivos que podremos encontrar en el apartado [Download](https://www.zerotier.com/download/), debemos unir el dispositivo con la zona central con el siguiente comando en caso de Debian/Ubuntu (cada sistema operativo tiene una forma distinta)

````
sudo zerotier-cli join IDdeTuRed
````

Luego de debemos autorizar el acceso a nuestra red y una vez que nosotros aceptamos el acceso , zerotier asignará automaticamente una IP del rango que elegimos en el paso 2

![image](/img/capturas/auth.png)

y una vez marcada la casilla "Auth?" estara aceptado el dispostivo en nuestra red, comprobaremos que la IP que Zerotier nos a asignado , tambien se crea en tu dispositivo.

![image](/img/capturas/interfa.png)