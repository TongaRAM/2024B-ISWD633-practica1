# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
```
docker create --name srv-web nginx:alpine
```
![srvWeb](img/srvWeb.PNG)

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
```
docker create hello-world:latest
```
![helloWorld](img/helloWorld.PNG)

### Listar los contenedores ejecutándose o no

```
docker ps -a
```
![listar](img/listar.PNG)

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 
```
docker start srv-web
```
![iniciarSrvWeb](img/iniciarSrvWeb.PNG)

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```
![listarContenedorEjecutandose](img/listarContenedorEjecutandose.PNG)

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

![stopSrvWeb](img/stopSrvWeb.PNG)

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](img/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
```
docker run --name srv-web2 nginx:alpine
```
![ejecPrimerPlano](img/ejecPrimerPlano.PNG)

**¿Qué sucede luego de la ejecución del comando?**
Al ejecutar el comando anterior la terminal queda atrapada (contenedo se ejecuta en primer plano), es decir no permite ingresar más comandos, hasta que se detenga el contenedor (ctrl+c).

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
```
docker run -d --name srv-web3 nginx:alpine
```
![ejecSegundoPlano](img/ejecSegundoPlano.PNG)

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 

```
docker rm vigorous_keller
```
![eliminarVigorous_keller](img/eliminarVigorous_keller.PNG)

Verificar que el contenedor que se eliminó
```
docker ps -a
```
![verificarContenedorEliminado](img/verificarContenedorEliminado.PNG)

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
```
docker rm -f srv-web3
```
![eliminarSrvWeb3](img/eliminarSrvWeb3.PNG)
Verificar que el contenedor que se eliminó
```
docker ps -a
```

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
```
docker inspect srv-web
```
![inspectSrvWeb](img/inspectSrvWeb.PNG)
