# Manual de Routing con Angular: Configuración y Ejercicios

En este manual, te guiaré a través de los conceptos básicos de routing en Angular, una poderosa herramienta que permite la navegación entre diferentes componentes y vistas dentro de una aplicación web. Aprenderás cómo configurar las rutas en Angular, crear enlaces y realizar ejercicios prácticos para consolidar tus conocimientos.

## Paso 1: Configuración de las Rutas

1. Crea un nuevo proyecto de Angular utilizando el CLI de Angular:

   ```bash
   ng new nombre-del-proyecto
   ```

2. Navega al directorio del proyecto:

   ```bash
   cd nombre-del-proyecto
   ```

3. Genera un módulo de routing para tu aplicación:

   ```bash
   ng generate module app-routing --flat --module=app
   ```

4. Abre el archivo `app-routing.module.ts` y configura las rutas:

   ```typescript
   import { NgModule } from '@angular/core';
   import { Routes, RouterModule } from '@angular/router';
   import { Componente1Component } from './componente1.component';
   import { Componente2Component } from './componente2.component';

   const routes: Routes = [
     { path: '', redirectTo: '/componente1', pathMatch: 'full' },
     { path: 'componente1', component: Componente1Component },
     { path: 'componente2', component: Componente2Component },
   ];

   @NgModule({
     imports: [RouterModule.forRoot(routes)],
     exports: [RouterModule],
   })
   export class AppRoutingModule {}
   ```

   Asegúrate de importar los componentes correspondientes y definir las rutas deseadas.

5. Actualiza el archivo `app.module.ts` para importar el módulo de routing:

   ```typescript
   import { NgModule } from '@angular/core';
   import { BrowserModule } from '@angular/platform-browser';
   import { AppRoutingModule } from './app-routing.module';
   import { AppComponent } from './app.component';
   import { Componente1Component } from './componente1.component';
   import { Componente2Component } from './componente2.component';

   @NgModule({
     declarations: [
       AppComponent,
       Componente1Component,
       Componente2Component
     ],
     imports: [
       BrowserModule,
       AppRoutingModule
     ],
     providers: [],
     bootstrap: [AppComponent]
   })
   export class AppModule { }
   ```

## Paso 2: Crear Componentes

1. Crea los componentes `Componente1` y `Componente2` utilizando el CLI de Angular:

   ```bash
   ng generate component componente1
   ng generate component componente2
   ```

2. Personaliza los componentes según tus necesidades.

## Paso 3: Enlaces y Navegación

1. Abre el archivo `app.component.html` y agrega enlaces de navegación:

   ```html
   <ul>
     <li><a routerLink="/componente1">Componente 1</a></li>
     <li><a routerLink="/componente2">Componente 2</a></li>
   </ul>
   <router-outlet></router-outlet>
   ```

2. Abre el archivo `app.component.css` y agrega estilos opcionales para los enlaces.

## Ejercicios Prácticos

Ahora que has configurado las rutas en tu aplicación Angular, puedes realizar algunos ejercicios para practicar el uso del routing:

1. Crea un nuevo componente llam

ado `Componente3` y configura una ruta para él en el módulo de routing. Asegúrate de agregar un enlace de navegación correspondiente.

2. Agrega parámetros a una de las rutas existentes. Por ejemplo, modifica la ruta del `Componente1` para que pueda recibir un parámetro `id`. Actualiza el componente correspondiente para mostrar el valor del parámetro en la vista.

3. Implementa una ruta secundaria dentro de uno de los componentes existentes. Por ejemplo, crea una ruta secundaria dentro del `Componente1` que muestre información adicional cuando se navega a `/componente1/detalles`.

4. Explora las opciones avanzadas de routing en Angular, como la protección de rutas, rutas anidadas, resolvers, etc. Realiza algunos experimentos y ajustes adicionales en tu aplicación para familiarizarte con estas características.

Recuerda que practicar estos ejercicios te ayudará a comprender mejor el enrutamiento en Angular y a ganar experiencia en su implementación. ¡Diviértete explorando las capacidades de routing en tu aplicación!
