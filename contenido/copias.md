# 8.-Copia de seguridad y restauración

En Check_MK, puedes hacer un snapshot de toda la configuración actual para restaurarla cuando quieras realizando los siguientes pasos.

## 1. Paso 1: Creación de Directorio
Crearemos un directorio para poder guardar nuestras copias de seguridad y poder restaurarlas en el momento que nos sea necesario.

`````
sudo mkdir nombreDirectorio
`````

## 2. Paso 2: Configurar el Destino de las Copias de Seguridad

En la ruta **Configuración --> Mantenimiento --> Copia de seguridad del sitio** marcamos **"Objetivos de copia de seguridad"** y añadimos objetivo para poder configurar la ruta donde se guardaran nuestras copias de seguridad

![image](/img/capturas/Back.png)

El siguiente paso será crear un trabajo de respaldo, esta vez sera en la ruta **Configuración --> Mantenimiento --> Copia de seguridad del sitio** pero en **"Añadir Trabajo"**

![image](/img/capturas/Trabajo.png)

## Paso 3: Crearemos la copia de seguridad

Si pulsamos el **"play"** se iniciará la copia de seguridad

![image](/img/capturas/seguridad1.png)

Si pulsamos el **"pause"** la copia de seguridad finalizará

![image](/img/capturas/seguridad2.png)

## Paso 4: Restauración
En el caso que perdamos todos nuestros datos y nos sea necesario restaurar nuestra copia de segurida , pulsaremos **"Restaurar"** y comenzara a restaurar nuestra copia.

![image](/img/capturas/restaura1.png)

![image](/img/capturas/resatura2.png)
