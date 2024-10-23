---

## Uso de Imágenes y Contenedores

Primero, descarguemos una imagen de Nginx desde Docker Hub con el comando:

```
docker pull nginx
```

Luego, podemos ejecutar un contenedor con esa imagen:

```
docker run -d -p 8080:80 --name webserver nginx
```

Este comando creará un contenedor de Nginx y lo expondrá en el puerto 8080 de nuestra máquina local. Si abren un navegador y van a http://localhost:8080, deberían ver la página de bienvenida de Nginx.

Podemos listar los contenedores en ejecución con:

```
docker ps
```

Y cuando terminemos, podemos detener y eliminar el contenedor:
```
docker stop webserver
docker rm webserver
```