# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](img/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
Una imagen es un empaquetado que contiene configuraciones, el cual sirve como una base (solo puede leerse) para crear los contenedores. Es decir, de una misma imagen pueden salir varios contenedores.

![Imagen y contenedores](img/imagenContenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
```
docker pull hello-world
```
![descargarImagenHelloWorld](img/descargarImagenHelloWorld.png)

**¿Qué es nginx**

  Software de código abierto diseñado para lograr el máximo rendimiento y estabilidad.

Descargar la imagen  **nginx** en la versión **alpine**
```
docker pull nginx:alpine
```
![descargarImagenNginxAlpine](img/descargarImagenNginxAlpine.png)

### Listar imágenes

```
docker images
```
![dockerimages](img/dockerImages.png)


**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
```
docker inspect hello-world 
```
![inspectHelloWorld](img/InspectHelloWorld.png)

**¿Con qué algoritmo se está generando el ID de la imagen**

  El algoritmo que se esta utilizando para calcular el ID de la imagen hello-world es el SHA-256. El cual consiste en generar un hash único para identificar la imagen en Docker.

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
```
docker rmi hello-world
```
![eliminarHelloWorld](img/eliminarHelloWorld.png)

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.
dores](img/dockerimages.PNG)
```
docker rmi -f <nombre imagen>:<tag>
```

