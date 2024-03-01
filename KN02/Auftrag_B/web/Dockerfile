# Verwenden Sie das offizielle PHP-Image mit Apache
FROM php:8.0-apache

# Kopieren der Dateien info.php und db.php in den Webserver-Ordner
COPY info.php /var/www/html/
COPY db.php /var/www/html/

# Installation des mysqli-Moduls für PHP
RUN docker-php-ext-install mysqli

# Exponieren des Ports 80
EXPOSE 80
