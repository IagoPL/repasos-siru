# Manual: Modificar, añadir, editar y borrar datos en un archivo JSON en Angular

En este manual, aprenderemos cómo realizar operaciones de modificación, adición, edición y borrado de datos en un archivo JSON en Angular. Utilizaremos un archivo JSON local y utilizaremos servicios y métodos en Angular para llevar a cabo estas operaciones.

## Requisitos previos

Antes de comenzar, asegúrate de tener un proyecto de Angular configurado y un archivo JSON existente con datos que deseas modificar, añadir, editar y borrar.

## Paso 1: Crear un servicio para manejar las operaciones del archivo JSON

1. Abre una terminal o línea de comandos.
2. Navega hasta el directorio raíz de tu proyecto de Angular.
3. Ejecuta el siguiente comando para crear un nuevo servicio:

   ```
   ng generate service nombre-del-servicio
   ```

   Reemplaza "nombre-del-servicio" por el nombre que desees darle a tu servicio.

4. Angular CLI generará los archivos necesarios para el servicio en el directorio correspondiente.

## Paso 2: Leer los datos del archivo JSON en el servicio

1. Abre el archivo del servicio que creaste (`nombre-del-servicio.service.ts`) en tu editor de código.
2. Importa el módulo `HttpClient` de `@angular/common/http`.
3. Inyecta el servicio `HttpClient` en el constructor del servicio.
4. Define un método en el servicio para leer los datos del archivo JSON. Por ejemplo:

   ```typescript
   import { HttpClient } from '@angular/common/http';
   import { Observable } from 'rxjs';

   // ...

   constructor(private http: HttpClient) {}

   getDatos(): Observable<any[]> {
     return this.http.get<any[]>('assets/datos.json');
   }
   ```

   Asegúrate de reemplazar `'assets/datos.json'` con la ruta correcta al archivo JSON en tu proyecto.

## Paso 3: Mostrar los datos en un componente

1. Abre el componente donde deseas mostrar los datos del archivo JSON.
2. Inyecta el servicio que creaste en el constructor del componente.
3. En el método `ngOnInit()`, llama al método del servicio para obtener los datos del archivo JSON y suscríbete a la respuesta. Por ejemplo:

   ```typescript
   import { Component, OnInit } from '@angular/core';
   import { NombreDelServicioService } from './nombre-del-servicio.service';

   // ...

   export class NombreDelComponente implements OnInit {
     datos: any[];

     constructor(private servicio: NombreDelServicioService) {}

     ngOnInit() {
       this.servicio.getDatos().subscribe((response) => {
         this.datos = response;
       });
     }
   }
   ```

   La variable `datos` contendrá los datos del archivo JSON.

4. En la plantilla del componente, utiliza directivas de Angular, como `*ngFor`, para iterar sobre los datos y mostrarlos. Por ejemplo:

   ```html
   <ul>
     <li *ngFor="let item of datos">{{ item.nombre }}</li>
   </ul>
   ```

   Esto generará una lista con los nombres de los elementos en el archivo JSON.

## Paso 4: Agregar una función para modificar los datos

1. En el servicio, define un método para modificar los datos del archivo JSON. Por ejemplo, para cambiar el nombre de un elemento:

   ```typescript
   modificarDato(id: number, nuevoNombre: string): Observable<any> {
     return this.http

.patch<any>('assets/datos.json', { id, nombre: nuevoNombre });
   }
   ```

   Este método utiliza el método `patch` de `HttpClient` para enviar una solicitud de modificación al archivo JSON.
   
## Paso 5: Agregar una función para añadir nuevos datos

1. En el servicio, define un método para añadir nuevos datos al archivo JSON. Por ejemplo:

   ```typescript
   agregarDato(nuevoDato: any): Observable<any> {
     return this.http.post<any>('assets/datos.json', nuevoDato);
   }
   ```

   Este método utiliza el método `post` de `HttpClient` para enviar una solicitud de adición al archivo JSON.

## Paso 6: Agregar una función para editar datos existentes

1. En el servicio, define un método para editar datos existentes en el archivo JSON. Por ejemplo:

   ```typescript
   editarDato(id: number, datosEditados: any): Observable<any> {
     return this.http.put<any>(`assets/datos.json/${id}`, datosEditados);
   }
   ```

   Este método utiliza el método `put` de `HttpClient` para enviar una solicitud de edición al archivo JSON.

## Paso 7: Agregar una función para borrar datos

1. En el servicio, define un método para borrar datos del archivo JSON. Por ejemplo:

   ```typescript
   borrarDato(id: number): Observable<any> {
     return this.http.delete<any>(`assets/datos.json/${id}`);
   }
   ```

   Este método utiliza el método `delete` de `HttpClient` para enviar una solicitud de borrado al archivo JSON.

## Paso 8: Utilizar las funciones en el componente

1. En el componente, importa el servicio correspondiente y inyéctalo en el constructor.
2. Utiliza las funciones del servicio según sea necesario para realizar operaciones de modificación, adición, edición y borrado en el archivo JSON.

## Paso 9: Ejecutar la aplicación

1. En la terminal, navega hasta el directorio raíz de tu proyecto de Angular.
2. Ejecuta el siguiente comando para iniciar la aplicación:

   ```
   ng serve
   ```

   Esto compilará y ejecutará la aplicación Angular en un servidor de desarrollo.

3. Abre tu navegador web y visita `http://localhost:4200` para ver tu aplicación en funcionamiento.

### Conclusiones

En este manual, hemos aprendido cómo realizar operaciones de modificación, adición, edición y borrado de datos en un archivo JSON en Angular. Hemos utilizado servicios y métodos de Angular para manejar estas operaciones, permitiéndonos interactuar con los datos en el archivo JSON.

Recuerda que debes adaptar los nombres de los servicios y componentes a tu proyecto, así como asegurarte de que la ruta al archivo JSON sea correcta.

¡Disfruta trabajando con JSON en Angular y construyendo aplicaciones poderosas!
