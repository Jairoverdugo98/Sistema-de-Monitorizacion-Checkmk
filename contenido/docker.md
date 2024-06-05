# 3. Instalación De Checkmk en Docker

## Paso 1: Descargar Checkmk
Entramos en la página oficial de checkmk en el apartado [Downloand](https://checkmk.com/download?utm_content=headerCta) y elegimos la edición que vamos a instalar, en este caso escogeremos Checkmk para Docker y la edición **Raw**

![image](/img/capturas/eledock.png)

## Paso 2: Instalación Checkmk en Docker

Una vez elegido nuestra plataforma , se nos desplegara un poco mas abajo un enlace que deberemos copiar para poder instalar en nuestro servidor la edición que hemos elegido de Checkmk

```````
docker container run -dit -p 8080:5000 -p 8000:8000 --tmpfs /opt/omd/sites/cmk/tmp:uid=1000,gid=1000 -v monitoring:/omd/sites --name monitoring -v /etc/localtime:/etc/localtime:ro --restart always checkmk/check-mk-raw:2.3.0p4
````````
(*Puedes cambiar los nombres del sitio que vayas a crear a tu gusto en el comando)

## Paso 3: Ejecución de la imagen

Una vez que se haya descargado la imagen y el contenedor se esté ejecutando, verá un resultado similar al siguiente.

![image](/img/capturas/ejedock.png)

## Paso 4: Comprobación
Después de ejecutar la imagen puedes iniciar sesión y probar Checkmk. Encontrararemos  la contraseña provisional para la cuenta cmkadmin en los registros escritos para este contenedor con el siguiente comando:
`````
docker container logs nombrequehayaspuesto
``````
![image](/img/capturas/dockerlo.png)

(*La URL que se muestra en el registro para acceder a la interfaz web con el ID del contenedor solo se reconoce dentro del contenedor y no es adecuada para el acceso desde fuera en el navegador web.)

En su lugar, debe acceder a la interfaz de usuario de Checkmk a través de:
````
http://localhost:8080/cmk/check_mk/`
````

![image](/img/capturas/DockerCheck.png)



