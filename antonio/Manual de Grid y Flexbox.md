# Manual de Grid y Flexbox: Diseño de Páginas Web Flexibles

En este manual, te guiaré a través de los conceptos básicos de Grid y Flexbox, dos técnicas de diseño en CSS que te permiten crear diseños de páginas web flexibles y responsivos. Aprenderás cómo utilizar Grid y Flexbox para organizar y distribuir elementos en tu diseño, así como también realizar ejercicios prácticos para fortalecer tus habilidades.

## Paso 1: Utilizando CSS Grid

1. Crea un contenedor utilizando la propiedad `display: grid;` en tu hoja de estilos CSS:

   ```css
   .container {
     display: grid;
   }
   ```

2. Define las filas y columnas de tu grid utilizando las propiedades `grid-template-rows` y `grid-template-columns`. Puedes utilizar valores como `fr` (fracciones), `px` (píxeles) o `%` (porcentaje):

   ```css
   .container {
     display: grid;
     grid-template-rows: 1fr 1fr;
     grid-template-columns: 1fr 1fr;
   }
   ```

3. Añade elementos dentro de tu contenedor y utilice las propiedades `grid-row` y `grid-column` para definir la ubicación de los elementos en el grid:

   ```css
   .item {
     grid-row: 1 / 3;
     grid-column: 1 / 3;
   }
   ```

## Paso 2: Utilizando Flexbox

1. Crea un contenedor utilizando la propiedad `display: flex;` en tu hoja de estilos CSS:

   ```css
   .container {
     display: flex;
   }
   ```

2. Define cómo los elementos dentro del contenedor se distribuyen utilizando las propiedades `justify-content` y `align-items`. Puedes utilizar valores como `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, entre otros:

   ```css
   .container {
     display: flex;
     justify-content: center;
     align-items: center;
   }
   ```

3. Añade elementos dentro de tu contenedor y utilice la propiedad `flex` para ajustar la flexibilidad y el tamaño de los elementos:

   ```css
   .item {
     flex: 1;
   }
   ```

## Ejercicios Prácticos

1. Crea una página con una cuadrícula de 4 columnas utilizando Grid.

2. Utiliza Flexbox para alinear verticalmente elementos en una lista.

3. Crea una galería de imágenes utilizando Grid o Flexbox para organizar las imágenes en filas y columnas.

4. Diseña un formulario de contacto utilizando Flexbox para alinear y distribuir los campos de forma adecuada.

5. Crea un diseño responsivo utilizando Grid o Flexbox para adaptar el diseño a diferentes tamaños de pantalla.

¡Felicidades! Has completado los ejercicios prácticos de Grid y Flexbox. Estas técnicas te permiten crear diseños flexibles y responsivos para tus páginas web. Continúa explorando y experimentando con Grid y Flexbox para aprovechar al máximo sus capacidades y crear diseños modernos y atractivos.
