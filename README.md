# Symfony-simple

Es un mini proyecto con las bases del framework Symfony. El proyecto está creado para ir instalando paquetes a medida que se van precisando.

## Para levantar el proyecto

Se debe tener instalado:

-   PHP
-   Composer
-   MySql
-   Node y NPM

Ejecutar el comando

`symfony serve`

### Instalando sistema de plantillas Twig

En la terminal se debe ejecutar el siguiente comando:

`composer require symfony/twig-pack`

### Instalando herramienta debug

En la terminal se debe ejecutar el siguiente comando:

`composer require symfony/debug-pack`

### Trabajando con la base de datos

Para poder trabajar con la base de datos, necesitamos ejecutar el siguiente comando:

`composer require symfony/orm-pack`

Y al final del archivo `.env` tenemos toda la configuración necesaria para la conexión a la base de datos.

Una vez configurado el .env ejecutar el siguiente comando:

`php bin/console doctrine:database:create`
