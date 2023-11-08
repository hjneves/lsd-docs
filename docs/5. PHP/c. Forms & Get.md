
## Interação com o frontend

Quando colocamos um endereço para uma determinada página web no browser, estamos a efectuar um *request* http ao servidor web. Neste request são enviadas várias propriedades num *header* para serem interpretados pelo servidor backend. Uma destas propriedades é o *method* que indica o que se pretende realizar com o recurso pedido. Os métodos mais usuais são o `GET`, `POST`, `PUT`, `DELETE`.

O método usado no http request determina a forma como o vamos interpretar em PHP. Por defeito o método utilizado é o `GET`.

Num método GET a informação enviada no pedido para o backend é codificada no URL.

Por exemplo, se quisermos enviar o identificador do utilizador (por. ex. `userID=5`) que queremos ver na página de perfil, o endereço a usar será o seguinte:
<http://localhost:8888/profile.php?userID=5>

A informação é codificado em pares variável=valor: 
- `userID` com o valor `5`

Podemos ter várias informações codificadas. Por exemplo:
<http://localhost:8888/profile.php?userID=5&status=active>

A informação é codificado em pares variável=valor: 
- `userID` com o valor `5`
- `status`com o valor `active`

> **Desafio**
> Apresentar a lista do utilizadores com links para a sua página de perfil.


```html

<div>
	<a href='profile.php?userID=1' >João Franco</a>
	<a href='profile.php?userID=2' >Rita Neves</a>
	<a href='profile.php?userID=3' >Isabel Silva</a>
</form>

```


## Como uma página HTLM codifica os parâmetros

Até agora colocámos manualmente os parâmetros na barra de endereços, mas o normal são os utilizadores introduzirem as informação nos campos de input das páginas.
Os forms são o ponto de interligação com o utilizador no que respeita a introdução de informação. É através das propriedades do forms e dos campos de input que se processa a codificação do URL para ser enviado ao backend.

>[!tip] Codificação do form
>Os campos do form são codificados em pares `variável=valor` separados por `&`, no url. A `variável` corresponde ao atributo `name` do campo de input, e o seu valor terá o `value` do campo de input.

Existem dois atributos do forma que estão muito ligados com este processo, o `method` que indica qual o método http a usar, e o `action`que indica qual é a página que vai processar a submissão do form.

Neste exemplo o form não tem especificado os atributos `method` e `action`. Logo assume por defeito o método `GET` e a `action`é a pagina que contém o form.
```html
<p> Pesquisa</p>
<form>
	<input name="search" type="text" />
	<input name="submit" type="submit" value="Search" />
</form>
```

Neste exemplo o form depois de submetido vai ser processado numa página diferente `search-results.php`.
```html

<p> Pesquisa</p>
<form action='search-results.php'>
	<input name="search" type="text" />
	<input name="submit" type="submit" value="Search" />
</form>
```

## Como o backend lê a informação

Existe um array associativo de sistema `$_GET` que recebe a informação codificada no url pelo frontend, aquando de um pedido http com o método `get`.
As chaves deste array correspondem à propriedade `name` de cada  campo de input no form.

Neste exemplo, vamos ler o valor do campo de input com o name `search`
```php
<?php 
	echo $_GET["search"];
?>
```


```php
<?php 

	if (isset($_GET["submit"]))
	{

		echo "Resultados da pesquisa por ".$_GET["search"];
	}
?>
```


```php
/* search-results.php */
<?php 

	if (isset($_GET["submit"]))
	{

		echo "Resultados da pesquisa por ".$_GET["search"];
	}
?>
```



## Processamento num ficheiro separado e com feedback

Neste exemplo temos o processamento do form num ficheiro `congrats.php` que simula o processamento do pedido, e se estiver tudo ok, devolve uma resposta criando um redirect novamente para o `iindex.php`mas com um parâmetro de feedback que depois é utilizado para escrever uma mensagem e auto preencher campo de input. 
```php
<!-- index.php -->
<?php 
	if (isset($_GET["nameok"]))
	{
		echo "Olá ".$_GET["nameok"].". O seu nome foi processado. Obrigado.";
	}
?>
```
```html
<p>Como te chamas?</p>
<form method="get" action="congrats.php">

	<!-- Change dinamically value atribute if $_GET["nameok"] is set -->
	<?php if (isset($_GET["nameok"])) { ?>
	<input name="nametoprocess" value="<?php echo $_GET["nameok"] ?>" type="text" />
	<?php } else { ?>
	<input name="nametoprocess" value="" type="text" />
	<?php } ?>
	<input type="submit" value="Submit" />

</form>
```

```php
<!-- congrats.php -->
<?php 


	if (isset($_GET["nametoprocess"]))
	{
		// Processo nametoprocess
		// Changes to DB

		Header("Location:index.php?nameok=".$_GET["nametoprocess"]);
	}
?>
```


