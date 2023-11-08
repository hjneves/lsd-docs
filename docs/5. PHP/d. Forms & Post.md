O método `post`é um outro método http que pode ser utilizado para enviar informação do frontend para o backend, neste caso sem expor a informação no url,  e por isso deve ser usado quando se quer passar informação sensível ou informação binária (ex. ficheiros). Por exemplo em página de no signup e no login de um utilizador, genericamente também quando existe necessidade de guardar a informação recebida.
A informação é codificada e enviada no `body` do pedido http.

# Página de signup

Por exemplo, um registo de signup de um novo user, usando o método `post`:
https://github.com/hjneves/lsd-php-signup

```html
<form method="post" enctype="multipart/form-data">

	<img src="https://cdn3.iconfinder.com/data/icons/vector-icons-6/96/256-512.png" class="img-thumbnail w-25" alt="...">
	<div class="mb-3">
		<input type="hidden" name="MAX_FILE_SIZE" value="3000000" />
		<input class="form-control" type="file" name="image" id="image">
	</div>

	<div class="mb-3">
		<label for="name" class="form-label">Nome</label>
		<input type="text" class="form-control" id="name" name="name" aria-describedby="nameHelp" value="">
	</div>
	<div class="mb-3">
		<label for="email" class="form-label">Email</label>
		<input type="email" class="form-control" id="email" name="email" aria-describedby="emailHelp" value="">
	</div>

	<div class="mb-3">
		<label for="password" class="form-label">Password</label>
		<input type="password" class="form-control" id="password" name="password" aria-describedby="passwordHelp">
	</div>

	<button type="submit" name="signup" class="btn btn-primary">Signup</button>
</form>
```

Para processar este form de signup no backend vamos ter outro array associativo em php que é o `$_POST`. A leitura deste array segue a mesma lógica que no método get, temos como chaves do array as propriedades `name`dos campos de input e o seu valor corresponde ao `value` introduzido pelo utilizador nos campos de input.

Neste caso, para ler a informação do form em backend :
```php
if (isset($_POST['signup'])){
	$name = $_POST["name"];
	$email = $_POST["email"];
	$password = $_POST["password"];
}
```

>[!tipo] Porque se valida com o isset?
> Porque estamos a ler a informação apenas se tiver sido efectuado um submit (através do `isset`) ? Como o código de backend se escontra na mesma página que o código de frontend existem aqui dois momentos. O primeiro em que a página é pedida para ser preenchida pelo utilizador. Nesta fase não existe nenhum submit e portanto não faz sentido ler valores do `$_POST`. O segundo momento acontece quando o utilizador faz submit ao form após o ter preenchido. Nesta fase já chega informação ao servidor web e o PHP tem a estrutura `$_POST`com a informação necessária.

# Escrita de ficheiros

A escrita em ficheiros no servidor é uma forma de persistência de informação. Pegando no exemplo anterior, podemos criar um ficheiro e colocar lá os registos dos utilizadores. Mais tarde este processo será feito utilizando uma base de dados.

```php
<?php 
if (isset($_POST['signup'])){
	$name = $_POST["name"];
	$email = $_POST["email"];
	$password = $_POST["password"];

	// Backend code to write users on a file
    $usersFile = 'users.txt';
    $file = fopen($usersFile, 'a');
    $result = fwrite($file, $name.','.$email.','.$password.PHP_EOL);

    // fwrite returns false if some error exists
    if (!$result) {
        // error
        $msg = "Erro ao criar user";
        $msgtype = "danger";
    }
    else {
        //ok
        $msg = "User criado com sucesso";
        $msgtype = "success";
    }
}
?>

```


# Upload de ficheiros

O nosso form de signup também tem um campo de input do tipo `file` que nos permite carregar uma imagem para servir de imagem de perfil (Temos também um campo escondido que limita o utilizador de submeter ficheiros acima de uma determinada dimensão. Deverá ser colocado antes do campo de input do tipo file)

Para que o submit do form possa considerar este campo é necessário:
- garantir que o php está configurado para permit o upload de ficheiros. No ficheiro `php.ini` verificar que a seguinte propriedade está ativa: `file_uploads = On`
* garantir o método post no form: `method="post"`
* garantir o seguinte atributo no form: `enctype="multipart/form-data"`. Ele especifica que `content-type`vai ser usado na submissão do form. g the form

No backend, a informação dos ficheiros carregados fica disponível em PHP através do array associativo `$_FILES`_

Descrição do array `$_FILES`:
```php 
$_FILES['my-file']['name'] - Original Name of File Before It Was Uploaded
$_FILES['my-file']['type'] - The MIME Type of File, Provided By the Browser
$_FILES['my-file']['size'] - Size of the File (In Bytes)
$_FILES['my-file']['tmp_name'] - Location of Temporary File on Server
$_FILES['my-file']['error'] - Any Error Codes Resulting From the File Upload
```

* `basename($path)` - obtém o nome do ficheiro num caminho.
* `getimagesize($path)`- devolve o tamanho de uma imagem e `false`caso não consiga obter esta informação ou o ficheiro não é uma imagem.
* `move_uploaded_file($from, $to)`- move uma imagem de uma local para outro. Utilizado para mover o ficheiro carregado do seu local temporário para um local específico no site.

```php
<?php

$result = true;
$name = "";
$email= "";
$password = "";
$msgtype = "";
$msg = "";
$image = "https://cdn3.iconfinder.com/data/icons/vector-icons-6/96/256-512.png";
$target_dir = 'uploads/';

// read values to fill input values (signup moment)
if (isset($_POST['signup'])){
    $name = $_POST["name"];
    $email = $_POST["email"];
    $password = $_POST["password"];

    // read user image profile
    if ( isset($_FILES['image']) && $_FILES["image"]["tmp_name"]!== "" ){
        
        // exemplo de target_file '/uploads/3.jpg'
        $target_file = $target_dir . basename($_FILES['image']['name']);
        $uploadOK = true;

        // Check if user is realy uploading an image
        $check = getimagesize($_FILES["image"]["tmp_name"]);
        if ($check === false) {
            $result = false;
            $msg = "Imagem de perfil inválida";
            $msgtype = "danger";
        } else {
            // move uploaded file from server tmp space to our project directory
            $result = move_uploaded_file($_FILES["image"]["tmp_name"], $target_file);
            if ($result) {
                // correu bem
                $image = $target_file;
            } else {
                // houve erros
                $result = false;
                $msg = "Erro no upload da imagem de perfil";
                $msgtype = "danger";
            }

        }
    }
}

?>
```

