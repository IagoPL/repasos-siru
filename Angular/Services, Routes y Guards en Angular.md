# Manual: Services, Routes y Guards en Angular

En este manual, aprenderemos sobre los Services, Routes y Guards en Angular. Exploraremos cómo crear y utilizar Services para compartir datos y funcionalidades entre componentes, cómo configurar y utilizar Routes para la navegación en la aplicación y cómo utilizar Guards para proteger las rutas y controlar el acceso a determinadas partes de la aplicación.

## Requisitos previos

Antes de comenzar, asegúrate de tener un proyecto de Angular configurado y creado.

## Paso 1: Crear un Service

1. Abre una terminal o línea de comandos.
2. Navega hasta el directorio raíz de tu proyecto de Angular.
3. Ejecuta el siguiente comando para crear un nuevo service:

   ```
   ng generate service nombre-del-servicio
   ```

   Reemplaza "nombre-del-servicio" por el nombre que desees darle a tu service.

4. Angular CLI generará los archivos necesarios para el service en el directorio correspondiente.

## Paso 2: Implementar lógica en el Service

1. Abre el archivo del Service que creaste (`nombre-del-servicio.service.ts`) en tu editor de código.
2. Define propiedades y métodos en el Service según tus necesidades. Por ejemplo:

   ```typescript
   import { Injectable } from '@angular/core';

   @Injectable({
     providedIn: 'root',
   })
   export class NombreDelServicioService {
     datos: any[] = [];

     constructor() {}

     agregarDato(dato: any) {
       this.datos.push(dato);
     }

     obtenerDatos() {
       return this.datos;
     }
   }
   ```

   En este ejemplo, se ha creado una propiedad `datos` que almacenará los datos y dos métodos: `agregarDato()` para añadir un dato al array y `obtenerDatos()` para obtener los datos almacenados.

## Paso 3: Inyectar el Service en un Componente

1. Abre el componente donde deseas utilizar el Service.
2. Importa el Service y añádelo en el constructor del componente. Por ejemplo:

   ```typescript
   import { Component } from '@angular/core';
   import { NombreDelServicioService } from './nombre-del-servicio.service';

   @Component({
     selector: 'app-nombre-del-componente',
     template: `...`,
   })
   export class NombreDelComponente {
     constructor(private servicio: NombreDelServicioService) {}

     // Utiliza los métodos y propiedades del servicio en este componente
   }
   ```

   Al inyectar el Service en el constructor del componente, se creará una instancia del Service que se puede utilizar en ese componente.

## Paso 4: Configurar las Routes

1. Abre el archivo `app-routing.module.ts` en tu proyecto de Angular.
2. Importa los componentes que deseas utilizar en las rutas.
3. Agrega las rutas en la propiedad `routes` del módulo. Por ejemplo:

   ```typescript
   import { NgModule } from '@angular/core';
   import { RouterModule, Routes } from '@angular/router';
   import { HomeComponent } from './home.component';
   import { LoginComponent } from './login.component';
   import { AuthGuard } from './auth.guard';

   const routes: Routes = [
     { path: '', component: HomeComponent },
     { path: 'login', component: LoginComponent },
     { path: 'admin', component: AdminComponent, canActivate: [AuthGuard] },
   ];

   @NgModule({
     imports: [RouterModule.forRoot(routes

)],
     exports: [RouterModule],
   })
   export class AppRoutingModule {}
   ```

   En este ejemplo, se han definido tres rutas: la ruta raíz se asigna al componente `HomeComponent`, la ruta `/login` se asigna al componente `LoginComponent` y la ruta `/admin` se asigna al componente `AdminComponent` y se utiliza un Guard `AuthGuard` para proteger el acceso a la ruta `/admin`.

## Paso 5: Crear un Guard

1. Crea un archivo `auth.guard.ts` en tu proyecto de Angular.
2. Define un Guard y su lógica. Por ejemplo:

   ```typescript
   import { Injectable } from '@angular/core';
   import { CanActivate, Router } from '@angular/router';

   @Injectable({
     providedIn: 'root',
   })
   export class AuthGuard implements CanActivate {
     constructor(private router: Router) {}

     canActivate(): boolean {
       // Aquí puedes agregar tu lógica de autenticación o autorización
       // Si el usuario tiene acceso, devuelve true. De lo contrario, redirige a otra ruta.
       if (usuarioAutenticado) {
         return true;
       } else {
         this.router.navigate(['/login']);
         return false;
       }
     }
   }
   ```

   En este ejemplo, el Guard `AuthGuard` implementa la interfaz `CanActivate` y proporciona la lógica de autenticación o autorización. Si el usuario está autenticado, el Guard permite el acceso a la ruta protegida (`/admin`). De lo contrario, redirige al usuario a la ruta de inicio de sesión (`/login`).

## Paso 6: Utilizar las rutas en el componente principal

1. Abre el archivo `app.component.html` en tu proyecto de Angular.
2. Utiliza la directiva `router-outlet` para mostrar el contenido de las rutas en el componente principal. Por ejemplo:

   ```html
   <router-outlet></router-outlet>
   ```

   Esto permite que Angular renderice los componentes correspondientes según la ruta actual.

## Paso 7: Ejecutar la aplicación

1. En la terminal, navega hasta el directorio raíz de tu proyecto de Angular.
2. Ejecuta el siguiente comando para iniciar la aplicación:

   ```
   ng serve
   ```

   Esto compilará y ejecutará la aplicación Angular en un servidor de desarrollo.

3. Abre tu navegador web y visita `http://localhost:4200` para ver tu aplicación en funcionamiento.

