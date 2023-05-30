# Manual: Bindings & Events con Directivas Estructurales en Angular

En este manual, exploraremos cómo utilizar bindings y eventos con directivas estructurales en Angular. Aprenderemos cómo vincular datos a elementos del DOM, cómo utilizar eventos para responder a interacciones del usuario y cómo utilizar directivas estructurales para manipular la estructura del DOM.

## Requisitos previos

Antes de comenzar, asegúrate de tener instalado Node.js y Angular CLI en tu sistema. Puedes descargar e instalar Node.js desde el [sitio web oficial de Node.js](https://nodejs.org) y Angular CLI ejecutando el siguiente comando en la línea de comandos:

```
npm install -g @angular/cli
```

## Paso 1: Crear un nuevo proyecto de Angular

1. Abre una terminal o línea de comandos.
2. Navega hasta la ubicación donde deseas crear tu proyecto de Angular.
3. Ejecuta el siguiente comando para crear un nuevo proyecto de Angular:

   ```
   ng new nombre-del-proyecto
   ```

   Reemplaza "nombre-del-proyecto" por el nombre que desees darle a tu proyecto.

4. Angular CLI instalará todas las dependencias necesarias y generará la estructura básica del proyecto.

## Paso 2: Crear un componente

1. Abre una terminal o línea de comandos.
2. Navega hasta el directorio raíz de tu proyecto de Angular.
3. Ejecuta el siguiente comando para crear un nuevo componente:

   ```
   ng generate component nombre-del-componente
   ```

   Reemplaza "nombre-del-componente" por el nombre que desees darle a tu componente.

4. Angular CLI generará los archivos necesarios para el componente en el directorio correspondiente.

## Paso 3: Utilizar bindings en el componente

1. Abre el archivo del componente que creaste (`nombre-del-componente.component.ts`) en tu editor de código.
2. Dentro de la clase del componente, define una propiedad con el valor que deseas mostrar en el HTML. Por ejemplo:

   ```typescript
   nombre: string = 'Juan';
   ```

3. En el archivo de la plantilla del componente (`nombre-del-componente.component.html`), utiliza el binding para mostrar el valor de la propiedad en el HTML. Por ejemplo:

   ```html
   <h1>Hola, {{ nombre }}!</h1>
   ```

   Esto mostrará "Hola, Juan!" en el navegador.

## Paso 4: Utilizar eventos en el componente

1. En el archivo de la plantilla del componente, agrega un elemento HTML con un evento que deseas capturar. Por ejemplo:

   ```html
   <button (click)="saludar()">Saludar</button>
   ```

   Esto crea un botón que llamará al método "saludar()" cuando se haga clic en él.

2. En el archivo del componente, define el método "saludar()" dentro de la clase del componente. Por ejemplo:

   ```typescript
   saludar() {
     console.log('¡Hola!');
   }
   ```

   Este método imprimirá "¡Hola!" en la consola cuando se haga clic en el botón.

## Paso 5: Utilizar directivas estructurales

1. En el archivo de la plantilla del componente, utiliza directivas estructurales, como `*ngIf`, `*ngFor`, `ngClass` y `ngStyle`, para manipular la estructura y el estilo del DOM.

   - `

*ngIf`: Permite mostrar o ocultar elementos en función de una condición. Por ejemplo:

     ```html
     <div *ngIf="mostrarMensaje">
       <p>Este mensaje se muestra si la variable "mostrarMensaje" es verdadera.</p>
     </div>
     ```

   - `*ngFor`: Permite iterar sobre una lista de elementos y generar contenido dinámicamente. Por ejemplo:

     ```html
     <ul>
       <li *ngFor="let item of items">{{ item }}</li>
     </ul>
     ```

   - `ngClass`: Permite aplicar clases CSS condicionalmente a un elemento. Por ejemplo:

     ```html
     <div [ngClass]="{'clase-1': condicion1, 'clase-2': condicion2}">
       <!-- Contenido del elemento -->
     </div>
     ```

   - `ngStyle`: Permite aplicar estilos CSS condicionalmente a un elemento. Por ejemplo:

     ```html
     <div [ngStyle]="{'color': color, 'font-size': tamano + 'px'}">
       <!-- Contenido del elemento -->
     </div>
     ```

2. En el archivo del componente, define las propiedades y condiciones necesarias para controlar las directivas estructurales. Por ejemplo:

   ```typescript
   mostrarMensaje: boolean = true;
   items: string[] = ['Item 1', 'Item 2', 'Item 3'];
   condicion1: boolean = true;
   condicion2: boolean = false;
   color: string = 'red';
   tamano: number = 14;
   ```

   Puedes cambiar los valores de estas propiedades para controlar las directivas estructurales según sea necesario.

## Paso 6: Ejecutar la aplicación

1. En la terminal, navega hasta el directorio raíz de tu proyecto de Angular.
2. Ejecuta el siguiente comando para iniciar la aplicación:

   ```
   ng serve
   ```

   Esto compilará y ejecutará la aplicación Angular en un servidor de desarrollo.

3. Abre tu navegador web y visita `http://localhost:4200` para ver tu aplicación en funcionamiento.
