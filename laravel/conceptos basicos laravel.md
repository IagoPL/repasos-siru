# Manual de inicio de Laravel: Introducción y conceptos básicos

En este manual, te guiará a través de los pasos necesarios para comenzar a trabajar con Laravel, un popular framework de desarrollo de aplicaciones web basado en PHP. Aprenderás los conceptos básicos y conocerás el contenido principal de Laravel.

## Requisitos previos

Antes de comenzar, asegúrate de tener instalado PHP y Composer en tu sistema. Puedes descargar la última versión de PHP desde el [sitio web oficial de PHP](https://www.php.net) y Composer desde el [sitio web oficial de Composer](https://getcomposer.org).

## Paso 1: Instalación de Laravel

Laravel utiliza Composer para gestionar sus dependencias y facilitar la instalación. Sigue estos pasos para instalar Laravel:

1. Abre una terminal o línea de comandos.
2. Ejecuta el siguiente comando para instalar Laravel globalmente utilizando Composer:

   ```
   composer global require laravel/installer
   ```

3. Espera a que se complete la instalación. Una vez finalizada, tendrás Laravel instalado en tu sistema.

## Paso 2: Creación de un nuevo proyecto Laravel

Con Laravel, puedes generar rápidamente la estructura básica de un nuevo proyecto. Sigue estos pasos para crear un nuevo proyecto Laravel:

1. En la terminal, navega a la ubicación donde deseas crear tu proyecto.
2. Ejecuta el siguiente comando para crear un nuevo proyecto Laravel:

   ```
   laravel new nombre-del-proyecto
   ```

   Reemplaza "nombre-del-proyecto" por el nombre que desees darle a tu proyecto.

3. Composer instalará todas las dependencias necesarias y generará la estructura básica del proyecto. Este proceso puede llevar unos minutos.

## Paso 3: Explorando la estructura del proyecto

Después de crear el proyecto, Laravel generará una estructura de archivos y directorios preconfigurada. Aquí hay una descripción de algunos de los archivos y directorios más importantes:

- `app`: Este directorio contiene los modelos, controladores y otros archivos principales de la aplicación.
- `config`: Aquí se encuentran los archivos de configuración de Laravel, como la configuración de la base de datos y las opciones de la aplicación.
- `database`: En este directorio se encuentran las migraciones y las semillas de la base de datos.
- `public`: Este directorio es la raíz del servidor web y contiene el archivo `index.php`, que es el punto de entrada de la aplicación.
- `resources`: Aquí se encuentran las vistas, los archivos de traducción y los assets (CSS, JavaScript, imágenes, etc.) de la aplicación.
- `routes`: En este directorio se definen las rutas de la aplicación.
- `tests`: Aquí se encuentran los archivos de prueba automatizados.

## Paso 4: Iniciando el servidor de desarrollo

Una vez que el proyecto se haya creado correctamente, puedes iniciar el servidor de desarrollo de Laravel para ver tu aplicación en funcionamiento. Sigue estos pasos:

1. En la terminal, navega hasta el directorio raíz de tu proyecto.
2. Ejecuta el siguiente comando para iniciar el servidor de desarrollo:

   ```
   php artisan serve
   ```

3. Laravel iniciará el servidor de desarrollo y mostrará la URL en la que puedes acceder a tu aplicación en el navegador (por lo general, "http://localhost:8000").
4.

 Abre tu navegador web y visita la dirección proporcionada para ver tu aplicación Laravel en funcionamiento.

### Paso 5: Edición y desarrollo

Una vez que la aplicación se esté ejecutando, puedes comenzar a editar el código fuente y ver los cambios en tiempo real. Puedes editar los controladores en `app/Http/Controllers` para definir la lógica de la aplicación, las rutas en `routes/web.php` y las vistas en `resources/views` para construir la interfaz de usuario.

Además, Laravel ofrece muchas características y herramientas poderosas, como el enrutamiento, las migraciones de base de datos, el sistema de autenticación y la integración de paquetes mediante Composer. Puedes explorar más sobre estas características en la [documentación oficial de Laravel](https://laravel.com/docs).
