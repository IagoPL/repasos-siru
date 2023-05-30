# Manual: Inputs y Outputs en Angular

En este manual, aprenderemos cómo utilizar los Inputs y Outputs en Angular para la comunicación entre componentes. Los Inputs nos permiten pasar datos de un componente padre a un componente hijo, mientras que los Outputs nos permiten emitir eventos desde un componente hijo hacia un componente padre.

## Paso 1: Utilizar un Input para pasar datos al componente hijo

1. En el componente padre, define una propiedad y asigna un valor a esta propiedad. Por ejemplo:

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-padre',
     template: `
       <h1>Componente Padre</h1>
       <app-hijo [dato]="datoPadre"></app-hijo>
     `,
   })
   export class PadreComponent {
     datoPadre: string = 'Hola desde el componente padre';
   }
   ```

   En este ejemplo, hemos definido una propiedad `datoPadre` en el componente padre y le hemos asignado un valor.

2. En el componente hijo, declara una propiedad con el decorador `@Input()` para recibir el dato del componente padre. Por ejemplo:

   ```typescript
   import { Component, Input } from '@angular/core';

   @Component({
     selector: 'app-hijo',
     template: `
       <h2>Componente Hijo</h2>
       <p>Dato recibido: {{ datoHijo }}</p>
     `,
   })
   export class HijoComponent {
     @Input() datoHijo: string;
   }
   ```

   En este ejemplo, hemos declarado la propiedad `datoHijo` con el decorador `@Input()` en el componente hijo para recibir el dato del componente padre.

3. Ahora, cuando se utiliza el componente hijo en el componente padre, se puede pasar el dato utilizando la sintaxis `[dato]="datoPadre"`.

## Paso 2: Utilizar un Output para emitir eventos hacia el componente padre

1. En el componente hijo, declara un evento utilizando el decorador `@Output()` y la clase `EventEmitter`. Por ejemplo:

   ```typescript
   import { Component, Output, EventEmitter } from '@angular/core';

   @Component({
     selector: 'app-hijo',
     template: `
       <h2>Componente Hijo</h2>
       <button (click)="emitirEvento()">Emitir Evento</button>
     `,
   })
   export class HijoComponent {
     @Output() eventoHijo = new EventEmitter();

     emitirEvento() {
       this.eventoHijo.emit('Evento emitido desde el componente hijo');
     }
   }
   ```

   En este ejemplo, hemos declarado la propiedad `eventoHijo` utilizando el decorador `@Output()` y la clase `EventEmitter`. Luego, en el método `emitirEvento()`, emitimos el evento utilizando el método `emit()` y pasamos los datos que deseamos enviar al componente padre.

2. En el componente padre, utiliza la sintaxis `(eventoHijo)="manejarEvento($event)"` para suscribirte al evento y manejarlo en el componente padre. Por ejemplo:

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-padre',
     template: `
       <h1>Componente Padre</h1>
       <app-hijo (eventoHijo)="manejarEvento($event)"></app-hijo>
       <p>Evento recibido: {{ eventoPadre }}</p>
     `,
   })
   export class PadreComponent {
    

 eventoPadre: string;
  ```
     manejarEvento(evento: string) {
       this.eventoPadre = evento;
     }
   }
   ```

   En este ejemplo, hemos utilizado la sintaxis `(eventoHijo)="manejarEvento($event)"` para suscribirnos al evento emitido por el componente hijo. Luego, en el método `manejarEvento()`, asignamos el valor del evento a la propiedad `eventoPadre` del componente padre.

## Paso 3: Ejecutar la aplicación

1. En la terminal, navega hasta el directorio raíz de tu proyecto de Angular.
2. Ejecuta el siguiente comando para iniciar la aplicación:

   ```
   ng serve
   ```

   Esto compilará y ejecutará la aplicación Angular en un servidor de desarrollo.

3. Abre tu navegador web y visita `http://localhost:4200` para ver tu aplicación en funcionamiento.
