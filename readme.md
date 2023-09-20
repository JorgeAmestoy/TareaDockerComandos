# TAREA COMANDOS BÁSICOS DOCKER
### 1. Descarga la imagen ubuntu y comprueba que está en tu equipo
```
DOCKER RUN UBUNTU: ejecuta un contenedor basado en la imagen de Ubuntu

DOCKER IMAGE LS: lista las imágenes del contenedor
```

### 2. Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre
```
DOCKER RUN -IT UBUNTU:LATEST BASH: crea un contenedor basado en la última versión de Ubuntu

DOCKER PS -A: lista los contenedor que hay en el sistema
```
Al no especificar el nombre, Docker asigna un nombre aleatorio

### 3. Crea un contenedor con el nombre 'dam_ubu1'. ¿Como puedes acceder a él?
```
DOCKER RUN -IT --NAME dam_ubu1 UBUNTU:LATEST BASH: crea el contenedor con el nombre especificado e inicia sesión en el bash para poder interactuar
```

### 4. Comprueba que ip tiene y si puedes hacer un ping a google.com


