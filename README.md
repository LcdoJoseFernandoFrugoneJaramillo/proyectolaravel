# proyectolaravel
Sistema de Compra y venta de productos desarrollado en laravel 5.7 y vue.js

Instalación de Laravel 5.7 - Requerimientos del Servidor
El marco de Laravel tiene algunos requísitos en el sistema, si utiliza la máquina virtual de Laravel Laravel Homestead cumple todos estos requísitos; pero, sin embargo, si no esta usando Homestead deberá asegurarse que su servidor cumpla con los siguientes requísitos:

PHP> = 7.1.3
Extensión PHP OpenSSL
PDO PHP Extension
Extensión PHP Mbstring
Tokenizer PHP Extension
Extensión XML PHP
Extensión PHP Ctype
Extensión PHP JSON
Extensión PHP BCMath

Instalando Laravel

laravel utiliza composer para gestionar sus dependencias (https://getcomposer.org/) Vía instalación de Laravel.

Primero, descargue el instalador de Laravel usando Composer:

composer global require laravel/installer

Una vez instalado, el comando creará una nueva instalación de Laravel en el directorio que especifique:

laravel new proyectolaravel

Servidor de desarrollo local
Si tiene PHP instalado localmente y desea utilizar el servidor de desarrollo integrado de PHP para servir su aplicación, puede usar el servecomando Artisan. Este comando iniciará un servidor de desarrollo en :http://localhost:8000

php artisan serve

Configuración.
Directorio público

Después de instalar Laravel, debe configurar el documento / raíz web de su servidor web para que sea el publicdirectorio. El en este directorio sirve como controlador frontal para todas las solicitudes HTTP que ingresan a su aplicación.index.php

Archivos de configuración
Todos los archivos de configuración para el marco de Laravel se almacenan en el configdirectorio. Cada opción está documentada, así que siéntase libre de revisar los archivos y familiarizarse con las opciones disponibles para usted.

Configuración del servidor web
URLs bonitas - apache

Laravel incluye un archivo que se utiliza para proporcionar URL sin el controlador frontal en la ruta. Antes de servir Laravel con Apache, asegúrese de habilitar el módulo para que el servidor cumpla con el archivo.public/.htaccessindex.phpmod_rewrite.htaccess

Si el .htaccessarchivo que se incluye con Laravel no funciona con su instalación de Apache, pruebe esta alternativa:

Options +FollowSymLinks -Indexes
RewriteEngine On

RewriteCond %{HTTP:Authorization} .
RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ index.php [L]


