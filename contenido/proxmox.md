# 6. Integración de Agente en Proxmox

## Paso 1 : Instalación e integración de ZeroTier en Proxmox
Para poder integrar Proxmox en nuestra red privada de ZeroTier deberemos realizar los siguientes pasos:

En primer lugar debemos actualizar nuestro sistema
````
apt update
apt upgrade -y
````
A continuación debemos instalar el sudo.

````
apt install sudo
````
y una vez instalado , buscaremos en el apartado [Download](https://www.zerotier.com/download/) de ZeroTier el comando para instalar ZeroTier en nuestro Proxmox.

````
curl -s https://install.zerotier.com | sudo bash
````
Una vez instalado ZeroTier, añadiremos a nuestra red el nuevo dispositivo.

````
sudo zerotier-cli join IDdeTuRed
````
y autorizaremos en nuestra central de ZeroTier el Proxmox.

## Paso 2: Abrir puertos en el firewall de Proxmox

El siguiente paso será abrir en el firewall de Proxmox los puertos **22** (SSH), **80** (HTTP), **443** (HTTPS) y el puerto **6556** (Checkmk Agente)

Al abrir estos puertos en el firewall de Proxmox, se establece una conexión confiable y segura entre Proxmox y Checkmk, permitiendo el monitoreo efectivo del rendimiento del sistema.

![image](/img/capturas/firewallProx.png)

## Paso 3: Creación de Agente en Checkmk

Dentro del Checkmk en la ruta **Configuración --> Agentes --> Archivos de Linux** copiaremos la dirección del enlace del paquete .deb que instalaremos en nuestro Proxmox.

Ejecutaremos el siguiente comando:

````
wget direcciónDeEnlace.deb
````


Ya descargado , procederemos a su instalación con el comando:

````
sudo apt install ./nombredelAgente.deb
````
![image](/img/capturas/agenteProxmo.png)


# Paso 4: Creación de Host en Checkmk
Para poder integrar nuestro Proxmox en Checkmk debemos irnos a la ruta **""Configuración --> Hosts --> Añadir Hosts""** configuraremos la IP del agente , que pondremos la que nos ha asignado ZeroTier.

![image](/img/capturas/HProxmo.png)

Una vez todo añadido , pulsamos en "Guardar y ejecutar la detección de servicios" para poder empezar con la deteccion de servicios a monitorizar.

![image](/img/capturas/Sproxmo.png)

Y despues de Aceptar todo , activaremos los cambios realizados en la parte superior derecha.


