# Manual de Despliegue: Servidor Laravel y Cliente Angular en un mismo proyecto

En este manual, te guiaré a través de los pasos para desplegar un servidor Laravel y un cliente Angular en un mismo proyecto. Esto te permitirá trabajar de forma paralela con ambos, aprovechando las ventajas de cada tecnología.

## Requisitos previos

Antes de comenzar, asegúrate de tener instalados los siguientes componentes:

- PHP: Verifica que tienes PHP instalado en tu sistema. Puedes descargarlo desde el sitio web oficial de PHP (https://www.php.net).
- Composer: Composer es una herramienta de administración de dependencias para PHP. Asegúrate de tenerlo instalado en tu sistema. Puedes descargarlo desde https://getcomposer.org.
- Node.js: Asegúrate de tener Node.js instalado en tu sistema. Puedes descargarlo desde el sitio web oficial de Node.js (https://nodejs.org).
- Angular CLI: Instala Angular CLI globalmente en tu sistema ejecutando el siguiente comando en tu terminal: `npm install -g @angular/cli`.

## Paso 1: Crear un nuevo proyecto de Laravel

1. Abre tu terminal y navega a la ubicación donde deseas crear tu proyecto Laravel.
2. Ejecuta el siguiente comando para crear un nuevo proyecto de Laravel: `composer create-project --prefer-dist laravel/laravel mi-proyecto`.
3. Una vez que se complete la instalación, tendrás una estructura básica de proyecto Laravel lista para ser utilizada.

## Paso 2: Crear un nuevo proyecto de Angular

1. Abre tu terminal y navega a la ubicación donde deseas crear tu proyecto Angular.
2. Ejecuta el siguiente comando para crear un nuevo proyecto de Angular: `ng new cliente-angular`.
3. Responde las preguntas interactivas de Angular CLI, como el estilo de hoja de estilos a utilizar.
4. Una vez que se complete la instalación, tendrás una estructura básica de proyecto Angular lista para ser utilizada.

## Paso 3: Configurar el servidor Laravel

1. Navega a la carpeta de tu proyecto Laravel utilizando la terminal: `cd mi-proyecto`.
2. Abre el archivo `.env` y configura las variables de entorno relacionadas con la base de datos y otros ajustes necesarios para tu aplicación Laravel.
3. Ejecuta el siguiente comando para generar una clave de aplicación: `php artisan key:generate`.
4. Ejecuta el siguiente comando para iniciar el servidor Laravel: `php artisan serve`.

## Paso 4: Configurar el cliente Angular

1. Navega a la carpeta de tu proyecto Angular utilizando la terminal: `cd cliente-angular`.
2. Abre el archivo `src/environments/environment.ts` y configura la URL del servidor Laravel. Por ejemplo, `apiUrl: 'http://localhost:8000/api'`.
3. Opcionalmente, puedes configurar otras variables de entorno según tus necesidades.
4. Ejecuta el siguiente comando para iniciar el cliente Angular: `ng serve`.

## Paso 5: Verificar la integración

Ahora, tanto el servidor Laravel como el cliente Angular están en funcionamiento. Puedes verificar la integración realizando una solicitud desde el cliente Angular al servidor Laravel.

1. Abre tu navegador web y navega a la URL `http://localhost:4200` para acceder al cliente Angular.
2. Crea una solicitud HTTP en el cliente Angular para interactuar con el servidor Laravel, utilizando la URL configurada en el archivo de ent

orno.
3. Realiza la solicitud y verifica la respuesta recibida desde el servidor Laravel.
4. Puedes seguir desarrollando tanto el servidor como el cliente de forma paralela, utilizando las rutas, controladores y componentes necesarios en cada caso.

¡Felicidades! Ahora tienes un proyecto con un servidor Laravel y un cliente Angular funcionando juntos en paralelo. Puedes continuar desarrollando tu aplicación utilizando la combinación de estas tecnologías y aprovechar todas sus capacidades.

Recuerda que este manual solo cubre los aspectos básicos del despliegue. A medida que avances en tu proyecto, puedes explorar características adicionales, como la autenticación, el enrutamiento avanzado y la comunicación entre el servidor y el cliente.

¡Disfruta del desarrollo de tu proyecto Laravel y Angular!
