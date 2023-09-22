# TAREA COMANDOS BÁSICOS DOCKER
## Utilizando la imagen de Ubuntu, usa el Visual Studio COde y Docker y realiza la tarea poniendo los comandos y una breve descripción del proceso:

### 1. Descarga la imagen ubuntu y comprueba que está en tu equipo

```
$ DOCKER RUN UBUNTU: ejecuta un contenedor basado en la imagen de Ubuntu

$ DOCKER IMAGE LS: lista las imágenes del contenedor
```

### 2. Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre
```
$ DOCKER RUN -IT UBUNTU:LATEST BASH: crea un contenedor basado en la última versión de Ubuntu y entramos en este

$ DOCKER PS -A: lista los contenedor que hay en el sistema
```
Al no especificar el nombre, Docker asigna un nombre aleatorio

### 3. Crea un contenedor con el nombre 'dam_ubu1'. ¿Como puedes acceder a él?
```
$ DOCKER RUN -IT --NAME DAM_UBU1 UBUNTU:LATEST BASH: crea el contenedor con el nombre especificado e inicia sesión en el bash para poder interactuar
```

### 4. Comprueba que ip tiene y si puedes hacer un ping a google.com

```
# APT UPDATE: actualiza la lista de paquetes disponibles
# APT INSTALL NET-TOOLS: instala las net-tools para poder usar las herramientas
```
Una vez descargadas:
```
$ IFCONFIG: muestra la IP e información adicional
```
La IP es: 172.17.0.2. Para hacer ping con Google:
```
# APT INSTALL IPUTILS-PING: instala la herramienta ping para poder utilizarla

# PING WWW.GOOGLE.COM
```
### 5. Crea un contenedor con el nombre 'dam_ubu2'. ¿Puedes hacer ping entre los contenedores?

```
$ DOCKER RUN -IT --NAME DAM_UBU2 UBUNTU:LATEST BASH: crea el contenedor con el nombre especificado e inicia sesión en el bash para poder interactuar
```
No se puede hacer ping entre los contenedores. Para ello habría que volver a realizar el proceso anterior, actualizar y descargar las tools.

### 6. Sal del terminal, ¿que ocurrió con el contenedor?
```
# EXIT: sales del contenedor

$ DOCKER PS -A: para comprobar su estado

```
Este se cierra.
### 7. ¿Cuanta memoria en el disco duro ocupaste?
```
DOCKER SYSTEM DF: identifica la cantidad de espacio en disco con Docker

TYPE            TOTAL     ACTIVE    SIZE      RECLAIMABLE
Images          4         4         348.9MB   0B (0%)
Containers      28        1         366.1MB   319.9MB (87%)
Local Volumes   0         0         0B        0B
Build Cache     0         0         0B        0B
```

### 8. ¿Cuanta RAM ocupan los contenedores? ¿Hay algún comando docker para saber esto?.
> [!IMPORTANT] 
> Si no están iniciados los contenedores, primero debemos entrar en ellos, ejecutarlos y salir:

```
DOCKER START DAM_UBU1: inicia el contenedor

DOCKER EXEC -IT DAM_UBU1 BASH: ejecuta el shell del contenedor dam-ubu1

EXIT: cierra la sesión del shell del contenedor
```

Tras esto, buscamos la información requerida:
```
DOCKER STATS: muestra información sobre el uso del CPU, la memoria y otros recursos
```

Saliendo como resultado:

|     NAME     | MEM USAGE/LIMIT    |
|--------------|--------------      |
|   dam_ubu1   | 892KiB / 15.39GiB  |
|   dam_ubu2   | 5.152MiB / 15.39GiB| 


