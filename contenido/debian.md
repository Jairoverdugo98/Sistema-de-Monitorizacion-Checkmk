# Integración de Agente Debian/Ubuntu

## Paso 1: Integrar Debian/Ubuntu en nuestra red ZeroTier

En el apartado [Download](https://www.zerotier.com/download/) de Zerotier encontramos el comando para poder instalar ZeroTier en nuestro Agente Debian/Ubuntu

En primer lugar actualizaremos nuestro sistema.

````
sudo apt update
sudo apt upgrade -y
````
Acto seguido ejecutaremos el siguiente comando para poder instalar ZeroTier
````
curl -s https://install.zerotier.com | sudo bash
````

Una vez instalado ZeroTier, añadiremos a nuestra red el nuevo dispositivo.

````
sudo zerotier-cli join IDdeTuRed
````
y aceptaremos en nuestra red el nuevo dispositivo.

![image](/img/capturas/Autorizacion.png)

## Paso 2: Creación de Agente en Checkmk

Dentro del Checkmk en la ruta **Configuración --> Agentes --> Archivos de Linux** copiaremos la dirección del enlace del paquete .deb que instalaremos en nuestro debian/ubuntu.
Ejecutaremos el siguiente comando:

````
wget direcciónDeEnlace.deb
````

![image](/img/capturas/wget.png)

Ya descargado , procederemos a su instalación con el comando:

````
sudo apt install ./nombredelAgente.deb
````

# Paso 3: Creación de Host en Checkmk
Por último en la ruta **""Configuración --> Hosts --> Añadir Hosts""** configuraremos la IP del agente , que pondremos la que nos ha asignado ZeroTier.

![image](/img/capturas/HDebian.png)

Una vez todo añadido , pulsamos en "Guardar y ejecutar la detección de servicios" para poder empezar con la deteccion de servicios a monitorizar.

![image](/img/capturas/SDebian.png)

Y despues de Aceptar todo , activaremos los cambios realizados en la parte superior derecha.
