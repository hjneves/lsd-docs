Os sites que têm um acesso diferenciado conforme um utilizador está ou não registado têm de lidar com um problema: o servidor web no backend não sabe quem é o utilizador ou o que ele está a fazer, apenas dá respostas a pedidos e não guarda nenhum estado ao longo do tempo. Ou seja, um utilizador teria constantemente de efectuar login para poder entrar qualquer página  apenas disponível para utilizadores registados.

Em php as variáveis de sessão `$_SESSION` resolvem este problema guardando as informações do utilizador para serem usadas ao longo das diversas páginas do site (nome, id, email , ...). Por defeito as variáveis de sessão duram até o utilizador fechar o browser.

Para iniciar as variáveis de sessão a função `session_start()`deverá ser colocada no inicio de cada página, mesmo antes das tag `<html>`.

# login.php

Podemos por exemplo guardar as informações do utuilizador na sessão, após um login com sucesso:
```php
<?php 
session_start();

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
    $query = "select name, email, password from user where email = '$email'";
    $result = mysqli_query($connection, $query);

    if (mysqli_num_rows($result) > 0) {
        // email is registered
        // read password from db
        $row = mysqli_fetch_assoc($result);
        $dbPassword = $row['password'];
        $name = $row['name'];
        
        // 2 - comparar dbpassword com password do form login
        $encryptedPassword = md5($password);

        if ($encryptedPassword == $dbPassword) {
            // Login com sucesso
            // Create session
            $_SESSION['email'] = $email;
            $_SESSION['name'] = $name;
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
```

# index.php

Podemos no ficheiro `index.php`, validar se o user está ou não logged in, e em função disso redireccioná-lo para para a página de login

```php
<?php 
    session_start();
    // se user não está logged in redirecciona para login.php
    // Redireciona para main.php se logged in

    if (isset($_SESSION['email'])) {
        Header('Location: main.php');
    } else {
        Header('Location: login.php');
    }
?>
```

Também podemos efectuar esta validação no inicio do `index.php`

```php
<?php 
	session_start();

	if (isset($_SESSION["email"])) {
		header("Location: main.php");
	}
?>

(...)
```

# Logout.php

Quando se efetuar logout a sessão do utilizador deve ser destruída. 

```php
<?php
	// Initialize the session.
	session_start();
	
	// Unset all of the session variables.
	$_SESSION = array();
	// ou session_unset()
	
	// Finally, destroy the session.
	session_destroy();
	
	Header('Location: login.php');
?>
```

