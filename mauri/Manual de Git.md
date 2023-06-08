# Manual de Git: Control de Versiones para tu Proyecto

En este manual, te guiaré a través de los conceptos básicos de Git, una herramienta de control de versiones ampliamente utilizada en el desarrollo de software. Aprenderás cómo iniciar un repositorio, realizar cambios, gestionar ramas y colaborar con otros desarrolladores en un proyecto.

## Paso 1: Instalación y Configuración de Git

1. Descarga e instala Git en tu sistema operativo desde el sitio oficial: [https://git-scm.com/downloads](https://git-scm.com/downloads).
2. Abre una terminal o línea de comandos y configura tu nombre de usuario y dirección de correo electrónico utilizando los siguientes comandos:

   ```bash
   git config --global user.name "Tu Nombre"
   git config --global user.email "tu@email.com"
   ```

## Paso 2: Iniciar un Repositorio Git

1. Navega hasta el directorio raíz de tu proyecto en la terminal.
2. Ejecuta el siguiente comando para inicializar un repositorio Git en tu proyecto:

   ```bash
   git init
   ```

## Paso 3: Realizar Cambios y Hacer Commits

1. Agrega archivos al área de preparación para ser incluidos en el próximo commit. Puedes agregar archivos individualmente o todos los archivos modificados utilizando los siguientes comandos:

   ```bash
   git add nombre-archivo.extensión
   git add .
   ```

2. Realiza un commit para guardar los cambios en el repositorio. Asegúrate de incluir un mensaje descriptivo para el commit:

   ```bash
   git commit -m "Mensaje descriptivo del commit"
   ```

## Paso 4: Gestionar Ramas

1. Crea una nueva rama para trabajar en una funcionalidad o corrección específica:

   ```bash
   git branch nombre-rama
   ```

2. Cambia a la rama recién creada:

   ```bash
   git checkout nombre-rama
   ```

3. Fusiona una rama con la rama actual:

   ```bash
   git merge nombre-rama
   ```

4. Elimina una rama después de fusionar los cambios:

   ```bash
   git branch -d nombre-rama
   ```

## Paso 5: Colaboración con Repositorios Remotos

1. Conecta tu repositorio local a un repositorio remoto existente:

   ```bash
   git remote add origin url-repositorio-remoto
   ```

2. Sube tus cambios locales al repositorio remoto:

   ```bash
   git push origin nombre-rama
   ```

3. Descarga los cambios más recientes del repositorio remoto:

   ```bash
   git pull origin nombre-rama
   ```

4. Colabora con otros desarrolladores utilizando pull requests y merge para incorporar cambios al repositorio principal.

## Paso 6: Gestión de Ramas en Repositorios Remotos

1. Listar las ramas locales y remotas:

   ```bash
   git branch -a
   ```

2. Crear una nueva rama local a partir de una rama remota:

   ```bash
   git checkout -b nombre-rama origin/nombre-rama-remota
   ```

3. Empujar una rama local a un repositorio remoto:

   ```bash
   git push origin nombre-rama-local
   ```

4. Eliminar una rama rem

ota:

   ```bash
   git push origin --delete nombre-rama-remota
   ```

## Ejercicios Prácticos

1. Inicia un nuevo repositorio Git en una carpeta vacía de tu elección.

2. Crea un archivo de texto llamado "ejercicio.txt" y añade algunas líneas de texto.

3. Realiza un commit con el mensaje "Añadido archivo de ejercicio".

4. Crea una nueva rama llamada "feature/nueva-funcionalidad" y cámbiate a ella.

5. Modifica el archivo "ejercicio.txt" y añade más contenido.

6. Realiza un commit en la rama "feature/nueva-funcionalidad" con el mensaje "Añadido contenido adicional".

7. Cambia nuevamente a la rama principal y fusiona la rama "feature/nueva-funcionalidad" en ella.

8. Elimina la rama "feature/nueva-funcionalidad".

9. Conecta tu repositorio local a un repositorio remoto en GitHub.

10. Sube tus cambios al repositorio remoto.

¡Felicidades! Has completado los ejercicios prácticos de Git. Recuerda practicar y explorar más funcionalidades de Git para aprovechar al máximo esta poderosa herramienta de control de versiones.
