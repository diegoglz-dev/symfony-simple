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

Con el comando `php bin/console` podemos ver todos los comandos disponibles

## Instalando sistema de plantillas Twig

En la terminal se debe ejecutar el siguiente comando:

`composer require symfony/twig-pack`

## Instalando herramienta debug

En la terminal se debe ejecutar el siguiente comando:

`composer require symfony/debug-pack`

## Trabajando con la base de datos

Para poder trabajar con la base de datos, necesitamos ejecutar el siguiente comando:

`composer require symfony/orm-pack`

Y al final del archivo `.env` tenemos toda la configuración necesaria para la conexión a la base de datos.

Una vez configurado el .env ejecutar el siguiente comando:

`php bin/console doctrine:database:create`

## Creando Entidades

Se require trabajar con un paquete, el cual se instala con el siguiente comando:

`composer require symfony/maker-bundle --dev`

Una entidad es una representación en código PHP de una tabla de nuestra base de datos. Se crea con el siguiente comando:

`php bin/console make:entity` si se le agrega el flag `--help` podemos obtener más info. del comando.
Se preciona enter y se sigue los distintos mensajes de guia.

Y se guardan en src/Entity
