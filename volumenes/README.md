Gestión de Volúmenes y Redes en Docker
Uno de los problemas que enfrentamos con los contenedores es la persistencia de datos. Los contenedores, por defecto, no guardan datos una vez que se eliminan. Aquí es donde entran los volúmenes. Los volúmenes nos permiten mantener los datos fuera del ciclo de vida de los contenedores.

Podemos crear un volumen con:

```
docker volume create mi-volumen
```

Luego, podemos montar ese volumen en un contenedor, lo que permitirá que los datos sean persistentes:

```
docker run -d -p 8081:80 --name servidor-volumen -v mi-volumen:/usr/share/nginx/html nginx
```

En cuanto a las redes, Docker proporciona varias formas de conectar contenedores entre sí. Podemos crear una red con:

```
docker network create mi-red
```

Y conectar contenedores a esa red para que puedan comunicarse entre sí.
