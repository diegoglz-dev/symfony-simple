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

## Migraciones

Es la estructura inicial que se convertira en una tabla de la base de datos. Permite trabajar como si fuera un sistema de control de versiones de nuestra DB.

Para crear una nueva migración ejecutar el comando:
`php bin/console make:migration`

Esto crea un nuevo archivo en la carpeta migrations que tiene todo el código necesario para construir la tabla y la creará a partir de lo que tiene en nuestra entidad.

Y para que se convierta en una tabla real se necesita ejecutar el comando:
`php bin/console doctrine:migrations:migrate`

### Repositorio

Es el que contiene todos los metodos de consulta.

El mismo se encuentra en Repository/EntityNameRepository

## Formularios

Para trabajar con formularios necesitamos ejecutar el siguiente comando:

`composer require symfony/form`

Para crear un nuevo formulario ejecutar el comando:

`php bin/console make:form`

1. Te pedirá el nombre de la clase del formulario.
2. Te pedirá con que entidad trabjará.

Creará un nuevo formulario en src/Form

## Validador

Para trabajar con el validador, se require instalar un paquete con el siguiente comando:

`composer require symfony/validator`

Luego en la entidad, importar al sistema que acabamos de instalar:

`use Symfony\Component\Validator\Constraints as Assert;`

## Front-end

Para trabajar con el front-end de nuestra aplicación, vamos a necesitar el siguiente paquete:

`composer require symfony/webpack-encore-bundle`

Y de manera automatica crea la carpeta assets correspondiente a los archivos de diseño.

Luego ejecutar el comando `npm install` para instalar todo lo necesario

### Instalando Bootstrap

Ejecutamos el siguiente comando:

`npm install bootstrap --save-dev`

En el archivo package.json se inserta la linea que instala bootstrap

En assets/styles/app.css agregar `@import 'bootstrap';`

Luego para crear los archivos correspondientes al front en la carpeta public. Se necesita correr el comando `npm run dev`.

Se crea una carpeta build en public con los archivos finales.

Se utilizan de forma automatica los estilos, porque en la plantilla base base.html.twig se encuentra la linea `{{ encore_entry_link_tags('app') }}`
