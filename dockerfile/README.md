Project structure:
```
.
├── Dockerfile
├── wp-config.php
└── README.md
```

Crea una carpeta para tu proyecto y ubícate en ella:

```
mkdir demo-wordpress
cd demo-wordpress
```

Crea un archivo llamado Dockerfile y agrega el siguiente contenido:

```
# Imagen base de WordPress
FROM wordpress:latest

# Instalar el controlador de MySQL para PHP
RUN docker-php-ext-install mysqli

# Copiar el archivo de configuración personalizado
COPY ./wp-config.php /var/www/html/wp-config.php
```

En este Dockerfile, utilizamos la imagen base de WordPress y luego instalamos el controlador de MySQL para PHP. También copiamos nuestro archivo de configuración personalizado en la ubicación correcta dentro del contenedor.

Ahora vamos a contruir nuestra imagen

```
docker build . --tag wordpress-docker:101
```

veremos el siguiente output

```
[+] Building 69.1s (6/6) FINISHED
 => [internal] load .dockerignore                                                                              0.0s
 => => transferring context: 2B                                                                                0.0s
 => [internal] load build definition from Dockerfile                                                           0.0s
 => => transferring dockerfile: 269B                                                                           0.0s
 => [internal] load metadata for docker.io/library/wordpress:latest                                            0.0s
 => CACHED [1/2] FROM docker.io/library/wordpress:latest                                                       0.0s
 => [2/2] RUN docker-php-ext-install mysqli                                                                   69.0s
 => exporting to image                                                                                         0.0s
 => => exporting layers                                                                                        0.0s
 => => writing image sha256:84098cc600da3afcc8b1d795ebb507d8ce095b8456d9bebb0d4ab3afe4d6e0fa                   0.0s
 => => naming to docker.io/library/wordpress-docker:101
```
