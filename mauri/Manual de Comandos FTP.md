# Manual de Comandos FTP: Transferencia de Archivos en Protocolo FTP

En este manual, te guiaré a través de los comandos básicos del Protocolo de Transferencia de Archivos (FTP), una forma común de transferir archivos entre un cliente y un servidor remoto. Aprenderás cómo conectarte a un servidor FTP, realizar operaciones de transferencia de archivos y administrar directorios.

## Paso 1: Conexión a un Servidor FTP

1. Abre una terminal o línea de comandos en tu sistema operativo.
2. Utiliza el siguiente comando para conectarte a un servidor FTP:

   ```bash
   ftp servidor-ftp
   ```

   Reemplaza "servidor-ftp" con la dirección IP o el nombre de dominio del servidor FTP al que deseas conectarte.

3. Ingresa tu nombre de usuario y contraseña cuando se te solicite. Si no tienes un usuario, verifica con el administrador del servidor FTP para obtener las credenciales correctas.

## Paso 2: Comandos Básicos de FTP

A continuación se presentan algunos comandos básicos de FTP que puedes utilizar una vez que te hayas conectado al servidor:

- `ls`: Lista los archivos y directorios en el directorio actual del servidor FTP.
- `cd directorio`: Cambia al directorio especificado en el servidor FTP.
- `get archivo`: Descarga el archivo especificado desde el servidor FTP al directorio local.
- `put archivo`: Sube el archivo especificado desde el directorio local al servidor FTP.
- `delete archivo`: Elimina el archivo especificado en el servidor FTP.
- `mkdir directorio`: Crea un nuevo directorio en el servidor FTP.
- `rmdir directorio`: Elimina el directorio especificado en el servidor FTP (debe estar vacío).

## Paso 3: Transferencia de Archivos

1. Para descargar un archivo del servidor FTP, utiliza el comando `get` seguido del nombre del archivo:

   ```bash
   get archivo.txt
   ```

   Esto descargará el archivo "archivo.txt" del servidor FTP al directorio local actual.

2. Para subir un archivo al servidor FTP, utiliza el comando `put` seguido del nombre del archivo:

   ```bash
   put archivo.txt
   ```

   Esto cargará el archivo "archivo.txt" desde el directorio local actual al directorio remoto actual en el servidor FTP.

3. Para eliminar un archivo del servidor FTP, utiliza el comando `delete` seguido del nombre del archivo:

   ```bash
   delete archivo.txt
   ```

   Esto eliminará el archivo "archivo.txt" del servidor FTP.

## Paso 4: Administración de Directorios

1. Para cambiar al directorio raíz del servidor FTP, utiliza el comando `cd` sin argumentos:

   ```bash
   cd
   ```

2. Para cambiar al directorio padre del directorio actual, utiliza el comando `cd ..`:

   ```bash
   cd ..
   ```

3. Para crear un nuevo directorio en el servidor FTP, utiliza el comando `mkdir` seguido del nombre del directorio:

   ```bash
   mkdir nuevo-directorio
   ```

4. Para eliminar un directorio del servidor FTP, utiliza el comando `rmdir` seguido del nombre del directorio:

   ```bash
   rmdir directorio-a-eliminar
   ```

   Ten en cuenta que el directorio debe estar vacío para poder eliminarlo.

¡Enhorabuena! Ahora estás familiarizado con los comandos

 básicos de FTP. Puedes utilizar estos comandos para administrar y transferir archivos en servidores FTP. Asegúrate de verificar la documentación del servidor FTP o consultar con el administrador del servidor para obtener más información sobre los comandos y opciones específicos disponibles en tu entorno de FTP.
