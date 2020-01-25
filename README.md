# proyectolaravel
Sistema de Compra y venta de productos desarrollado en laravel 5.7 y vue.js

Instalación
Instalación
Requerimientos del servidor
Instalando Laravel
Configuración
Configuración del servidor web
URLs bonitas

Instalación

Requerimientos del servidor
El marco Laravel tiene algunos requisitos del sistema. La máquina virtual Laravel Homestead cumple todos estos requisitos , por lo que se recomienda que utilice Homestead como su entorno de desarrollo local de Laravel.

Sin embargo, si no está utilizando Homestead, deberá asegurarse de que su servidor cumpla con los siguientes requisitos:

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
Laravel utiliza Composer https://getcomposer.org/ para gestionar sus dependencias. Entonces, antes de usar Laravel, asegúrese de tener Composer instalado en su máquina.

Vía instalador de Laravel
Primero, descargue el instalador de Laravel usando Composer:

composer global require laravel/installer
Asegúrese de colocar el directorio bin de proveedores de todo el sistema del compositor en su sistema $PATHpara que el ejecutable laravel pueda ser localizado por su sistema.

Una vez instalado, el comando creará una nueva instalación de Laravel en el directorio que especifique. Por ejemplo, creará un directorio llamado que contiene una nueva instalación de Laravel con todas las dependencias de Laravel ya instaladas:laravel newlaravel new blogblog

laravel new blog

Vía Composer Create-Project
Alternativamente, también puede instalar Laravel emitiendo el comando Composer en su terminal:create-project

composer create-project --prefer-dist laravel/laravel blog "5.7.*"

Servidor de desarrollo local
Si tiene PHP instalado localmente y desea utilizar el servidor de desarrollo integrado de PHP para servir su aplicación, puede usar el servecomando Artisan. Este comando iniciará un servidor de desarrollo en :http://localhost:8000

php artisan serve

Configuración
Directorio publico
Después de instalar Laravel, debe configurar el documento / raíz web de su servidor web para que sea el publicdirectorio. El en este directorio sirve como controlador frontal para todas las solicitudes HTTP que ingresan a su aplicación.index.php

Archivos de configuración
Todos los archivos de configuración para el marco de Laravel se almacenan en el configdirectorio. Cada opción está documentada, así que siéntase libre de revisar los archivos y familiarizarse con las opciones disponibles para usted.

Configuración del servidor web

URLs bonitas
apache
Laravel incluye un archivo que se utiliza para proporcionar URL sin el controlador frontal en la ruta. Antes de servir Laravel con Apache, asegúrese de habilitar el módulo para que el servidor cumpla con el archivo.public/.htaccessindex.phpmod_rewrite.htaccess

Si el .htaccessarchivo que se incluye con Laravel no funciona con su instalación de Apache, pruebe esta alternativa:

Options +FollowSymLinks -Indexes
RewriteEngine On

RewriteCond %{HTTP:Authorization} .
RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ index.php [L]


