## Manual paso a paso para crear un CRUD simple con PHP, Postman y MySQL utilizando XAMPP

Este manual te guiará a través de los pasos necesarios para crear un CRUD (Create, Read, Update, Delete) básico utilizando PHP y MySQL con XAMPP como servidor local. También utilizaremos Postman para probar las operaciones CRUD.

### Requisitos previos

Antes de comenzar, asegúrate de tener instalados los siguientes componentes:

1. XAMPP: un paquete de software que incluye Apache, MySQL y PHP. Puedes descargarlo e instalarlo desde el sitio oficial de Apache Friends.
2. Postman: una herramienta de desarrollo de API que nos permitirá probar las operaciones CRUD.

### Paso 1: Configurar el entorno

1. Inicia XAMPP y asegúrate de que los servicios de Apache y MySQL estén en ejecución. Puedes hacerlo abriendo el panel de control de XAMPP y haciendo clic en los botones "Start" para los servicios correspondientes.
2. Abre tu navegador web e ingresa "http://localhost/phpmyadmin" en la barra de direcciones. Esto abrirá phpMyAdmin, una interfaz gráfica para administrar bases de datos MySQL.

### Paso 2: Crear la base de datos

1. En phpMyAdmin, crea una nueva base de datos llamada "crud_example".
2. Haz clic en la base de datos recién creada en el panel izquierdo y luego en la pestaña "SQL" en la parte superior.
3. En el campo de texto, ingresa el siguiente código SQL para crear una tabla llamada "users":

```sql
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  email VARCHAR(50) NOT NULL
);
```

4. Haz clic en el botón para ejecutar el código SQL y crear la tabla.

### Paso 3: Configurar el proyecto PHP

1. Crea una nueva carpeta en la carpeta "htdocs" de tu instalación de XAMPP. Puedes llamarla "crud-example".
2. Dentro de la carpeta "crud-example", crea un archivo llamado "index.php" y ábrelo con tu editor de texto favorito.
3. Copia y pega el siguiente código en el archivo "index.php":

```php
<?php
header("Content-Type: application/json");

// Conexión a la base de datos
$servername = "localhost";
$username = "root";
$password = "";
$database = "crud_example";

$conn = new mysqli($servername, $username, $password, $database);
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// Manejo de las solicitudes CRUD
$method = $_SERVER['REQUEST_METHOD'];
$request = explode('/', trim($_SERVER['PATH_INFO'],'/'));

switch ($method) {
    case 'GET':
        $id = isset($_GET['id']) ? $_GET['id'] : '%';
        $sql = "SELECT * FROM users WHERE id LIKE '$id'";
        $result = $conn->query($sql);
        if ($result->num_rows > 0) {
            $rows = array();
            while ($row = $result->fetch_assoc()) {
                $rows[] = $row;
            }
            echo json_encode($rows);
        } else {
            echo "No users found.";
        }
        break;
    case 'POST':
        $name = isset($_POST['name']) ? $_POST['name'] : '';
        $email = isset($_POST['email']) ? $_POST['email'] : '';
        $sql = "INSERT INTO users (name, email) VALUES ('$name', '$email')";
        if ($conn->query($sql) === TRUE) {
            echo "User created successfully.";
        } else {
            echo "Error creating user: " . $conn->error;
        }
        break;
    case 'PUT':
        parse_str(file_get_contents("php://input"), $put_vars);
        $id = isset($put_vars['id']) ? $put_vars['id'] : '';
        $name = isset($put_vars['name']) ? $put_vars['name'] : '';
        $email = isset($put_vars['email']) ? $put_vars['email'] : '';
        $sql = "UPDATE users SET name='$name', email='$email' WHERE id='$id'";
        if ($conn->query($sql) === TRUE) {
            echo "User updated successfully.";
        } else {
            echo "Error updating user: " . $conn->error;
        }
        break;
    case 'DELETE':
        parse_str(file_get_contents("php://input"), $delete_vars);
        $id = isset($delete_vars['id']) ? $delete_vars['id'] : '';
        $sql = "DELETE FROM users WHERE id='$id'";
        if ($conn->query($sql) === TRUE) {
            echo "User deleted successfully.";
        } else {
            echo "Error deleting user: " . $conn->error;
        }
        break;
    default:
        echo "Invalid request method.";
        break;
}

$conn->close();
?>
```

4. Guarda el archivo "index.php".

### Paso 4: Prueba el CRUD con Postman

1. Abre Postman en tu ordenador.
2. Crea una nueva solicitud y establece la URL de la solicitud en "http://localhost/crud-example/index.php" (reemplaza "crud-example" si usaste un nombre de carpeta diferente).
3. Configura el método de la solicitud según la operación CRUD que deseas probar (GET, POST, PUT o DELETE).
4. Para la operación POST y PUT, selecciona la pestaña "Body" en Postman y establece el formato en "x-www-form-urlencoded". Luego, agrega los parámetros "name" y "email" con sus respectivos valores.
5. Haz clic en el botón "Send" para enviar la solicitud y recibir la respuesta del servidor.

¡Enhorabuena! Has creado un CRUD básico utilizando PHP, MySQL y XAMPP, y lo has probado con Postman.
