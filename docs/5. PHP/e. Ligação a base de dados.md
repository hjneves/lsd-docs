Vimos que podemos ter uma base de dados para organizar e guardar a informação necessária ao nosso site. Também vimos que podemos questionar, inserir, eliminar e alterar a informação usando a linguagem `SQL`.

Vai ser através do php que o backend do nosso site vai poder comunicar com a base de dados para realizar as operações que necessitem de informação.

Para estabelecer este ligação à base de dados devemos criar uma connection em php com as credenciais de acesso à base de dados e validar se tudo correu bem.

Vamos criar um ficheiro `config.php` para este efeito que será posteriormente incluido noutros ficheiros php que necessitem de acesso à bd. As variáveis definidas neste ficheiro são visíveis no ficheiro que o inclui.

```php
// --- config.php
<?php
    // Set up connection to db
    $server = 'localhost'; // 127.0.0.1 is the same as localhost

    $user = 'root'; // db user
    $pwd = 'root';  // db user password
    $schema = 'store'; // base de dados a utilizar 

    $connection = mysqli_connect($server, $user, $pwd, $schema);

    if (!$connection) {
        // error connecting to db
        die("Error connecting to db ...");
    }

    // to store portuguese characters correctly
    mysqli_set_charset($connection, 'utf8');

?>

// --- index.php
<?php
    require('config.php');
?>

```

Podemos incluir ficheiros php noutros usando o `require`ou o `include`.
No caso de um erro se o ficheiro foi incluído com `require`, o script produz um erro (E_COMPILE_ERROR) e o script pára.
Se for usado o `require`será produzido um aviso (E_WARNING) mas o script continua a sua execução.

## Sign Up a user

Não esquecer o sanitizing de sql `mysqli_real_escape_string($connection, $_POST['email’])`

```php
// Backend code to write users on a file
// Now we are going to write signup user info to 'user' table
require('config.php');

// check if email is already registered
$selectEmail = "select * from user where email = '$email'";
$emailResult = mysqli_query($connection, $selectEmail);

if (isset($emailResult)){

	if (mysql_num_rows($emailResult) == 0) {
		// email is not registered
		
		$insert = "insert into user (name, email, password, profile) values ('$name', '$email', '$password', '$image')";
		//print_r( $connection );
		echo $insert;
		mysqli_query ($connection, $insert);
	} else {
		$result = false;
		$msg = "Email already registered";
		$msgtype = "danger";
	}

}

if ($result) {
	//ok
	$msg = "User criado com sucesso";
	$msgtype = "success";
}


```
```html
<div class="alert alert-<?php echo $msgtype; ?>" role="alert">
	<?php echo $msg; ?>
</div>
```

## Como guardar as passwords

As passwords que os utilizadores definem no registo de um site são normalmente um ponto fraco em termos de segurança. Não poucas vezes utilizam palavras chave muito óbvias e de fraca qualidade em termos de força de segurança (por ex. sem caracteres especiais)

Uma password deverá ser sempre encriptada antes de guardar em base de dados. Em php existem diversos algoritmos de encriptação
- `md5($pwd)` grava uma password num formato mais completo e único (one way)
- `hash(‘sha256’, $pwd)` é um método onde podemos especificar qual o algoritmo de encriptação a usar, neste caso o sha256.

Apesar da encriptação, que basicamente ofusca uma password transformando-a num conjunto de caracteres, permitir esconder a palavra passe real, ela não vai aumentar a sua força. Se tivermos uma password fraca vamos ter uma password fraca encriptada.

Para aumentar a segurança na definição de passwords existe também o processo de *salting* que permite reforçar uma password fraca para a tornar mais forte.
Funciona concantenando à password do utilizador uma string conhecida, aumentando a dimensão e características da password. Por ex.

```php
$salt = "1iuqgrubq!_.kjbadf?*uwfef_";
$userPwd = $_POST['pwd'];
$strongPwd = $salt.$userPwd;

$pwd = hash('sha256', $strongPwd);
```

O php tem funções para criação de versões hashed das palavras chave e a sua validação no login:
```php
<?php
// Signup
// Assume user-provided password from a registration form
$password = 'user_password123';

// Hash the password
$hash = password_hash($password, PASSWORD_DEFAULT);

// Store $hash in the database
// Example database insert query (assuming $db is your database connection):
$sql = "INSERT INTO users (username, password_hash) VALUES (:username, :password_hash)";
$stmt = $db->prepare($sql);
$stmt->bindParam(':username', $username);
$stmt->bindParam(':password_hash', $hash);
$stmt->execute();
?>

// Login
<?php
// Assume user-provided username and password from a login form
$username = 'user_provided_username';
$password = 'user_password123';

// Retrieve the stored hash from the database based on the username
$sql = "SELECT password_hash FROM users WHERE username = :username";
$stmt = $db->prepare($sql);
$stmt->bindParam(':username', $username);
$stmt->execute();
$row = $stmt->fetch(PDO::FETCH_ASSOC);

// Check if a user with the given username was found
if ($row) {
    $stored_hash = $row['password_hash'];

    // Verify the password against the stored hash
    if (password_verify($password, $stored_hash)) {
        echo "Login successful!";
        // Proceed with authenticated session
    } else {
        echo "Invalid password.";
    }
} else {
    echo "No user found with that username.";
}
?>


```


## Desafio: Efetuar a página de login

```php
<?php 
$email = '';
$password = '';
$msg = '';
$msgType = '';

// Check if user is making a login
if (isset($_POST['login'])) {

    $email = $_POST['email'];
    $password = $_POST['password'];

    require('config.php');

    // 1 - consulta password para o email introduzido no login
    $query = "select email, password from user where email = '$email'";
    $result = mysqli_query($connection, $query);

    if (mysqli_num_rows($result) > 0) {
        // email is registered
        // read password from db
        $row = mysqli_fetch_assoc($result);
        $dbPassword = $row['password'];

        // 2 - comparar dbpassword com password do form login
        $encryptedPassword = md5($password);

        if ($encryptedPassword == $dbPassword) {
            // Login com sucesso
            Header("Location: main.php");

        } else {
            // erro no login
            $msg = 'Email ou password inválidos';
            $msgType = 'danger';
        }


    } else {
        // email não registado
        // erro no login
        $msg = 'Email ou password inválidos';
        $msgType = 'danger';
    }

}
?>
```
```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Login</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-0evHe/X+R7YkIZDRvuzKMRqM+OrBnVFBL6DOitfPri4tjfHxaWutUpFmBp4vmVor" crossorigin="anonymous">
</head>

<body>
    <div class="container">
        <h1>Welcome to Babs</h1>

        <div class="alert alert-<?php echo $msgType; ?>" role="alert">
            <?php echo $msg; ?>
        </div>

        <form method="post">

            <div class="mb-3">
                <label for="email" class="form-label">Email</label>
                <input type="email" class="form-control" id="email" name="email" aria-describedby="emailHelp" value="<?php echo $email; ?>">
            </div>

            <div class="mb-3">
                <label for="password" class="form-label">Password</label>
                <input type="password" class="form-control" id="password" name="password" aria-describedby="passwordHelp"
                value="<?php echo $password; ?>">
            </div>

            <button type="submit" name="login" class="btn btn-primary">Login</button>

            <div id="emailHelp" class="form-text">Se não tiver uma conta pode criá-la <a href="signup.php">aqui</a></div>
        </form>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/js/bootstrap.bundle.min.js" integrity="sha384-pprn3073KE6tl6bjs2QrFaJGz5/SUsLqktiwsUTF55Jfv3qYSDhgCecCxMW52nD2" crossorigin="anonymous"></script>
</body>

</html>
```

