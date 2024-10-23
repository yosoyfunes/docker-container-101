# Imagen base de WordPress
FROM wordpress:latest

# Instalar el controlador de MySQL para PHP
RUN docker-php-ext-install mysqli

# Copiar el archivo de configuración personalizado
#COPY ./wp-config.php /var/www/html/wp-config.php