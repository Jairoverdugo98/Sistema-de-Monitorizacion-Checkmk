# Integración de Agente Wserver

## Paso 1: Integrar WServer en nuestra red ZeroTier
En primer lugar debemos instalar Zerotier para poder incorporar el dispositivo Wserver en nuestra red privada.

El primer paso sera instalar el paquete .msi en nuestro wserver que podemos encontrar en el apartado [Download](https://www.zerotier.com/download/) de zerotier

![image](/img/capturas/msi.png)

Después de instalar el paquete .msi , debemos incorporar el dispositivo en nuestra red mediante el ID de nuestra red.

![image](/img/capturas/join.png)

Una vez escrito nuestro ID y autorizado en nuestra central de Zerotier , ya tendremos el dispositivo incorporado a nuestra red.

## Paso 2: Abrir una regla en el firewall

A continuación debemos abrir una regla de entrada en el firewall para poder tener acceso desde fuera al puerto 6556 que es el puerto que utiliza Checkmk.

- Accederemos a Windows Defender Firewall con seguridad avanzada
- Creamos una nueva regla de entrada y se nos abrira el asistente de regla, marcaremos tipo Puerto
- A continuación elegiremos regla TCP y marcamos **"Puertos locales especificos"** y escribimos el puerto **"6556"**.
- En la siguiente ventana marcaremos **"Permitir la conexión"**
- Y para finalizar escribimos un nombre para la regla y alguna descripción que quieras añadirle (esto es opcional)

## Paso 3: Creación de Host en Checkmk
Por último debemos descargarnos dentro de nuestro checkmk el agente para instalarlo en nuestro dispositivo Wserver para que puedan sincronizarse y monitorizar los servicios disponibles.

Dentro del Checkmk en la ruta **Configuración --> Agentes --> Archivos de Windows**
descargaremos el paquete .msi


![image](/img/capturas/AgenteW.png)

A continuación en la ruta **""Configuración --> Hosts --> Añadir Hosts""** configuraremos la IP del agente , que pondremos la que nos ha asignado ZeroTier.

![image](/img/capturas/ConfiWs.png)

*Importante! , Debemos dejar la opción **"API integrations if configured, else Checkmk agent"** ya que este Host esta configurado mediante el agente que hemos instalado.

## Paso 4: Servicios Monitorizables

Por último, una vez añadido el host , debemos aceptar los servicios que estan disponibles para monitorizar.

![Image](/img/capturas/ServiciosWs.png)

Una vez aceptamos todo , debemos confirmar los cambios realizados en la esquina superior derecha y ya tendremos añadido el host para monitorizar en Checkmk.
