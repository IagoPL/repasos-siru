## Manual de inicio de Angular: Introducción y conceptos básicos

En este manual, te guiará a través de los pasos necesarios para comenzar a trabajar con Angular, un popular framework de desarrollo de aplicaciones web de código abierto creado por Google. Aprenderás los conceptos básicos y conocerás el contenido principal de Angular.

### Requisitos previos

Antes de comenzar, asegúrate de tener instalado Node.js en tu sistema. Puedes descargar la versión más reciente de Node.js desde su sitio web oficial.

### Paso 1: Instalación de Angular CLI

Angular CLI (Command Line Interface) es una herramienta de línea de comandos que facilita la creación y gestión de proyectos de Angular. Para instalarlo, sigue estos pasos:

1. Abre una terminal.
2. Ejecuta el siguiente comando para instalar Angular CLI globalmente:

   ```
   npm install -g @angular/cli
   ```

3. Espera a que se complete la instalación. Una vez finalizado, tendrás Angular CLI instalado en tu sistema.

### Paso 2: Creación de un nuevo proyecto de Angular

Con Angular CLI, puedes generar rápidamente la estructura básica de un nuevo proyecto de Angular. Sigue estos pasos para crear un nuevo proyecto:

1. En la terminal, navega a la ubicación donde deseas crear tu proyecto.
2. Ejecuta el siguiente comando para crear un nuevo proyecto de Angular:

   ```
   ng new nombre-del-proyecto
   ```

   Reemplaza "nombre-del-proyecto" por el nombre que desees darle a tu proyecto.

3. Angular CLI instalará todas las dependencias necesarias y generará la estructura básica del proyecto. Este proceso puede llevar unos minutos.

### Paso 3: Explorando la estructura del proyecto

Después de crear el proyecto, Angular generará una estructura de archivos y directorios preconfigurada. Aquí hay una descripción de algunos de los archivos y directorios más importantes:

- `src`: Este directorio contiene el código fuente principal de la aplicación Angular.
  - `src/app`: Aquí es donde se encuentra el código TypeScript de los componentes, servicios y otros elementos de la aplicación.
  - `src/assets`: Puedes colocar recursos estáticos como imágenes o archivos JSON en este directorio.
  - `src/index.html`: Este es el archivo HTML principal de la aplicación donde se carga la aplicación Angular.
- `angular.json`: Este archivo contiene la configuración global del proyecto de Angular, incluyendo dependencias, rutas y opciones de compilación.
- `package.json`: Este archivo es utilizado por Node.js para gestionar las dependencias del proyecto.
- `tsconfig.json`: Aquí se encuentra la configuración del compilador TypeScript para el proyecto.

### Paso 4: Iniciando la aplicación

Una vez que el proyecto se haya creado correctamente, puedes iniciar la aplicación de Angular para verla en tu navegador. Sigue estos pasos:

1. En la terminal, navega hasta el directorio raíz de tu proyecto.
2. Ejecuta el siguiente comando para iniciar la aplicación:

   ```
   ng serve --open
   ```

3. Angular CLI compilará la aplicación y lanzará un servidor de desarrollo. Verás un mensaje que indica en qué dirección se está ejecutando la aplicación (por lo general, "http://localhost:4200").
4. Abre tu navegador web y visita la dirección proporcionada para ver tu aplicación Angular en funcionamiento.

### Paso 5: Edición y

 desarrollo

Una vez que la aplicación se esté ejecutando, puedes comenzar a editar el código fuente y ver los cambios en tiempo real. Angular CLI habilita la característica de recarga automática, lo que significa que la aplicación se actualizará automáticamente cada vez que guardes los cambios en los archivos fuente.

Puedes editar los componentes en `src/app` para construir la interfaz de usuario, definir rutas en `src/app/app-routing.module.ts` y crear servicios en `src/app/services` para la lógica del negocio. Además, Angular ofrece muchas características y herramientas para construir aplicaciones web modernas, como enlace de datos, enrutamiento, manejo de formularios y más.
