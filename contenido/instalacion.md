# Instalación De Checkmk

## Paso 1: Descargar Checkmk

Entramos en la página oficial de checkmk en el apartado [Downloand](https://checkmk.com/download?utm_content=headerCta) y elegimos la edición que vamos a instalar, en mi caso escogere para Linux y la edición **Raw**

![image](/img/capturas/1.png)

A continuación elegiremos nuestra plataforma como por ejemplo en mi caso:

![image](/img/capturas/2.png)

Una vez elegido nuestra plataforma , se nos desplegara un poco mas abajo un enlace que deberemos copiar para poder descargarnos en nuestro servidor la edición que hemos elegido de **Checkmk**

![image](/img/capturas/3.png)

Ejecutaremos el enlace copiado en nuestro servidor y se nos descargará.

![image](/img/capturas/Descarga.png)

## Paso 2: Instalación Checkmk

Ya descargado nuestra versión elegida de Checkmk , en primer lugar actualizaremos nuestro sistema.
```
sudo apt update
sudo apt upgrade -y
```
A continuación de haber actualizado nuestro sistema, en el directorio donde descargamos nuestra versión Checkmk elegida ejecutaremos el siguiente comando para instalar.

```
sudo apt install .\versionElegida
```

## Paso 3: Creación y Configuración de Checkmk

El primer paso una vez instalado es crear un sitio (unidad lógica de monitoreo) para poder desplegar y acceder nuestro checkmk.

El comando sera:
```
sudo omd su create nombrequequieras
```
Después de crear el sitio , nos dara la opción de cambiar la contraseña de el usuario administrador que se crea llamado **cmkadmin** (debemos estar dentro del sitio creado!) o acceder con los datos predeterminados que nos a creado la instalación del sitio

![image](/img/capturas/cmkadmin.png)

Cuando hayamos cambiado la contraseña (o no) del sitio debemos iniciar el sitio.

En primer lugar vemos el estado del sitio con:
```
omd status
```
Si el estado de los servicios esta **stoped** iniciaremos el sitio con:
```
omd start
```
Cuando haya finalizado volvemos a comprobarlo y veremos que los servicios estaran **running**

## Comprobación

Para finalizar la instalación y configuración accederemos a nuestro navegador y buscaremos **"tuip/tunombredesitio"** (ejemplo mio: 192.168.4.101/Proyecto) y podremos acceder con el usuario cmkadmin y vuestra contraseña.

![image](/img/capturas/interfaz.png)

![image](/img/capturas/check.png)


