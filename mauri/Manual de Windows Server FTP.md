# Manual de Windows Server FTP: Configuración de un Servidor FTP en Windows Server

En este manual, te guiaré a través de los pasos para configurar y administrar un servidor FTP en Windows Server. Aprenderás cómo habilitar el servicio FTP, configurar usuarios y permisos, y realizar la conexión desde un cliente FTP.

## Paso 1: Habilitar el Servicio FTP en Windows Server

1. Abre el "Administrador del servidor" en Windows Server.
2. Haz clic en "Agregar roles y características".
3. Sigue el asistente de instalación y selecciona "Servidor FTP" en la lista de roles disponibles.
4. Configura las opciones adicionales según tus necesidades y completa el proceso de instalación.

## Paso 2: Configurar Usuarios y Permisos

1. Abre el "Administrador de usuarios y grupos locales" en Windows Server.
2. Crea un nuevo usuario o selecciona un usuario existente para asignarle permisos de acceso FTP.
3. Haz clic derecho en el usuario y selecciona "Propiedades".
4. En la pestaña "Miembro de", agrega el grupo "FTP Users" para otorgar permisos de acceso FTP al usuario.

## Paso 3: Configurar el Firewall de Windows

1. Abre el "Firewall de Windows con seguridad avanzada" en Windows Server.
2. Crea una nueva regla de entrada para permitir el tráfico FTP.
3. Selecciona el protocolo "TCP" y el puerto "21" para la regla.
4. Configura las opciones adicionales según tus necesidades y guarda la regla.

## Paso 4: Configurar Opciones de FTP

1. Abre el "Administrador de Internet Information Services (IIS)" en Windows Server.
2. Expande el nodo del servidor y haz clic en "Sitios FTP".
3. Haz doble clic en "Sitio FTP predeterminado" para abrir la configuración del sitio.
4. En la pestaña "Seguridad de autenticación", habilita las opciones de autenticación apropiadas, como "Inicio de sesión anónimo" o "Inicio de sesión básico".
5. En la pestaña "Configuración de enlace", configura la dirección IP y el número de puerto para el sitio FTP.

## Paso 5: Conexión desde un Cliente FTP

1. Abre un cliente FTP en tu computadora, como FileZilla, File Explorer (en Windows) o cualquier otro cliente FTP de tu elección.
2. Ingresa la dirección IP del servidor FTP en el campo del servidor.
3. Utiliza el nombre de usuario y contraseña configurados previamente para acceder al servidor FTP.
4. Si el puerto utilizado es diferente al puerto predeterminado (21), asegúrate de especificarlo en la configuración del cliente FTP.

¡Enhorabuena! Ahora has configurado un servidor FTP en Windows Server. Puedes comenzar a transferir archivos entre el servidor y los clientes FTP utilizando las credenciales y los permisos asignados. Asegúrate de realizar las configuraciones de seguridad adecuadas y de mantener actualizado tu servidor FTP para garantizar un entorno seguro y confiable.
