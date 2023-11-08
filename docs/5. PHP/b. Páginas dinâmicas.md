
# Página de perfil 

Uma página de perfil é uma página que apresenta os detalhes de um utilizador, sendo normalmente usada sempre a mesma base de código HTML, mas garantindo o dinamismo através do preenchimento da informação (nome, email, ...) através de blocos PHP

Ver exemplo base:
https://github.com/hjneves/lsd-php-profile-page

A partir desta página estática podemos modificá-la para poder servir qualquer utilizador, ou seja, criar componentes dinâmicos usando PHP para preencher os blocos de informação do utilizador.

Para isso vamos assumir que temos a informação dos utilizadores no array de objetos que criamos anteriormente.

```php
Class User {

  public $id, $name, $email, $street, $postal, $image;

  function __construct($id, $name, $email, $street, $postal, $image)
  {
    $this->id = $id;
    $this->name = $name;
    $this->email = $email;
    $this->street = $street;
    $this->postal = $postal;
    $this->image = './images/profiles/'.$image;
  }
}

$users = [
new User("1",'João Franco', 'joao.franco@gmail.com','Rua da Pimenta, 4','1990-503 Lisboa', '10.jpg'),
new User("2",'Rita Neves','rita.neves@gmail.com','Rua Alta, 12', '4990-503 Faro','5.jpg'),
new User("3",'Isabel Silva','isabel.silva@gmail.com','Rua Baixa, 2', '2990-503 Portimao','3.jpg'),
];

```


Por exemplo, para tornar dinâmico o nome do utilizador, onde está João Franco, vamos colocar uma variável php com o nome do utilizador. Neste caso vamos ler o objeto que está na posição 0 do array `users` e mostrar a propriedade `name`.
```html
<h5 class="card-title"><?php echo $users[0]->name; ?></h5>
```

Com esta alteração, se não fizermos mais nada a página vai estar sempre a mostrar o mesmo nome. Será necessário alterar o índice do array `users` para obtermos outro utilizador, ou seja, é necessário controlar a variável que é usada para preencher o nome.


# Mudar conteúdo em função do userID

Vamos considerar que temos uma variável `userID` que identifica de forma única o utilizador. 
O valor do `userID` vai assim determinar qual o utilizador que se pretende mostrar na pagina de perfil. É usada também uma variável auxiliar que vai receber o objeto do utilizador a apresentar.

```php
$userID = 2;
$user;

// Find object with userID 
foreach ($users as $curUser) {
  # code...
  if ($curUser->id == $userID) {
    $user = $curUser;
  }
}

```

```html
<h5 class="card-title"><?php echo $user->name; ?></h5>
```



